# Despliegue automatizado de WordPress con Docker y Jenkins

## Descripción

Este proyecto implementa un ambiente completo de WordPress con MySQL utilizando Docker Compose.

La solución incluye una red personalizada, volúmenes persistentes, variables de entorno, política de reinicio automático y un pipeline de Jenkins para automatizar el despliegue desde GitHub.

## Tecnologías utilizadas

- Docker
- Docker Compose
- WordPress
- MySQL
- Git
- GitHub
- Jenkins

## Estructura del proyecto

- `docker-compose.yml`: configura los servicios de WordPress y MySQL.
- `.env`: contiene las variables de entorno del proyecto.
- `.env.example`: plantilla de las variables necesarias.
- `Jenkinsfile`: contiene el pipeline de despliegue automatizado.
- `README.md`: documentación del proyecto.
- `.gitignore`: evita subir archivos sensibles al repositorio.

## Servicios

### WordPress

- Imagen: `wordpress:latest`
- Nombre del contenedor: `wordpress-app`
- Puerto: `8080:80`
- Política de reinicio: `always`

### MySQL

- Imagen: `mysql:8.0`
- Nombre del contenedor: `wordpress-db`
- Puerto interno: `3306`
- Política de reinicio: `always`

## Red personalizada

Los contenedores de WordPress y MySQL utilizan la red:

```text
wordpress-jenkins_wp-net