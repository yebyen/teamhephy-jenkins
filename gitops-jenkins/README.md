### Jenkins GitOps Deployment

Jenkins is installed as a Helm Release, via FluxCD and Helm Operator (GitOps)

If you need to add resources, "HelmRelease" resources should go in `releases/`
and other manifest files should go in `manifests/`

Commits are applied to the cluster from the "release" branch only, and they are
verified using "first-parent" strategy as described in the FluxCD docs:

https://docs.fluxcd.io/en/1.20.2/references/git-gpg/#first-parent
