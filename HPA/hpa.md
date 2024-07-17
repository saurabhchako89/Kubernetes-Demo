Step 1 : Download metrics server spec
wget https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.5.0/components.yaml

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml


Step 2 : Edit the downloaded components.yaml


Step 3 : Check availability of metrics server
kubectl get apiservices

Step 4 : 