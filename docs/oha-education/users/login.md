# Token

Este endpoint se encarga del inicio de sesión, la creación de usuario y la activación de usuario.

|    URL    | Método |   Tipo de Medio    | Autorización Requerida |
| :-------: | :----: | :----------------: | ---------------------- |
| `/token/` | `POST` | `application/json` | `No`                   |

## Cuerpo de la Petición

| Campo                | Tipo     | Requerido | Descripción                           |
| :------------------- | :------- | :-------: | :------------------------------------ |
| `authorization_code` | `string` |   `Si`    | Token generado por ohaAuthentication. |

**Ejemplo de Dato**

```json
{
	"authorization_code": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImNhcmxvc29zdW5hMTEiLCJpYXQiOjE2NDM3MzA2ODAsImV4cCI6MTY0MzczNDI4MCwianRpIjoiYTkzY2JlYWQtZGIzNi00ZmQ3LTliMDAtZDkzYzQwZTQ0MTNhIiwib3JpZ19pYXQiOjE2NDM3MzA2ODB9.u7PTJNnmScebCuXvcuLvudAd8SCbOWPPgPDQKS6JXEI"
}
```

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
  "status": true,
  "message": "Login Successful",
  "data": {
    "username": "jo4hntravolta",
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6ImNhcmxvc29zdW5hMTEiLCJpYXQiOjE2NDM3MzA3MTcsImV4cCI6MTY0MzczNDMxNywianRpIjoiYjUwZDZhMGQtNDA5OS00NDBiLWIyNWMtYThmZWQwZTU1NmE2IiwidXNlcl9pZCI6MSwib3JpZ19pYXQiOjE2NDM3MzA3MTd9.jD63ZjTgxX6twpNekCBOOyTuWQ_N9xIDb0C45ipMuqc",
    "issued_at": 1643730717
  }
```

**Datos de Respuesta**

| Campo       | Tipo     | Descripción                  |
| :---------- | :------- | :--------------------------- |
| `username`  | `string` | Nombre de usuario.           |
| `token`     | `string` | Token de autenticación.      |
| `issued_at` | `int`    | Fecha de creación del token. |

### Respuesta Fallida

**Condición** : Si el nombre de usuario o contraseña no son válidos.

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
	"non_field_errors": ["Unable to login with provided credentials."]
}
```
