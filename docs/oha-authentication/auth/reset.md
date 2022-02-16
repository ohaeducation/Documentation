# Cambio de Contraseña

> Este endpoint se encarga del proceso de cambio de contraseña del usuario de Oha.

Se requiere un token el cual fue enviado por correo.

## Validación de Token

|           URL           | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------------: | :----: | :----------------: | ---------------------- |
| `/reset/?token={token}` | `GET`  | `application/json` | `NO`                   |

### Parámetros Obligatorios

En la Url de la petición, se debe incluir el siguiente parámetro:

| Parametro | Tipo     | Descripción                            |
| :-------- | :------- | :------------------------------------- |
| `token`   | `string` | Token generado para cambiar contraseña |

### Respuesta

```json
{
	"status": true,
	"message": "Valid Token",
	"data": {
		"username": "jonathan",
		"email": "carlojon@gmail.com"
	}
}
```

## Cambio de Contraseña

|           URL           | Método |   Tipo de Medio    | Autorización Requerida |
| :---------------------: | :----: | :----------------: | ---------------------- |
| `/reset/?token={token}` | `POST` | `application/json` | `NO`                   |

### Parámetros Obligatorios

En la Url de la petición, se debe incluir el siguiente parámetro:

| Parametro | Tipo     | Descripción                            |
| :-------- | :------- | :------------------------------------- |
| `token`   | `string` | Token generado para cambiar contraseña |

### Cuerpo de la Petición

La información que se debe enviar es:

| Campo          | Tipo     | Requerido | Descripción      |
| :------------- | :------- | :-------: | :--------------- |
| `new_password` | `string` |   `Si`    | Nueva contraseña |

### Respuesta

```json
{
	"status": true,
	"message": "Password changed successfully",
	"data": {
		"username": "jonathan",
		"email": "carlojon@gmail.com"
	}
}
```
