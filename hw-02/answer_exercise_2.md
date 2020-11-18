Se crea el replicaset con el siguiente comando
kubectl apply -f replicaset.yaml

Y se visualiza lo creado con el siguiente comando
kubectl get rs

¿Cúal sería el comando que utilizarías para escalar el número de replicas a 10?
kubectl scale rs --replicas=10 nginx-rs

Si necesito tener una replica en cada uno de los nodos de Kubernetes, ¿qué objeto se adaptaría mejor? (No es necesario adjuntar el objeto)
Se adaptaría en vez de usar replicaset usar deployment
