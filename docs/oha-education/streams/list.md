# Listar Streams

> Este endpoint se encarga de listar los Streams de Oha Education.

|     URL     | Método |   Tipo de Medio    | Autorización Requerida |
| :---------: | :----: | :----------------: | ---------------------- |
| `/streams/` | `GET`  | `application/json` | `Opcional`             |

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro    | Tipo      | Descripción                                                                                                                                                       |
| :----------- | :-------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `channel`    | `string`  | Permite filtrar streams en función de un canal.                                                                                                                   |
| `search`     | `string`  | Permite buscar un Stream en función del título, descripción, nombre de usuario de canal o uid del stream                                                          |
| `limit`      | `integer` | Permite limitar la cantidad de streams que se devuelven.                                                                                                          |
| `offset`     | `integer` | Permite paginar los streams.                                                                                                                                      |
| `status`     | `string`  | Permite filtrar streams en función de su estado. Los estados disponibles son `pending`, `live`, `finished` o `cancel`                                             |
| `status__in` | `string`  | Permite filtrar streams en función de varios estados. El formato es `status_1,status_2,...`. Los estados disponibles son `pending`, `live`, `finished` o `cancel` |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"count": 1,
	"next": null,
	"previous": null,
	"results": [
		{
			"uid": "HsYSnsjKcngGAKh-oZaAjg",
			"title": "string",
			"description": "string",
			"status": "finished",
			"thumbnail": "https://res.cloudinary.com/ohaeducation/image/upload/v1646079421/channels/streams/thumbnails/aQL0xb74XB5toZZj6pHD8Q.png",
			"video": "https://res.cloudinary.com/ohaeducation/video/upload/v1646079407/channels/streams/aQL0xb74XB5toZZj6pHD8Q.mp4",
			"record": true,
			"record_status": "done",
			"is_programed": false,
			"program_date_time": null,
			"created_at": "2022-02-28T14:43:37.844942-04:00",
			"started_at": "2022-02-28T14:43:51.560945-04:00",
			"ended_at": "2022-02-28T14:44:59.999110-04:00"
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

| Campo               |   Tipo   | Descripción                                                      |
| :------------------ | :------: | :--------------------------------------------------------------- |
| `uid`               | `string` | Identificador único del Stream                                   |
| `key`               | `string` | Clave de acceso al Stream (Solo visible para el autor del canal) |
| `title`             | `string` | Título del Stream                                                |
| `description`       | `string` | Descripción del Stream                                           |
| `status`            | `string` | Estado del Stream                                                |
| `thumbnail`         | `string` | URL de la miniatura del Stream                                   |
| `video`             | `string` | URL del video del Stream                                         |
| `websocket`         | `string` | URL del websocket del Stream                                     |
| `record`            |  `bool`  | Indica si el Stream está grabando                                |
| `record_status`     | `string` | Estado de la grabación del Stream                                |
| `is_programed`      |  `bool`  | Indica si el Stream está programado                              |
| `program_date_time` | `string` | Fecha y hora de programación del Stream                          |
| `created_at`        | `string` | Fecha de creación del Stream                                     |
| `started_at`        | `string` | Fecha de inicio del Stream                                       |
| `ended_at`          | `string` | Fecha de finalización del Stream                                 |

En caso de no estar haciendo Stream:

| Campo               |   Tipo   | Descripción                                                      |
| :------------------ | :------: | :--------------------------------------------------------------- |
| `uid`               | `string` | Identificador único del Stream                                   |
| `key`               | `string` | Clave de acceso al Stream (Solo visible para el autor del canal) |
| `title`             | `string` | Título del Stream                                                |
| `description`       | `string` | Descripción del Stream                                           |
| `status`            | `string` | Estado del Stream                                                |
| `thumbnail`         | `string` | URL de la miniatura del Stream                                   |
| `video`             | `string` | URL del video del Stream                                         |
| `record`            |  `bool`  | Indica si el Stream está grabando                                |
| `record_status`     | `string` | Estado de la grabación del Stream                                |
| `is_programed`      |  `bool`  | Indica si el Stream está programado                              |
| `program_date_time` | `string` | Fecha y hora de programación del Stream                          |
| `created_at`        | `string` | Fecha de creación del Stream                                     |
| `started_at`        | `string` | Fecha de inicio del Stream                                       |
| `ended_at`          | `string` | Fecha de finalización del Stream                                 |
