***WARNING: THIS REPO IS AN AUTO-GENERATED COPY.*** *This repo has been copied from [Gruntwork’s](https://gruntwork.io/) GitHub repositories so that you can consume it from your company’s own internal Git repositories. This copy is automatically created and updated by the `repo-copier` CLI tool. If you need to make changes to this repo, you should make the changes in a separate fork, and NOT make changes directly in this repo, as otherwise, the `repo-copier` will overwrite your changes! Please see the `repo-copier` [documentation](https://github.com/tpc-gw/repo-copier) for more information on how the code is copied, how cross-references are updated, how the changelog is handled, etc.*

***

_You may find it valuable to view the following resources in the original repo. If these links give you a 404, visit https://app.gruntwork.io to gain access or email support@gruntwork.io if you need assistance._

[Home Page](https://github.com/gruntwork-io/pipelines-workflows/) |
[Pull Requests](https://github.com/gruntwork-io/pipelines-workflows/pulls) |
[Issues](https://github.com/gruntwork-io/pipelines-workflows/issues) |
[Releases and Assets](https://github.com/gruntwork-io/pipelines-workflows/releases)

_Alternatively, you can view a copied version of the resources listed above._

[Pull Requests](https://github.com/tpc-gw/pipelines-workflows/blob/main/.github/PULL_REQUESTS.md) |
[Issues](https://github.com/tpc-gw/pipelines-workflows/blob/main/.github/ISSUES.md) |
[ChangeLog](https://github.com/tpc-gw/pipelines-workflows/blob/main/.github/CHANGELOG.md)

***

# Gruntwork Pipelines Workflows

These two workflows contain the encapsulated logic for the Gruntwork Pipelines CI/CD system.

They are designed to integrate with the [Gruntwork Pipelines CLI](https://github.com/gruntwork-io/pipelines-cli).

## Workflows

### [pipelines-root.yml](./.github/workflows/pipelines-root.yml)

This workflow handles the CI/CD for deploying updates to infrastructure managed by the DevOps Foundations `infrastructure-live-root` repository.

### [pipelines-delegated.yml](./.github/workflows/pipelines-delegated.yml)

This workflow handles the CI/CD for deploying updates to infrastructure managed by all the other repositories vended as part of DevOps Foundations.

## Customization

Ask Gruntwork Support for guidance on this if you have a subscription.
