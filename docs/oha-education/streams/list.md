# Listar Streams

> Este endpoint se encarga de listar los Streams de Oha Education.

|     URL     | Método |   Tipo de Medio    | Autorización Requerida |
| :---------: | :----: | :----------------: | ---------------------- |
| `/streams/` | `GET`  | `application/json` | `Opcional`             |

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro | Tipo     | Descripción                                                                                 |
| :-------- | :------- | :------------------------------------------------------------------------------------------ |
| `channel` | `string` | Permite filtrar shorts en función de un canal.                                              |
| `search`  | `string` | Permite buscar un Stream en función de una palabra. Este hará match con el nombre del canal |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
[
	{
		"key": "qB-TJaGTR_kjWE4w388KEQ",
		"thumbnail": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/thumbnail.png",
		"video": {
			"index": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index.m3u8",
			"720p2628kbs": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index_720p2628kbs/index.m3u8",
			"480p1128kbs": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index_480p1128kbs/index.m3u8",
			"360p878kbs": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index_360p878kbs/index.m3u8",
			"240p528kbs": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index_240p528kbs/index.m3u8",
			"240p264kbs": "https://api.oha.education/live/qB-TJaGTR_kjWE4w388KEQ/index_240p264kbs/index.m3u8"
		},
		"author": "carlososuna11",
		"chat": "wss://api.oha.education/ws/streams/qB-TJaGTR_kjWE4w388KEQ/",
		"created_at": "2022-02-10T13:06:17.754620-04:00",
		"stopped_at": null
	}
]
```

**Datos de Respuesta**

Este endpoint retorna una lista de Streams. Los datos de cada stream varia según si está en vivo o no.

Si está haciendo stream:

| Campo        |   Tipo   | Descripción                                                                                            |
| :----------- | :------: | :----------------------------------------------------------------------------------------------------- |
| `key`        | `string` | Identificador único del Stream.                                                                        |
| `thumbnail`  | `string` | URL de la miniatura del Stream.                                                                        |
| `video`      | `object` | Objeto que contiene los enlaces de los videos disponibles para el stream (Las diferentes resoluciones) |
| `author`     | `string` | Nombre del autor del Stream.                                                                           |
| `chat`       | `string` | URL del chat del Stream.                                                                               |
| `created_at` | `string` | Fecha de creación del Stream.                                                                          |
| `stopped_at` | `string` | Fecha de finalización del Stream.                                                                      |

Si no está en vivo (Luego del Stream)

| Campo        |   Tipo   | Descripción                       |
| :----------- | :------: | :-------------------------------- |
| `key`        | `string` | Identificador único del Stream.   |
| `thumbnail`  | `string` | URL de la miniatura del Stream.   |
| `video`      | `string` | URL del video del Stream          |
| `author`     | `string` | Nombre del autor del Stream.      |
| `created_at` | `string` | Fecha de creación del Stream.     |
| `stopped_at` | `string` | Fecha de finalización del Stream. |
