.PHONY: fluxcd

GIT_REPO := git@github.com:ndoit/empfin-jenkins.git

fluxcd:
	helm upgrade -i flux fluxcd/flux \
	    --namespace fluxcd \
	    --set git.url=$(GIT_REPO) \
	    --set git.path="gitops-jenkins/releases\,gitops-jenkins/manifests" \
	    --set git.branch=release \
	    --set gpgKeys.configMapName=flux-gpg-public-keys \
	    --set gpgKeys.secretName=flux-gpg-signing-key \
	    --set additionalArgs[0]="--git-verify-signatures-mode=first-parent" \
	    --set git.signingKey=6CF0282ED43CEB0EFA5DA9335A88501AE567254E

