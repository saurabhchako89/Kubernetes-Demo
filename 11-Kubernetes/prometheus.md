https://www.macstadium.com/blog/how-to-k8s-getting-started-with-prometheus-and-grafana

//start minikube and the dashboard
minikube start
minikube dashboard

//Install helm
brew install helm

//Add the kube-prometheus-stack helm repo
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

//deploy the helm chart
helm install my-kube-prometheus-stack prometheus-community/kube-prometheus-stack - version 34.10.0

//retrieve the Grafana password. Username is admin
kubectl get secret my-kube-prometheus-stack-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

//Access the Grafana dashboard
kubectl port-forward svc/my-kube-prometheus-stack-grafana :80

//Access the prometheus dashboard
kubectl port-forward svc/my-kube-prometheus-stack-prometheus 9090