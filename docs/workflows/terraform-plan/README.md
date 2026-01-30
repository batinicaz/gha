# Terraform Plan

Workflow File: [terraform-plan.yml](../../../.github/workflows/terraform-plan.yml)

Reusable workflow for running `terraform plan` with Infisical secrets integration. Posts plan output as a comment on associated pull requests.

<!-- TOC -->
* [Terraform Plan](#terraform-plan)
  * [Features](#features)
  * [Requirements](#requirements)
  * [Usage](#usage)
    * [Configuration Reference](#configuration-reference)
  * [Infisical Configuration](#infisical-configuration)
<!-- TOC -->

## Features

- Fetches secrets from Infisical using OIDC authentication
- Runs `terraform init` and `terraform plan`
- Posts plan output as a PR comment (replaces previous comment if exists)
- Truncates plan output if exceeds 60,000 characters

## Requirements

- Infisical project with OIDC identity configured for GitHub Actions
- Repository variable `INFISICAL_IDENTITY_ID` containing the machine identity ID
- Terraform configuration in the repository

## Usage

```yaml
name: Lint & Plan
on:
  push:
    branches:
      - "**"
      - "!main"

jobs:
  terraform:
    uses: batinicaz/gha/.github/workflows/terraform-plan.yml@v1.3.0
    permissions:
      contents: read
      id-token: write
      pull-requests: write
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

1. Create a machine identity in Infisical with OIDC authentication
2. Configure the identity to trust your GitHub repository:
   - Set the OIDC audience to `https://github.com/<org>`
   - Configure subject claims as needed
3. Add the identity ID as a repository variable named `INFISICAL_IDENTITY_ID`
4. Ensure your Infisical project has:
   - A `terraform-common` environment for shared secrets (OCI credentials, etc.)
   - A project-specific environment (e.g., `terraform-oci-apps`) for project secrets
