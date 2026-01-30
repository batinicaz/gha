# Terraform Apply

Workflow File: [terraform-apply.yml](../../../.github/workflows/terraform-apply.yml)

Reusable workflow for running `terraform apply` with Infisical secrets integration. Designed for deployment pipelines triggered by tags or merges to main.

<!-- TOC -->
* [Terraform Apply](#terraform-apply)
  * [Features](#features)
  * [Requirements](#requirements)
  * [Usage](#usage)
    * [Configuration Reference](#configuration-reference)
  * [Infisical Configuration](#infisical-configuration)
<!-- TOC -->

## Features

- Fetches secrets from Infisical using OIDC authentication
- Runs `terraform init` and `terraform apply -auto-approve`
- Designed to pair with [terraform-plan](../terraform-plan/README.md) workflow

## Requirements

- Infisical project with OIDC identity configured for GitHub Actions
- Repository variable `INFISICAL_IDENTITY_ID` containing the machine identity ID
- Terraform configuration in the repository

## Usage

```yaml
name: Deploy
run-name: "Deploy ${{ github.ref }}"
on:
  push:
    tags:
      - "v**"

jobs:
  deploy:
    uses: batinicaz/gha/.github/workflows/terraform-apply.yml@v1.3.0
    permissions:
      contents: read
      id-token: write
    with:
      terraform_version: "1.14.4"
      working_directory: terraform
      infisical_project_env: terraform-my-project
    secrets:
      INFISICAL_IDENTITY_ID: ${{ vars.INFISICAL_IDENTITY_ID }}
```

### Configuration Reference

| Configuration Type | Name                  | Description                                                              | Default Value                       | Required |
|--------------------|-----------------------|--------------------------------------------------------------------------|-------------------------------------|:---------|
| input              | terraform_version     | Terraform version to use                                                 | 1.14.4                              | No       |
| input              | working_directory     | Directory containing Terraform configuration                            | terraform                           | No       |
| input              | infisical_common_env  | Infisical environment slug for common secrets                           | terraform-common                    | No       |
| input              | infisical_project_env | Infisical environment slug for project secrets                          | terraform-{repo-name}               | No       |
| input              | infisical_project_slug| Infisical project slug                                                   | terraform                           | No       |
| secret             | INFISICAL_IDENTITY_ID | Infisical machine identity ID for OIDC auth                             |                                     | Yes      |

## Infisical Configuration

See [Terraform Plan - Infisical Configuration](../terraform-plan/README.md#infisical-configuration) for setup instructions.
