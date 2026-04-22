# BIND MOUNT
En un bind mount mapeamos (montar) un directorio o archivo específico del sistema de archivos del host con una parte del sistema de ficheros del contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
ó
```
docker run -d --name <nombre contenedor> --mount type=bind,source=<ruta carpeta host>,target=<ruta carpeta contenedor> <imagen>
```
- destination, dst, target: La ruta donde se monta el archivo o directorio en el contenedor.
- source, src: El origen del montaje.
  
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](directorio.PNG)

### Crear un contenedor con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](volumen-host.PNG)
# COMPLETAR CON EL COMANDO

docker run -d --name nginx-bind -P -v "C:\nginx\html:/usr/share/nginx/html" nginx:alpine

### ¿Qué sucede al ingresar al servidor de nginx?

La ausencia de la página inicial de Nginx se debe a que el directorio original dentro del contenedor fue sustituido por uno proveniente del host mediante un bind mount. Al encontrarse vacía la carpeta html, el servidor no dispone de archivos para renderizar, por lo que la página no se muestra e incluso puede producirse un fallo.

### ¿Qué pasa con el archivo index.html del contenedor?

El *index.html* que venía dentro del contenedor deja de intervenir, debido a que su ruta original fue sustituida por un directorio proveniente del host. Por ello, Nginx ya no toma en cuenta ese archivo interno y pasa a depender únicamente del contenido disponible en la nueva ubicación.


### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?

Se muestra el template web descargado, en este caso el que se muestra en la imagen: 

<img width="1365" height="730" alt="image" src="https://github.com/user-attachments/assets/2c7dab77-d43e-4a59-b7b5-14b1ffaac533" />


### Eliminar el contenedor
# COMPLETAR CON EL COMANDO

### ¿Qué sucede al crear nuevamente un contenedor montado al directorio definidos anteriormente?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA


