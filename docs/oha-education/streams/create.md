# Creación de un Stream

Este método permite a un Canal crear un stream. Existen dos tipos de streams:

1. **Streams Programados**: Permite a los Canales crear un stream programado. Este aparecerá en el calendario de eventos del canal. Los usuarios pueden suscribirse a este stream para recibir notificaciones cuando el stream se empieza a emitir. (**Nota:** Los streams programados pueden comenzar antes, ya depende del creador de contenido).

2. **Streams No Programados**: Crea un stream instantáneo, solo se puede crear uno a la vez. Este stream no aparecerá en el calendario de eventos del canal. (**Nota:** Los streams no programados pueden pasar a ser un stream programado siempre y cuando el stream no haya iniciado).

|     URL     | Método |   Tipo de Medio    | Autorización Requerida | Permiso  |
| :---------: | :----: | :----------------: | ---------------------- | :------: |
| `/streams/` | `POST` | `application/json` | `SI`                   | `IsSelf` |

## Cuerpo de la Petición

|        Campo        |   Tipo   | Requerido | Descripción                                                                                                                        |
| :-----------------: | :------: | :-------: | :--------------------------------------------------------------------------------------------------------------------------------- |
| `channel_username`  | `string` |   `Si`    | Nombre de usuario del canal. **Nota**: Esta petición tiene el permiso `IsSelf` lo que significa que deberás ser el dueño del canal |
|       `title`       | `string` |   `No`    | Título del stream.                                                                                                                 |
|    `description`    | `string` |   `No`    | Descripción del stream.                                                                                                            |
| `program_date_time` | `string` |   `No`    | Fecha y Hora programada para el stream.                                                                                            |

**Ejemplo de Dato**

```json
{
	"channel_username": "jo4hntravolta",
	"title": "Stream de Jo4hntravolta",
	"description": "En este stream te enseñaremos a crear un stream",
	"program_date_time": "2022-03-01T02:34:42.769Z"
}
```

## Respuesta

### Respuesta Exitosa

**Código de Estado** : `201 Created`

**Content example**

```json
{
	"uid": "string",
	"key": "string",
	"title": "string",
	"description": "string",
	"status": "pending",
	"thumbnail": "string",
	"video": "string",
	"websocket": "string",
	"record": true,
	"record_status": "start",
	"is_programed": true,
	"program_date_time": "2022-03-01T02:34:42.792Z",
	"created_at": "2022-03-01T02:34:42.792Z",
	"started_at": "2022-03-01T02:34:42.792Z",
	"ended_at": "2022-03-01T02:34:42.792Z"
}
```

Explicación de cada uno de los campos retornados:

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

Para saber como iniciar un stream ver [Inicio de Stream](./start.md)