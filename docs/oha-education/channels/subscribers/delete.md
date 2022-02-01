# Cancelar Suscripción a un canal

> Este endpoint se encarga de desuscribirse a un canal.

|                 URL                 |  Método  |   Tipo de Medio    | Autorización Requerida |
| :---------------------------------: | :------: | :----------------: | ---------------------- |
| `/channels/{username}/subscribers/` | `DELETE` | `application/json` | `Si`                   |

## Parámetros

En la Url de la petición, se deben incluir los siguientes parámetros:

| Parametro  | Tipo     | Descripción      |
| :--------- | :------- | :--------------- |
| `username` | `string` | Nombre de canal. |

## Respuesta

### Respuesta Exitosa

**Code** : `204 No Content`
