# Contributing to z/OS FTP MCP Server

Thank you for your interest in contributing!

## Development Setup

1. Clone the repository:
```bash
git clone https://github.com/arunkumars-mf/zos-ftp-mcp.git
cd zos-ftp-mcp
```

2. Install uv (if not already installed):
```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

3. Install dependencies:
```bash
uv sync
```

This creates a virtual environment and installs the package in development mode.

## Making Changes

1. Create a new branch for your feature or bugfix
2. Make your changes
3. Test your changes thoroughly
4. Update documentation if needed
5. Submit a pull request

## Code Style

- Follow PEP 8 guidelines
- Use type hints where appropriate
- Add docstrings to functions and classes
- Keep functions focused and modular

## Testing

Before submitting a PR, ensure:
- Your code works with Python 3.10+
- No syntax or import errors
- Documentation is updated

## Reporting Issues

When reporting issues, please include:
- Python version
- Operating system
- Steps to reproduce
- Expected vs actual behavior
- Error messages or logs

## Questions?

Feel free to open an issue for questions or discussions.
