# Publishing to PyPI

This guide walks you through the steps to publish your `bw-converter-python` package to PyPI.

## Prerequisites

1.  **Create a PyPI Account**: Go to [pypi.org](https://pypi.org/) and register for an account.
2.  **Enable 2FA**: Enable Two-Factor Authentication in your account settings. This is required for publishing.
3.  **Create an API Token**:
    *   Go to Account Settings > API Tokens.
    *   Create a new token with "Entire account" scope (since this is a new project).
    *   Copy the token. You will use it as your password when uploading.

## Build the Package

Make sure you are in the package root directory (`bw-converter-python`) and your virtual environment is active.

```bash
# Install build tools if you haven't already
pip install build

# Build the package
python3 -m build
```

This will create a `dist/` directory containing `.tar.gz` and `.whl` files.

## Upload to PyPI

We will use `twine` to upload the package.

```bash
# Install twine
pip install twine

# Upload to PyPI
twine upload dist/*
```

*   **Username**: `__token__`
*   **Password**: Paste your API token (starting with `pypi-`).

## Verification

Once uploaded, you can try installing your package in a clean environment:

```bash
pip install bw-converter-python
```
