# provider-upjet-elasticstack

Helm chart for namespaced managed resources from provider-upjet-elasticstack

## Supported Resources

This chart can render the following namespaced resources from `provider-upjet-elasticstack`:

- `ClusterSettings`
- `IndexLifecycle`
- `ElasticsearchRole`
- `ElasticsearchUser`
- `SnapshotLifecycle`
- `SnapshotRepository`
- `ProviderConfig`

## Usage

Render the chart:

```bash
helm template my-release .
```

For `providerConfigs`, you can either provide `spec.credentials` directly or set top-level `username`, `password`, and `endpoints`. When those top-level values are set, the chart creates a Secret named `<providerConfig name>-credentials` with a `credentials` key and wires `spec.credentials.secretRef` automatically.

Regenerate the documentation:

```bash
helm-docs --sort-values-order=file
```

## Values

The full example schemas live in `values.yaml` as commented examples below each top-level key.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| clusterSettings | list | `[]` (see the commented example below for the full schema) | List of namespaced `ClusterSettings` managed resources. `persistent` and `transient` use `settingName: value` or `settingName: [values...]` and are translated to the provider CRD structure by the template. |
| indexLifecycles | list | `[]` (see the commented example below for the full schema) | List of namespaced `IndexLifecycle` managed resources. |
| elasticsearchRoles | list | `[]` (see the commented example below for the full schema) | List of namespaced `ElasticsearchRole` managed resources. |
| elasticsearchUsers | list | `[]` (see the commented example below for the full schema) | List of namespaced `ElasticsearchUser` managed resources. |
| snapshotLifecycles | list | `[]` (see the commented example below for the full schema) | List of namespaced `SnapshotLifecycle` managed resources. |
| snapshotRepositories | list | `[]` (see the commented example below for the full schema) | List of namespaced `SnapshotRepository` managed resources. |
| providerConfigs | list | `[]` (see the commented example below for the full schema) | List of namespaced `ProviderConfig` resources used by the managed resources in this chart. |
