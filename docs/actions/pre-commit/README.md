# pre-commit

Action File: [action.yml](../../../.github/actions/pre-commit/action.yml)

Simple wrapper action to make use of [batinicaz/pre-commit](https://github.com/batinicaz/pre-commit/) image built on
top of chainguards images that do not run as root.

Hook environments are automatically cached between runs using `actions/cache`, keyed on `.pre-commit-config.yaml`.
This avoids re-downloading and re-installing hooks on every run.

## Usage

You can call the action from the workflow in your repo like so:

```yaml
  pre-commit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Run pre-commit
        uses: batinicaz/gha/.github/actions/pre-commit@latest
```

### Configuration Reference

| Configuration Type | Name  | Description                                             | Default Value                       | Required |
|--------------------|:------|---------------------------------------------------------|-------------------------------------|:---------|
| input              | image | The docker image to run                                 | ghcr.io/batinicaz/pre-commit:latest | No       |
| input              | path  | The path to the configuration to run pre-commit against | ${{ github.workspace }}             | No       |
