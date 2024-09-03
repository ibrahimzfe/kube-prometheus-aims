## Quickstart
* Install

```shell
kubectl apply --server-side -f manifests/setup
kubectl wait \
	--for condition=Established \
	--all CustomResourceDefinition \
	--namespace=monitoring
kubectl apply -f manifests/
```

We create the namespace and CustomResourceDefinitions first to avoid race conditions when deploying the monitoring components.
Alternatively, the resources in both folders can be applied with a single command
`kubectl apply --server-side -f manifests/setup -f manifests`, but it may be necessary to run the command multiple times for all components to
be created successfully.

Uninstall (hati2. akan delete semua termasuk namespace)

```shell
kubectl delete --ignore-not-found=true -f manifests/ -f manifests/setup
```

To contribute to kube-prometheus, refer to [Contributing](CONTRIBUTING.md).

## Join the discussion

If you have any questions or feedback regarding kube-prometheus, join the [kube-prometheus discussion](https://github.com/prometheus-operator/kube-prometheus/discussions). Alternatively, consider joining [the kubernetes slack #prometheus-operator channel](http://slack.k8s.io/) or project's bi-weekly [Contributor Office Hours](https://docs.google.com/document/d/1-fjJmzrwRpKmSPHtXN5u6VZnn39M28KqyQGBEJsqUOk/edit#).

## License

Apache License 2.0, see [LICENSE](https://github.com/prometheus-operator/kube-prometheus/blob/main/LICENSE).
