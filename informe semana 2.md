# Informe de Práctica: Creación y Personalización de Servidores Web con Nginx usando Docker

## 1. Título
**Tarea autónoma semana 1: Crear y personalizar dos servidores web con Nginx usando Docker**

## 2. Tiempo de duración
**120 minutos** .

## 3. Fundamentos

En esta práctica, aprenderé a desplegar dos servidores web utilizando Nginx en contenedores Docker. Nginx es un servidor web de alto rendimiento que también puede funcionar como proxy inverso y equilibrador de carga. Docker, por su parte, es una plataforma que permite crear, desplegar y ejecutar aplicaciones en contenedores, facilitando la gestión de entornos de desarrollo y producción.

El objetivo de esta práctica es personalizar el contenido de cada servidor web. En el primer contenedor, se mostrará información institucional, mientras que en el segundo contenedor se incluirá información personal del estudiante.

### Imagen relacionada con la teoría:
![Diagrama de contenedores Nginx](ngnix/nginx.jpg)  
*Figura 1-1. Diagrama de contenedores Nginx.*

## 4. Conocimientos previos

Para realizar esta práctica, necesito tener claros los siguientes temas:

- Comandos básicos en Linux.
- Instalación y manejo de Docker.
- Familiaridad con Nginx.
- Conocimiento básico sobre la manipulación de archivos en Linux.

## 5. Objetivos a alcanzar

- Desplegar dos servidores web utilizando Nginx en contenedores Docker.
- Personalizar el contenido de cada servidor editando el archivo `index.html`.
- Familiarizarme con el uso de comandos de Docker para gestionar contenedores.

## 6. Equipo necesario

- Un computador con sistema operativo **Linux** (también se puede realizar en Windows o Mac).
- Docker instalado y en funcionamiento.
- Acceso a una terminal de comandos.

## 7. Material de apoyo

- Documentación oficial de **Docker**: [https://docs.docker.com/](https://docs.docker.com/)
- Documentación oficial de **Nginx**: [https://nginx.org/en/docs/](https://nginx.org/en/docs/)

## 8. Procedimiento

A continuación, te explico los pasos que seguiré para crear y personalizar los servidores web en mi sistema Linux:

**Paso 1: Crear el primer contenedor Nginx**  
Ejecutaré el siguiente comando para crear el primer contenedor Nginx llamado `nginx1`, exponiendo el puerto 8089:

```bash
docker run -d --name nginx1 -p 8089:80 nginx
```
## Paso 2: Crear el segundo contenedor Nginx

Ahora, crearé el segundo contenedor Nginx llamado `nginx2`, exponiendo el puerto 8090:

```bash
docker run -d --name nginx2 -p 8090:80 nginx
```
## Paso 3: Copiar el archivo index.html desde el contenedor nginx1 al sistema anfitrión

Para personalizar el contenido, primero copiaré el archivo `index.html` desde el contenedor `nginx1` al sistema anfitrión:

```bash
docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html
```
## Paso 4: Editar el archivo index1.html

Usaré un editor de texto como `nano` o `vi` para editar el archivo `index1.html`, incluyendo información del instituto:

```bash
nano index1.html
```
## Paso 5: Copiar el archivo editado nuevamente al contenedor nginx1

Después de editar el archivo, lo copiaré de nuevo al contenedor `nginx1`:

```bash
docker cp index1.html nginx1:/usr/share/nginx/html/index.html
```
## Paso 6: Personalizar el segundo contenedor 

Si se desea, se puede repetir el proceso para el segundo contenedor `nginx2`, creando un archivo `index2.html` con información personal del estudiante.
```
## Resultados esperados

**Paso 7: Acceder a las aplicaciones en el navegador**  
Finalmente, abriré el navegador y escribiré las siguientes URLs para ver el contenido de cada servidor:

- Para el primer servidor (información institucional):  
  ```bash
  http://localhost:8089
```
```bash
-Para el segundo servidor (información personal):
bash
http://localhost:8090
```
