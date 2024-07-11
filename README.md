# API de Envío de Correos

Esta API permite a los usuarios enviar correos electrónicos mediante una solicitud HTTP con el método POST. La API está diseñada para recibir datos en formato JSON y enviar un correo electrónico al webmaster.


## Cómo se realiza una solicitud

### Formato de la Solicitud
La solicitud debe ser de tipo POST y el cuerpo debe estar en formato JSON.

### Cuerpo de la Solicitud
```json

POST http://dominio/api/v1/endpoint-webservice/
Content-Type: "application/json"

{
  "name": "Nombre del remitente",
  "email": "Correo electrónico del remitente",
  "message": "Mensaje a enviar"
}
````
## Respuestas que se pueden recibir

### Respuesta exitosa
Cuando todos los datos están completos y son correctos la respuesta es exitosa y se muestra así:
````json
{
  "status": "success",
  "message": "Correo enviado correctamente."
}
````

### Respuesta inválida
Cuando los datos están incompletos o no son correctos devuelve esta respuesta: 
````json
{
  "status": "error",
  "message": "Datos inválidos."
}
````

### Respuesta de Error
Cuando hay un error de conexión con el servidor la respuesta que devuelve es la siguiente:
````json
{
  "status": "error",
  "message": "Error al enviar el correo."
}
````