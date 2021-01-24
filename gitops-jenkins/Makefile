.PHONY: fluxcd helm-operator

GIT_REPO := git@github.com:yebyen/teamhephy-jenkins.git

fluxcd:
	helm upgrade -i flux fluxcd/flux \
	    --namespace flux \
	    --set image.tag=1.21.1 \
	    --set git.url=$(GIT_REPO) \
	    --set git.path="gitops-jenkins/releases\,gitops-jenkins/manifests" \
	    --set git.branch=release \
	    --set gpgKeys.configMapName=flux-gpg-public-keys \
	    --set gpgKeys.secretName=flux-gpg-signing-key \
	    --set additionalArgs[0]="--git-verify-signatures-mode=first-parent" \
	    --set git.signingKey=6634687FCEDD8B215313827900B28B654B6427B7

helm-operator:
	helm upgrade -i helm-operator fluxcd/helm-operator \
	    --namespace flux \
	    --set git.ssh.secretName=flux-git-deploy \
	    --set helm.versions=v3
