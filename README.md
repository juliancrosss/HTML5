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
	
##Mas sobre Article y Section

*puede un article contener un section?*

*Puede que no sea claro si un < section > puede contener uno o varios < article > elementos, o si un < article > puede contener uno o varios < section > elementos.*

* El elemento < article > fue diseñado para partes independientes de un documento que con el tiempo sería sindicado en RSS.

* < section > elementos se utilizan para cortar una parte lógica en subpartes.

* Un < article > se puede cortar en diferentes < section > elementos!

		<article id="id1">
   			<section id="id1part1">
     				<h2>Introduction</h2>
   			</section>
   			<section id="id1part2">
     				<h2>My travel to Colombia</h2>
   			</section>
   			<section id="id1part3">
     				<h2>Return to France</h2>
   			</section>
		</article>
		
* Un < section > se puede cortar en diferentes < articles > elementos, también!

		<section id="id1">
   			<article id="id1part1">
     				<h2>Introduction</h2>
   			</article>
   			<article id="id1part2">
     				<h2>My travel to Colombia</h2>
   			</article>
   			<article id="id1part3">
     				<h2>Return to France</h2>
   			</article>
		</section>
		
##podemos poner un nav en un article?

*Sí se puede, en caso de que le gustaría proponer algunos enlaces de navegación con cada entrada del blog, por ejemplo:*

		<article>
   			<header>
     				<h1>Blog post title</h1>
       				<p>Author: Michel</p>
   			</header>
   			<nav>
       				<ul>
           				<li><a href="...">Next post</a></li>
           				<li><a href="...">Previous post</a></li>
           				<li><a href="...">Contact author</a></li>
       				</ul>
   			</nav>
   			<p>Content...</p>
   			<footer>
     				<p>Posted by Michel, the <time datetime="2012-02-02">February 2, 
     				   2012</time> </p>
   			</footer>
		</article>
		
*En ese caso, el < nav > elemento propone enlaces de navegación a la siguiente o la anterior entrada del blog, así como un enlace para ponerse en contacto con el autor del blog.*

*También tenga en cuenta que hemos utilizado en este ejemplo, un < footer > en la entrada del blog.*

##¿Que pasara con el elemento < div > ? ¿Sigue siendo útil?

*Los nuevos elementos se han diseñado principalmente para estructurar mejor el código de las páginas HTML, como los generados por el blog o software CMS, sin embargo no hay que olvidar que añaden nueva semántica y se tomarán en cuenta a través de:*

* Los navegadores de forma nativa o extensiones de navegadores, es decir,  generar automáticamente una tabla de contenidos,      una vista de esquema del documento, para la aplicación de reglas CSS por defecto para estos elementos, etc. Véase por ejemplo   el estructurador HTML5 (extensión de Chrome)
* "https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo".
* rastreadores Web

*Puedemos usar < div > elementos en todos los casos en los elementos estructurales o propuestas que no se ajustan a sus necesidades: para la definición de algunos contenidos que deben ser de estilo.*

##Titulos y elementos estructurales

*Ahora vamos a presentar algunas mejores prácticas para comenzar a utilizar < section >, < article >, < nav >, < aside >, en particular, en relación con el uso de encabezados (H1, H2, H3, H4, H5 y H6).*

*use <H1> ... <H6> para los títulos, como lo han hecho CON HTML4 ...*

*Desde el principio, HTML ha tenido elementos: <h1> .. <h6>. Estos elementos se utilizan para mostrar los titulos con diferentes tamaños por defecto, cuando no se utiliza CSS.*

##Uso de los titulos y las nuevas seccionamiento elementos (section, article, aside, nav)

*Definicion de titulos contenido y seleccionamiento contenido*

*El < section >, < article >, < nav > y < aside > elementos se denominan "elementos de seccionamiento". Ellos cortan un documento en rodajas que llamamos "secciones".*







