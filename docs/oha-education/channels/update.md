# Actualización del Perfil de Usuario

> Este endpoint se encarga de actualizar el canal.

|           URL           |    Método     |   Tipo de Medio    | Autorización Requerida |
| :---------------------: | :-----------: | :----------------: | ---------------------- |
| `/channels/{username}/` | `PUT`,`PATCH` | `application/json` | `Si`                   |

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro  | Tipo     | Descripción      |
| :--------- | :------- | :--------------- |
| `username` | `string` | Nombre de canal. |

## Cuerpo de la Petición

Los campos que se pueden actualizar son:

| Campo         | Tipo     | Requerido | Descripción                            |
| :------------ | :------- | :-------: | :------------------------------------- |
| `username`    | `string` |   `Si`    | Nombre de usuario que tendrá el canal. |
| `name`        | `string` |   `Si`    | Nombre del canal.                      |
| `description` | `string` |   `No`    | Descripción del canal.                 |
| `instagram`   | `string` |   `No`    | URL de instagram.                      |
| `facebook`    | `string` |   `No`    | URL de facebook.                       |
| `twitter`     | `string` |   `No`    | URL de twitter.                        |
| `tiktok`      | `string` |   `No`    | URL de tiktok.                         |

Cabe destacar que según el tipo de petición (`PUT` o `PATCH`) se requeriran enviar todos los datos o solo el que se desea actualizar. Si se usa el método `PUT` deberás enviar todos los datos (incluso los que no deseas actualizar, en este caso envia el mismo valor que tenía anteriormente) y si se usa el método `PATCH` solo se deberá enviar los datos que se desean actualizar.

**Ejemplo de Dato**

```json
{
	"email": "user@example.com",
	"first_name": "John",
	"last_name": "Travolta",
	"birth_date": "2002-02-01",
	"phone": "+1234567891",
	"country": "Venezuela",
	"gender": "male",
	"username": "johntravolta"
}
```

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "User Profile Update Successful",
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

### Respuesta Fallida
