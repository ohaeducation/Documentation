# Creación de un canal

> Este endpoint permite crear un canal de contenido.
>
> Limitaciones:
>
> - solo puede haber un canal por usuario.
> - el nombre de usuario del canal debe ser único.

|     URL      | Método |   Tipo de Medio    | Autorización Requerida |
| :----------: | :----: | :----------------: | ---------------------- |
| `/channels/` | `POST` | `application/json` | `Si`                   |

## Cuerpo de la Petición

| Campo      | Tipo     | Requerido | Descripción        |
| :--------- | :------- | :-------: | :----------------- |
| `username` | `string` |   `Si`    | Nombre de usuario que tendrá el canal. |
| `name`     | `string` |   `Si`    | Nombre del canal.  |
| `description` | `string` |   `No`    | Descripción del canal.  |
| `instagram` | `string` |   `No`    | URL de instagram.  |
| `facebook` | `string` |   `No`    | URL de facebook.  |
| `twitter`  | `string` |   `No`    | URL de twitter.  |
| `tiktok`  | `string` |   `No`    | URL de tiktok.  |

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

**Code** : `201 Created`

**Content example**

```json
{
  "status": true,
  "message": "Channel Created Successful",
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