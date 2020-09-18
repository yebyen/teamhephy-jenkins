### Jenkins GitOps Deployment

Jenkins is installed as a Helm Release, via FluxCD and Helm Operator (GitOps)

If you need to add resources, "HelmRelease" resources should go in `releases/`
and other manifest files should go in `manifests/`
