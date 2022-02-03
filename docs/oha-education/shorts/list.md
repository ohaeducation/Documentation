# Listar Videos

> Este endpoint se encarga de listar los shorts de Oha Education.

|    URL     | Método |   Tipo de Medio    | Autorización Requerida |
| :--------: | :----: | :----------------: | ---------------------- |
| `/shorts/` | `GET`  | `application/json` | `Opcional`             |

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro | Tipo     | Descripción                                    |
| :-------- | :------- | :--------------------------------------------- |
| `channel` | `string` | Permite filtrar shorts en función de un canal. |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "Videos Listed Successful",
	"data": [
		{
			"title": "My First Video",
			"key": "Ob4KU5D7m4zrvrNiCNg6uQ",
			"description": "This is my first video, enjoy it!",
			"thumbnail": "https://res.cloudinary.com/ds1cdo5lx/image/upload/v1/media/ohaeducation/channels/videos/thumbnails/dioscondios_hleczb",
			"video": "https://res.cloudinary.com/ds1cdo5lx/video/upload/v1/media/ohaeducation/channels/videos/video_zp7etq",
			"created_at": "2022-01-31T16:50:14.096794-04:00",
			"updated_at": "2022-01-31T16:50:14.096818-04:00"
		}
	]
}
```

**Datos de Respuesta**

Este endpoint retorna una lista de canales de contenido. Los datos de cada canal son:

| Campo               | Tipo      | Descripción              |
| :------------------ | :-------- | :----------------------- |
| `title`             | `string`  | Nombre del video.        |
| `key`               | `string`  | Clave del video.         |
| `description`       | `string`  | Descripción del video.   |
| `thumbnail`         | `string`  | Imagen del video.        |
| `video`             | `string`  | Video del video.         |
| `created_at`        | `string`  | Fecha de creación.       |
| `updated_at`        | `string`  | Fecha de actualización.  |
