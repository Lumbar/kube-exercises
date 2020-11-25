- Se crea el statefulset con el siguiente comando
kubectl create -f mongodb-statefulset.yaml

- Vemos los pods creados
kubectl get pods
kubectl get pods -w

- Luego se edita el statefulset agregando por ejemplo más réplicas
kubectl edit statefulset mongo

- Y aumentamos el número de réplicas, luego vemos el resultado con el siguiente comando
kubectl get pods -w

- Luego desde una instancia de MongoDB que forme parte del cluster(a nivel de aplicación) esta nueva réplica
kubectl exec -it mongo-0 mongo

>>rs.initiate()
>>rs.secondaryOk()
>>rs.conf()

- Y se añade lo siguiente:
rs.initiate({_id: "rs0", version: 1, members: [
{_id: 3, host: "mongo-3.mongodb-svc.default.svc.cluster.local:27017" }
]});

- Y para verificar 
kubectl describe statefulset mongo


- Diferencias que existiría si el montaje se hubiera realizado con el objeto de ReplicaSet
StatefulSet se usa cuando se quiere persistir volumenes y se usa para garantizar que puedan mantener el estado en los reinicios de los componentes