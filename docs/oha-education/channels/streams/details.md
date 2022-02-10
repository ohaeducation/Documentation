# Obtención del Perfil de Stream

> Este endpoint permite obtener el perfil de stream de tu canal.

|              URL              | Método |   Tipo de Medio    | Autorización Requerida | Permisos |
| :---------------------------: | :----: | :----------------: | ---------------------- | -------- |
| `/channels/{username}/stream` | `GET`  | `application/json` | `SI`                   | `IsSelf` |

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro  | Tipo     | Descripción      |
| :--------- | :------- | :--------------- |
| `username` | `string` | Nombre de canal. |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"rtmp_url": "rtmp://api.oha.education/stream/",
	"key": "oha_6ImNhcmxvc29zdW5hMTEiLCJpYXQiOj",
	"started_at": null
}
```

**Datos de Respuesta**

Este endpoint retorna una serie de datos relacionados con el perfil de stream del canal.

| Campo        | Tipo     | Descripción                                                                                                   |
| :----------- | :------- | :------------------------------------------------------------------------------------------------------------ |
| `rtmp_url`   | `string` | Servidor de Stream. Este valor se colocan en los programas para hacer streaming como OBS o ffmpeg             |
| `key`        | `string` | Clave de Retransmisión: Clave Única para perteneciente a un canal, permitirá validar le stream del canal      |
| `started_at` | `string` | Fecha de inicio del stream. Si este se encuentra en null, significa que el usuario no está haciendo streaming |

### Respuesta Fallida
