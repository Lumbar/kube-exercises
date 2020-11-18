
Crear un objeto de tipo deployment con las especificaciones del ejercicio 1.
kubectl apply -f deplyoment.yaml

Despliega una nueva versión de tu nuevo servicio mediante la técnica “recreate”
Se modifica el archivo y se agrega el tag strategy
kubectl apply -f deployment-recreate.yaml

Despliega una nueva versión haciendo “rollout deployment”
kubectl rollout status deployment nginx-deployment

Realiza un rollback a la versión generada previamente
kubectl rollout undo deploy nginx-deployment --to-revision=1