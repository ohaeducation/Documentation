# Listar Subscriptores de un canal

> Este endpoint se encarga de listar subscriptores de un canal.

|                 URL                 | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------------------------: | :----: | :----------------: | ---------------------- |
| `/channels/{username}/subscribers/` | `GET`  | `application/json` | `Opcional`             |

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
	"message": "Subscribers Listed Successful",
	"data": [
		{
			"username": "jo4hntravolta",
			"type": "free",
			"created_at": "2022-02-01T15:47:50.898196-04:00",
			"updated_at": "2022-02-01T15:47:50.898219-04:00"
		},
		{
			"username": "mateo",
			"type": "free",
			"created_at": "2022-02-01T15:45:01.279307-04:00",
			"updated_at": "2022-02-01T15:45:01.279332-04:00"
		}
	]
}
```

**Datos de Respuesta**

Este endpoint retorna una lista de subscriptores de un canal. Los datos de cada subscriptor son:

| Campo        | Tipo     | Descripción                                |
| :----------- | :------- | :----------------------------------------- |
| `username`   | `string` | Nombre de usuario del subscriptor.         |
| `type`       | `string` | Tipo de subscriptor.                       |
| `created_at` | `string` | Fecha de creación de la subscripción.      |
| `updated_at` | `string` | Fecha de actualización de la subscripción. |
