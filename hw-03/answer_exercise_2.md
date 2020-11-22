- Se crea el statefulset con el siguiente comando
kubectl create -f mongodb-statefulset.yaml

- Luego se edita el statefulset agregando por ejemplo más réplicas
kubectl edit statefulset mongo

- Diferencias que existiría si el montaje se hubiera realizado con el objeto de ReplicaSet
StatefulSet se usa cuando se quiere persistir volumenes y se usa para garantizar que puedan mantener el estado en los reinicios de los componentes