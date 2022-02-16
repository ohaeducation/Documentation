# Proceso de Recuperación de contraseña

## Pasos

1. Utilizar el endpoint [`POST /token/?reset=true`](login.md#recuperación-de-contraseña) para recuperar la contraseña.

Se envia un correo electrónico con un enlace para recuperar la contraseña.

2. En el correo electrónico se encuentra un enlace que redirecciona a la página de recuperación de contraseña. (TODO: enlace base a recuperación de contraseña es Frontend)

3. Frotend obtiene el token y verifica con el endpoint [`GET /reset/?token={token}`](reset.md#validacion-de-token) para verificar que el token es válido.

4. Si el Token es válido, se muestra un formulario para actualizar la contraseña.

5. Enviar el formulario con la nueva contraseña. al endpoint [`POST /reset/?token={token}`](reset.md#cambio-de-contraseña) (este endpoint es el mismo)
