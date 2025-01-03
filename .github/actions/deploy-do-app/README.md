# 🚀 Deploy DO App Action

This GitHub Action automates the deployment process to DigitalOcean Apps Platform while managing environment variables and git versioning.

## Features

- Deploys applications to DigitalOcean Apps Platform
- Updates environment files with git tag versions
- Handles git versioning and commits
- Sets up doctl for additional DigitalOcean CLI operations

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----|---------|
| `app_name` | Name of the application to deploy on DO Apps Platform | Yes | - |
| `do_token` | DigitalOcean API token with appropriate permissions | Yes | - |
| `env_file` | Path to the environment file to update | No | `.env.production` |
| `pat_pipeline_token` | Personal Access Token for pipeline operations | Yes | - |

## Usage

Add the following step to your workflow:

```yaml
name: 🚀 Deployment to Digital Ocean
run-name: Deploy to Production
on:
  push:
    tags:
      - v*.*

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: 🚀 Deploy to Digital Ocean
        uses: dfcors/pipeline/.github/actions/deploy-do-app@master
        with:
          app_name: app_name 
          do_token: ${{ secrets.DO_ACCESS_TOKEN }}
          env_file: .env.production
          pat_pipeline_token: ${{ secrets.PAT_PIPELINE }}
```