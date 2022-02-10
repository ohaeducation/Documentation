# Documentación de la API de Oha Education

La API de Oha Education es una colección de endpoints de la API que permite interactuar en la plataforma de Educación de Oha.

## Hacer llamadas a la API

En las llamadas a la API de REST, incluya la URL del servicio de la API para el entorno:

- Sandbox: `http://18.232.77.138/`.
- Live: `https://auth.oha.education/`.

En las llamadas a la API de WebSocket, incluya la URL del servicio de la API para el entorno:

- Sandbox: `ws://18.232.77.138/ws/`.
- Live: `wss://auth.oha.education/ws/`.

## Lista de Endpoints API REST

### Autenticación y Registro

- [Token](users/login.md) : `POST /token/`

### Canal de contenido

- [Listar](channels/list.md) : `GET /channels/`
- [Obtener un canal](channels/details.md) : `GET /channels/{username}/`
- [Crear un canal](channels/create.md) : `POST /channels/`
- [Actualizar un canal](channels/update.md) : `PUT /channels/{username}/`

### Perfil de Stream (Cofiguracion de Stream)

- [Obtener Perfil de Stream](channels/streams/details.md) : `GET /channels/{username}/stream/`

#### Suscripción a un canal

- [Listar suscripciones](channels/subscribers/list.md) : `GET /channels/{username}/subscribers/`
- [Suscribirse a un canal](channels/subscribers/create.md) : `POST /channels/{username}/subscribers/`
- [Desuscribirse a un canal](channels/subscribers/delete.md) : `DELETE /channels/{username}/subscribers/`

### Videos

- [Listar](videos/list.md) : `GET /videos/`
- [Obtener un video](videos/details.md) : `GET /videos/{key}/`

### Shorts

- [Listar](shorts/list.md) : `GET /shorts/`
- [Obtener un short](shorts/details.md) : `GET /shorts/{key}/`

### Streams

- [Listar](streams/list.md) : `GET /streams/`
- [Obtener un stream](streams/details.md) : `GET /streams/{key}/`


## Lista de Endpoints API WebSocket

### Streams
- [Chat](streams/chat.md) : `/streams/{key}/`