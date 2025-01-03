# 🚀 Deploy to PyPI Action

This GitHub Action automates the process of building and publishing Python packages to PyPI (Python Package Index).

## Features

- Builds Python packages using setuptools
- Generates both source and wheel distributions
- Handles authentication with PyPI
- Supports custom Python versions
- Automated package uploading using twine

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `pypi_username` | PyPI username or account name | Yes | - |
| `pypi_password` | PyPI password or API token | Yes | - |
| `python_version` | Python version to use for build | No | "3.x" |

## Usage

Add the following step to your workflow:

```yaml
name: 🚀 Deploy to PyPI
run-name: Publish Python Package
on:
  push:
    tags:
      - v*.*

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: 🚀 Deploy to PyPI
        uses: dfcors/pipeline/.github/actions/deploy-to-pypi@master
        with:
          pypi_username: ${{ secrets.PYPI_USERNAME }}
          pypi_password: ${{ secrets.PYPI_PASSWORD }}
          python_version: "3.9"
```