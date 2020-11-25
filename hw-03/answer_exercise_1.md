- Crear un deployment con su servicio
kubectl apply -f deployment.yaml

--Verificamos la url del servicio
minikube service nginx-service --url --namespace=kube-exercises

a)
- Para habilitar NGINX Ingress controller se usa el siguiente comando
minikube addons enable ingress

- Luego se tiene un archivo yaml creado
kubectl apply -f ingress.yaml

Se debe agregar la siguiente línea al siguiente archivo c:\windows\system32\drivers\etc\hosts
192.168.146.178 eduardoguadalupe.developerlasalle.com

Para probar se usa la siguiente url:
http://eduardoguadalupe.student.lasalle.com

b)

kubectl apply -f ingress-secret.yaml

Para probar se usa la siguiente url:
https://eduardoguadalupe.student.lasalle.com