# superorbital-helm-charts

This site contains SuperOrbital's public facing helm chart repo.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  `helm repo add superorbital https://superorbital.github.io/helm-charts`

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
superorbital` to see the charts.

To install the `cludod` chart:

  `helm install cludod superorbital/cludod`

To uninstall the chart:

  `helm delete cludod`

## Documentation

* For detailed application installation and usage documentation please check the `README.md` in the appropriate source code repository. (e.g. [superorbital/cludo README](https://github.com/superorbital/cludo/blob/main/README.md))
