
#  Docker

###  ¿Qué es docker?

Docker es un manejador de contenedores que ayuda a facilitar compartir proyectos y ejecutarlos en distintos ambientes. 

### ¿Por qué usar Docker?

Usar Docker asegura que nuestro código funcionará cunado se comparte un proyecto sin necesidad de preocuparse de versiones de paquetes y dependencias. 

###  Imágenes y contenedores

Una **imagen** es una especie de cascarón o plantilla no modificable. Un ejemplo de imagen es  `ubuntu` 

Un **contenedor** es creado a partir de una *imagen*. Los contenedores es aquello con lo que se interactúa. Pueden ser ejecutados, iniciados, detenidos, movidos, borrados, etc. Cada contenedor es un ambiente aislado. 


## Comandos

Para ver qué imágenes hay en tu computadora:
```
docker images
```

Descargar una imagen. Se usa el comando pull seguido del nombre de la imagen. 
```
docker pull rocker/tidyverse
```

Crear un contenedor. Se crea a partir de la imagen que se especifica con el comando run. Si la imagen no existe se descarga en automático.
```
docker run hello-world
```

Para ver que contenedores están activos
```
docker ps -a
```

Detener un contenedor. Los símbolos <> no se escriben
```
docker container stop <container id>
```

Eliminar un contenedor
```
docker container rm <container id>
```

Eliminar una imagen
```
docker image rm <image id>
```

---

### Ejemplo 

```
sudo docker run -d -p 8787:8787 -v $(pwd):/home/rstudio -e PASSWORD=xxxxxxxx -e ROOT=TRUE rocker/tidyverse
```
El flag -p vincula un puerto con el contenedor. El flag -v vincula un volumen con el contenedor, es decir, asocia una carpeta entre nuestro equipo local y el ambiente creado. La variable $pwd asigna la ruta actual pero si se desea se puede asignar cualquier otra ruta como /home 

Si se ejecutan varios contenedores simultaneamente no es recomendable usar la variable $pwd para vincular el volumen. En tal caso es conveniente especificar la ruta.


Se requiere agregar su usuario al grupo docker para eliminar la molestia de teclear `sudo` antes de todos los comandos.

---

**WARNING:** Cada que se ejecuta esa un docker run se crea un contenedor nuevo. Tener cuidado para no llenarse de contenedores pues consumen recursos del equipo.

Para probar que se está ejecutando RStudio ir al puerto local 8787: http://localhost:8787

En este caso particular para el contenedor de esta imagen 
- user: rstudio
- pass: xxxxxxx


**Nota** Se pueden agregar más banderas al momento de crear un contenedor conforme a las necesidades de cada usuario.

Esto es una muy breve introducción. Se pueden personalizar imágenes con un `Dockerfile` según se requiera.


**Tips Extras**

Detener todos los contenedores (para eliminar los contenedores, primero debemos detenerlos)
```
sudo docker container stop $(sudo docker container ls -aq)
```

Remover todos los contenedores
```
sudo docker container rm $(sudo docker container ls -aq)
```

Remover todas las imágenes
```
sudo docker image rm $(sudo docker images -q)
```





