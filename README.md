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
	
##El "type" atributo es opcional

*Con el atributo rel = " stylesheet ", ya no es necesario indicar type = " text / css " (a partir de la especificación: "el tipo por defecto para los recursos dados  es por la palabra clave de stylesheet de text / css ".)*

	<link href="file.css" rel="stylesheet"/>

*en lugar de:*

	<link href="file.css" rel="stylesheet" type="text/css"/>
	
*con javascript*

	<script src="script.js"></script>
	
*en lugar de:*

	<script type="text/javascript" src="script.js"></script>
	
##Mas fexible sintaxis restricciones

* Gracias a HTML5, puede omitir las comillas (no siempre, pero la mayoría de las veces) o usar mayúsculas, minúsculas o una combinación de los dos.

* Muchos de los elementos ya no necesitan una etiqueta de cierre: </ li> </ dt>, </ dd> </ tr> </ th>, </ td> </ thead>, </ tfoot>, </ tbody> </ option>, </ optgroup>, </ p> (en la mayoría de los casos), </ head>, </ body> y </ html>. Los navegadores más antiguos suelen añadir el cierre de las etiquetas de forma automática en tiempo de render. Se recomienda, sin embargo, el cierre de las etiquetas que, naturalmente, se cerraron: los que delimitan una zona en particular en el documento.

* Los valores de atributo sólo tienen que ser encomillado si contienen espacios o algunos caracteres no alfanuméricos, en lugar de escribir < link rel = href "stylesheet" = "style.css" >, podríamos haber utilizado < link rel=stylesheet href=style.css >  en lugar. Sin embargo, para la compatibilidad con navegadores antiguos, puede que sea más prudente utilizar todavía las comillas ... 

##Nuevos elementos agregados a HTML5


* header 		
	
		Introducción de "elementos de seccionamiento": un artículo, una sección, la entrada del documento 
		(header page). Normalmente, el encabezado de un sitio web que aparece en la parte superior de cada 
		página, o un header de un largo < article > o de un < section > largo

* footer

		Contiene el pie de página de un sitio, un largo < article >, o un largo < section >
	
* nav

		Sección que contiene los principales enlaces de navegación (en el documento o en otras páginas).
	
* article

		Contenido Independiente, que se puede extraer individualmente del documento y sindicados (RSS o equivalente)
		sin penalizar su comprensión. Normalmente, una entrada de blog.
	
* section
	
		Sección genérica utilizada para agrupar diferentes artículos para diferentes propósitos o temas, o para definir
		las diferentes secciones de un solo artículo. Generalmente se utiliza con un header.

* time

		Se utiliza para marcar los tiempos y las fechas.
	
* aside

		Sección cuyo contenido no es necesariamente directamente relacionado con el contenido principal que lo rodea,
		pero puede proporcionar información adicional.
	
* figure y figcaption

		Se utiliza para encapsular una figura como un único elemento, y contiene una descripcion para la figura, 
		respectivamente.
	
* main

		El principal elemento representa el contenido principal del cuerpo de un documento o aplicación. El área de 
		contenido principal consta de contenido que se relaciona directamente con o se amplía sobre el tema central de
		un documento o la funcionalidad central de una aplicación. No puede haber un solo < main > en un documento.
	

