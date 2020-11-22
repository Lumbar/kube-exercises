- Crear un deployment con su servicio
kubectl apply -f deployment.yaml

a)
- Para habilitar NGINX Ingress controller se usa el siguiente comando
minikube addons enable ingress

- Luego se tiene un archivo yaml creado
kubectl apply -f ingress.yaml

Para probar se usa la siguiente url:
http://eduardoguadalupe.student.lasalle.com

