

all: s2i-lab-elyra s2i-odh-dashboard intel-aikit-notebook

.PHONY: s2i-lab-elya s2i-odh-dashboard

s2i-lab-elyra: s2i-lab-elyra.json
	kubectl get imagestream $@ 2>/dev/null && kubectl delete imagestream $@ || exit 0
	kubectl get buildconfig $@ 2>/dev/null && kubectl delete buildconfig $@ || exit 0
	cat $@.json | yq r - -P items[0] | kubectl apply -f -
	cat $@.json | yq r - -P items[1] | kubectl apply -f -

s2i-odh-dashboard: s2i-odh-dashboard.json
	kubectl get imagestream $@ 2>/dev/null && kubectl delete imagestream $@ || exit 0
	kubectl get buildconfig $@ 2>/dev/null && kubectl delete buildconfig $@ || exit 0
	cat $@.json | yq r - -P items[0] | kubectl apply -f -
	cat $@.json | yq r - -P items[1] | kubectl apply -f -

intel-aikit-notebook: intel-aikit-notebook.json
	kubectl get imagestream $@ 2>/dev/null && kubectl delete imagestream $@ || exit 0
	kubectl get buildconfig $@ 2>/dev/null && kubectl delete buildconfig $@ || exit 0
	cat $@.json | yq r - -P items[0] | kubectl apply -f -
	cat $@.json | yq r - -P items[1] | kubectl apply -f -
