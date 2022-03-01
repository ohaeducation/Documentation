# Obtención de un Stream

> Este endpoint se encarga de retornar la información referente a un stream.

|        URL        | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------: | :----: | :----------------: | ---------------------- |
| `/streams/{key}/` | `GET`  | `application/json` | `Opcional`             |

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro | Tipo     | Descripción                     |
| :-------- | :------- | :------------------------------ |
| `key`     | `string` | Identificador único del Stream. |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
    "uid": "HsYSnsjKcngGAKh-oZaAjg",
    "key": "aQL0xb74XB5toZZj6pHD8Q",
    "title": "string",
    "description": "string",
    "status": "finished",
    "thumbnail": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/thumbnail.png",
    "video": {
        "index": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index.m3u8",
        "720p2628kbs": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index_720p2628kbs/index.m3u8",
        "480p1128kbs": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index_480p1128kbs/index.m3u8",
        "360p878kbs": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index_360p878kbs/index.m3u8",
        "240p528kbs": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index_240p528kbs/index.m3u8",
        "240p264kbs": "https://api.oha.education/live/HsYSnsjKcngGAKh-oZaAjg/index_240p264kbs/index.m3u8"
    },
    "websocket": "chat": "wss://api.oha.education/ws/streams/HsYSnsjKcngGAKh-oZaAjg/",
    "record": true,
    "record_status": "done",
    "is_programed": false,
    "program_date_time": null,
    "created_at": "2022-02-28T14:43:37.844942-04:00",
    "started_at": "2022-02-28T14:43:51.560945-04:00",
    "ended_at": "2022-02-28T14:44:59.999110-04:00"
}
```

**Datos de Respuesta**

Este endpoint retorna un Stream de un Canal. Los datos de cada stream varia según si está en vivo o no.

| Campo               |   Tipo   | Descripción                                                         |
| :------------------ | :------: | :------------------------------------------------------------------ |
| `uid`               | `string` | Identificador único del Stream                                      |
| `key`               | `string` | Clave de acceso al Stream (Solo visible para el autor del canal)    |
| `title`             | `string` | Título del Stream                                                   |
| `description`       | `string` | Descripción del Stream                                              |
| `status`            | `string` | Estado del Stream                                                   |
| `thumbnail`         | `string` | URL de la miniatura del Stream                                      |
| `video`             | `string` | URL del video del Stream                                            |
| `websocket`         | `string` | URL del websocket del Stream (solo visible si está haciendo stream) |
| `record`            |  `bool`  | Indica si el Stream está grabando                                   |
| `record_status`     | `string` | Estado de la grabación del Stream                                   |
| `is_programed`      |  `bool`  | Indica si el Stream está programado                                 |
| `program_date_time` | `string` | Fecha y hora de programación del Stream                             |
| `created_at`        | `string` | Fecha de creación del Stream                                        |
| `started_at`        | `string` | Fecha de inicio del Stream                                          |
| `ended_at`          | `string` | Fecha de finalización del Stream                                    |

### Respuesta Fallida
