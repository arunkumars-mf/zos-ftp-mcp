# Publishing Guide

This guide covers how to publish `zos-ftp-mcp` to GitHub and PyPI.

## Prerequisites

### For GitHub
- GitHub account
- Git installed locally
- Repository created at: https://github.com/arunkumars-mf/zos-ftp-mcp

### For PyPI
- PyPI account at https://pypi.org
- PyPI API token (recommended) or username/password

## Publishing to GitHub

### 1. Initialize Git Repository (if not already done)

```bash
git init
git add .
git commit -m "Initial commit"
```

### 2. Add Remote and Push

```bash
git remote add origin https://github.com/arunkumars-mf/zos-ftp-mcp.git
git branch -M main
git push -u origin main
```

### 3. Create a Release

#### Option A: Via GitHub Web Interface
1. Go to https://github.com/arunkumars-mf/zos-ftp-mcp/releases
2. Click "Create a new release"
3. Tag version: `v0.1.0`
4. Release title: `v0.1.0 - Initial Release`
5. Description: Copy from CHANGELOG.md
6. Click "Publish release"

#### Option B: Via Git Tags
```bash
git tag -a v0.1.0 -m "Initial release v0.1.0"
git push origin v0.1.0
```

## Publishing to PyPI

### Method 1: Automated via GitHub Actions (Recommended)

This is already set up! When you create a GitHub release, it will automatically publish to PyPI.

#### Setup Steps:
1. Go to https://pypi.org/manage/account/publishing/
2. Add a new Trusted Publisher:
   - PyPI Project Name: `zos-ftp-mcp`
   - Owner: `arunkumars-mf`
   - Repository name: `zos-ftp-mcp`
   - Workflow name: `publish.yml`
   - Environment name: (leave blank)

That's it! The workflow uses Trusted Publishing (OIDC), which is more secure than API tokens.

### Method 2: Manual Publishing with uv

#### 1. Build the Package
```bash
uv build
```

This creates:
- `dist/zos_ftp_mcp-0.1.0-py3-none-any.whl`
- `dist/zos-ftp-mcp-0.1.0.tar.gz`

#### 2. Test Upload (Optional)
Upload to TestPyPI first to verify everything works:

```bash
uv publish --publish-url https://test.pypi.org/legacy/
```

Then test installation:
```bash
uv pip install --index-url https://test.pypi.org/simple/ zos-ftp-mcp
```

#### 3. Upload to PyPI
```bash
uv publish
```

You'll be prompted for your PyPI API token. Alternatively, set it as an environment variable:
```bash
export UV_PUBLISH_TOKEN="pypi-your-token-here"
uv publish
```

## Post-Publishing Checklist

### After GitHub Release
- [ ] Verify release appears at https://github.com/arunkumars-mf/zos-ftp-mcp/releases
- [ ] Check that GitHub Actions workflow ran successfully
- [ ] Verify README displays correctly on GitHub

### After PyPI Release
- [ ] Verify package appears at https://pypi.org/project/zos-ftp-mcp/
- [ ] Test installation: `pip install zos-ftp-mcp`
- [ ] Verify command works: `zos-ftp-mcp --help` (if applicable)
- [ ] Check that README displays correctly on PyPI
- [ ] Verify badges in README show correct version

## Version Updates

For future releases:

1. Update version in `pyproject.toml`
2. Update version in `src/zos_ftp_mcp/__init__.py`
3. Update `CHANGELOG.md` with new changes
4. Commit changes
5. Create new git tag: `git tag -a v0.2.0 -m "Release v0.2.0"`
6. Push: `git push && git push --tags`
7. Create GitHub release (triggers automatic PyPI publish)

## Troubleshooting

### Build Fails
- Ensure `pyproject.toml` is valid
- Check that all required files exist
- Verify Python version compatibility
- Run `uv build --verbose` for detailed output

### Upload Fails
- Check PyPI credentials or token
- Ensure version number hasn't been used before
- Verify package name is available on PyPI
- For Trusted Publishing, verify GitHub repo settings match PyPI configuration

### GitHub Actions Fails
- Check workflow logs in Actions tab
- Verify PyPI token is correctly set in secrets
- Ensure Trusted Publishing is configured

## Security Notes

- Never commit API tokens or passwords
- Use GitHub Secrets for sensitive data
- Prefer Trusted Publishing over API tokens
- Rotate tokens periodically

## Resources

- [Python Packaging Guide](https://packaging.python.org/)
- [PyPI Help](https://pypi.org/help/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Trusted Publishing Guide](https://docs.pypi.org/trusted-publishers/)
