# newEndpoints

En base a los contenedores de nginx y postgres de prácticas pasadas:

Correr ambos contenedores con docker start <name || id>


Queremos saber la ip del postgres, así que en el contenedor docker de postgres corremos


```Batchfile
kiovahn@Kiovahns--MacBook-Air ~ % docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' 7089cfa002e0
```


Lo cual nos arroja la sig. IP


```
172.17.0.3
```


Ahora entramos al docker de nginx


```Batchfile
kiovahn@Kiovahns--MacBook-Air ~ % docker exec -it d832bc1a087a bash
```
```
root@d832bc1a087a:/# cd home/fire
root@d832bc1a087a:/home/fire# touch postgrepython.py
root@d832bc1a087a:/home/fire# vim postgrepython.py 
```


Agregamos el sig. código, la base para este codigo fue obtenido de https://arc.net/l/quote/ggttuqzq


<img width="754" alt="image" src="https://github.com/user-attachments/assets/a846ee52-da4d-46b5-b949-cfb487c33846">


Editamos el archivo default.conf


![image](https://github.com/user-attachments/assets/8cf9ede8-44b5-45e7-a012-41304980302d)


Reiniciamos con 
```Batchfile
nginx -s reload
```


En el browser, vamos a http://localhost:8080/usuario


<img width="970" alt="image" src="https://github.com/user-attachments/assets/9639b52e-0931-4976-b787-d198e5b86bbd">


Y luego a algún usuario


<img width="970" alt="image" src="https://github.com/user-attachments/assets/10a53d46-4b05-473f-8036-07f499e79b0a">



