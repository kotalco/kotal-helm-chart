## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add kotal https://kotalco.github.io/kotal-helm-chart

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo kotal` to see the charts.

To install the kotal chart:

    helm install kotal kotal/kotal


To upgrade the kotal chart:

    # Upgrading dependencies CRDs
    kubectl apply --server-side --force-conflicts -k https://github.com/traefik/traefik-helm-chart/traefik/crds/
    # Update repository
    helm repo update
    # Upgrade kotal
    helm upgrade kotal kotal/kotal


To uninstall the chart:

    helm delete kotal
