# Changelog


# v4.9.0
_Released Feb 26, 2026_
## What's Changed

:nut_and_bolt: This release contains some internal reworks around how we collect and process Terragrunt output during plan/apply, as well as adding the Terragrunt [Run Report](https://terragrunt.gruntwork.io/docs/features/run-report/) to Job artifacts for future use. There is additional internal Gruntwork telemetry around deploys being added, but we expect no user facing impact from this release.


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.9.0
<br>

# v4.8.0-rc1
_Released Feb 20, 2026_
## What's Changed
* Add inventory report by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/187
* Pipelines CLI v0.46.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/188
* Add self vars for self hosted pipelines actions and pipelines-credentials by @odgrim in https://github.com/gruntwork-io/pipelines-workflows/pull/189

## New Contributors
* @odgrim made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/189

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.6.1...v4.8.0-rc1
<br>

# v4.8.0
_Released Feb 23, 2026_
## What's Changed
* feat: Add self vars for self hosted pipelines actions and pipelines-credentials by @odgrim in https://github.com/gruntwork-io/pipelines-workflows/pull/189
* chore: Bumping Pipelines CLI from `v0.46.1` to `v0.46.2` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/191

## New Contributors
* @odgrim made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/189

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.7.0...v4.8.0
<br>

# v4.7.0
_Released Feb 12, 2026_
## What's Changed

### Go 1.26.0

Upgraded pipelines CLI to use go 1.26.0 to address CVE-2025-68121

### Internal telemetry updates

Updates to Gruntwork internal telemetry

* Add inventory report by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/187
* Pipelines CLI v0.46.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/188


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.7.0
<br>

# v4.6.1
_Released Feb 6, 2026_
## What's Changed

### :bug: Fixed a bug preventing step output artifacts being created when more than 30 jobs are running

* Fix missing step artifacts caused by unpaginated jobs query by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/185
* Pipelines CLI v0.45.3 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/186


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.6.1
<br>

# v4.6.0
_Released Feb 3, 2026_
## What's Changed

### :dart:  SHA Pinning

Updated all third party actions to use [SHA Pinning](https://github.blog/changelog/2025-08-15-github-actions-policy-now-supports-blocking-and-sha-pinning-actions/#enforce-sha-pinning). Customers that require SHA pinning in their organization should now be able to use Pipelines workflows with this security setting enabled.

### ⚠️ Minimum Compatible Runner Version

Updated third party actions, some of which require actions/runner v2.327.1 or higher for node24 support. This should have no effect on the default runner. If you are using self-hosted runners and have disabled automatic updates, ensure your actions/runner is at this version or newer. See [Runner software updates on self-hosted runners](https://docs.github.com/en/actions/reference/runners/self-hosted-runners#runner-software-updates-on-self-hosted-runners) for more information.

#### Changes

* Fix pipelines-credentials not using PIPELINES_CREDENTIALS_REF by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/183
* Pin actions versions by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/184

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.6.0
<br>

# v4.5.0
_Released Jan 26, 2026_
## What's Changed

This is a parity release to keep GitLab and GitHub pipelines binaries in sync. There are no expected changes to GitHub functionality.

* Pipelines CLI v0.45.0 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/182


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.5.0
<br>

# v4.4.0
_Released Jan 21, 2026_
## What's Changed

- Added retries to pipelines-credentials when network errors occur
- Added support for import count in the Pipelines plan summary comment
- Fixed a bug where modifications to stack files were not ignored by pipelines ignore_list
- Fixed a bug where `PIPELINES_FEATURE_EXPERIMENT_IGNORE_UNITS_WITHOUT_ENVIRONMENT` was not ignoring unit deletions.

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.4.0
<br>

# v4.3.0
_Released Jan 7, 2026_
## What's Changed

- Added new experiment flag `PIPELINES_FEATURE_EXPERIMENT_USE_MISE_EXEC_TG_WRAPPER` to allow individual units to specify the OpenTofu/Terraform version to use. See the full docs [here](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags#pipelines_feature_experiment_use_mise_exec_tg_wrapper)

- Fixed a bug where the default branch name for drift detection PRs was not set when running via cron

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.3.0
<br>

# v4.2.1
_Released Dec 18, 2025_
## What's Changed

- Fixed a bug causing some lines in the plan comment to drop characters at the beginning of the line

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.2.1
<br>

# v4.2.0-rc1
_Released Dec 3, 2025_
## What's Changed
`PIPELINES_FEATURE_EXPERIMENT_GENERATE_ALL_STACKS`
<br>

# v4.2.0
_Released Dec 5, 2025_
## What's Changed

- Added `PIPELINES_FEATURE_EXPERIMENT_GENERATE_ALL_STACKS` this feature causes Pipelines to generate all stacks before running a plan or apply operation. See [the docs](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags/#pipelines_feature_experiment_generate_all_stacks) for more info.

- Fixed a bug causing the wrong unit to be plan/applied during drift remediation inside stacks

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.2.0
<br>

# v4.10.1
_Released Mar 25, 2026_
## What's Changed

:bug: Terragrunt stack directories are now excluded from Terragrunt discovery if they are ignored by the Pipelines ignore list or `PIPELINES_FEATURE_EXPERIMENT_IGNORE_UNITS_WITHOUT_ENVIRONMENT`. This affects the startup of Terragrunt during the Plan/Apply, but does not affect stack generation.

:bug: Fixed the text at the bottom of Plan comments to correctly say pull request instead of merge request.

* Pipelines CLI v0.48.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/197


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.10.1
<br>

# v4.10.0
_Released Mar 6, 2026_
## What's Changed

:bug: Fixed a panic in Account Factory when account creation fails
:bug: Fixed some retry cases in pipelines-credentials not retrying
:nut_and_bolt: Added graceful handling of free tier limits
:nut_and_bolt: Internal telemetry updates

* pipelines-credentials v1.2.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/194
* Handle free tier limits by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/196


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.9.0...v4.10.0
<br>

# v4.1.0
_Released Dec 2, 2025_
## What's Changed

Added experimental feature flag `PIPELINES_FEATURE_EXPERIMENT_IGNORE_UNITS_WITHOUT_ENVIRONMENT`. This feature flag makes Pipelines ignore changes if they have no environment defined - and is intended to help simplify adding Pipelines to existing repositories.

See the [documentation](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags#pipelines_feature_experiment_ignore_units_without_environment) for full details.


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.1.0
<br>

# v4.0.7
_Released Nov 27, 2025_
## What's Changed

Parity release to keep Pipelines CLI version in sync. No impacts to GitHub functionality.

* Pipelines CLI v0.40.7 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/174


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.7
<br>

# v4.0.6
_Released Nov 14, 2025_
## What's Changed

- Fixed a race condition affecting the status check when retrying failed jobs
- Fixed drift-detection PR_CREATE_TOKEN fallback token

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.6
<br>

# v4.0.5
_Released Nov 13, 2025_
## What's Changed

### 🐛 Bug Fix
* Fix child account baseline auth bug by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/172


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.0.4...v4.0.5
<br>

# v4.0.4
_Released Nov 10, 2025_
## 🐛 Bug Fixes

### The `-destroy` flag is explicitly moved to the end of the argument list

To mitigate a bug related to the OpenTofu/Terraform `-destroy` flag being set before Terragrunt flags when used with `run --all plan -destroy`, the flag is explicitly moved to the end of the argument list with an `--` separator if detected. 

This is an interim fix, with more nuanced flag ordering planned for the future.

## What's Changed
* chore: Bumping Pipelines CLI version to `v0.40.5` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/171

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.4
<br>

# v4.0.3
_Released Nov 5, 2025_
## What's Changed

- Allow Drift Detection to run on branches other than the deploy branch
- Remove ahead of main check from preflight when workflow is manually dispatched
- Allow alpha and beta Terragrunt releases to be used (minimum version check no longer applies)

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.3
<br>

# v4.0.2
_Released Oct 30, 2025_
- Fixed unknown event type when `repository_dispatch` is used
- Reduced log noise during authentication

## What's Changed
* Pipelines CLI v0.40.3 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/167


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.2
<br>

# v4.0.1
_Released Oct 27, 2025_
## What's Changed
* Use updated actions with fix for logs parsing by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/166


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4...v4.0.1
<br>

# v4.0.0-rc4
_Released Oct 22, 2025_
## What's Changed
* Use updated preflight action and binary by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/165


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.0.0-rc3...v4.0.0-rc4
<br>

# v4.0.0-rc3
_Released Oct 21, 2025_
## 🐛 Bug Fixes

### `--queue-include-units-reading` used instead of `--units-that-include`

Pipelines will now always use `--queue-include-units-reading` instead of `--units-that-include`. 

Previously, Pipelines would only use the former flag for `FileChanged` events for the sake of providing greater backwards compatibility, but the minimum supported version of Terragrunt in Pipelines now supports `--units-that-include`, and this is no longer necessary.

By making this change, Pipelines now behaves more in-line with customer expectations, as customers expect that a file with an `.hcl` extension read via an HCL function like `read_terragrunt_config()` should still result in inclusion into the run queue.

## What's Changed
* chore: Bumping Pipelines CLI version to `v0.40.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/164


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.0.0-rc2...v4.0.0-rc3
<br>

# v4.0.0-rc2
_Released Oct 16, 2025_
## What's Changed
* fix: Adding concatenation of command and args back by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/163


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v4.0.0-rc1...v4.0.0-rc2
<br>

# v4.0.0-rc1
_Released Oct 8, 2025_
# Pipelines v4 Release Candidate 1

This is a release candidate for an upcoming Pipelines v4 major release. If you wish to be an early adopter contact a Gruntwork support representative.


# What's new in Pipelines v4
Pipelines v4 is nearly a full rewrite of the pipelines implementation within GitHub.  Prior to v4 the bulk of the "glue" logic to stitch together various components of the workflow was written in bash. In v4 we've replaced the majority of the bash code with golang code which is both faster, more maintainable and has significantly improved test coverage.  v4 also includes a handful of new features:

## Run-All Log Parsing
Pipelines will now request a custom log format from Terragrunt (via `TG_LOG_CUSTOM_FORMAT`) and then parse the resulting output into different streams, and present each Unit's output independently and deinterlaced in the pipelines comment engine.

## Support for newer Terragrunt Versions (through to 1.0)
Pipelines v3 has maximum Terragrunt version of 0.84.  Pipelines v4 removes this restriction and will support all Terragrunt versions from `0.86.3` through to 1.0+.

## Azure Support
Pipelines v4 includes support for Azure OIDC and state storage.  New configuration options are now available in [HCL configuration](https://docs.gruntwork.io/2.0/reference/pipelines/configurations-as-code/api#azure_oidc-block-attributes) for Azure.

## Improved / Faster commenting engine
Pipelines v4 includes a rewrite of several components of the commenting engine which should result in less time spent calculating and  posting PR comments.

## Improved Drift Detection filters
Pipelines v4 includes [a more expressive syntax](https://docs.gruntwork.io/2.0/docs/pipelines/guides/running-drift-detection#drift-detection-filter) for filters when triggering drift detection.

## Removal of several feature flags
The following [feature flags](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags) are now all *enabled* by default:

* PIPELINES_FEATURE_EXPERIMENT_AGGRESSIVE_CONSOLIDATION
* PIPELINES_FEATURE_EXPERIMENT_COLOCATED_FILE_UNIT_CHANGE_DETECTION
* PIPELINES_FEATURE_EXPERIMENT_MINIMIZE_BLAST_RADIUS

# Migration Guide

Please see a full migration guide at https://docs.gruntwork.io/2.0/docs/pipelines/previous-versions/upgrading-github-v3-to-v4

<br>

# v4.0.0
_Released Oct 22, 2025_
# What's new in Pipelines v4
Pipelines v4 is nearly a full rewrite of the pipelines implementation within GitHub.  Prior to v4 the bulk of the "glue" logic to stitch together various components of the workflow was written in bash. In v4 we've replaced the majority of the bash code with golang code which is both faster, more maintainable and has significantly improved test coverage.  v4 also includes a handful of new features:

## Support for newer Terragrunt Versions (through to 1.0)
Pipelines v3 has maximum Terragrunt version of 0.84.  Pipelines v4 removes this restriction and will support all Terragrunt versions from `0.86.3` through to 1.0+.

## Updated Configuration: Deprecating YML and promoting HCL out of beta
As of this release we are promoting HCL to the default configuration language for Pipelines.  This release includes additions to the pipelines HCL configuration specification that bring it up to full feature parity with YML, and we intend to build forwards using only HCL.  As a result, the YML configuration for Pipelines is now deprecated and will be removed in a future release.

## Run-All Log Parsing
Pipelines will now request a custom log format from Terragrunt (via `TG_LOG_CUSTOM_FORMAT`) and then parse the resulting output into different streams, and present each Unit's output independently and deinterlaced in the pipelines comment engine.

## Azure Support
Pipelines v4 includes support for Azure OIDC and state storage.  New configuration options are now available in [HCL configuration](https://docs.gruntwork.io/2.0/reference/pipelines/configurations-as-code/api#azure_oidc-block-attributes) for Azure.

## Improved / Faster commenting engine
Pipelines v4 includes a rewrite of several components of the commenting engine which should result in less time spent calculating and  posting PR comments.

## Improved Drift Detection filters
Pipelines v4 includes [a more expressive syntax](https://docs.gruntwork.io/2.0/docs/pipelines/guides/running-drift-detection#drift-detection-filter) for filters when triggering drift detection.

## Removal of several feature flags
The following [feature flags](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags) are now all *enabled* by default:

* PIPELINES_FEATURE_EXPERIMENT_AGGRESSIVE_CONSOLIDATION
* PIPELINES_FEATURE_EXPERIMENT_COLOCATED_FILE_UNIT_CHANGE_DETECTION
* PIPELINES_FEATURE_EXPERIMENT_MINIMIZE_BLAST_RADIUS

## `--queue-include-units-reading` used instead of `--units-that-include`

Pipelines will now always use `--queue-include-units-reading` instead of `--units-that-include`. 

Previously, Pipelines would only use the former flag for `FileChanged` events for the sake of providing greater backwards compatibility, but the minimum supported version of Terragrunt in Pipelines now supports `--units-that-include`, and this is no longer necessary.

By making this change, Pipelines now behaves more in-line with customer expectations, as customers expect that a file with an `.hcl` extension read via an HCL function like `read_terragrunt_config()` should still result in inclusion into the run queue.

## Updated Terminology: Module -> Unit
Pipelines v4 now refers to leaf folders with a `terragrunt.hcl` file as `units`.  Prior versions used the term `module`.  This change aligns Pipelines' terminology with Terragrunt's.

# Migration Guide

Please see a full migration guide at https://docs.gruntwork.io/2.0/docs/pipelines/previous-versions/upgrading-github-v3-to-v4


## What's Changed
* Use updated actions for comments by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/125
* Use updated preflight action that uses logic in binary by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/127
* Pass cli, actions, and credentials versions as inputs by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/126
* Fix pipelines comment token used in pipelines-root.yml preflight call by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/131
* fix: Addressing misnamed step status by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/134
* Use provision-account action that uses binary's create account by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/132
* fix: Using modern env vars instead of legacy `TERRAGRUNT_` environment variables by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/133
* Use baseline-core action that uses the pipelines binary by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/136
* Use pipelines propose-baseline-infra-change by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/137
* Use pipelines binary's auth for child account baselining  by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/138
* 2025 07 04 fix commenting by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/139
* Support status-update in baselining by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/143
* Pipelines CLI v0.40.0-rc17 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/146
* Drift Detection 2.0 Workflow by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/147
* DEV-1010 Per unit drift detection by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/152
* chore: Remove requirement for tokens by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/153
* chore: Bumping `mise` version to `2025.10.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/154
* Revert "chore: Bumping `mise` version to `2025.10.0`" by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/155
* chore: Bumping `mise` version to `2025.10.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/156
* Use pipelines binary for delegated repo setup by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/151
* Use updated actions to correctly report delegated repo job status by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/157
* Use pipelines binary unlock commands by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/158
* Remove pipelines-bootstrap action by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/159
* Fix invalid output by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/160
* 2025 10 08 v4.0.0 rc1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/162
* fix: Adding concatenation of command and args back by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/163
* chore: Bumping Pipelines CLI version to `v0.40.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/164
* Use updated preflight action and binary by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/165


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.9.0...v4.0.0
<br>

# v3.9.5
_Released Aug 13, 2025_
## Upgrade to Pipelines `v0.39.6`

This pulls in:

1. A bug fix for correct handling of patch versions of Terragrunt version v0.84, allowing patch versions (e.g. `v0.84.1`).
2. An improvement of the [Pipelines Ignore List](https://docs.gruntwork.io/2.0/reference/pipelines/ignore-list), which now supports excluding Terragrunt units during Execution in addition to ignoring Git changes during Orchestration.

## What's Changed
* chore: Bumping Pipelines CLI version to `v0.39.6` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/145


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.9.5
<br>

# v3.9.4
_Released Aug 6, 2025_
## Maximum Supported Terragrunt Version Introduced

This release introduces a maximum supported Terragrunt version of `v0.84` for the `v3` line of Pipelines Workflows.

The `v4` line of Pipelines Workflows will support versions of Terragrunt >= `v0.85`.

## What's Changed
* chore: Bumping Pipelines CLI version to `v0.39.4` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/144


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.9.4
<br>

# v3.9.3
_Released Jul 7, 2025_
## What's Changed
* Pin-mise-version-in-unlock by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/142


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.9.2...v3.9.3
<br>

# v3.9.2
_Released Jul 7, 2025_
## What's Changed
* Fix mise install by pinning mise version by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/141


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.9.1...v3.9.2
<br>

# v3.9.1
_Released Jun 26, 2025_
# What's Changed

## Fixed Account Factory Regression with PIPELINES_FEATURE_EXPERIMENT_MINIMIZE_BLAST_RADIUS

Fixed a regression in Account Factory when baselining new accounts with PIPELINES_FEATURE_EXPERIMENT_MINIMIZE_BLAST_RADIUS enabled.

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.9.0...v3.9.1
<br>

# v3.9.0
_Released May 20, 2025_
# What's Changed

## Opt-In Improvements to Change Detection

This release of Pipelines supports three new opt-in feature flags to improve the way we detect infra changes and execute Terragrunt in your repository. These features can be enabled by setting the following env vars to `"true"` in your Pipelines configuration. We expect to enable these behaviors by default in a future major version of Pipelines.

- `PIPELINES_FEATURE_EXPERIMENT_AGGRESSIVE_CONSOLIDATION`
Enabling this feature will cause more changes to be consolidated into a single run-all.

- `PIPELINES_FEATURE_EXPERIMENT_COLOCATED_FILE_UNIT_CHANGE_DETECTION` 
Enables changes to files colocated with a Terragrunt Unit (`terragrunt.hcl`) to be detected as a ModuleChanged job.

- `PIPELINES_FEATURE_EXPERIMENT_MINIMIZE_BLAST_RADIUS`
Enables Terragrunt [queue-strict-include](https://terragrunt.gruntwork.io/docs/reference/cli-options/#queue-strict-include) and [queue-exclude-external](https://terragrunt.gruntwork.io/docs/reference/cli-options/#queue-exclude-external) by default.

You can read more detail about each of these feature flags [here](https://docs.gruntwork.io/2.0/reference/pipelines/feature-flags).

## Pipelines Ignore List
Added support for excluding files and directories from Pipelines runs. The ignore list can be added to your Pipelines config. Read more about the ignore list [here](https://docs.gruntwork.io/2.0/reference/pipelines/ignore-list).
<br>

# v3.8.3
_Released May 8, 2025_
## What's Changed
* Use actions with root terragrunt file updates by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/123


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.8.2...v3.8.3
<br>

# v3.8.2
_Released May 5, 2025_
* Bump to actions 3.6.3 which includes a bugfix in how we calculate commit hashes for orchestrate

 **Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.8.2
<br>

# v3.8.1
_Released Apr 29, 2025_
## What's Changed

### Stacks Support For Account Vending

Account vending now supports Terragunt Stacks in the account template. Pipelines will generate stacks before plan and apply for new accounts.

### Bug Fixes

Fixed an issue where Pipelines Orchestrate would create duplicate jobs for stack units
<br>

# v3.8.0
_Released Apr 16, 2025_
## What's Changed

### Stacks Support Added

Pipelines now supports [Terragrunt stacks](https://terragrunt.gruntwork.io/docs/features/stacks/). When you push updates involving `terragrunt.stack.hcl` files in your Pull/Merge Requests, Pipelines automatically evaluates the required changes and orchestrates the infrastructure updates. This process ensures:

1. **Lowest Blast Radius:** Pipelines uses `terragrunt stack generate` to identify the minimum set of infrastructure units affected by your changes, avoiding unnecessary operations.
2. **Complete Management:** All relevant infrastructure actions triggered by your `terragrunt.stack.hcl` updates (create, read, update, destroy) are handled automatically.
3. **DAG Aware Execution:** Updates are applied respecting the dependency graph (DAG) order:
    - **Adds:** New units are created *after* any dependencies that also need adding.
    - **Changes:** Modified units are updated *after* any dependencies that also need changing.
    - **Destroys:** Units marked for removal are destroyed *after* any resources depending on them are also destroyed.

You can freely mix changes to `terragrunt.stack.hcl` and `terragrunt.hcl` files within the same Pull/Merge Request. Pipelines will process everything correctly.

#### Related Pull Requests
* Ore/dev-878-support-pipelines-unlock-on-stacks by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/116
* Stacks support by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/117


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.8.0
<br>

# v3.7.9
_Released Mar 6, 2025_
## Release Notes

This release changes the behavior of pipelines comment generation to ignore any comment artifacts that, for whatever reason, contain invalid json. Previously such invalid artifacts would cause the comment generation to fail entirely, now instead it continues and emits a warning.

## What's Changed
* bump actions to 3.4.3 by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/113


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.9
<br>

# v3.7.8
_Released Mar 6, 2025_
## Release Notes

If `pipelines-execute` exits with non-zero return code we now forward stderr to the comment.

## What's Changed
* Bump to actions 3.4.2 by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/112


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.8
<br>

# v3.7.7
_Released Mar 4, 2025_
## What's Changed

* Increase to pipelines cli v0.36.2 which includes updates to TOML parsing to avoid warnings/errors in logs for more sophisticated mise toml configurations

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.7
<br>

# v3.7.6
_Released Feb 25, 2025_
## Release Notes

* Updated orchestrate logic so changes in `.terraform.hcl.lock` do not generate HCLChanged events
* Updated orchestrate logic so FileChanged events are not emitted for changes in `accounts.yml` during AccountsAdded workflow runs.

## What's Changed
* Bump CLI to v0.36.0 by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/111


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.6
<br>

# v3.7.5
_Released Feb 21, 2025_
## What's Changed
* DEV-786 - Allow org_repo_admin fetch to fail on orchestrate by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/109

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.5
<br>

# v3.7.4
_Released Feb 18, 2025_
## Release Notes

Fixes a bug that caused a crash during account vending, https://github.com/gruntwork-io/pipelines-actions/issues/110

## What's Changed
* bump cli version by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/106


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.7.3...v3.7.4
<br>

# v3.7.3
_Released Feb 13, 2025_
## Release Notes

This version of pipelines reverts the real minimum version requirement for Terragrunt back to 0.59.7 (which has been the minimum going back to the 2.x line of releases).

Absolute Minimum Terragrunt Version Supported
* 0.59.7

Recommended Minimum Terragrunt Version
* 0.68.13 - This version contains additional flags required to enhance pipelines logging and support for [File Dependencies](https://docs.gruntwork.io/2.0/docs/pipelines/guides/file-dependencies)


## What's Changed
* bump cli version by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/106


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.7.2...v3.7.3
<br>

# v3.7.2
_Released Feb 12, 2025_
## What's Changed
* Pull in a bugfix from pipelines cli by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/105


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.2
<br>

# v3.7.10
_Released Apr 15, 2025_
## Changelog
* When codebases have both pipelines config-as-code (HCL) and config.yml configs, we now prefer the HCL configs for deploy_branch_name and tf_binary
* Pipelines no longer crashes if config.yml is missing when run in GitHub with only HCL based configuration.
* Make preflight comments collapsible and link to logs
* Adds GitLab log grouping
* Errors are red now in GitLab logs

## What's Changed
* Use latest CLI v0.36.6 by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/119


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.10
<br>

# v3.7.1
_Released Feb 11, 2025_
# Release Notes

Fixes a bug was introduced in pipelines [v0.32.0](https://github.com/gruntwork-io/pipelines/releases/tag/v0.32.0) that made it such that `enable-terragrunt-provider-cache` and `env` blocks would not propagate correctly to the terragrunt execution environment.

## What's Changed
* chore: Use binary v0.35.1 to fix env loading by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/104


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.1
<br>

# v3.7.0
_Released Feb 10, 2025_
## Release Notes

### New Features
- Gruntwork Pipelines can now run plan/apply automatically based on dependent-file changes
  - Users have requested the ability to trigger pipelines based on dependencies, such as yaml and json data files. Up until now the recommendation had been to make a white-space change in relevant Terragrunt files. This is an awkward workflow and one that's prone to error.
  - With this release, Pipelines will now detect changes in data files and emit `FileChanged` events, which then trigger pipelines runs that invoke terragrunt with the [`--queue-include-units-reading`](https://terragrunt.gruntwork.io/docs/reference/cli-options/#terragrunt-queue-include-units-reading) flag. You can also use the [`mark_as_read`](https://terragrunt.gruntwork.io/docs/reference/built-in-functions/#mark_as_read) function to track files that are read by OpenTofu code or bash scripts.
  - More information and examples for this feature will be published to docs.gruntwork.io in the coming days following this release.

## What's Changed
* Bump to CLI v0.35.0 by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/103

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.7.0

### UPDATE: Unintentional Breaking Change
- The minimum supported version of Terragrunt was increased to [v0.72.1](https://github.com/gruntwork-io/terragrunt/releases/tag/v0.72.1) in v3.7.0. This was not an intentional change, and there will shortly be a patch version to the 3.7.x branch that reverts the need for newer versions of Terragrunt.

### UPDATE 2: 
- Use v3.7.3+ to regain full compatibility with Terragrunt going back to 0.59.7
<br>

# v3.6.1
_Released Feb 10, 2025_
* Fix reference to actions versions in non-root workflows

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.6.0...v3.6.1
<br>

# v3.6.0
_Released Feb 10, 2025_
## What's Changed
* feat: allow passing in a custom binary by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/99


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.5.1...v3.6.0
<br>

# v3.5.1
_Released Jan 23, 2025_
* Increase the AWS session duration during the account vending process to make session timeouts less likely

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.5.1
<br>

# v3.5.0
_Released Dec 19, 2024_
# What's New

This release contains an update to account factory to forward the boolean values `disable_macie` `disable_security_hub` and `disable_guardduty` from the new account request files to the `accounts.yml` file.  This allows terragrunt units in infra-live to more easily access these three per-account configuration options and adjust their inputs appropriately.

Namely, in `terraform-aws-architecture-catalog`  `v2.12.0` we update the functionality of the `logs` account to read these values and disable the `macie` and `security_hub` modules, which prevents invites from being sent to accounts that don't have those features enabled.  This isn't strictlty required, as previously the invites were sent and never accepted, but this reduces the number of resources provisioned and makes the real world infrastructure better match the intent of the IaC.  

# Changelog
Bump to pipelines-actions v3.3.0

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.5.0
<br>

# v3.4.0
_Released Dec 9, 2024_
## What's Changed

- Fixed a bug where changes to [Pipelines Configurations as Code](https://docs.gruntwork.io/2.0/reference/pipelines/configurations-as-code/) would trigger pipelines plan / apply to be run. These operations were no-ops as no infrastructure was changed, but were unnecessarily using github action minutes.
- Improved startup time for PipelinesCLI by removing terragrunt/tofu/terraform version checks when not running execute. This improves overall pipelines run time.
<br>

# v3.3.0
_Released Dec 4, 2024_
## Release Notes

Pipelines uses a concept of "Gruntwork Context" which is basically a large bundle of runtime context and pipelines configuration.  Generating this context was several hundred lines of bash which included both simple read-and-store logic as well as sophisticated business logic. That code hard to test and a source of many bugs. This release includes a new implementation of all of that logic built into our pipelines binary (written in GoLang), which allows us to unit test the behavior and drive performance improvements over time. 

Customers will likely not notice any chance with this release other than maybe 1-2 faster runs in some cases, and ideally fewer corner-case bugs based on less commonly used configurations.

## What's Changed
* DEV-663: Bump version of actions that uses binary for reading config by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/100


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.3.0
<br>

# v3.2.1
_Released Nov 15, 2024_
## What's Changed
* Update pipelines-actions version by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/97


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.2.1
<br>

# v3.2.0
_Released Nov 14, 2024_
## What's Changed
* Record a job start time at the beginning of jobs by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/95


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.2.0
<br>

# v3.1.0
_Released Oct 31, 2024_
## What's Changed
* Pipelines CLI v0.31.0 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/93

## New Features
### Detect changes based on dependent HCL files (Pipelines CLI v.0.31)
If your `terragrunt.hcl` files use `include {}` blocks to bring in data from other HCL files, pipelines will now detect if those hcl files are changed and trigger a HCL Changed event which will run a `run-all plan` with `--terragrunt-modules-that-include` argument pointed to the changed HCL file. This is currently limited to only work with the `include` block, we plan to address other methods of nesting configuration such as `read_terragrunt_config` in a later release.

## Fixes & Improvements
- Bootstrap will now correctly detect missing configuration values in `.gruntwork/config.yml`. Previously empty values would be passed through which caused issues with templating new accounts.
- AWS credentials are now cached which significantly reduces the number of calls made to AWS APIs during a run-all


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.1.0
<br>

# v3.0.5
_Released Oct 10, 2024_
## What's Changed
* Pipelines CLI v0.29.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/91


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.0.4...v3.0.5
<br>

# v3.0.4
_Released Oct 9, 2024_
## What's Changed
* fix: Bumping up `pipelines-actions` to `v3.0.3` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/90


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.0.4
<br>

# v3.0.3
_Released Oct 8, 2024_
## What's Changed

- feat: Bump `pipelines-actions` to `v3.0.2`.

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3.0.2...v3.0.3
<br>

# v3.0.2
_Released Oct 8, 2024_
## What's Changed
* Pipelines actions v3.0.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/89


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.0.2
<br>

# v3.0.1
_Released Oct 8, 2024_
## What's Changed
* Fix syntax error due to bad character by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/88


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v3...v3.0.1
<br>

# v3.0.0
_Released Oct 8, 2024_
# :balloon: Gruntwork Pipelines v3.0.0 Release Notes

Pipelines version 3 introduces several new features which include a number of breaking changes.  The migration guide below should take less than 5 minutes for most teams to complete, but please do make sure to follow it closely.  We're providing a checklist here to help teams ensure that steps are not skipped.

- [ ] Install and configure the Gruntwork.io GitHub App
  - [ ] (Alternative) Add `actions:read` permission to PIPELINES_READ_TOKEN
  - [ ] (Alternative) (Enterprise Only) Add PR_CREATE_TOKEN to delegated repository workflows
- [ ] Update to Terragrunt v0.67.16 or later 
- [ ] (If necessary) Add new actions to GitHub Organization allow list settings
- [ ] (Enterprise Only) Install and activate Drift Detection

## Migration Guide
<details>
<summary><h2>Install and configure the Gruntwork.io GitHub App</h2></summary>

Pipelines now uses the Gruntwork.io GitHub App for workflow permissions, which simplifies permission management. Follow the [GitHub App Installation Instructions](https://docs.gruntwork.io/foundations/github-app/setup) to install the Gruntwork.io GitHub App and add your `infrastructure-live-root` repository to your account.

Using the Gruntwork.io GitHub App is recommended and provides full feature support for pipelines workflows. Alternatively, if you do not wish to install the Gruntwork.io GitHub App you can modify your existing workflows to continue using GitHub secrets, although some features will not be available. Read more about App only features [here](https://docs.gruntwork.io/foundations/github-app/availability#app-only-features).
<details>
<summary><h3>Alternative steps</h3></summary>

1. Add `actions: read` permissions

Customers explicitly list permissions that Gruntwork Pipelines workflows has by default in the pipelines workflow files in `.github/workflows` inside their infrastructure repositories.  Pipelines v3 now requires `actions: read` permissions in order to introspect its own runs and provide more helpful logging capabilities.

Customers should make the one-line change to add the `actions: read` permission in the following files <b>in every repository that uses Gruntwork pipelines</b> (including root, access control and delegated repos).  Note, most repositories will have only 1 or two of these workflow files, in which case update what is present and don't worry about the others.

* `.github/workflows/pipelines.yml`
* `.github/workflows/pipelines-drift-detection.yml`
* `.github/workflows/pipelines-root.yml`
* `.github/workflows/pipelines-unlock.yml`

### Old Permissions
```yml
permissions:
  id-token: write
  contents: write
  pull-requests: write
```
### New Permissions
```yml
permissions:
  id-token: write
  contents: write
  pull-requests: write
  actions: read
```

2. (Enterprise only) Add PR_CREATE_TOKEN to delegated repository workflows.

Delegated repositories that are not using the Gruntwork.io GitHub App will need to add  `PR_CREATE_TOKEN: ${{ github.token }}` to the secrets in their workflow files:

### Old Secrets
```yml
secrets:
  PIPELINES_READ_TOKEN: ${{ secrets.PIPELINES_READ_TOKEN }}
```
### New Secrets
```yml
secrets:
  PIPELINES_READ_TOKEN: ${{ secrets.PIPELINES_READ_TOKEN }}
  PR_CREATE_TOKEN: ${{ github.token }}
```

</details>

</details>
<details>
<summary><h2>Update to Terragrunt v0.67.16</h2></summary>

The latest pipelines works best with the latest version of Terragrunt.  Recent versions of Terragrunt have much improved logging, performance and correctness improvements in `run-all` scenarios with pipelines.
</details>
<details>
<summary><h2>Allowlist Actions</h2></summary>
<i>This is only for customers who only allow GitHub actions to run if they are on an <a href="https://docs.github.com/en/organizations/managing-organization-settings/disabling-or-limiting-github-actions-for-your-organization#allowing-select-actions-and-reusable-workflows-to-run">explicit allowlist</a></i>

<h3>New actions to add</h3>

* `gruntwork-io/pipelines-credentials`
* `gruntwork-io/pipelines-actions/.github/actions/pipelines-drift-detection-consolidate-jobs`
* `gruntwork-io/pipelines-actions/.github/actions/pipelines-drift-detection-determine-units`
* `gruntwork-io/pipelines-actions/.github/actions/pipelines-drift-detection-determine-drift`
* `gruntwork-io/pipelines-actions/.github/actions/pipelines-new-pr-action`
* `gruntwork-io/pipelines-actions/.github/actions/pipelines-get-job-logs-url`
</details>
<details>
<summary><h2>(Enterprise Only) Install and activate Drift Detection</h2></summary>
Pipelines Drift Detection can be installed in your repositories by adding a new workflow file:

1. Create a new file at `.github/workflows/pipelines-drift-detection.yml`
2. Add the following content to the file

```yml
name: Pipelines Drift Detection
run-name: "[GWP]: Pipelines Drift Detection"
on:
  # Uncomment to enable scheduled Drift Detection
  # schedule:
  #  - cron: '15 12 * * 1'
  workflow_dispatch:
    inputs:
      path:
        description: (Optional) Path to filter units e.g. "./management/*"
        type: string
      branch-name:
        description: (Optional) branch name to open Drift Detection PRs with
        default: drift-detection
        type: string
permissions:
  id-token: write

jobs:
  GruntworkPipelines:
    uses: gruntwork-io/pipelines-workflows/.github/workflows/pipelines-drift-detection.yml@v3
    with:
      path: ${{ inputs.path }}
      branch-name: ${{ inputs.branch-name }}
```

</details>

## New Features
- [Pipelines as a GitHub App](https://docs.gruntwork.io/foundations/github-app/)
- [Pipelines Drift Detection](https://docs.gruntwork.io/pipelines/maintain/drift-detection) (Enterprise Only)
- Improved Account Factory Bootstrap Customization Hooks
- Pipelines Log Link Improvements
- [new config options](https://docs.gruntwork.io/pipelines/overview/configurations) in `config.yaml`
  - `consolidate-added-or-changed`: allows the pipeline to run as a single parallelized terragrunt instance such that dependencies are respected for deletions
  - `consolidate-deleted`: Enable conslidating ModuleDeleted jobs with `run-all`
  - `enable-terragrunt-provider-cache`: uses the new terragrunt provider cache so that you don't fetch the same 500 meg aws provider binary 20 times

<br>

# v3
_Released Aug 13, 2025_
This is a floating release tracking the latest `v3.y.z` release.
<br>

# v2.6.1
_Released Sep 27, 2024_
## What's Changed
* fix: Pin `pipelines-actions` to `v.12.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/87


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.6.1
<br>

# v2.6.0
_Released Aug 14, 2024_
## New Features

* We now allow for specifying arbitrary env values via `config.yml`.  See the [docs](https://docs.gruntwork.io/pipelines/overview/configurations) for an example of how to set `.pipelines.env` with your custom environment values.
* An update to the `pipelines-unlock` workflow with an optional `unlock_all` flag that iterates over every state file and unlocks all of them.  This is useful in the event of a large run, e.g. `run-all plan` that is cancelled midway leaving many locks stuck.

## Enhancements

* Pipelines now detects if the `PIPELINES_READ_TOKEN` is invalid and posts a more helpful error to logs, the PR comment and the step summary letting you know to ensure the token is valid.

## PR Changelog

* Pipelines CLI v0.23.0 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/71
* Pipelines CLI v0.23.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/72
* Pipelines CLI v0.24.0 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/74
* Force unlock all by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/77
* feat: detect invalid read tokens by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/80
* chore: Bumping `pipelines-cli` to `v0.28.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/81


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.6.0
<br>

# v2.5.0
_Released Jul 30, 2024_
## What's Changed
* DEV-427 - Unlock State Workflow by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/64
* chore: Bumping `pipelines` to `v0.21.2` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/65
* DEV-129: Add additional pipelines preflight checks by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/67
* Fix action reference in account bootstrap job's name by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/70
* Bump to version v1.9.0 of pipelines-actions which brings in complementary changes for the above new features (unlocking and preflight) as well as a handful of bug fixes - https://github.com/gruntwork-io/pipelines-actions/releases/tag/v1.9.0

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.5.0
<br>

# v2.4.0
_Released Jul 18, 2024_
## What's Changed
This pulls in a change to Pipelines HCL Configuration as Code system to segment the `aws_accounts` block into an `accounts` block nested as the `aws` block.

While this is a breaking change, it is not in use by any customers at the moment, and should be safe to use without modification.

## Changelog
* chore: Bumping `pipelines` and `pipelines-actions` versions by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/63


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2.3.3...v2.4.0
<br>

# v2.3.3
_Released Jul 16, 2024_
## What's Changed

This pulls in a rename of the `pipelines` HCL configuration block for Pipelines to `repository` via updates to the `pipelines-cli`.

In addition, it pulls in changes to `pipelines-actions` which result in a new `CATALOG_TAGS` value being used during repository vending. This allows for central management of AWS cost allocation tags for delegated repositories.

Some plumbing changes have been done in addition to improve the configurability of the `TF_BINARY` configuration, making it easier to decide whether you want to use OpenTofu or Terraform.

## Changelog
* feat: Bumping `pipelines-cli` to `v0.20.0` and `pipelines-actions` to `v1.8.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/62


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.3.3
<br>

# v2.3.2
_Released Jul 16, 2024_

* Include bugfix version of pipelines actions https://github.com/gruntwork-io/pipelines-actions/releases/tag/v1.7.1

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.3.2
<br>

# v2.3.1
_Released Jul 16, 2024_
## What's Changed
* chore: Bumping `pipelines-cli` to `v0.19.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/61


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2.3.0...v2.3.1
<br>

# v2.3.0
_Released Jul 16, 2024_
## What's Changed
* feat: Adding `pipelines.yml` workflow by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/51
* chore: Bumping `pipelines-cli` to `v0.19.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/60
* chore: Bumping `pipelines-actions` to `v1.7.0` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/59


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2.2.1...v2.3.0
<br>

# v2.2.1
_Released Jul 8, 2024_
## What's Changed
* Bump to version [v1.5.0 of pipelines actions](https://github.com/gruntwork-io/pipelines-actions/releases/tag/v1.5.0) which includes an updated commenting strategy that should be much faster for all users.
* Fix delegated workflow's bootstrap reference by @oredavids in https://github.com/gruntwork-io/pipelines-workflows/pull/48

## New Contributors
* @oredavids made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/48

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v2...v2.2.0
<br>

# v2.1.0
_Released Jul 3, 2024_
## What's Changed

Take special note of the changes in https://github.com/gruntwork-io/pipelines-workflows/pull/45. It introduces significant changes to how Pipelines workflows operate, and should be evaluated carefully when considering an upgrade to this release.

In particular, https://github.com/gruntwork-io/pipelines-workflows/pull/45 changes the behavior of the EnvCommonChanged job. Pipelines Orchestrate will no longer emit a single job for each AWS account, looking for relevant updates to an _envcommon file that has changed. Instead, a single job will be emitted from the root of the repository that will look for changes throughout the repository. This change leverages the new capabilities released as of [v2.0.0](https://github.com/gruntwork-io/pipelines-workflows/releases/tag/v2.0.0) where Terragrunt will dynamically assume the correct role in a given directory through integration with Pipelines.

## Changelog
* fix: Adjusting delegated workflow so that it uses dynamic authentication too by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/44
* feat: Bumping Pipelines CLI to `v0.15.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/45
* chore: Pin actions version by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/46


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.6.0...v2.1.0
<br>

# v2.0.0
_Released Jul 2, 2024_
## What's Changed

This release introduces the concept of "hooks" in `pipelines-root.yml` as a mechanism to customize the account factory workflows.  The intention is that consumers will fork `pipelines-workflows`, add a step to checkout their own actions repository (or their own fork of `pipelines-actions`), and then change the "uses" block in the pre/post steps to point to their customized workflows.  

We're actively trying to balance providing a highly extensible mechanism for users to adapt pipelines to their needs, whilst also maintaining upgrade-ability down the line. We hope that by encouraging customizations to live in separate actions that future updates to `pipelines-root.yml` will not cause significant merge conflicts, and that updates to `pipelines-actions` can continue to be pulled in via a version bump, even in a highly customized environment.

### 🛠️ Breaking Changes

This release includes a breaking change requiring that a minimum version of `v0.59.5` for Terragrunt is used in CI.

This is due to the fact that Pipelines now integrates with the newly available [dynamic authentication capabilities in Terragrunt](https://github.com/gruntwork-io/terragrunt/releases/tag/v0.59.5).

For most, this entails making an update to the `.mise.toml` file in the root of the repository where Pipelines runs.

While this is the minimum version required, take note of the bug fix introduced in [v0.59.7](https://github.com/gruntwork-io/terragrunt/releases/tag/v0.59.7). If you are using the `get_aws_account_id` function in your Terragrunt configurations, you are advised to upgrade to this version to incorporate that bug fix.

### New Action Usage
For Pipelines users that allowlist specific actions, version 2.0 includes the following new actions
* ./pipelines-actions/.github/custom-actions/pre-provision-new-account
* ./pipelines-actions/.github/custom-actions/post-provision-new-account
* ./pipelines-actions/.github/custom-actions/pre-baseline-core-accounts
* ./pipelines-actions/.github/custom-actions/post-baseline-core-accounts
* ./pipelines-actions/.github/custom-actions/pre-baseline-child-account
* ./pipelines-actions/.github/custom-actions/post-baseline-child-account
* ./pipelines-actions/.github/custom-actions/post-create-delegated-repo

### Changelog

* Use pipelines auth for terragrunt execute by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/37
* chore: add bootstrap to root, make bootstrap step id consistent by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/41
* Fix missed rename by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/42
* Customization Hooks by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/40
* fix: Moving yml configurations for custom actions to an `action.yml` nested under the action name by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/43

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v2.0.0
<br>

# v2
_Released Sep 27, 2024_
This is a floating release tracking the latest release with major version `2`.
<br>

# v1.5.0
_Released Jun 17, 2024_
## What's Changed
* Remove out of date comment by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/35
* chore: Bump `pipelines-actions` to `v1.3.3` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/36

## Breaking Changes
As of this release, the `gruntwork-installer-version` and `boilerplate-version` versions are no longer configurable in the `.gruntwork/config.yml` in `infrastructure-live` repositories.

They are now configurable as environment variables directly in the workflows instead, as the average customer has no need to configure them on a per-infrastructure-live repository basis.

No action needs to be taken to adopt this change. Just take note that the configurations in `.gruntwork/config.yml` will be ignored if present.

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.5.0
<br>

# v1.4.0
_Released Jun 13, 2024_
## What's Changed
* Add runner as input by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/34
* chore: Bump `pipelines-actions` to `1.3.2` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/33
* feat: Migrating unnecessary configs out of `.gruntwork/config.yml` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/32


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.4.0
<br>

# v1.3.2
_Released Jun 4, 2024_
## What's Changed
* Bump pipelines to 0.10.1 actions to 1.3.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/31


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.3.2
<br>

# v1.3.1
_Released Jun 3, 2024_
## What's Changed
* Upgrade pipelines-cli and actions to use tfplan output by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/30


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.3.1
<br>

# v1.3.0
_Released May 29, 2024_
## What's Changed
* Bump pipelines actions to v1.2.0 to get configurable account names by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/29


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.3.0
<br>

# v1.2.9
_Released May 28, 2024_
## What's Changed
* chore: Bumping `pipelines-cli` to `v0.9.11` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/28


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.2.9
<br>

# v1.2.8
_Released May 23, 2024_
## What's Changed
* chore: Bumping `pipelines-cli` to `v0.9.10` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/27


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.2.8
<br>

# v1.2.7
_Released May 23, 2024_
## What's Changed
* chore: Bumping `pipelines-actions` to `v1.1.3` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/26


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.2.6...v1.2.7
<br>

# v1.2.6
_Released May 23, 2024_
## What's Changed
* chore: Bumping `pipelines-actions` to `v1.1.2` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/25


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.2.5...v1.2.6
<br>

# v1.2.5
_Released May 23, 2024_
## What's Changed
* chore: Bumping `pipelines-actions` to `v1.1.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/23


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.2.5
<br>

# v1.2.4
_Released May 21, 2024_
## What's Changed
* Use env.PIPELINES_CLI_VERSION by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/16
* Use gruntwork-io/pipelines-actions v1.0.1 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/18
* feat: Adding plan/apply to job names by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/21


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.2.4
<br>

# v1.2.3
_Released May 14, 2024_
## What's Changed
* Update pipelines cli to v0.9.8 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/17
* Bumping `pipelines-provision-account-action` to `v1.1.1` by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/15


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1...v1.2.3
<br>

# v1.2.2
_Released May 10, 2024_
## What's Changed
* Fix: Setup step details extended (e.g. plan stdout)  by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/13


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.2.1...v1.2.2
<br>

# v1.2.1
_Released May 8, 2024_
## What's Changed
* Tweak comment text if no step input exists by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/12


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.2.0...v1.2.1
<br>

# v1.2.0
_Released May 6, 2024_
## What's Changed
* chore(deps): bump gruntwork-io/pipelines-provision-account-action from 1.0.0 to 1.1.0 by @dependabot in https://github.com/gruntwork-io/pipelines-workflows/pull/11


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.1.0...v1.2.0
<br>

# v1.1.0
_Released May 6, 2024_
## What's Changed
* feat: Updating all actions by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/9
* Fix readme links by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/10

## Special Release
This release includes updates to breaking changes in multiple actions. Given that the integration with [the breaking change](https://github.com/gruntwork-io/pipelines-bootstrap/pull/2) is already updated in [the upstream reference](https://github.com/gruntwork-io/terraform-aws-architecture-catalog/pull/1067) to the `v1` tag of this repository, this will only be considered a minor release, even though it would normally result in a major version bump.

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.0.1...v1.1.0
<br>

# v1.0.1
_Released May 3, 2024_
## What's Changed
* Use pipelines v0.9.4 by @Resonance1584 in https://github.com/gruntwork-io/pipelines-workflows/pull/8

## New Contributors
* @Resonance1584 made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/8

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v1.0.0...v1.0.1
<br>

# v1.0.0
_Released Apr 30, 2024_
## What's Changed
* chore: bump aws execute by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/6


**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v0.0.5...v1.0.0
<br>

# v1
_Released Jun 17, 2024_

<br>

# v0.0.5
_Released Apr 30, 2024_
## What's Changed
* Version dump dependencies by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/3
* chore(deps): bump gruntwork-io/pipelines-provision-account-action from 0.0.3 to 0.0.4 by @dependabot in https://github.com/gruntwork-io/pipelines-workflows/pull/4
* AWS Execute Improvement by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/5

## New Contributors
* @dependabot made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/4

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v0.0.4...v0.0.5
<br>

# v0.0.4
_Released Apr 26, 2024_
* Bump versions of downstream actions

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v0.0.3...v0.0.4
<br>

# v0.0.3
_Released Apr 26, 2024_
* bump version of pipelines-aws-execute 

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v0.0.2...v0.0.3
<br>

# v0.0.2
_Released Apr 26, 2024_
## What's Changed
* Move pipelines CLI version into the workflow by @ZachGoldberg in https://github.com/gruntwork-io/pipelines-workflows/pull/1
* chore: Updating README.md by @yhakbar in https://github.com/gruntwork-io/pipelines-workflows/pull/2

## New Contributors
* @ZachGoldberg made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/1
* @yhakbar made their first contribution in https://github.com/gruntwork-io/pipelines-workflows/pull/2

**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/compare/v0.0.1...v0.0.2
<br>

# v0.0.1
_Released Apr 26, 2024_
**Full Changelog**: https://github.com/gruntwork-io/pipelines-workflows/commits/v0.0.1
<br>

