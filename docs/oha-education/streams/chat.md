# Chat de Un Stream

> Este endpoint se encarga de conectarse al chat de un stream. Enviar y recibir mensajes.

|        URL        |   Método    |   Tipo de Medio    | Autorización Requerida |
| :---------------: | :---------: | :----------------: | ---------------------- |
| `/streams/{key}/` | `WEBSOCKET` | `application/json` | `Opcional`             |

## Uso

Se necesita el utilizar via una libreria de WebSockets.
Ejemplo: Usando [ws](https://www.npmjs.com/package/ws)

```js
const { WebSocket } = require("ws");

const ws = new WebSocket("wss://api.oha.education/ws/streams/uFXHjP-sUukXUh8gw-S3yw/", [], {
	headers: {
		"Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImNhcmxvc29zdW5hMTEiLCJpYXQiOjE2NDQ1Mjg1NTYsImV4cCI6MTY0NDUzMjE1NiwianRpIjoiNGE5MzhkMmYtYjVhOS00ZWQyLWEzMTEtZmE5YTNhZDNlZTQzIiwidXNlcl9pZCI6MSwib3JpZ19pYXQiOjE2NDQ1Mjg1NTZ9.e5T867YIyC8JtO79Dy63OHyc78LcF_a0eHN9Xtd0ohc",
	},
});

ws.onopen = function (e) {
	console.log("Successfully connected to the WebSocket.");
    send_message("chat", "hola");
};

ws.onclose = function (e) {
	console.log("Successfully disconnected");
};

ws.onerror = function (err) {
    console.log("WebSocket encountered an error: " + err.message);
    console.log("Closing the socket.");
    ws.close();
}

ws.onmessage = function (e) {
	const data = JSON.parse(e.data);
	console.log(data);
};

const send_message = (type, message) => {
	ws.send(
		JSON.stringify({
			type,
			"data": {
				message,
			},
		})
	);
};

```

### Tipos de mensajes que se pueden enviar

#### Mensaje de Chat

Se utiliza para enviar mensajes de chat.

```json
{
    "type": "chat",
    "data": {
        "message": "hola",
    }
}
```

#### Mensaje de Chat

Se utiliza para enviar mensajes de chat.

```json
{
    "type": "auth",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImNhcmxvc29zdW5hMTEiLCJpYXQiOjE2NDUyOTgwMzAsImV4cCI6MTY0NTMwMTYzMCwianRpIjoiOTUzNDYyOTgtODE3Ni00ZDlkLWFkNGUtNWIxM2IyMDM5YjI2IiwidXNlcl9pZCI6NCwib3JpZ19pYXQiOjE2NDUyOTgwMzB9.fZxK7Rxmmc3HwimvsitwFyA_RR8v2XDv0gAxMKh1-rM",
    }
}
```

### Tipos de Mensajes Recibidos

#### Mensaje de Chat

Este es el mensaje más usual que se recibe. Es el que usan los usuarios para enviar/reciber mensajes. dentro del chat del stream.

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
