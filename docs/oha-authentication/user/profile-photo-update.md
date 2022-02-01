# Actualización de la Foto de Perfil

>Este endpoint se encarga de actualizar la foto del usuario.

| URL | Método | Tipo de Medio |  Autorización Requerida |
| :---: | :---: | :---: | --- |
| `/users/{username}/photo/` | `PUT`,`PATCH` | `multipart/form-data` | `Si` | 

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro | Tipo | Descripción |
|:----------|:-----|:------------|
| `username` | `string` | Nombre de usuario. |

### Cuerpo de la Petición

Los campos que se pueden actualizar son:

| Campo | Tipo | Requerido |Descripción |
|:------|:-----|:---------:|:------------|
| `phot` | `file` | `Si`|  Foto del usuario |

Cabe destacar que según el tipo de petición (`PUT` o `PATCH`) se requeriran enviar todos los datos o solo el que se desea actualizar. Si se usa el método `PUT` deberás enviar todos los datos (incluso los que no deseas actualizar, en este caso envia el mismo valor que tenía anteriormente) y si se usa el método `PATCH` solo se deberá enviar los datos que se desean actualizar.

## Respuesta
### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
{
  "status": true,
  "message": "Photo Update Susccesful",
  "data": {
    "photo": "https://s3.amazonaws.com/ohaus-dev/users/johntravolta/photo/photo.jpg"
  }
}
```

### Respuesta Fallida