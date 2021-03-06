# superorbital-helm-charts

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/superorbital)](https://artifacthub.io/packages/search?repo=superorbital)

The public repo is rendered into the `gh-pages` branch and can be found online at:

[SuperOrbital Helm Repo](https://helm.superorbital.io/)

---

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  `helm repo add superorbital https://helm.superorbital.io/`

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
superorbital` to see the charts.

To install the `cludod` chart:

  `helm install cludod superorbital/cludod`

To uninstall the chart:

  `helm delete cludod`

## Documentation

* For detailed application installation and usage documentation please check the `README.md` in the appropriate source code repository. (e.g. [superorbital/cludo README](https://github.com/superorbital/cludo/blob/main/README.md))
