# Chat de Un Stream

> Este endpoint se encarga de conectarse al chat de un stream. Enviar y recibir mensajes.

|        URL        |   Método    |   Tipo de Medio    | Autorización Requerida |
| :---------------: | :---------: | :----------------: | ---------------------- |
| `/streams/{key}/` | `WEBSOCKET` | `application/json` | `Opcional`             |

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro | Tipo     | Descripción             |
| :-------- | :------- | :---------------------- |
| `token`   | `string` | Permite Iniciar Sesión. |

## Uso

Se necesita el utilizar via una libreria de WebSockets.
Ejemplo:

```js
const url = "wss://api.oha.education/ws/streams/qB-TJaGTR_kjWE4w388KEQ/"; // URL del Stream
const ws = new WebSocket(url);

ws.onopen = () => {
	// Cuando se conecta al chat
	console.log("Connected to server");
};

ws.onmessage = (event) => {
	// Cuando recibe un mensaje
	console.log(event.data);
};

ws.onclose = () => {
	// Cuando se desconecta del chat
	console.log("Disconnected from server");
};
```

### Tipos de Mensajes

#### Mensaje de Chat

Este es el mensaje más usual que se envía al chat. Es el que usan los usuarios para enviar/reciber mensajes. dentro del chat del stream.

```json
{
	"type": "chat",
	"data": {
		"user": "user",
		"message": "message"
	}
}
```

#### Mensaje de Autenticación

Este es el mensaje que retornará el servidor al usuario luego de conectarse al websocket indicando si el consumidor está autenticado como usuario o no. Por supuesto cualquiera puede conectarse pero solo los usuarios autenticados pueden enviar mensajes. Al no estar autenticado, solo podrá recibir mensajes.

```json
{
	"type": "auth",
	"data": {
		"authenticated": true
	}
}
```

#### Mensaje de Error

Mensaje que se envía al consumidor cuando se produce un error.

```json
{
	"type": "error",
	"data": {
		"error_code": "error_code",
		"message": "message"
	}
}
```
