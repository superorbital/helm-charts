# Development

All public SuperOrbital helm charts should be maintained in this repo.

* In general you should only be PRing changes to the `main` branch.
  * The only normal exception to this, is if you want to update the README that is presented to users at the root of the [helm repo](https://helm.superorbital.io/). In this case, it is safe to update the [gh-pages README.md directly](https://github.com/superorbital/helm-charts/blob/gh-pages/README.md).
  * Anything merged into main will be published to the public repo.

## Github Actions

### CI Pipeline (`ci.yaml`)

Our CI pipeline uses [GitHub Actions](https://github.com/features/actions) and [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets) to test, build, and release our code.

*Note: With the exception of GITHUB_TOKEN, secrets are not passed to the runner when a workflow is triggered from a forked repository.*

The workflow looks something like this:

* On any push:
  * Set up Helm
  * Setup Python
  * Prepare cludod config stub files
  * Set up helm chart-testing tool (ct)
  * Run chart-testing (list-changed)
  * Run chart-testing (lint)
    * We only do this step if:
      * If chart-testing (lint) detects changes between this branch and the main branch.
  * Create kind cluster
    * We only do this step if:
      * If chart-testing (list-changed) detected changed between this branch and the main branch.
  * Run chart-testing (install)
    * We only do this step if:
      * If chart-testing (install) detects changes between this branch and the main branch.

### Release Process (`release.yaml`)

The workflow looks something like this:

* On any merge into `main`:
  * Checkout source code
  * Configure git
  * Create chart tarballs and related github release and then update the `gh-pages` branch as required.
