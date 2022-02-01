# Actualización del Perfil de Usuario

>Este endpoint se encarga de actualizar el perfil del usuario.

| URL | Método | Tipo de Medio |  Autorización Requerida |
| :---: | :---: | :---: | --- |
| `/users/{username}/` | `PUT`,`PATCH` | `application/json` | `Si` | 

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro | Tipo | Descripción |
|:----------|:-----|:------------|
| `username` | `string` | Nombre de usuario. |

### Cuerpo de la Petición

Los campos que se pueden actualizar son:

| Campo | Tipo | Requerido |Descripción |
|:------|:-----|:---------:|:------------|
| `email` | `string` | `Si`|  Email del usuario. |
| `username` | `string` | `Si`|  Nombre de usuario. |
| `first_name` | `string` | `Si`| Nombre del usuario. |
| `last_name` | `string` | `Si`| Apellido del usuario. |
| `phone` | `string` | `Si`| Teléfono del usuario. Formatos aceptados `+1 (123)-458624` o `+12345679`|
| `birth_date` | `string` | `Si`| Fecha de nacimiento del usuario. Formato de envio `YYYY/mm/dd`|
| `country` | `string` | `Si`| País del usuario. |
| `gender` | `string` | `Si` | Género del usuario. Los valores aceptados son `male`, `female` o `other`|

Cabe destacar que según el tipo de petición (`PUT` o `PATCH`) se requeriran enviar todos los datos o solo el que se desea actualizar. Si se usa el método `PUT` deberás enviar todos los datos (incluso los que no deseas actualizar, en este caso envia el mismo valor que tenía anteriormente) y si se usa el método `PATCH` solo se deberá enviar los datos que se desean actualizar.

**Ejemplo de Dato**

```json
{
  "username": "jo4hntravolta",
  "name": "Jo4hntravolta",
  "description": "Jo4hntravolta",
  "instagram": "https://www.instagram.com/jo4hntravolta/",
  "facebook": "https://www.facebook.com/jo4hntravolta/",
  "twitter": "https://twitter.com/jo4hntravolta",
  "tiktok": "https://www.tiktok.com/jo4hntravolta/"
}
```

## Respuesta
### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
  "status": true,
  "message": "Channel Profile Update Successful",
  "data": {
    "username": "johntravolta",
    "email": "johntravolta@gmail.com",
    "photo": null,
    "first_name": "John",
    "last_name": "Travolta",
    "gender": "male",
    "country": "string",
    "phone": "+58-123-456789",
    "birth_date": "2001-01-26"
  }
}
```

### Respuesta Fallida