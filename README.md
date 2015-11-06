# HTML5

##Mayor Simplicidad

*'Keep it simple'*

Se han hecho cambios a los elementos particulares en HTML5 por lo que es más fácil de utilizar,incluyendo los siguientes:

* la nueva definición del tipo de documento;
* el hecho de que el atributo "type" de elementos como < link > o < script > ahora son opcionales;
* las restricciones de sintaxis que se han relajado;
* los nuevos elementos estructurales que se han añadido, etc.

*Ejemplo minimal de HTML5*

    <!DOCTYPE html>
    <html lang="es">
    <head>
	    <meta charset="utf-8">
	    <title>Titulo del Sitio</title>
	    <link rel="stylesheet" href="style.css">
	    <script src="script.js"></script>	
    </head>
    <body>
	    <!-- El resto del contenido -->
    </body>
    </html>
    
##Una simple manera de encoding del documento

*Una palabra sobre el < charset meta = "UTF-8" > es una buena práctica para declarar el conjunto de caracteres del documento para proteger contra un riesgo de seguridad grave.*

##No mas complicadas definiciones DOCTYPE

*El "Doctype", a menudo llamado DTD "Document Type Declaration"(Documento Declaración Type), es utilizado por herramientas como validadores HTML (es decir, el validador del W3C), y especifica las reglas utilizadas por un archivo HTML o una página XHTML. Estas normas están contenidas en documentos especiales llamadas "Document Type Definitions" (también abreviado como DTD), escritos en un lenguaje que puede parecer un poco bárbara a los humanos (que están destinados a ser leídos por  el software), y organizadas por el W3C.*

*DTD no son utilizados por los navegadores web actuales para validar la estructura de una página HTML, ya que "leen" el código sin necesidad de utilizar el DTD de descifrarlo, utilizando sólo "reglas" que figuran en su propio "motor de HTML", pero sigue siendo preferible indicar el tipo de documento como los navegadores modernos tienen varios motores de renderizado que se elige en función del tipo de documento.*

*Con HTML5, sólo hay una manera de indicar el tipo de documento, y es tan simple que no hay razón para olvidarse de él:*

	<!doctype html>
