Crea un objeto de tipo service para exponer la aplicación del ejercicio anterior de las siguientes formas:

• Exponiendo el servicio hacia el exterior (crea service1.yaml)
kubectl apply -f service1.yaml

• De forma interna, sin acceso desde el exterior (crea service2.yaml)
kubectl apply -f service2.yaml

• Abriendo un puerto especifico de la VM (crea service3.yaml)
kubectl apply -f service3.yaml

comprobamos lo creado con el comando
kubectl get services

kubectl proxy --port=8080