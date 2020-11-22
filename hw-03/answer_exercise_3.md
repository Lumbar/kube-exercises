Se debe habilitar lo siguiente:
minikube addons enable metrics-server

kubectl apply -f deployment.yaml

kubectl autoscale deployment nginx --cpu-percent=50 --min=1 --max=10

kubectl get hpa

- Y aquí se verificará que al superar el 50% de los límites de cpu se harán las réplicas necesarias
kubectl get hpa -w

