# Suscripción a un canal

> Este endpoint se encarga de suscribirse a un canal.

|                 URL                 | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------------------------: | :----: | :----------------: | ---------------------- |
| `/channels/{username}/subscribers/` | `POST` | `application/json` | `Si`                   |

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro  | Tipo     | Descripción      |
| :--------- | :------- | :--------------- |
| `username` | `string` | Nombre de canal. |

## Cuerpo de la Petición

No se requiere ningún dato en el cuerpo de la petición.

**Ejemplo de Dato**

```json
{}
```

## Respuesta

### Respuesta Exitosa

**Code** : `201 Created`

**Content example**

```json
{
	"status": true,
	"message": "Channel Subscribe Successful",
	"data": {
		"username": "jo4hntravolta",
		"type": "free",
		"created_at": "2022-02-01T15:47:50.898196-04:00",
		"updated_at": "2022-02-01T15:47:50.898219-04:00"
	}
}
```

**Datos de Respuesta**

| Campo        | Tipo     | Descripción                               |
| :----------- | :------- | :---------------------------------------- |
| `username`   | `string` | Nombre de usuario del suscriptor.         |
| `type`       | `string` | Tipo de suscriptor.                       |
| `created_at` | `string` | Fecha de creación de la suscripción.      |
| `updated_at` | `string` | Fecha de actualización de la suscripción. |
