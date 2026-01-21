# 🚀 Install cert-manager GitHub Action  
This Action installs cert-manager and creates  Kubernetes deployments including status checks, log collection, and test validation.

## Features
- Install cert-manager
- Creates cert-manager entities - Issuer, ClusterIssuer

## 📌 Inputs

| Name                             | Description                                   | Required | Default      |
|----------------------------------|-----------------------------------------------|----------|--------------|
| `namespace`                      | Target Kubernetes namespace for cert-manager  | No       | cert-manager |
| `version`                        | The version of cert-manager to install        | No       | v1.16.3      |
| `create_entities`                | Whether to create cert-manager entities       | No       | true         |

## Usage Example

```yaml
name: Install cert-manager

on:
  workflow_dispatch:

jobs:
  installation:
    runs-on: ${{ inputs.runner_type }}
    steps:
      - name: Install cert-manager
        uses: Netcracker/qubership-test-pipelines/actions/shared/install_cert_manager@main
        with:
          namespace: 'cert-manager'
          version: 'v1.16.3'
          create_entities: true
```
