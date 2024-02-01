# How to run Prometheus & Grafana with kubernetes

1. Use Kompose to generate k8s .yaml files:
`kompose convert -f compose.yaml -o k8s/`
2. Create secrets in secrets.yaml (login and password)
3. Create grafana and prometheus configmaps using respective .yml files
4. Change volumes in the `prometheus-deployment.yaml` to "prometheus-configmap"
5. Deploy with kubectl command:
`kubectl apply -f k8s/`
6. Show artifacts:
`kubectl get pods,services,secrets,configmaps`
7. Acess grafana UI:
`minikube service grafana`