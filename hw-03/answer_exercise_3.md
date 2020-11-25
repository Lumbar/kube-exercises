Se debe habilitar lo siguiente:
minikube addons enable metrics-server

kubectl apply -f deployment.yaml

-- Se realiza el autoscaling con el siguiente comando
kubectl autoscale deployment nginx-dply --cpu-percent=50 --min=1 --max=10

-- Se verifica lo creado
kubectl get hpa

-- Se verifica la url del servicio
minikube service nginx-srvc --url --namespace=kube-exercises

- Y aquí se verificará que al superar el 50% de los límites de cpu se harán las réplicas necesarias usando los siguientes comandos
kubectl get hpa -w
kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://172.17.186.6:31217; done"