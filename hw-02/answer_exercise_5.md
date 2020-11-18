a. Existe una aplicación que está desplegada en el clúster

Se tiene una versión "1.0" creada en el archivo blue.yaml
kubectl apply -f blue.yaml

Se crea un servicio con la versión 1.0 para exponer el servicio
kubectl apply -f service.yaml

b. Antes de ofrecer el servicio a los usuarios, la compañía necesita realizar una serie de validaciones con la versión 2.0. Los usuarios siguen accediendo a la versión 1.0:
Se crea una versión "2.0" en el archivo green.yaml, ya con las modificaciones realizadas que podrían ser versión, mejoras, etc
kubectl apply -f green.yaml

Se crea un servicio , primero con la versión 1
kubectl apply -f service.yaml


Una vez que el equipo ha validado la aplicación, se realiza un switch del tráfico a la versión 2.0 sin impacto para los usuarios:
Se modifica el servicio, para que apunte a la versión 2
kubectl apply -f service.yaml

