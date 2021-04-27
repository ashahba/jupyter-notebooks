

all: s2i-lab-elyra

.PHONY: s2i-lab-elya

s2i-lab-elyra: s2i-lab-elyra.json
	kubectl get imagestream $@ 2>/dev/null && kubectl delete imagestream $@ || exit 0
	kubectl get buildconfig $@ 2>/dev/null && kubectl delete buildconfig $@ || exit 0
	cat $@.json | yq r - -P items[0] | kubectl apply -f -
	cat $@.json | yq r - -P items[1] | kubectl apply -f -
