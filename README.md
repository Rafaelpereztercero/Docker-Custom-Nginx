# Docker-Custom-Nginx

## INSTALACION
### 1.0
  En primer lugar, nos dirigiremos al docker hub donde filtraremos en el buscador "nginx" y realizamos un pull a nuestra máquina
  
  ##### 1.1
  En primer lugar, nos dirigimos a la siguiente web : <a href="https://hub.docker.com/">DOCKER HUB</a>
  
  ![image](https://user-images.githubusercontent.com/91564342/168928949-8cd15b64-8a07-4386-ad44-e02fd68213b5.png)

  ##### 1.2
  Filtramos por nginx : <a href="https://hub.docker.com/_/nginx">NGINX DOCKER HUB</a>
  
  ![image](https://user-images.githubusercontent.com/91564342/168929122-c4afadd4-5ce3-443a-8aa5-db2c14fa68ed.png)

  
  ##### 1.3
  Realizamos el pull
  <code>sudo docker pull nginx</code>
  ![image](https://user-images.githubusercontent.com/91564342/168929175-53e674fc-114f-4927-b4a2-d125334538dd.png)

### 2.0
Levantamos el contenedor que alberga el servicio nginx ejecutando el siguiente comando
<code>docker run --rm -d -p 8080:80 --name web nginx</code>

![image](https://user-images.githubusercontent.com/91564342/168929488-a5ca7d82-f700-44f9-981c-5b457630392e.png)

#### 2.1
Como podemos observar, si nos dirigimos al localhots:8080, nos encontraremos con la página default de nginx

![image](https://user-images.githubusercontent.com/91564342/168929679-7fd0a77f-b1ce-48d7-b6f7-8d4c8afe75ec.png)

#### 2.2
A continuación, "matamos" al contenedor
<code>sudo docker stop web</code>

![image](https://user-images.githubusercontent.com/91564342/168929721-4110b41d-e95d-4a5a-80b2-d206c35c95b4.png)

### 3.0
Procedemos a crear el index.html que emplearemos en nuestro nginx

![image](https://user-images.githubusercontent.com/91564342/168929878-82a143c2-e26d-40db-bed3-5a3a064b03a2.png)
![image](https://user-images.githubusercontent.com/91564342/168929893-21a49986-e28a-4c46-8ad2-c6b38442ba3a.png)

#### 3.1
Después, mapeamos el volumen para poder pasar ese index.html e implementarlo
<code>docker run --rm -d -p 8080:80 --name web -v ~/Home:/usr/share/nginx/html nginx
</code>

![image](https://user-images.githubusercontent.com/91564342/168930005-68937eda-bcdc-44e2-baa9-c94290f81efd.png)

#### 3.2
Como podemos observar, ahora si accedemos a nuestro hostlocal:8080, nos encontraremos con el index.html definido previamente

![image](https://user-images.githubusercontent.com/91564342/168930122-c10865aa-8a89-47c3-ae82-ebdc10946de2.png)


