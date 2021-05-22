# vcluster jsonnet library

Jsonnet library for [vcluster](https://github.com/loft-sh/vcluster) based on their [kubectl
manifests](https://github.com/loft-sh/vcluster/#2-create-a-vcluster).

## Usage

Install it with jsonnet-bundler:

```console
jb install github.com/duologic/vcluster-libsonnet
```

Import into your jsonnet:

```jsonnet
// environments/default/main.jsonnet
local vcluster = import 'github.com/duologic/vcluster-libsonnet/vcluster/main.libsonnet';

{
  vcluster:
    vcluster(
      name='vcluster',
      namespace='my-vcluster-ns',
      service_cidr='10.96.0.0/12',  # Important: make sure this matches with the Service CIDR of the host cluster.
    ),
}
```
