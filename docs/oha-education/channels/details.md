# Obtención del Perfil

> Este endpoint se encarga de retornar el perfil de un canal.

|           URL           | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------------: | :----: | :----------------: | ---------------------- |
| `/channels/{username}/` | `GET`  | `application/json` | `Opcional`             |

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
	"status": true,
	"message": "Channel Retrieve Successful",
	"data": {
		"username": "jo4hntravolta",
		"name": "Canal de Jo4hntravolta",
		"description": "Esta es la descripción de mi Canal. Cheers",
		"author": "jo4hntravolta",
		"photo": "http://54.162.99.197:8000/static/users/images/default.jpg",
		"instagram": null,
		"facebook": null,
		"twitter": null,
		"tiktok": null,
		"subscriptions_count": 0,
		"i_subscribed": false,
		"created_at": "2022-01-31T16:46:01.857739-04:00",
		"updated_at": "2022-01-31T16:46:01.857767-04:00"
	}
}
```

**Datos de Respuesta**

Este endpoint retorna una lista de canales de contenido. Los datos de cada canal son:

| Campo                 | Tipo      | Descripción                        |
| :-------------------- | :-------- | :--------------------------------- |
| `username`            | `string`  | Nombre de usuario del canal.       |
| `name`                | `string`  | Nombre del canal.                  |
| `description`         | `string`  | Descripción del canal.             |
| `author`              | `string`  | Nombre de usuario del autor.       |
| `photo`               | `string`  | URL de la imagen del canal.        |
| `instagram`           | `string`  | URL de Instagram del canal.        |
| `facebook`            | `string`  | URL de Facebook del canal.         |
| `twitter`             | `string`  | URL de Twitter del canal.          |
| `tiktok`              | `string`  | URL de TikTok del canal.           |
| `subscriptions_count` | `integer` | Número de suscripciones del canal. |
| `created_at`          | `string`  | Fecha de creación del canal.       |
| `updated_at`          | `string`  | Fecha de actualización del canal.  |

si el usuario inició sesión, este retorna un campo adicional:

| Campo          | Tipo      | Descripción                                  |
| :------------- | :-------- | :------------------------------------------- |
| `i_subscribed` | `boolean` | Indica si el usuario está suscrito al canal. |

### Respuesta Fallida
