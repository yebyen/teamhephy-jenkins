.PHONY: fluxcd

GIT_REPO := git@github.com:ndoit/empfin-jenkins.git

fluxcd:
	helm upgrade -i flux fluxcd/flux \
	    --namespace fluxcd \
	    --set git.url=$(GIT_REPO) \
	    --set git.path="releases\,manifests" \
	    --set git.branch=release \
	    --set git.verifySignatures=true \
	    --set gpgKeys.configMapName=flux-gpg-public-keys
