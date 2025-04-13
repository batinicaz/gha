# Docker

Workflow File: [docker.yml](../../../.github/workflows/docker.yml)

Workflow designed to build and publish a daily docker image with optimised cache configuraiton.
<!-- TOC -->
* [Release](#release)
  * [Requirements](#requirements)
  * [Usage](#usage)
    * [Configuration Reference](#configuration-reference)
<!-- TOC -->

## Requirements

- Single Dockerfile at the root of the repo

## Usage

You can call the workflow from the workflow in your repo like so:

```yaml
name: Daily Docker Build and Publish

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: read
  packages: write

jobs:
  release:
    uses: batinicaz/gha/.github/workflows/docker.yml@latest
    secrets:
      GHCR_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Configuration Reference
| Configuration Type | Name             | Description                                                                                                                       | Default Value                   | Required |
|--------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------|----------|
| secret              | GHCR_TOKEN   | The token with permission to access the GHCR for the repo                                                                 |  | Yes       |
