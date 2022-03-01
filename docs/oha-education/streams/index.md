# Stream

### Tabla de Contenidos
- [Conceptos Básicos](#conceptos-basicos)
- [Flujo del Stream](#flujo-del-stream)
- [WebSocket](#websocket)

## Conceptos Básicos

### `Stream`

 > En informática , un stream es una secuencia de elementos de datos disponibles a lo largo del tiempo. Se puede pensar en un stream como elementos en una cinta transportadora que se procesan uno a la vez en lugar de en grandes lotes. - [Wikipedia](https://en.wikipedia.org/wiki/Stream_(computing))

### `Streaming`

 > Tecnología que permite ver y oír contenidos que se transmiten desde internet u otra red sin tener que descargar previamente los datos al dispositivo desde el que se visualiza y oye el archivo. - [Diccionario Sae](https://www.sae.edu/esp/es/diccionario-sae-streaming)

### `RTMP`

> Protocolo de comunicación que permite la transmisión de contenidos de audio y video en streaming. - [Wikipedia](https://en.wikipedia.org/wiki/Real-Time_Messaging_Protocol)

### `WebSocket`

> WebSocket es una tecnología que proporciona un canal de comunicación bidireccional y full-duplex sobre un único socket TCP. - [Wikipedia](https://es.wikipedia.org/wiki/WebSocket)


### `WebRTC`

> WebRTC (Web Real-Time Communication) es un proyecto libre y de código abierto que proporciona a los navegadores web y a las aplicaciones móviles comunicación en tiempo real (RTC) a través de interfaces de programación de aplicaciones (API). Permite que la comunicación de audio y vídeo funcione dentro de las páginas web al permitir la comunicación entre pares, eliminando la necesidad de instalar plugins o descargar aplicaciones nativas. - [Wikipedia](https://es.wikipedia.org/wiki/WebRTC)

## Flujo del Stream 

La Plataforma de Oha permite la transmisión de Streaming como Twitch o YouTube. A continuación se presenta una lista de los pasos que se deben seguir para crear un Stream en la Plataforma de Oha:

**Nota**: Este flujo es mediante el uso de peticiones API REST, no está contemplado el flujo del frontend.

1. Crear una cuenta en la Plataforma de Oha. [Crear Cuenta](../../oha-authentication/auth/login.md#creación-de-usuario)

2. Iniciar sesión en la Plataforma de Oha. [Iniciar sesión](../users/login.md)

3. Crear un Stream. [Crear Stream](./create.md)

4. Iniciar el Stream. [Iniciar Stream](./start.md)

Luego de iniciar el stream, existen diferentes opciones del streaming:

- Ver el Stream. [Ver Stream](./details.md)

- Pausar - Reanudar el Stream. [Pausar - Reanudar Stream](./pause.md)

- Detener el Stream. [Detener Stream](./stop.md)

## WebSocket

Cuando el stream está en vivo, la petición http al stream retorna un atributo llamado `websocket` que contiene la URL del WebSocket. Este websocket tiene multiples funciones:

- Enviar y recibir mensajes (chat). [Chat](./ws/chat.md)
- Recibir cantidad de usuarios conectados. [Usuarios Conectados](./ws/users.md)
- Recibir estado del Stream. [Estado del Stream](./ws/status.md)
- Recibir Preguntas de los usuarios. [Preguntas](./ws/questions.md)
- Iniciar llamada de voz. [Llamada de voz](./ws/voice.md)

El websocket es fundamental para el streaming puesto que permite obtener en tiempo real información del Stream.