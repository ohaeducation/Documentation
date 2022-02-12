# Listar Streams

> Este endpoint se encarga de listar los Streams de Oha Education.

|     URL     | Método |   Tipo de Medio    | Autorización Requerida |
| :---------: | :----: | :----------------: | ---------------------- |
| `/streams/` | `GET`  | `application/json` | `Opcional`             |

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro | Tipo      | Descripción                                                                                 |
| :-------- | :-------- | :------------------------------------------------------------------------------------------ |
| `channel` | `string`  | Permite filtrar streams en función de un canal.                                             |
| `live`    | `boolean` | Permite filtrar streams en función de si están en vivo o no.                                |
| `search`  | `string`  | Permite buscar un Stream en función de una palabra. Este hará match con el nombre del canal |
| `limit`   | `integer` | Permite limitar la cantidad de streams que se devuelven.                                    |
| `offset`  | `integer` | Permite paginar los streams.                                                                |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"count": 4,
	"next": null,
	"previous": null,
	"results": [
		{
			"key": "vX9aaiOppS623DS9UrMtxA",
			"thumbnail": "https://res.cloudinary.com/ds1cdo5lx/image/upload/v1644619583/channels/streams/thumbnails/NDE32uMhEJG7LLJcbVjO7w.png",
			"video": "https://res.cloudinary.com/ds1cdo5lx/video/upload/v1644619581/channels/streams/NDE32uMhEJG7LLJcbVjO7w.mp4",
			"author": "carlososuna11",
			"created_at": "2022-02-11T18:10:17.402437-04:00",
			"stopped_at": "2022-02-11T18:13:34.324270-04:00"
		},
		{
			"key": "2u18-bmXxthsLFJ2VQftsQ",
			"thumbnail": "https://res.cloudinary.com/ds1cdo5lx/image/upload/v1644617025/channels/streams/thumbnails/XB767nHcwPVCFGNJ5pJPSQ.png",
			"video": "https://res.cloudinary.com/ds1cdo5lx/video/upload/v1644617023/channels/streams/XB767nHcwPVCFGNJ5pJPSQ.mp4",
			"author": "carlososuna11",
			"created_at": "2022-02-11T17:41:02.513086-04:00",
			"stopped_at": "2022-02-11T17:46:14.394355-04:00"
		},
		{
			"key": "eE3UYo_y1Y3SpEI-uv9DFA",
			"thumbnail": "https://res.cloudinary.com/ds1cdo5lx/image/upload/v1644604066/channels/streams/thumbnails/eE3UYo_y1Y3SpEI-uv9DFA.png",
			"video": "https://res.cloudinary.com/ds1cdo5lx/video/upload/v1644604064/channels/streams/eE3UYo_y1Y3SpEI-uv9DFA.mp4",
			"author": "carlososuna11",
			"created_at": "2022-02-11T14:25:36.115515-04:00",
			"stopped_at": "2022-02-11T14:27:07.325758-04:00"
		},
		{
			"key": "EprLVq6XNQqovWmB3mPMtw",
			"thumbnail": "https://res.cloudinary.com/ds1cdo5lx/image/upload/v1644603133/channels/streams/thumbnails/EprLVq6XNQqovWmB3mPMtw.png",
			"video": "https://res.cloudinary.com/ds1cdo5lx/video/upload/v1644603131/channels/streams/EprLVq6XNQqovWmB3mPMtw.mp4",
			"author": "carlososuna11",
			"created_at": "2022-02-11T14:11:11.235100-04:00",
			"stopped_at": "2022-02-11T15:03:54.574801-04:00"
		}
	]
}
```

**Datos de Respuesta**

campos de respuesta del paginador

|   Campo    |   Tipo   |        Descripción         |
| :--------: | :------: | :------------------------: |
|  `count`   |  `int`   |    Número de resultados    |
|   `next`   | `string` | URL de la siguiente página |
| `previous` | `string` | URL de la página anterior  |
| `results`  |  `list`  |      Lista de Streams      |

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
