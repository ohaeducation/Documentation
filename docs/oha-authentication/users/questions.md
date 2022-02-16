# Obtención de la Lista de Preguntas de Seguridad Disponibles

> Este endpoint se encarga de retornar la lista de preguntas de seguridad disponibles.

|     URL      | Método |   Tipo de Medio    | Autorización Requerida |
| :----------: | :----: | :----------------: | ---------------------- |
| `/question/` | `GET`  | `application/json` | `NO`                   |

## Respuesta

### Respuesta Exitosa

**Code** : `200 OK`

**Content example**

```json
[
	{
		"id": 1,
		"question": "¿Cuál es el nombre de tu mamá?"
	},
	{
		"id": 2,
		"question": "¿Cómo se llama tu perro?"
	},
	{
		"id": 3,
		"question": "¿Cuál es tu postre favorito?"
	},
	{
		"id": 4,
		"question": "¿Cuál es tu color favorito?"
	}
]
```

**Datos de Respuesta**

| Campo      | Tipo     | Descripción                                                                         |
| :--------- | :------- | :---------------------------------------------------------------------------------- |
| `id`       | `int`    | Id de la pregunta, este es el que se colocará en los campos question_1 y question_2 |
| `question` | `string` | Pregunta                                                                            |
