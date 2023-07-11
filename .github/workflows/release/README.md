# Release

Workflow designed to be run on the main branch and automatically create a release on each merge.

Generates a new major/minor/patch tag and updates the `CHANGELOG.md` based on the conventional commit standard.

<!-- TOC -->
* [Release](#release)
  * [Requirements](#requirements)
  * [Usage](#usage)
    * [Configuration Reference](#configuration-reference)
  * [GitHub App Configuration](#github-app-configuration)
  * [Ruleset Configuration](#ruleset-configuration)
<!-- TOC -->

## Requirements

- Using [conventional commit](https://www.conventionalcommits.org/en/) messages
- GitHub app created to perform the push to main
- Branch protection must be configured using rulesets so that the GitHub app you create has permission to bypass protection rules

## Usage

Call the workflow from the workflow in your repo like so:

```yaml
name: Create Release
on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  # Call with auto propagation of secrets
  release:
    uses: ./.github/workflows/release/release.yml
    with:
      includeLatestTag: true
    secrets: inherit
```

Or if you want to name secrets differently, pass them in explicitly:

```yaml
name: Create Release
on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
 # Call with explicit passing of secrets
  release:
    uses: batinicaz/gha/.github/workflows/release/release.yml@latest
    with:
      parameterName: "Desired value"
    secrets:
      secretName: ${{ secrets.differentlyNamedSecret }}
```

### Configuration Reference

| Configuration Type | Name             | Description                                                                                                                       | Default Value                   | Required |
|--------------------|:-----------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------|:---------|
| input              | committerEmail   | The email address to use for author of the release commit message                                                                 | ghabot@users.noreply.github.com | No       |
| input              | committerName    | The name to use for author of the release commit message                                                                          | GitHub Actions Bot              | No       |
| input              | includeLatestTag | Optionally also tag the release as "latest"                                                                                       | false                           | No       |
| secret             | APP_ID           | The ID of the GitHub App with permission to bypass branch protection. See below for details on configuring GitHub app.            |                                 | Yes      |
| secret             | APP_INSTALL_ID   | The ID of the GitHub App install with permission to bypass branch protection. Only required if not installed to the current repo. |                                 | No       |
| secret             | APP_PRIVATE_KEY  | The private key of the GitHub App with permission to bypass branch protection                                                     |                                 | Yes      |

## GitHub App Configuration

1. Follow the steps from the [GitHub docs](https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app) to register a new app.
    1. Set the `GitHub App name`
    2. Set the `Homepage URL` to any URL.
    3. Uncheck the `Active` checkbox under the `Webhook` section.
    4. Under permissions, expand repository permission and find the `Contents` permission. Change the dropdown on the right to `Read and write`
    5. Leave all other options blank/default and click `Create GitHub app`
2. On the app settings page scroll down to `Private keys` and click `Generate a private key`. Store this somewhere safe as you will need to add it to your repository secrets later.
3. On the app settings page look to the left hand side and click `Install App`. Install the app to a specific repository or all repositories depending on your need. If are installing the app to all repos note the installation ID you will see in the URL when editing the install.
4. In your repository create the following secrets:
    1. `appID` - Found on the app settings page right at the top.
    2. `appInstallID` - Optional, found in step 4 above.
    3. `privateKey` - The key you downloaded in step 2 above.

## Ruleset Configuration

Instead of using the standard branch protection rules, you should use the `Rulesets` found under: repostiory settings --> Rules --> Rulesets.

Unlike branch protection rules, rulesets allow for exceptions.

Configure the ruleset to meet your requirements and then click `Add bypass` in the `Bypass list` section. Search for the name of your app, select it and set the bypass to `always`.