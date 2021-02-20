# getthedocs-helm-starter
Helm starter to define Kubernetes resources (pv, sc) for the getthedocs template engine

Template engine docs: https://github.com/videki/template-utils

## Usage

Install this repository in your local Helm starter repository:

```bash
git clone https://github.com/videki/getthedocs-helm-starter.git $HOME/.helm/starters/getthedocs-app
```
 
Create an Helm chart for your app volume dependencies:

```bash
helm create --starter=getthedocs-app myapp-docs
Creating myapp-docs
```

Edit the generated file `myapp-docs/values.yml` and set up the volumes with 
the template, document structure and result paths:

```yaml
config:
  storage:
    fonts:
      path: /mnt/data/sample-app/repositories/source/fonts
      size: 100Mi
    docStructures:
      path: /mnt/data/sample-app/repositories/source/documentstructures
      size: 100Mi
    templates:
      path: /mnt/data/sample-app/repositories/source/templates
      size: 100Mi
    results:
      path: /mnt/data/sample-app/repositories/target/generated-documents
      size: 50Gi
```
 
