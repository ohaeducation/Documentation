# Documentación de la API de Oha Education

La API REST de Oha Education es una colección de endpoints de la API REST que permite interactuar en la plataforma de Educación de Oha.

## Hacer llamadas a la API

En las llamadas a la API de REST, incluya la URL del servicio de la API para el entorno:

- Sandbox: `http://54.162.99.197:8000/`.
- Live:

## Lista de Endpoints

### Autenticación y Registro

- [Token](users/login.md) : `POST /token/`

### Canal de contenido
- [Listar](channels/list.md) : `GET /channels/`
- [Obtener un canal](channels/details.md) : `GET /channels/{username}/`
- [Crear un canal](channels/create.md) : `POST /channels/`
- [Actualizar un canal](channels/update.md) : `PUT /channels/{username}/`

### Videos
- [Listar](videos/list.md) : `GET /videos/`
- [Obtener un video](videos/details.md) : `GET /videos/{key}/`
