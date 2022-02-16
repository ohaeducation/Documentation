# Token

Este endpoint se encarga del inicio de sesión, la creación de usuario y la activación de usuario.

|    URL    | Método |   Tipo de Medio    | Autorización Requerida |
| :-------: | :----: | :----------------: | ---------------------- |
| `/token/` | `POST` | `application/json` | `No`                   |

<!-- ### Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro | Tipo | Descripción |
|:----------|:-----|:------------| -->

## Parámetros Opcionales

En la Url de la petición, se pueden incluir los siguientes parámetros opcionales:

| Parametro  | Tipo      | Descripción                                 |
| :--------- | :-------- | :------------------------------------------ |
| `create`   | `boolean` | Indica si se quiere crear un usuario nuevo. |
| `activate` | `boolean` | Indica si se quiere activar un usuario.     |

## Creación de Usuario

> Este Endpoint se encarga de crear al usuario de Oha. El parámetro `create` debe ser `true`.

|          URL          | Método |   Tipo de Medio    | Autorización Requerida |
| :-------------------: | :----: | :----------------: | ---------------------- |
| `/token/?create=true` | `POST` | `application/json` | `No`                   |

### Cuerpo de la Petición

| Campo        | Tipo     | Requerido | Descripción                                                              |
| :----------- | :------- | :-------: | :----------------------------------------------------------------------- |
| `email`      | `string` |   `Si`    | Email del usuario.                                                       |
| `username`   | `string` |   `Si`    | Nombre de usuario.                                                       |
| `password`   | `string` |   `Si`    | Contraseña del usuario.                                                  |
| `first_name` | `string` |   `Si`    | Nombre del usuario.                                                      |
| `last_name`  | `string` |   `Si`    | Apellido del usuario.                                                    |
| `phone`      | `string` |   `Si`    | Teléfono del usuario. Formatos aceptados `+1 (123)-458624` o `+12345679` |
| `birth_date` | `string` |   `Si`    | Fecha de nacimiento del usuario. Formato de envio `YYYY/mm/dd`           |
| `country`    | `string` |   `Si`    | País del usuario.                                                        |
| `gender`     | `string` |   `Si`    | Género del usuario. Los valores aceptados son `male`, `female` o `other` |
| `question_1` | `int`    |   `No`    | Id de la pregunta 1                                                      |
| `answer_1`   | `string` |   `No`    | Respuesta a la pregunta 1                                                |
| `question_2` | `int`    |   `No`    | Id de la pregunta 2                                                      |
| `answer_2`   | `string` |   `No`    | Respuesta a la pregunta 2                                                |

**Ejemplo de Dato**

```json
{
	"password": "secretpassword",
	"email": "user@example.com",
	"first_name": "John",
	"last_name": "Travolta",
	"birth_date": "2002-02-01",
	"phone": "+1234567891",
	"country": "Venezuela",
	"gender": "male",
	"username": "johntravolta",
	"question_1": 1,
	"answer_1": "Madonna",
	"question_2": 4,
	"answer_2": "Blue"
}
```

### Respuesta

#### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "User created"
}
```

#### Respuesta Fallida

**Condición** : Si el nombre de usuario o contraseña no son válidos.

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
	"non_field_errors": ["Unable to login with provided credentials."]
}
```

## Activación de Usuario

> Este Endpoint se encarga de activar al usuario de Oha. El parámetro `active` debe ser `true`. Cuando se da de alta a un usuario, este recibe un correo electrónico con un código de 6 dígitos para activar su cuenta.

|          URL          | Método |   Tipo de Medio    | Autorización Requerida |
| :-------------------: | :----: | :----------------: | ---------------------- |
| `/token/?active=true` | `POST` | `application/json` | `No`                   |

### Cuerpo de la Petición

| Campo             | Tipo     | Requerido | Descripción                             |
| :---------------- | :------- | :-------: | :-------------------------------------- |
| `email`           | `string` |   `Si`    | Email del usuario.                      |
| `activation_code` | `string` |   `Si`    | Código de Activación enviado por correo |

**Ejemplo de Dato**

```json
{
	"email": "user@example.com",
	"activation_code": "123456"
}
```

### Respuesta

#### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "Login Successful",
	"data": {
		"username": "jo4hntravolta",
		"token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImpvNGhudHJhdm9sdGEiLCJpYXQiOjE2NDM3MjcxNzMsImV4cCI6MTY0MzczMDc3MywianRpIjoiNDdmZmMwZTEtMTdhNS00MWYzLWI1NDgtOGE3Yjc2ZmE2N2YzIiwib3JpZ19pYXQiOjE2NDM3MjcxNzN9.pTLrZFQNJ209IS2uQ3b-tdnLC4eIfDelFt7u9Sq1Ll8",
		"issued_at": 1643727173
	}
}
```

**Datos de Respuesta**

| Campo       | Tipo     | Descripción                  |
| :---------- | :------- | :--------------------------- |
| `username`  | `string` | Nombre de usuario.           |
| `token`     | `string` | Token de autenticación.      |
| `issued_at` | `int`    | Fecha de creación del token. |

#### Respuesta Fallida

**Condición** : Si el nombre de usuario o contraseña no son válidos.

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
	"non_field_errors": ["Unable to login with provided credentials."]
}
```

## Inicio de Sesión

> Este Endpoint se encarga de iniciar sesión al usuario de Oha.

|    URL    | Método |   Tipo de Medio    | Autorización Requerida |
| :-------: | :----: | :----------------: | ---------------------- |
| `/token/` | `POST` | `application/json` | `No`                   |

### Cuerpo de la Petición

| Campo      | Tipo     | Requerido | Descripción                                                                                               |
| :--------- | :------- | :-------: | :-------------------------------------------------------------------------------------------------------- |
| `username` | `string` |   `Si`    | En esta campo se puede enviar el nombre de usuario, correo o número de télefono para el inicio de sesión. |
| `password` | `string` |   `Si`    | Contraseña del usuario.                                                                                   |

**Ejemplo de Dato**

```json
{
	"username": "jo4hntravolta",
	"password": "secretpassword"
}
```

### Respuesta

#### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "Login Successful",
	"data": {
		"username": "jo4hntravolta",
		"token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImpvNGhudHJhdm9sdGEiLCJpYXQiOjE2NDM3MjcxNzMsImV4cCI6MTY0MzczMDc3MywianRpIjoiNDdmZmMwZTEtMTdhNS00MWYzLWI1NDgtOGE3Yjc2ZmE2N2YzIiwib3JpZ19pYXQiOjE2NDM3MjcxNzN9.pTLrZFQNJ209IS2uQ3b-tdnLC4eIfDelFt7u9Sq1Ll8",
		"issued_at": 1643727173
	}
}
```

**Datos de Respuesta**

| Campo       | Tipo     | Descripción                  |
| :---------- | :------- | :--------------------------- |
| `username`  | `string` | Nombre de usuario.           |
| `token`     | `string` | Token de autenticación.      |
| `issued_at` | `int`    | Fecha de creación del token. |

#### Respuesta Fallida

**Condición** : Si el nombre de usuario o contraseña no son válidos.

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
	"non_field_errors": ["Unable to login with provided credentials."]
}
```

## Recuperación de Contraseña

> Este Endpoint se encarga de la Recuperación de Contraseña del usuario de Oha.

|         URL          | Método |   Tipo de Medio    | Autorización Requerida |
| :------------------: | :----: | :----------------: | ---------------------- |
| `/token/?reset=true` | `POST` | `application/json` | `No`                   |

### Cuerpo de la Petición

| Campo      | Tipo     | Requerido | Descripción                                                             |
| :--------- | :------- | :-------: | :---------------------------------------------------------------------- |
| `username` | `string` |   `Si`    | En esta campo se puede enviar el nombre de usuario o correo electrónico |

**Ejemplo de Dato**

```json
{
	"username": "jo4hntravolta"
}
```

### Respuesta

#### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
	"status": true,
	"message": "Password reset link sent to your email"
}
```

see [Proceso de Recuperación de Contraseña](reset-password.md)
