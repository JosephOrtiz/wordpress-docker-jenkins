\# Despliegue Automatizado de WordPress con Docker, Git y Jenkins



Proyecto que implementa un ambiente de WordPress + MySQL usando Docker Compose,

versionado con Git y desplegado automáticamente mediante un pipeline de Jenkins.



\## Arquitectura

\- \*\*WordPress\*\*: contenedor basado en la imagen `wordpress:latest`, expuesto en el puerto 8080.

\- \*\*MySQL 8.0\*\*: contenedor basado en la imagen `mysql:8.0`, expuesto en el puerto 3306.

\- \*\*Red personalizada\*\*: `wp-net`, tipo bridge, conecta ambos contenedores.

\- \*\*Volúmenes\*\*: `wp\_data` (persistencia de WordPress) y `db\_data` (persistencia de MySQL).



\## Requisitos

\- Docker Desktop (con WSL2 en Windows)

\- Docker Compose

\- Git

\- Jenkins



\## Uso local

1\. Clonar el repositorio

2\. Ejecutar `docker compose up -d`

3\. Acceder a http://localhost:8080



\## Pipeline de Jenkins

El `Jenkinsfile` incluido automatiza:

1\. Checkout del repositorio

2\. `docker compose down`

3\. `docker compose up -d`

4\. Verificación con `docker ps`



## Autor
Josseph Ortiz - Universidad Politécnica Internacional
Práctica: Organización de Archivos
