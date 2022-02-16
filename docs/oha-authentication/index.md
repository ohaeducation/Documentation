# Documentación de la API de Oha Authentication

La API REST de autenticación de Oha es una colección de endpoints de la API REST que permiten que las aplicaciones accedan a los datos de las cuentas de Oha.

## Hacer llamadas a la API

En las llamadas a la API de REST, incluya la URL del servicio de la API para el entorno:

- Sandbox: `http://54.162.99.197:8001/`.
- Live:

## Lista de Endpoints

### Autenticación y Registro

- [Login](auth/login.md#inicio-de-sesión) : `POST /token/`
- [Listar las Preguntas de Seguridad](users/questions.md) : `GET /questions/`
- [Registro](auth/login.md#creación-de-usuario) : `POST /token/?create=true`
- [Activación](auth/login.md#activación-de-usuario) : `POST /token/?activate=true`

### Recuperación de Contraseña (y desbloquedo) [Proceso](auth/reset-password.md)
- [Recuperación de contraseña](auth/login.md#recuperación-de-contraseña) : `POST /token/?reset=true`
- [Cambio de contraseña](auth/reset.md) : `POST /reset/?token={token}`

### Usuarios

- [Obtener Usuario](users/profile-retrieve.md): `GET /users/{username}/`
- [Actualizar Usuario](users/profile-update.md): `PUT /users/{username}/`
- [Actualizar foto de Perfil](users/profile-photo-update.md): `PUT /users/{username}/photo/`
