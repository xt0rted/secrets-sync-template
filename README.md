# secrets-sync

The [secrets-sync](https://github.com/xt0rted/secrets-sync) config for managing secrets across multiple repositories through code.

## Getting started

1. Edit the [config](secrets-sync.yml) and mappings in the [`workflow`](.github/workflows/secrets-sync.yml).
2. Create a [Personal Access Token](https://github.com/settings/tokens/new?scopes=repo) with the `repo` scope.
3. Add it as a secret to this repository with the name `SECRET_SYNC_TOKEN`.

## Behavior

Secrets will be created if they don't exist in the destination repository, or updated if they do exist.

If a secret value is removed from the config it will be deleted from any repository it was assigned to.

## Usage

The [`secrets-sync`](.github/workflows/secrets-sync.yml) workflow can be manually triggered whenever you want to re-sync your secrets.

[yamllint](https://github.com/adrienverge/yamllint) will run on any pull request or push to `main` to help ensure the config file is formatted correctly.

[Enable debug logging](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/enabling-debug-logging) to see more details about the workflow run.
