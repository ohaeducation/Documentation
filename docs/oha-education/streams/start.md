# Inicio de Stream

El inicio del Stream es una acción que se realiza en el momento en que el Stream está listo para ser visto. En la plataforma de Oha, se crean los streams pero se necesita de una aplicación que soporte el Protocolo `RTMP` para poder hacer stream. Esta aplicación debe estar configurada para que el Stream pueda ser visto.

## Aplicaciones para hacer Streaming

1. OBS
2. Streamlabs
3. FFmpeg
5. VLC

## Configuración de las Aplicaciones

Para hacer un streaming, indiferentemente de la aplicación que se use, se deben tener dos datos:

1. __URL para hacer streaming__: Este es el URL que se debe enviar a la aplicación para que se pueda hacer streaming. la url es la siguiente: `rmtp://api.oha.education/streams/`

2. __Key del Stream__: Al crear un Stream programado o No programado, este retorna varios datos, dentro de los datos se encuentra el __Key__ del Stream. Este solo se muestra al autor del canal asociado al stream, es una clave secreta, **NO SE DEBE COMPARTIR**.

Una vez esos dos datos, basta con ingresarlos en la aplicación de confianza para poder iniciar el stream, este se comunicará con el backend, cambiando el estado del streaming a `live` y al hacerle una petición a la url de streaming, se retornará los atributos video y thumbnail del stream con las urls de los videos y thumbnails respectivamente.

