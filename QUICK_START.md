# Quick Start Guide

## For GitHub

```bash
# Initialize and push to GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/arunkumars-mf/zos-ftp-mcp.git
git branch -M main
git push -u origin main

# Create a release tag
git tag -a v0.1.0 -m "Initial release v0.1.0"
git push origin v0.1.0
```

Then create a release on GitHub web interface.

## For PyPI

### One-Time Setup (Trusted Publishing - Recommended)

1. Go to https://pypi.org/manage/account/publishing/
2. Add publisher:
   - Project: `zos-ftp-mcp`
   - Owner: `arunkumars-mf`
   - Repo: `zos-ftp-mcp`
   - Workflow: `publish.yml`

### Manual Publish

```bash
# Build
uv build

# Publish
uv publish
```

That's it! Creating a GitHub release will automatically publish to PyPI.

## Quick Commands

```bash
# Build package
uv build

# Test locally
uv run zos-ftp-mcp

# Publish to PyPI
uv publish

# Publish to TestPyPI first
uv publish --publish-url https://test.pypi.org/legacy/
```
