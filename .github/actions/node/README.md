# 🚀 Node Setup Action

This GitHub Action automates the Node.js environment setup process including dependency installation and caching for optimal workflow performance.

## Features

- Checks out repository code
- Sets up specified Node.js version
- Implements Yarn module caching
- Installs dependencies with frozen lockfile for consistency

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `node-version` | Version of Node.js to setup | No | `20` |

## Usage

Add the following step to your workflow:

```yaml
name: Node.js Setup
on: [push]

jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
      - name: 🛠️ Setup Node Environment
        uses: dfcors/pipeline/.github/actions/node@master
        with:
          node-version: '20'
```