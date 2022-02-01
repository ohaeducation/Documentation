# Obtención del Perfil

>Este endpoint se encarga de retornar el perfil del usuario.

| URL | Método | Tipo de Medio |  Autorización Requerida |
| :---: | :---: | :---: | --- |
| `/users/{username}/` | `GET` | `application/json` | `Si` | 

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro | Tipo | Descripción |
|:----------|:-----|:------------|
| `username` | `string` | Nombre de usuario. |

## Respuesta
### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
  "status": true,
  "message": "User Profile Retrieve Successful",
  "data": {
    "username": "jo4hntravolta",
    "email": "johntravolta@yopmail.com",
    "photo": "http://54.162.99.197:8001/static/users/images/default.jpg",
    "first_name": "John",
    "last_name": "Travolta",
    "gender": "male",
    "country": "venezuela",
    "phone": "+58-123-456789",
    "birth_date": "2001-01-26"
  }
}
```

### Respuesta Fallida