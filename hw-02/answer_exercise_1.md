Se corre primero este comando
minikube start -p myminikube — vm-driver="hyperv" — hyperv-virtual-switch=myminikube 


Se usa el siguiente comando para crear un namespace
kubectl create namespace kube-exercises

Luego cambiamos el contexto
kubectl config set-context --current --namespace=kube-exercises

Se crea el archivo pod.yaml y se ejecuta el siguiente comando
kubectl create -f pod.yaml

Y verificamos los pods 
kubectl get pods

¿Cómo puedo obtener las últimas 10 líneas de la salida estándar (logs generados por la aplicación)?
kubectl logs -f --tail 10 nginx

¿Cómo podría obtener la IP interna del pod?
kubectl get pod nginx -o wide
también se puede hacer con el siguiente comando
kubectl describe pod nginx

¿Qué comando utilizarías para entrar dentro del pod?
kubectl exec -it --namespace="kube-exercises" nginx bash -c "nginx-server-ctr"

Necesitas visualizar el contenido que expone NGINX, ¿qué acciones debes llevar a cabo?
Primero ingreso al pod y ejecuto el siguiente comando
curl 172.17.0.6

Indica la calidad de servicio (QoS) establecida en el pod que acabas de crear. ¿Qué lo has mirado?
kubectl get pod nginx --output=yaml