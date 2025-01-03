# 🛠 Merge Request Checks Action

This GitHub Action performs quality checks on merge requests including linting, formatting and build verification.

## Features

- Sets up Node.js environment
- Runs ESLint checks
- Runs Prettier formatting checks
- Verifies build process

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `node-version` | Version of Node.js to setup | No | `20` |

## Usage

Add the following step to your workflow:

```yaml
name: 🛠 Merge Request Checks
on:
  pull_request:
    types: [opened, edited, synchronize, reopened]
jobs:
  merge-request-check:
    runs-on: ubuntu-latest
    name: Run Merge Request Check
    steps:
      - name: 🛠 Merge Request Check
        uses: dfcors/pipeline/.github/actions/node-mr@master
        with:
          node-version: "20"
```