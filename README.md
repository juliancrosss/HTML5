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


*La especificación HTML5 dice que "cada elemento de seccionamiento potencialmente tiene un encabezado y tiene también un esquema asociado". < h1 > ... < h6 > se denominan títulos, y definir el encabezado de una sección (ya sea marcada explícitamente el uso de seccionamiento elementos de contenido, o implícita por el contenido de encabezado en sí). Esto significa eso:*


	<body>
    		<h1>Title of my document</h1>
    		...
	</body>
	
define la cabecera de una sección implícitamente, mientras que:

	<body>
	 ...
   	<section>
      		<h1>Title of my section</h1>
      		...
   	</section>
	</body>
	
... Define el título de la sección explícita (su elemento padre < section >).

Utilice múltiples titulos de distinto rangos, con el seleccionador de contenido

*Posteriores titulos de rango igual o superior comienzan nuevas (implícitas) secciones, los titulos de menor rango comienzan implicaban que forman parte de la anterior. En ambos casos, el elemento representa el encabezamiento de la sección implícita.*

	<body>
 	<section>
    		<h1>This H1 is the heading of an explicit section</h1>
    		...
       		<h2>This H2 is a subheading, part of the same section
           	    (lower rank)</h2>
            	....
    		<h1>This H1 starts an implicit new section in the explicit section (equal or higher rank)</h1>
        	...
        	<h2>This is a H2 heading in the new section that has just started</h2>
            	...
 	</section>
	</body>

Las mejores prácticas al utilizar elementos de seccionamiento

MEJOR PRÁCTICA 1: SIEMPRE AÑADIR UN TITULO AL CONTENIDO EXPLÍCITO DE SELECIONAMIENTO

*Siempre es mejor - sobre todo por razones de accesibilidad - para incluir un encabezado (a < h1 >, < h2 > ... < h6 >) en cada elemento de seccionamiento (< section >, < article >, < nav >, < aside >) , sino también después de que el elemento < body > (llamado "root seccionar").*

*EJEMPLOS*

	<section>
    		<h1>Blog post of April 2015</h1>
    		...
	</section>
	
*o*

	<section>
   	<header>
      		<h1>Blog post of April 2015</h1>
      		<p>Posted by Michel Buffa...</p>
   	</header>
	...
	</section>
	
*Esto esta mal*

	<section>
   	<header>
      		<p class="article title">Blog post of April 2015</p>
      		<p>Posted by Michel Buffa...</p>
   	</header>
   	...
	</section>
	
*Tenga en cuenta que <body> es también un elemento de seccionamiento. Se llama una "raíz de seccionamiento", y que también es necesario un título.*

	<body>
    		<h1>Example Blog</h1>
    	<section>
       	<header>
          <h2>Blog post of April 2015</h2>
          <p>Posted by Michel Buffa...</p>
       	</header>
      		<p>Content of the blog post...</p>
   	</section>
 	</body>

*Para resumir:*

*Utilice siempre un elemento de encabezado después de un elemento de selecionamiento, por ejemplo < section > < Hx > ... </ Hx > ... </ section >, y después de < body >, donde x puede ser 1..6,*

*O bien, utilizar un <header> elemento, como en < section > < header > < Hx > ... </ Hx > ..... </ header > ... </ section >*

##Un poco mas sobre header elemento

*El < header > elemento es sólo un contenedor. No se tiene en cuenta para la definición de nuevas secciones de un documento ni afecta los niveles de jerarquía.*

*Puede usar elementos de encabezado < h1 > ... < h6 > en un < header >, pero tenga cuidado si utiliza más de una, como las reglas explicadas en la parte anterior del curso será de aplicación y puede generar "secciones" implícitos en la cabecera.*

	<section>
   	<header>
     		<h1>Some text in a h1 in a header of a section</h1>
     		<h2>This a h2 in the header...</h2>
   	</header>
	</section>

*o*

	<header>
    		<h1>HTML 5.1 Nightly</h1>
    		<p>A vocabulary and associated APIs for HTML and XHTML</p>
    		<p>Editor's Draft 9 May 2013</p>
	</header>
	
BEST PRACTICE 2: TRY NOT TO RELY ON IMPLICIT SECTIONING, USE <SECTION>, <ARTICLE>, ETC. INSTEAD OF JUST < H1 >...< H6 >

*El siguiente ejemplo define varias "secciones" implícitos utilizando < Hx > directamente (en las líneas 7 y 9):*

	<body>
 	<h4>Apples</h4>
 	<p>Apples are fruit.</p>
 	<section>
     		<h2>Taste</h2>
     		<p>They taste lovely.</p>
     		<h6>Sweet</h6>
     		<p>Red apples are sweeter than green ones.</p>
     		<h1>Color</h1>
     		<p>Apples come in various colors.</p>
 	</section>
	</body>

*Mejor tecnica*

	<body>
 	<h1>Apples</h1>
 	<p>Apples are fruit.</p>
 	<section>
     		<h2>Taste</h2>
     		<p>They taste lovely.</p>
     	<section>
         	<h3>Sweet</h3>
         	<p>Red apples are sweeter than green ones.</p>
     	</section>
 	</section>
 	<section>
     		<h2>Color</h2>
     		<p>Apples come in various colors.</p>
 	</section>
	</body>
	
*mejor para mantener*

	<body>
 	<h1>Apples</h1>
 	<p>Apples are fruit.</p>
 	<section>
     		<h1>Taste</h1>
     		<p>They taste lovely.</p>
     	<section>
         	<h1>Sweet</h1>
         	<p>Red apples are sweeter than green ones.</p>
     	</section>
 	</section>
 	<section>
     		<h1>Color</h1>
     		<p>Apples come in various colors.</p>
 	</section>
	</body>
	
*se necesitaria css para modificar el tamaño*


##Incorporación de una tabla de contenidos


*Aquí proponemos una pequeña pieza de código JavaScript que puede utilizar en sus documentos para mostrar una tabla incrustada de contenidos. Este código viene del código fuente de la del HTML5 Outliner (H5O) extensión de Google Chrome.*

*Este ejemplo es un documento sencillo, con un hipervínculo que, una vez que se hace clic, se muestra la tabla de contenido en un <aside> en el <section> principal. Basta con mirar el código fuente y copiar / pegar el enlace en sus propios documentos HTML.*

	<body>
	<h1>This is an example of embedded table of content</h1>
 	<section>
     	     <header>
         	<h1>First section of the document (this is a h1)</h1>
         	This is a subheading...
     	      </header>
     		 <h2>First subsection of the first section (a h2)</h2>
     		 <p>Blah Blah...</p>
 	</section>
 	<section>
     		<h1>Second section of the document (a h1)</h1>
     		<h2>First subsection (a h2)</h2>
 	</section>
 	<aside>
     		<h3>Table of contents</h3>
     		<a href="javascript:(function(){...})();"
        		title="TableDeMatiere">
        	Click here to display the table of contents!
     		</a>
 	</aside>
	</body>

##¿Qué pasa con el < main > elemento que se encuentra en la especificación HTML5?

*si utiliza < nav > / < header > / < footer > etc, para estructurar el documento, también puede utilizar < main > para identificar el contenido principal del documento. Si lo hace, ofrece una estructura de documento navegable para los usuarios de tecnología de asistencia, así como los ganchos de estilo para los desarrolladores.*

*Hemos visto los diferentes elementos de seccionamiento de HTML5, así que ¿por qué no hablar de la < main > elemento anteriormente en esta parte del curso? ¿No debería < main > ... </ main > ser utilizado en lugar de < div class = "main" > ... </ div >*

*Un documento ha sido escrito por el grupo de trabajo de HTML5, que detalla los diferentes casos de uso para este elemento:*
http://www.w3.org/html/wg/wiki/User:Sfaulkne/main-usecases#Introduction

*Este elemento está sujeto a algunas restricciones:*

*No debe haber más de un < main > en un documento,*

*No debe ser un descendiente de un < article >, < aside >, < footer >, < header > o < nav > elemento.*

*Y finalmente aquí son algunos ejemplos (de la especificación HTML5) que mezclan la < main > elemento con los demás elementos de seccionamiento ya vistos en el curso:*

	<!-- other content -->
	<main>
   		<h1>Skateboards</h1>
   		<p>The skateboard helps kids to get around.</p>
   		<article>
      			<h2>Longboards</h2>
      			<p>Longboards are a type of skateboard with a longer
			    wheelbase and larger, softer wheels.</p>
      			<p>... </p>
      			<p>... </p>
   		</article>
   		<article>
      			<h2>Electric Skateboards</h2>
      			<p>These no longer require the propelling of the skateboard by means of the feet; rather an electric 				   motor propels the board, fed by an electric battery.</p>
      			<p>... </p>
      			<p>... </p>
   		</article>
	</main>
 
	<!-- other content -->
	
*He aquí otro ejemplo (también de la especificación). Aquí el < main > contiene un elemento <nav> elemento que consta de enlaces a las subsecciones de los contenidos principales:*

	<!DOCTYPE html>
 	<html>
   	<head>
     		<title>Graduation Ceremony Summer 2022</title>
   	</head>
 	<body>
 	<header>The Lawson Academy:
   	<nav>
     	<h2>Click these links to navigate...</h2>
     	<ul>
        	<li><a href="courses.html">Courses</a></li>
        	<li><a href="fees.html">Fees</a></li>
        	<li><a>Graduation</a></li>
     	</ul>
   	</nav>
 	</header>
	<main>
  		<h1>Graduation</h1>
  	<nav>
     		<h2>Please choose:</h2>
     	<ul>
        	<li><a href="#ceremony">Ceremony</a></li>
        	<li><a href="#graduates">Graduates</a></li>
        	<li><a href="#awards">Awards</a></li>
     	</ul>
  	</nav>
  		<h2 id="ceremony">Ceremony</h2>
  		<p>Opening Procession</p>
  		<p>Speech by Valedictorian</p>
  		<p>Speech by Class President</p>
  		<p>Presentation of Diplomas</p>
  		<p>Closing Speech by Headmaster</p>
  		<h2 id="graduates">Graduates</h2>
  	<ul>
     		<li>Eileen Williams</li>
     		<li>Andy Maseyk</li>
     		<li>Blanca Sainz Garcia</li>
     		<li>Clara Faulkner</li>
     		<li>Gez Lemon</li>
     		<li>Eloisa Faulkner</li>
  	</ul>
  		<h2 id="awards">Awards</h2>
  	<ul>
    		<li>Clara Faulkner</li>
    		<li>Eloisa Faulkner</li>
    		<li>Blanca Sainz Garcia</li>
  	</ul>
	</main>
	<footer>Copyright 2012 B.lawson</footer>
	</body>
	</html>
	
*MEJORES PRÁCTICAS Por cuestiones de accesibilidad, una buena práctica consiste en dividir el contenido de la página en "regiones" definidos por los cinco 5 elementos (aside, footer, header, main y  nav).*

##INTRODUCCIÓN: diseños sencillos utilizando los nuevos elementos estructurantes y CSS3

*Ejemplos de diseños de página clásicos*

*INTRODUCCIÓN En esta sección, mostraremos algunas técnicas de diseño CSS "clásicos" para el diseño de una página HTML que utiliza los nuevos elementos de seccionamiento.*

*Ejemplo 1: Un < section > A LA IZQUIERDA Y UN < aside > A la derecha, USO de float  y el ancho "WIDTH" propiedades CSS*

*Ejemplo*

	<header>
 		<code>&lt;header&gt;</code>
	</header>
 
	<section>
 		<code>&ltsection&gt; <br> float: left;</code>
	</section>
 
	<aside>
 		<code>&lt;aside&gt; <br> float: right;</code>
	</aside>
 
	<footer>
 		<code>&lt;footer&gt;</code>
	</footer>

*Here we use the CSS rule float:left for the <section> and the CSS rule float:right for the <aside>. When an element floats, it goes out of the normal flow of the HTML element. Then by default it floats to the edge of its parent; and its size depends on the elements it contains. So, in order to fill the whole horizontal space, we prefer here to "force the width" by setting the CSS width property with a percentage.  So we took width: 63% for the <section> on the left and width:30% for the <aside> on the right.*

	code {
  		background: #2db34a;
  		border-radius: 6px;
  		color: #fff;
  		display: block;
  		font: 14px/24px "Source Code Pro", Inconsolata, "Lucida Console", Terminal, "Courier New", Courier;
  		padding: 24px 15px;
  		text-align: center;
	}
	header,
	section,
	aside,
	footer {
  		margin: 0 1.5% 24px 1.5%;
	}
	section {
  		float: left;
  		width: 63%;
	}	
	aside {
  		float: right;
  		width: 30%;
	}
	footer {
  		clear: both;
  		margin-bottom: 0;
	}

*Ejemplo 2: TRES SECCIONES centrada, DE TAMAÑO EQUAL, UTILIZANDO TAMBIÉN el flotador y el ancho de las propiedades CSS*

*Ejemplo*

	<header>
 		<code>&lt;header&gt;</code>
	</header>
 
	<section>
 		<code>&lt;section&gt; <br> float: left;</code>
	</section>
 
	<section>
 		<code>&lt;section&gt; <br> float: left;</code>
	</section>
 
	<section>
 		<code>&lt;section&gt; <br> float: left;</code>
	</section>
 
	<footer>
 		<code>&lt;footer&gt;</code>
	</footer>

*con css*

	code {
  		background: blue;
  		border-radius: 6px;
  		color: #fff;
  		display: block;
  		font: 14px/24px "Source Code Pro", Inconsolata, "Lucida Console", Terminal, "Courier New", Courier;
  		padding: 24px 15px;
  		text-align: center;
	}
	header,
	section,
	aside,
	footer {
  		margin: 0 1.5% 24px 1.5%;
	}
	section {
 		float: left;
  		width: 30%;
	}
	footer {
  		clear: both;
  		margin-bottom: 0;
	}
	
##Ejemplo 3: mismo resultado usando la propiedad CSS FLEX

*En este ejemplo se utiliza la propiedad de la flex CSS para lograr un resultado similar al que se muestra en el Ejemplo 2*

Ejemplo 4: OTRO EJEMPLO escrito por un estudiante (ROYREY), que utiliza el FLEX PROPIEDAD


##< details > y < summary > elementos

*INTRODUCCIÓN Estos elementos se han introducido para la visualización de una zona plegable en un documento HTML.*

*El < details > elemento genera un widget simple de mostrar contenido del elemento / ocultar, opcionalmente pulsando sobre su hijo < summary > elemento.*

	<!DOCTYPE html>
	<html>
	<body>

	<details>
		<summary>How to beat the boss...spoiler alert !</summary>
		<p> Just aim to the red spots near his eyes</p>
		<p>Keep shooting at these spots until the eyes open, then hit quickly both eyes with your laser beam.</p>
	</details>

	</body>
	</html>
	
	details {
		display:block; 
		width:300px;
		margin:10px 0;
	}
	summary {
		display:block; 
		background:#99B92C;
		color:white;
		border-radius:5px;
		padding:5px;
		cursor:pointer;font-weight:bold;
	}
	
	
*El < summary > ... </ summary > está dentro de un < details > ... </ details > elemento. Al hacer clic en el icono a la izquierda del resumen, el contenido de la < details > valor se muestra / oculta.*

*< details  > bloques pueden ser incrustados dentro de otros*

	<details>
		<summary>How to beat the boss...spoiler alert !</summary>
		<p> Just aim to the red spots near his eyes</p>
		<p>Keep shooting at these spots until the eyes open, then hit quickly both eyes with your laser beam.</p>
  		<details>
    			<summary>Bonus and spoiler No 2: get a new weapon by cutting the tail of the boss</summary>
			<p>Before finishing him, try to cut his trail, you will get a new weapon</p>
			<p>Just try to stay behind him as long as you can, hitting his tail with your melee weapon, after a few 			hits the trail will fall and you will get a new bonus weapon, then finish the boss.</p>
		</details>
	</details>

##CLASES DE PSEUDO CSS DE ICONOS STYLING RESUMEN

*Hay clases seudo CSS para el estilo de este icono cuando está en el estado abierto o cerrado. El apoyo a estos todavía no oficial (funciona en Google Chrome).*

*El color y el fondo del icono de la izquierda se especifican por la siguiente regla CSS, que utiliza la clase de pseudo*

	::-webkit-details-marker
	
	summary::-webkit-details-marker {
    		color:#FF0000;
    		background:#FFFFFF;
	}

*Cuando se despliegue*

	details[open] summary::-webkit-details-marker {
    		color:#0000FF;
    		background:#00FFFF;
	}
	
*También es posible cambiar el icono de sí mismo utilizando la clase de pseudo CSS:after*

*Use un icono con forma de "+", rosa, negrita, etc ...:*

	summary:after {
    		content: "+";
    		color: #FF00FF;
    		float: left;
    		font-size: 1.5em;
    		font-weight: bold;
    		margin: -5px 5px 0 0;
    		padding: 0;
    		text-align: center;
    		width: 20px;
	}
	
*Use un icono "-" en forma, blanco, cuando se muestran los detalles:*

	details[open] summary:after {
    		content: "-";
    		color: #FFFFFF
	}
	
##Cómo agregar retro-compatibilidad: un ejemplo

*INTRODUCCIÓN Un polyfill es una pieza de código JavaScript que incluye en su página HTML, que emulará HTML5 características no implementado aún en los navegadores. Por lo general, un polyfill comienza emulando una característica sólo cuando no se detecta el soporte nativo.*

*¿Sabes dónde está el término "polyfill" está viniendo? Fue acuñado por Remy Sharp, un programador Web británico que había estado usando una marca de resina para llenar agujeros en la mampostería.*

*You will find a list of polyfills on these Web sites: http://caniuse.com/ or http://html5please.com/. Or just do a search using the keyword 'polyfill' with the name of the feature.*

*Algunas bibliotecas, como http://modernizr.com/, son útiles para la detección de las funciones compatibles con un navegador determinado. Se viene embalado con algunos polyfills de propósito general (como HTML5 cuña para el viejo IE) y la página wiki de su repositorio GitHub viene con una enorme lista de polyfills disponibles que se pueden cargar en la demanda sólo cuando el navegador no está apoyando una característica nativa .*


*EJEMPLO CON < details > Y < summary >*

*< details > y < summary > todavía no están soportadas por todos los navegadores. ¿Cómo podemos utilizar en un sitio web? La respuesta es: utilizar un polyfill!*

Version 1: no polyfill


##< time > elemento

*INTRODUCCIÓN El < time > es útil para marcar una hora o una duración en un documento.*

*Ofrece tanto una parte legible (la parte entre  < time > y </ time >) y una parte legible por máquina contenidos dentro de un atributo datetime. Las fechas se expresan como YYYY-MM-DD.*

*La parte legible por máquina añade semántica que pueden ser utilizados por los motores de búsqueda para la indexación, los navegadores o las extensiones del navegador o por el código JavaScript.Escenarios útiles incluyen la generación de alertas para cumpleaños, añadiendo automáticamente fechas o eventos que contienen < time > elementos en un calendario, etc.*

*ejemplo*

	We open at <time>10:00</time> every morning.
	I have a meeting the <time datetime="2012-02-14">Monday 14/02/2012.</time>.
	Blog posts from the year <time datetime="2012">2012</time>.
	Archives, blog posts for <time datetime="2012-04">April 2012</time>
	This recipe was published by Michel the <time datetime="2012-04-16">April 16, 2012</time>.
	
##EL ATRIBUTO DATETIME

*El atributo de fecha y hora "datetime" puede utilizarse para indicar una fecha / hora o una duración.*
*Fecha valores / hora Soporta diferentes especificaciones de tiempo como "un año", "un mes en un año", "una semana en un año", "un tiempo", etc ...*

*Ejemplos*

	<time datetime="1905">	The year 1905
	<time datetime="1905-11">	November 1905
	<time datetime="11-13"> 	November 13th (any year)
	<time datetime="1905-W21">	Week 21 from year 1905
	<time datetime="1905-11-13 09:00">	November 13th year 1905, time = 9:00
	<time datetime="1905-11-13T09:00">	Same as previous example, both syntaxes are supported, with and without the "T" 						between date and time.
	<time datetime="09:00Z">	9:00 in the morning, GMT
	<time datetime="09:00-05">	9:00 in the morning, GMT minus 5 hours
	<time datetime="09:00+05:45">	9:00 in the morning, GMT plus 5 hours 45 minutes, (for example, Nepal is 5:45 ahead of  					GMT)
	
*valores de duración*

*Valores de duración utilizan el prefijo "P" para "período", como en < time datetime = "P4D" > (periodo = cuatro días) ...*

*So you start the attribute string value with a "P", followed by a duration value that ends with another letter indicating the unit used: "D" for "days",  “H” for hours, “M” for minutes and “S” for seconds.*

*Puede separar los diferentes elementos "P", de valor y unidad con espacios, pero esto es opcional. Así <hora datetime = "P4D"> es una duración de 4 días, como es < time datetime = "P 4 D">.*

*El uso de una "T" después de que el marcador "P" le permite indicar una más precisa tiempo de duración: <hora datetime = "PT4H 6M 12.55S"> es una duración de 4 horas, 6 minutos y 12.55 segundos.*

*Como alternativa, puede usar también un componente de tiempo de duración. Desde el artículo de Bruce Lawson: "Cualquiera que elija, está representado internamente como un número de segundos Debido a esto, no se puede especificar una duración en términos de meses, ya que un mes no es un número exacto de segundos, un mes puede. . duran de 28 a 31 días la misma manera, un año no es un número exacto de segundos, es de 12 meses y febrero veces tiene un día extra.*

	<h2>Recipe:</h2>
	<ul>
  		<li> Preparation time: <time datetime="P30M">30 minutes</time> </li>
  		<li> Cooking time:     <time datetime="P10M"> 10 minutes</time> </li>
	</ul>
	
##< time > ELEMENTO SIN ATRIBUTOS

*Si se utiliza sin atributos, el valor entre la apertura < time > y cierre </ time > debe seguir la sintaxis propuesta por el pliego de condiciones para que las máquinas puede entenderlo (misma sintaxis que el presentado para el atributo datetime en la sección anterior). Sin embargo, se recomienda utilizar un atributo de fecha y hora, ya que da más libertad en la forma en que puede mostrar la fecha / hora / duración en un formato legible.*
	
##El < mark > elemento

*El HTML < mark > etiqueta se utiliza para indicar el texto como está marcado o marcada con fines de referencia, debido a su relevancia en otro contexto.*

Algunos casos de uso:

*Resultados de búsqueda Pantalla con cadenas de búsqueda resaltados en los resultados.*

*Resaltar partes importantes de un texto, como "partes citar", etc.*

*Reemplace < strong > y < em > por < mark > cuando adecuado.*

	<!DOCTYPE html>
	<html>
	<head>
	<meta charset=utf-8 />
	<title>JS Bin</title>
	</head>
	<body>
  		<p>Project is due in <mark>.zip format</mark> next monday.</p>
	</body>
	</html>
	
*ejemplo*

	<body>
	<pre>
		<code><mark>var</mark> i = 3;</code>
	</pre>
	<p>The var keyword is used to declare a variable in JavaScript.</p>
	</body>

##CHANGE THE DEFAULT STYLE OF THE <MARK> ELEMENT

*Si no te gusta el fondo amarillo por defecto, puede utilizar CSS para cambiar el estilo de la < mark > elemento: Por ejemplo:*

	mark {
    		background-color: green;
    		color: yellow;
	}
	
##El nuevo atributo HTML5 download para <A HREF>

*EL CAMINO VIEJO permitirá descargar archivos utilizando HTML y HTTP*

*Todo el mundo sabe la forma clásica de hacer hipervínculos, utilizando <a href="..."> algunos </a> texto. Lo que ocurre cuando se hace clic en el hipervínculo depende del tipo MIME recibido por el navegador. Si usted se conecta a un archivo el navegador sabe render (una página html, gif, jpg, png o imagen, etc.) hay una buena probabilidad de que el tipo MIME recibido por el navegador será algo como esto:*

	Content-type: text/html, text/plain, image/gif, image/jpg, etc.
	
	<a href="toto.jpg">
    		please right click this link to download
    		the toto.jpg picture</a>
    		
  *... le pedirá al servidor HTTP remoto para enviar el archivo toto.jpg. El navegador recibirá en la cabecera HTTP respuesta del servidor (y por defecto el navegador mostrará la imagen en una nueva pestaña):*
  
  	...
 	Content-type: image/jpg
	...
*Sin embargo, si el enlace apunta a un cierto código PHP, Java de código servlet, o cualquier tipo de script / aplicación en el lado del servidor, este código de servidor remoto puede enviar en su respuesta HTTP de un tipo de contenido que puede forzar al navegador a descargar la imagen en lugar de hacerla.*

*También podrá proponer un nombre para el archivo a descargar que puede ser distinta a la que aparece en la URL del atributo href. Esto se puede hacer mediante la generación, además de la línea de tipo de contenido en la cabecera HTTP de respuesta, una línea Content-Disposición que tiene este aspecto:*

	Content-Disposition: attachment; filename="MyImage.png";
	
##NEW WAY TO DOWNLOAD A FILE USING AN ARBITRARY NAME: THE DOWNLOAD ATTRIBUTE

*HTML5 propuso el uso de un nuevo atributo llamado de descarga para descargar recursos en lugar de navegar a ellos. El siguiente ejemplo muestra cómo activar la descarga de una imagen por el navegador (en lugar de hacerla, que es el comportamiento por defecto) con un nombre diferente del nombre del recurso.*

	<a href="/asset-v1:W3Cx+HTML5.1x+4T2015+type@asset+block/normal.gif"
   		download="MichelBuffa.gif">
    		download a picture of Michel Buffa
	</a>
	
*Este hecho obligará a la descarga de una imagen con un nombre de archivo diferente de su nombre de archivo original en el lado del servidor. Aquí hay una captura de pantalla del navegador de Internet, mientras que la descarga de la imagen. Podemos ver en la barra de estado el nombre del enlace (la imagen es "normal.gif") y el archivo descargado es "MichelBuffa.gif":*

*WARNING: since 2015, and for security reasons, the image should be located on the same domain as the HTML page that contains the link (using a relative URL works well, for example, but linking a page on another domain will not work - it will keep its original name).*

##El HTML5 TRANSLATE ATRIBUTO

*INTRODUCCIÓN HTML5 nos da un nuevo atributo traducir. Este atributo se utiliza para limitar el impacto de las herramientas de traducción como Google Translate, al prohibir la traducción de determinados contenidos. En muchos casos, algunas partes de un documento no deben ser traducidos.*

Los casos de uso son:

*Páginas HTML que contienen el código fuente: que sin duda no le gustaría ver el Java o PHP o cualquier programación partes lingüísticas de su página traducida a otro idioma hablado!*

*Los sitios web de videojuegos que proponen códigos de trucos; los códigos no tienen que ser traducidos,*

*Nombres de calles, nombres de autores en un "sobre" la página no debe traducirse

*Tanto Google translate y servicios de traducción en línea de Microsoft ya ofrecen la capacidad de prevenir la traducción de los contenidos mediante la adición de marcadores para tu sitio, aunque lo hacen de (múltiples) formas diferentes. Esperemos que el nuevo atributo ayudará significativamente al proporcionar un enfoque estándar.*

##PRINCIPIO: DAR CONSEJOS PARA HERRAMIENTAS TRADUCCIÓN

*nos dice que "El atributo traducir es un atributo enumerado que se utiliza para especificar si los valores de atributos de un elemento y los valores de sus hijos nodo de texto deben ser traducidos cuando se localiza a la página, o si dejarlos sin cambios.*

*Palabras clave del atributo son la cadena vacía, sí, y no. La cadena vacía y la palabra clave mapa sí al estado sí. Los hay mapas de palabras clave a la no estatal. Además, hay un tercer Estado, el Estado hereda, que es el valor predeterminado de falta (y el valor predeterminado valor no válido) ".*

Ejemplo ilustrativo cómo especificar partes de un elemento HTML que no debe ser traducido:

	<span translate="no" class="author">Michel Ham</span>
	
*En el ejemplo anterior, un elemento <span> define un autor (de un blog, por ejemplo) que se llama Michel Ham. Sin embargo, su apellido es el mismo que el cerdo y se traduciría a "Michel Jambon" en francés, o Michel Jamón en español ...*

*Utilizando el = "no" atributo traducir debería impedir este comportamiento ...*

	<span translate="no" class="author">Michel Ham</span> is a professor
		from the University of Nice,France.
		
##HERENCIA ENTRE ELEMENTOS

*Al definir un elemento como no ser traducible, sus hijos heredan este comportamiento y son ellos mismos no traducible. Lo contrario también es cierto.*

	<p translate="no">This is a text in a paragraph element, that should not be translated: the p element has a 			translate="no" attribute.<span> This part that is in a span element embedded within the paragraph. It does not have a 	translate attribute but inherits the translation-mode of the p and will not be translated too</span>. This is the end of the 	paragraph...</ p>
	
##Microdata

*INTRODUCCIÓN

*Existen 3 formas de proporcionar contenido legible por máquina incrustado en un documento Web clásica: HTML + RDFa, microformatos y microdatos. En esta sección, nos centraremos en los microdatos.*

*Adición de microdatos a páginas Web ayuda a los motores de búsqueda a comprender mejor el contenido de las páginas, sus temas, etc. El objetivo principal de los microdatos es la optimización del Search Engine.*

*Esta información no es visible para los humanos: es la información semántica pura. Tipos populares de microdatos son eventos, el perfil de una persona, la descripción de una organización, los detalles de una receta, una descripción del producto, una ubicación geográfica, etc.*

##QUICK EXAMPLE OF MICRODATA THAT DESCRIBES A PERSON:

	<section itemscope itemtype="http://schema.org/Person">
    	<h1>Contact Information</h1>
    	<dl>
      		<dt>Name</dt>
      		<dd itemprop="name">Michel Buffa</dd>
      		<dt>Position</dt>
      		<dd><span itemprop="jobTitle">
           	Professor/Researcher/Scientist</span> for
          	<span itemprop="affiliation">
              University of Côte d'Azur, France
          </span>
      		</dd>
    	</dl>
    	<!-- SURFACE ADDRESS GOES HERE -->
    	<h1>My different online public accounts</h1>
    	<ul>
       		<li><a href="http://www.twitter.com/micbuffa"
              	itemprop="url">Twitter profile</a></li>
       	<li><a href="http://www.blogger.com/micbuffa"
              itemprop="url">Michel Buffa's blog</a></li>
    	</ul>
	</section>
	
*Ejemplo*
	
	...
	</dl>
		<!-- SURFACE ADDRESS GOES HERE -->
		<dd itemprop="address" itemscope
    			itemtype="http://schema.org/PostalAddress">
    		<span itemprop="streetAddress">10 promenade des anglais</span><br>
    		<span itemprop="addressLocality">Nice</span>,
    		<span itemprop="addressRegion">Alpes maritimes, France</span>
    		<span itemprop="postalCode">06410</span><br>
    		<span itemprop="addressCountry" itemscope
          		itemtype="http://schema.org/Country">
         	<span itemprop="name">France</span>
    		</span>
	</dd>
		<h1>My different online public accounts</h1>
		...

In the following sections, we will look more closely at the itemprop, itemscope and itemtype attributes.

##DATOS  se pueden procesar, organizado, estructurar, o presentarse en un contexto dado

*Los diferentes casos de uso:*

*El navegador, o una extensión del navegador, pueden interpretar el último ejemplo como una dirección y pueden proponer a enviarlo a una aplicación de mapas,*

*Un rastreador Web puede interpretar esto como una dirección y mostrarlo en sus respuestas utilizando un diseño de presentación dedicada,*

*Algunos de código JavaScript en la página se puede acceder a estos datos,*

*Con otros tipos de microdatos, para eventos, por ejemplo, el navegador puede aparecer una aplicación de calendario, etc.*

*Nota: Para los usuarios avanzados, Microdatos es muy similar a los microformatos, que utilizan clases de HTML, o a RDFa, que no valida en HTML4 o HTML5. Debido a RDFa se consideró demasiado difícil para que los autores escriben (Google ha llevado a cabo una investigación que concluye que los autores hacen un 30% más errores con RDFa que con otros formatos), los microdatos es la respuesta de HTML5 a la necesidad de integrar la semántica en documentos html.*

##Testing tools

*GOOGLE RICH SNIPPETS AND STRUCTURED DATA TEST TOOL*

One of the most popular resources for testing microdata (as well as microformats and RDFa) is the Google page about rich snippets and structured data. This page contains a link to a structured data testing tool that you can use to see how Google recognizes the semantic data you embed in your HTML code.

Testing a real interactive example with an "about page" for Michel Buffa

Let's have a look now at a (small) example of an about page. It renders as a very simple paragraph that explains who Michel Buffa is... But we embedded Microdata, so it's interesting to see how a search engine sees it, and how it may produce "augmented search results".

	<!DOCTYPE html>
	<html>
	<head>
	<meta charset=utf-8 />
	<title>Michel Buffa</title>
	</head>
	<body>
 		<div itemscope itemtype="http://schema.org/Person">
    		My name is <span itemprop="name">Michel Buffa</span>,
    		And I'm a <span itemprop="jobTitle">professor/researcher</span> at
     		<a href="http://www.i3s.unice.fr/I3S/" itemprop="affiliation">I3S
		Laboratory</a> in the south of France, near the city of Nice. My
    				email
    		is : <span itemprop="email">micbuffa@gmail.com</span>.
		 I live in the city of
    	<span itemprop="address" itemscope
        itemtype="http://schema.org/PostalAddress">
         <span itemprop="addressLocality">Biot</span>, in a region named
         <span itemprop="addressRegion">Alpes Maritimes</span>
    	</span>
 	</div>
	</body>
	</html>
	
*Implementing microdata in your page / the itemscope, itemtype and itemprop attributes*

*BASIC STEPS*

Adding microdata to an HTML page is a really simple task and requires only three attributes: itemscope, itemtype  and itemprop.


Define a container element by adding an itemscope attribute

*First, you need to add an itemscope attribute to an HTML element. This will define the "global object" for which we will define properties. This element can be of different types that we will describe later, but for now let us keep looking at the same example we used in previous sections:*

	<section itemscope itemtype="http://schema.org/Person">
		...
	</section>
	
*We will look at the itemtype attribute later. Now that we have defined a global wrapper object/element (a Person in this case), we can  add properties inside this element to define the first name, last name, etc.*

2 - Specify the vocabulary used for your microdata with the itemtype attribute of the container element

*HTML5 proposes semantic elements for representing sections, articles, headers, etc, but it does not propose any specific elements or attributes to describe an address, a product, a person, etc.*

*We need a special vocabulary to represent a person or a physical address. With microdata you can define your own vocabulary or better, reuse one of the existing popular vocabularies, such as these: http://www.schema.org.*

*Microdata works with properties defined as name/value pairs. The names are defined in the corresponding vocabulary. For example, the vocabulary for representing a Person, available at http://schema.org/Person defines a set of property names, as illustrated by the following screenshot:*

As you can see in this small extract from the vocabulary (also called a "schema"), a Person can have a name (some text), an Address (the type is defined by another vocabulary named PostalAddress), an affiliation (defined by another vocabulary named Organization) and so on.

We notice that one property, such as the address of a Person, may use another vocabulary. Yes, a vocabulary may link to another vocabulary! There is also inheritance between vocabularies! The above screenshot shows that the Person vocabulary inherits from a Thing vocabulary, and the five first properties of the table come from this vocabulary that describes things.

If you are a developer and if you are familiar with object oriented programming, think of properties as class attributes and think of vocabularies as classes.

Vocabularies are meant to be shared

Picture wish words 'time to share'

If one of the existing vocabularies available at the schema.org Web site fits your needs, you should reuse it, as the most popular vocabularies are becoming de facto standards and will be taken into account by Web crawlers, browsers, and browser extensions.

However, if you do not find a vocabulary corresponding to your needs, keep in mind that anyone can define a microdata vocabulary and start embedding custom properties in their own Web pages. You need to define a namespace and put a description of your vocabulary in a Web page that has the name of your vocabulary. For example, if you own japaneserobots.com, you may define a vocabulary for describing Mech Warrior robots at http://japaneserobots/MechWarrior in the same way as http://schema.org/Person describes the properties of a person.

3 - Add properties using the itemprop attribute in HTML elements inside the container 

Basics:

Now that you have defined a container element, you may add properties to the HTML inside

	<section itemscope itemtype="http://schema.org/Person">
     	<h1>Contact Information</h1>
     	<dl>
         	<dt>Name</dt>
         	<dd itemprop="name">Michel Buffa</dd>
         	<dt>Position</dt>
         	<dd><span itemprop="jobTitle">
                     	Professor/Researcher/Scientist
             	     </span> for
             		<span itemprop="affiliation">University of Nice,
                    		France
             	</span>
          	</dd>
     		</dl>
     		<h1>My different online public accounts</h1>
     	<ul>
         	<li><a href="http://www.twitter.com/micbuffa"
             		itemprop="url">Twitter profile</a></li>
         	<li><a href="http://www.blogger.com/micbuffa"
             		itemprop="url">Michel Buffa's blog</a></li>
     	</ul>
	</section>

*In this example the container is a <section> that corresponds to a Person (we have one clue here: the name of the vocabulary given by the itemtype attribute), and each property defined inside this section is identified by the value of the itemprop attribute of sub-elements.*

*The line: *

	<dd itemprop="name">Michel Buffa</dd>
	
..defines a property called "name" that has a value of "Michel Buffa" (the text value between the opening and closing tags of the < dd > element)

##Nesting microdata items:

As we saw with the Person/Address example at the beginning of this chapter, it is possible to nest microdata items inside one another.

Give an element inside a microdata container its own itemscope attribute with the recommended itemtype attribute for indicating the name of the vocabulary used by the nested microdata.

Again, look at the Person/Address example:

	...
	</dl>
		<!-- SURFACE ADDRESS GOES HERE -->
		<dd itemprop="address" itemscope
    			itemtype="http://schema.org/PostalAddress">
     		<span itemprop="streetAddress">10 promenade des anglais</span><br>
     		<span itemprop="addressLocality">Nice</span>,
     		<span itemprop="addressRegion">Alpes maritimes, France</span>
     		<span itemprop="postalCode">06410</span><br>
     		<span itemprop="addressCountry" itemscope
           		itemtype="http://schema.org/Country">
          	<span itemprop="name">France</span>
     		</span>
		</dd>
		<h1>My different online public accounts</h1>
	...
	
The properties at lines 8-12 refer to the address nested microdata (they are defined in the Address vocabulary, not the Person vocabulary), and "France" (line 14) is a property that refers to the Country vocabulary.

Several properties with the same name but different values

It is possible to use the same property name several times in one microdata object, but with different values:

	...
 	<h1>My different online public accounts</h1>
 	<ul>
 		<li><a href="http://www.twitter.com/micbuffa" itemprop="url">Twitter
      			profile</a></li>
 		<li><a href="http://www.blogger.com/micbuffa" itemprop="url">Michel
      			Buffa's blog</a></li>
	</ul>
	
This will define the fact that Michel Buffa has two online accounts, and the two properties have the name url, each with its own value.

It is possible to set more than one property at once, with the same value

It is possible to set more than one property at once, with the same value

Here are some microdata that represent a song. In this example, at line 5 we set  two different properties: genre and keywords with the same value (see the MusicRecording schema definition at http://schema.org/MusicRecording):

	<div itemscope itemtype="http://schema.org/MusicRecording">
 	<h2>The song I just published</h2>
 	<ul>
 		<li>Name: <span itemprop="name">Please buy me on itunes, I need money!</span></li>
 		<li>Band: <span itemprop="genre keywords">Punk, Ska</span></li>
 	</ul>
	</div>
	
And so on...

Now let's see what elements are compatible with the itemprop attribute and where the values of the properties are located, depending on each element type.

##Microdata Tools

There are many tools available (most are free) that you can use for generating, visualizing and debugging microdata. We list some of them in this page, but feel free to share the tools you find / like in the forums.

MICRODATA GENERATORS

There are many free tools you can use to automatically generate microdata for describing persons, restaurants, movies, products, organizations, etc. such as:

http://www.barryko.com/seo/html5-microdata-schema-generator/ 
http://www.microdatagenerator.com/
http://schema-creator.org
Search for "microdata generators" using your favorite search engine, and you will find lots!

#Resumen

* Nuevos estructural elementos
* otros elementos y atributos
* microdata
* 


#HTML5 MULTIMEDIA

##El elemento <video>

*INTRODUCCIÓN El elemento < video > de HTML5 es una de las dos "asesinos Flash" (el otro es el elemento < canvas >). Fue diseñado para reemplazar las cosas horribles como objetos Flash incrustados que solíamos encontrar no hace mucho tiempo.*

El código fuente de este ejemplo muestra el uso típico del elemento < video >:

	<video width="320" height="240" controls="controls">
   		<source src="movie.mp4" type="video/mp4" />
   		<source src="movie.ogg" type="video/ogg" />
   		Your browser does not support the <video> element.
	</video>
	
Tenga en cuenta que:

* el controls atributo indica que un panel de control con el play / stop / volume / progreso de widgets deben mostrarse;
* Por lo general, el navegador usará el primer formato que reconoce (en este caso, el navegador comprueba si se admite mp4, y si no, se comprobará para el formato Ogg, y así sucesivamente). Algunos navegadores pueden usar una heurística diferente y elegir un formato de "preferido".
* El elemento <video> es un miembro de DOM, por lo que el estilo CSS se puede aplicar, así como la manipulación mediante la API DOM.
* 

##RESTRICCIÓN: NO PUEDES incrustar un YOUTUBE O DAILYMOTION vídeo mediante el elemento < video >

Help! <video src="my youtube video URL"></video> does not work! 

*Mientras que utilizan HTML5 para hacer sus videos, estos sitios de alojamiento (YouTube, etc.) utilizan técnicas más complejas con el fin de evitar que utilice con el elemento < video >. En cambio, a menudo es necesario incrustar un < iframe > que hará que los videos HTML5 en su sitio Web, y por supuesto, la publicidad que viene junto con ellos.*

*Por lo general, usted tiene un botón de "embed" cerca de los vídeos que le pide con algo de código HTML que puedes copiar y pegar para incrustar.*

An example using YouTube:

*Aquí está el código HTML tiene que copiar y pegar con el fin de integrar un vídeo (en este caso, un tutorial que explica cómo incrustar un vídeo de YouTube):*


	<iframe width="560" height="315" src="https://www.youtube.com/embed/ZH1XOsv8Oyo" frameborder="0" 					allowfullscreen></iframe>
	
	
*El vídeo de YouTube embebido en esta página el código de seguridad: es HTML5, pero no es un elemento < video > directamente insertado en el HTML de esta página, es un < iframe >:*

##CODEC SUPPORT

This is one of the main issues that the industry has had to solve during the last few years: codec support was not the same from one browser to another, for commercial/cost reasons. For example, Firefox only supported the ogg/oggm format from 2010 to 2013. It did not natively support mp3/mp4 encoding for audio/video, while Internet Explorer only supported the H.264 encoding. Since 2012, things have changed as browsers have been updated. In order to check codec support, the best way is to try it yourself: just visit Video Format Support from Microsoft IE (test works for all browsers).

	The recommended codec that works on most browsers, as of 2015: 
				H264/mp4
				
*However, the recommended way of doing things, assuming you want to target the largest possible audience with a large variety of browsers,  is to encode your videos in the major supported formats.*


##El elemento < audio >

INTRODUCCIÓN

*HTML5 de audio se compone de varias capas:*

El elemento < audio > es útil para incrustar un reproductor de audio en una página Web. Está dedicado para audio streaming. Es muy similar a la del elemento < video >, tanto en su uso y en su API.

El "API Web Audio" está diseñado para aplicaciones musicales y para añadir efectos de sonido para juegos. Esta es API JavaScript y soporte la manipulación de muestras de sonido (bucles, etc.), la síntesis de la música y la generación de sonido (osciladores, etc.). También viene con un conjunto de módulos de sonido predefinido de procesamiento (reverberación, retardo, etc.).

*Los atributos, conjunto de eventos y JavaScript API del elemento <audio> son sólo una versión "reducida" de los del elemento <video>, y aquí sólo se abordarán las diferencias y peculiaridades.*

##THE <AUDIO> ELEMENT, BASIC USAGE

	<html lang="en">
	<body>
  	<audio controls="controls">
      		<source src="https://dl.dropboxusercontent.com/u/1631516/horse.ogg" type="audio/ogg" />
      		<source src="https://dl.dropboxusercontent.com/u/1631516/horse.mp3" type="audio/mp3" />
      			Your browser does not support the audio element.
      			Download the audio/video in
     		<a href=”https://dl.dropboxusercontent.com/u/1631516/horse.ogg”>OGG</a>
     		or <a href=”https://dl.dropboxusercontent.com/u/1631516/horse.mp3”>MP3</a>
     		format.
 	</audio>
	</body>
	</html>
	
*En este ejemplo, al igual que para el elemento <video>, usamos el atributo controls con el fin de hacer que la reproducción / stop , tiempo, volumen y progresar widgets.*

*Note las otras similitudes: entre las etiquetas < audio > ... </  audio > etiquetas, hemos añadido un mensaje de texto que se muestra si el navegador Web no admite el elemento < audio > y utilizamos varios < source > .. . </  source > elementos que enlazan con diferentes formatos de audio para el mismo archivo. El navegador usará el primer formato que reconoce.*

##Atributos del < video > y < audio > elementos

	src
	Source of the video.
	
	width and height	
  	Size of the video.
	If unspecified, the default width and height of the video will be used. If you specify one dimension but not the 		other, the browser will adjust the size of the unspecified dimension to preserve the aspect ratio of the video.
	
	controls	
	If this boolean attribute is present, the browser displays its own controls for video playback and volume.
	
	poster	
	This attribute allows you to specify an image that the browser will use while video is being downloaded, or until the 	user starts playing the video.If this attribute is not specified, the first frame of the video will be used instead.
	
	autoplay	
	This attribute asks the browser to start playing the video automatically as soon as the page is ready
	
	preload	
	The preload attribute is used when autoplay is not used. It tells the browser what to do before a user plays a video. 	This attribute is a hint - the browser may ignore it. While autoplay and preload are mutually exclusive, if both are 			present, then preload is ignored.

	Possible values:
	none: do nothing. This saves bandwidth, no video will be downloaded in background before a user or a call to the 		play() method starts playing the video.
	metadata: download metadata, such as length of the video or its format.
	auto (default value): the browser will decide. This will depend on the implementation, and on the kind of connection: 	wifi, 3G, data roaming etc. 
	
	loop	
	Another boolean attribute that indicates to play the video in loop mode (and it starts again when finished).
	
*Tenga cuidado si usted apuntar aplicaciones móviles o si tiene varios vídeos en la misma página*

El atributo de reproducción automática no se recomienda si su sitio web se dirige a las aplicaciones móviles, ya que puede consumir ancho de banda, incluso si el usuario no está interesado en ver el video propuesto. Si usted apunta dispositivos móviles, se recomienda utilizar la precarga = ninguno, así, como el valor por defecto de este atributo es auto.


*Best practice: do not use autoplay and add preload="none" if you target mobile devices or if you have multiple audio/video on the same page. For example, this page  contains many audio elements and it does not make sense to have them preload or autoplay.*

*About the poster attribute*

Si el atributo poster no se encuentra, por lo general el primer cuadro no esté en blanco del video será utilizado como la imagen que se muestra cuando el vídeo no se reproduce

*About the autoplay attribute for general use*

No abuse del atributo autoplay. Hablamos antes sobre las aplicaciones móviles, pero incluso en las aplicaciones de escritorio por lo general es una mala idea para usarlo (a excepción de Webcam y para algunas animaciones con pequeños bucles de vídeo, sin sonido, o de sitios como YouTube, con sólo videos). Este es el testimonio de un usuario en este foro curso: "Cuando estoy siguiendo las noticias, abro varios titulares en pestañas separadas Y entonces todos ellos empiezo a gritar a mí con algunas autoplays Sé que se supone que me hacen.. ver el video, pero para mí - me hace cerrar la pestaña en voz alta e intento otra fuente ".

*Práctica recomendada: pensar dos veces antes de usar el atributo de reproducción automática, incluso para las aplicaciones de escritorio.*

##ATTRIBUTES OF THE < AUDIO > ELEMENT

Los atributos que se pueden utilizar con el elemento < audio > son un subconjunto de los disponibles para el elemento <video>. Excepto para el atributo poster, todos ellos son reconocidos y tienen los significados que se esperan:

	src: source of an audio stream
	
	controls: if this attribute is present, the browser displays its own controls for audio playback and volume.
	
	autoplay: tells the browser to start playing the audio stream automatically as soon as the page is ready - please read 		details in the above table.
	
	preload: tells the browser what to do before a user plays a video - please read details in the above table.
	
	loop:  indicates to play the audio stream in loop mode (start again when finished).
	
##Styling media players with CSS3

The <video> and <audio> elements are just like other HTML elements, so CSS3 can be used for styling, including CSS3 transitions, animations and transforms. This was not possible with Flash technology.


	<figure id="figaudio1">
  		<img id="imghorse" width="200" src="http://upload.wikimedia.org/wikipedia/commons/d/d4/Nokota_Horses.jpg" alt 			= "a horse"/>
  		<figcaption id="figcptionaudio1"> Press Play to hear the horse!
    		<audio controls="controls">
       			<source src="https://dl.dropboxusercontent.com/u/1631516/horse.ogg" type="audio/ogg" />
       			<source src="https://dl.dropboxusercontent.com/u/1631516/horse.mp3" type="audio/mp3" />
       			Your browser does not support the audio element. Download the audio/video in
			 or <a href=”https://dl.dropboxusercontent.com/u/1631516/horse.mp3”>MP3</a> format.
   		</audio>
 		</figcaption>
	</figure>
	
*css*

	#figaudio1 {
    		width : 420px;;
    		text-align:center;
    		padding : 6px;
    		background : white;
    		margin : 0 11px 0px 0;
    		border :solid 1px #888888;
    		border-radius : 8px ;
	}
 
	#figcptionaudio1 {
    		font-size : .8em;
    		padding : 6px 8px;
    		background : #dddddd;
    		display :block;
    		text-align :center;
    		font-family : georgia, serif;
    		font-style : italic;
    		border-radius : 7px ;
	}
 
	#figaudio1 > img {
    		background : #eeeeee;
    		padding : 5px;
    		border : solid 1px #444444;
	}
 
	/* For audio and img transitions/animation */
	audio, #figaudio1 > img {
    		transition:all 0.5s;
	}
 
	#figaudio1 > img:hover {
    		box-shadow: 15px 15px 20px rgba(0,0, 0, 0.4);
    		transform: scale(1.05);
	}
 
	audio:hover, audio:focus, audio:active {
    		box-shadow: 15px 15px 20px rgba(0,0, 0, 0.4);
    		transform: scale(1.05);
	}

#CHANGING THE SIZE OF A VIDEO ON THE FLY USING CSS3 TRANSFORMS

Resizing and rotating a video as the mouse pointer comes over it

This example uses the pseudo CSS class :hover in order to track the mouseover event. On mouseover, it uses a CSS3 transition property that interpolates the changes in the scale and orientation of the video element (done using a transform CSS property).

	<video id="w3devCampusVideo" autoplay controls>
     		<source src=http://html5doctor.com/demos/video-canvas-magic/video.webm type=video/webm>
     		<source src=http://html5doctor.com/demos/video-canvas-magic/video.ogg type=video/ogg>
     		<source src=http://html5doctor.com/demos/video-canvas-magic/video.mp4 type=video/mp4>
	</video>
	
*css*

	#w3devCampusVideo {
    		width: 300px;
    		transition: all 0.5s ease-in-out;
	}
 
	#w3devCampusVideo:hover {
    		width:400px;
    		transform:rotate(-5deg);
	}
	
*FullScreen video that resizes and maintains ratios. Uses simple JavaScript to modify CSS properties*

	<!DOCTYPE html>
	<html lang="en">
	<head>
    		<meta charset="utf-8">
    		<title>Full width video like PayPal site</title>
	</head>
	<body onload="init();">
    	<video id="myVideo" autoplay>
      		<source src=http://html5doctor.com/demos/video-canvas-magic/video.webm type=video/webm>
      		<source src=http://html5doctor.com/demos/video-canvas-magic/video.ogg type=video/ogg>
      		<source src=http://html5doctor.com/demos/video-canvas-magic/video.mp4 type=video/mp4>
    	</video>
	</body>

*css*

	body {
    		margin:0;
    		padding:0;
    		overflow:hidden;
	}
	
*javascript*

	var video;
 
	function init() {
   		// function called when the page is loaded
   		video = document.querySelector("#myVideo");
   		// For initial value
   		video.width = window.innerWidth;
   		video.height = window.innerHeight;
   		// For dealing with window resize
   		window.onresize = function() {
       		video.width = window.innerWidth;
       		video.height = window.innerHeight;
   		};
	}
	
Full screen video, pure CSS approaches (external resources)

Here is a JSBin with the video from the PayPal Web site, played full screen using only very simple CSS.

In this example, the video does not rescale; it's just cropped if the browser window is resized. Enlarge your browser and you'll see a man with a phone on the right. Resize your browser and you'll see only part of the video.

	body {
  		margin:0;
  		padding:0;
  		overflow:hidden;
	}
 
	video {
  		width:100%;
  		height:auto;
	}
	
Full screen video with CSS effects - example 2

This time the video is zoomed in so that it's much bigger than the browser's window. When we resize the browser, the part of the video that is visible adapts itself. It's not "real resize" of the video.

	<!DOCTYPE html>
	<html>
	<head>
   		<meta charset="utf-8">
   		<title>Full screen video, example from demosthene.info by </title>
	</head>
	<body>
	<header>
 	<video autoplay="" loop="" poster="https://s3-us-west-2.amazonaws.com/s.cdpn.io/4273/polina.jpg" id="bgvid">
    		<source src="http://demosthenes.info/assets/videos/polina.webm" type="video/webm">
    		<source src="http://demosthenes.info/assets/videos/polina.mp4"  type="video/mp4">
 	</video>
	</header>
	<section>
 	<h1>http://demosthenes.info/blog/777/Create-Fullscreen-HTML5-Page-Background-Video</h1>
	</section>
	</body>
	</html>
	
*css*

	html, body{
    		color:white;
    		height: 100%;
	}
	header{
    		height: 100%;
    		background-image: url('http://dupontcours.free.fr/IMG/dots.png'), url('#');
    		background-repeat: repeat, no-repeat;
    		background-size: auto, cover;
    		background-position: center center, top left;
    		font-family: sans-serif;
    		color: #051a00;
	}
 
	header video {
    		position:fixed;
    		top:50%;
    		left:50%;
    		min-width:100%;
    		min-height:100%;
    		width:auto;
    		height:auto;
    		z-index:-100;
    		transform:translateX(-50%) translateY(-50%);
	}
	
The trick here is that:

the video is in the header, and the header has a plotted transparent background that is repeated in X and Y (see line 8 and 9).
The video is positioned so that it's origin (top left corner) is away from the visible surface (line 25), while it is set to take 100% of the surface (lines 20 and 21).
Full screen video that resizes and keeps its ratio, using the viewport units (beware, not supported by old browsers)

##Control < audio > and < video > elements from JavaScript

The <video> element has methods, properties/attributes and events that can be manipulated with JavaScript. Using the DOM API it's possible to manipulate an audio or video element as a JavaScript object that has:

Methods for controlling the behavior, such as play(), pause(), etc.;

Properties (duration, current position, etc.), either in read/write mode (such as volume), or in read-only mode (such as encoding, duration, etc.);

Events generated during the life cycle of the element that can be processed using JavaScript callbacks. It is also possible to send events to control the video player.

Like any HTML element, the <video> element can be manipulated/created using the DOM JavaScript API. Here is an example of programmatically creating a < video > element:

	var video = document.createElement('video');
	video.src = 'video.mp4';
	video.controls = true;
	document.body.appendChild(video);
	
*This will create a complete video player for the file "video.mp4", with control buttons, and will add it to the <body> element of the page.*

##JavaScript API of the <audio> and <video> elements

METHODS, PROPERTIES, AND EVENTS

The JavaScript API gives you powerful tools to manipulate the <video> element, as the video object provides many properties, methods and events.

The complete list of events can be found at the W3C specification page, and numerous examples of each event can be found on many Web sites such as this one.

The complete list of properties can be found at the W3C HTML5 Video Events and API page. This page is interesting for Web developers because it shows an interactive view of the different values and events changing over time while the video is playing within the page.

#HTML5 Graphics

About JavaScript and HTML5

HTML5 is composed of new elements, but it also comes with many JavaScript APIs for controlling video and sound, drawing and animating things in the new < canvas > element, for offline applications, persistence, geolocation, orientation, etc.

WHAT DO YOU NEED? HOW TO DEBUG? HOW TO CATCH ERRORS?

We will not look at the JavaScript syntax here, but more at "JavaScript in the browser", how it works, how to start writing code, etc.

First of all, you need to find a way to debug your code and see errors. If your work does not produce any results, you must know why!

For that you will use the dev. tools of your browser. Press F12 in Windows or cmd-alt-i in Mac to open the dev. tools, then go to the console tab: this is where errors will be displayed, or messages of your own (use the console.log(string) JavaScript function in the JavaScript code embedded in your html page). In the console, you will be able to type any JavaScript command.

The simplest way to add JavaScript code in an HTML page, is by using the < script >...</ script > element.

The code in this example is executed sequentially when the page is loaded: the JavaScript code is executed before the browser could see the rest of the page (as the < script ></ script > is located before the <body>).

The H1 element, for example, does not exist in the Document Object Model, and has not yet been displayed when the JavaScript code is executed. If we move the <script></script> at the end of the document, then the H1 would have been built before the JavaScript code is executed.

The only line of code we have is console.log("Some JavaScript code has been executed");

This means "display in the JavaScript console the message...". If we open the console tab provided by jsbin.com in a dedicated tab (that redirects all console.log() messages), and re-execute the page (just type a space at the end of a line, this will re-render the page and display the message in the console), we see the message in the console tab, as well as in the dev. tools console. This is illustrated by the image below:

It is also possible to use the "real dev. tool console", and for this I recommend running the application in a single window, not in the JS Bin editor. Press the black arrow on the top right of the output window - this will render the page as a standalone Web page, then press F12. You should see:

*ABOUT THE ASYNCHRONOUS NATURE OF JAVASCRIPT*

Draw and animate graphics: the <canvas> element

*The <canvas> tag is one of the "Flash killer" features of HTML5. This course will focus on the fundamental drawing capabilities of the HTML5 canvas.*

*The W3C HTML5 specification about the <canvas> element states that "The canvas element provides scripts with a resolution-dependent bitmap canvas, which can be used for rendering graphs, game graphics, or other visual images on the fly."*

The canvas has been designed for pixel-based graphics, while SVG (Scalable Vector Graphics, another W3C standard) is for vector-based graphics.

*Indeed, the canvas JavaScript drawing API supports different kind of shapes: lines, rectangles, ellipses, arcs, curves, text, images. Some drawing styles need to be specified that will affect the way shapes are drawn (color, drawing width, shadows, etc.). An alpha channel for drawing in transparent mode is also supported, as well as many advanced drawing modes and global filters (blur, etc.).*

The canvas is also used to do animations at 60 frames per second (useful for games), to display videos with special effects, to display a webcam stream, and so on.


Note: 3D drawing using the WebGL API is also possible in a <canvas>, but will not be covered in this course. For the most curious among you, please have a look at the two popular libraries for doing 3D drawing/animation in a <canvas>: BabylonJS and ThreeJS.

##How to make the HTML5 canvas accessible to users with disabilities?

INTRODUCTION

The dynamic nature of the <canvas> element has made it difficult to use in applications that need to be accessible to people with disabilities. To be accessible, it must meet the following principles:

Providing alternative content for what is drawn on the < canvas >,
Exposing the location of shapes, paths, images drawn on the < canvas > to assistive technologies,
Visually indicating whether or not a shape in the canvas had keyboard focus.

THE W3C CANVAS TASK FORCE

The Canvas Task Force of the W3C's HTML Working Group is working on different features to be added to the HTML5.1 canvas specification in order to address canvas accessibility. This is only preliminary work and browsers implementations are not available yet.

Read more on this topic: 

What the canvas element means for accessibility is an article written by Mark Sadecki (ex-W3C, now working at edX).
From the W3C wiki: Canvas Element Accessibility Issues

##Canvas cheatsheet with all API methods and properties

This is a valuable resource, which we recommend either printing or keeping open in a separate browser tab. The original version was located at "http://blog.nihilogic.dk/2009/02/html5-canvas-cheat-sheet.html", but this URL no longer works. Here, we share the mirrored versions (HTML and PDF ones).

##The canvas coordinate system

X AXIS IS HORIZONTAL, DIRECTED TO THE RIGHT
Y AXIS IS VERTICAL, DIRECTED DOWNWARDS

The coordinate system used for drawing in canvases is similar to the one used by many drawing APIs like Java2D: the (0 , 0) is in the top left corner while the X axis is going to the right and the Y axis to the bottom, as  shown in the following picture (author Mark Pilgrim):

Small errata about what I said in the above video: "So let's get the canvas using the DOM API method document.getElementById() or better, use document.querySelector() that is a more recent method from the DOM API"..

The part is bold is not correct: querySelector, technically, comes from Selectors API. Just in case some people would like to go to the specs...

##Typical use of the <canvas> element

1 - Add the < canvas > element into an HTML page

	<canvas id="myCanvas" width="300" height="225">
    		Fallback content that will be displayed in case the web browser
    		does not support the canvas tag or in case scripting is disabled.
	</canvas>
	
Place code similar to the above somewhere in an HTML page. This example defines an area of 300 by 225 pixels on which content can be rendered with JavaScript.

Normally you should see nothing as a result; by default canvases are "transparent".

Make it visible using CSS: A good practice when you are learning to use canvases is to use some CSS to visualize the shape of the canvas. This is not mandatory, just a good trick...

The three lines of CSS will create a border around the canvas with id="myCanvas", of 1 pixel width, in black:

CSS code:

	<style>
    	#myCanvas {
        	border:1px solid black;
    	}
 	</style>
 	
 2 - Select the < canvas > element for use from JavaScript
 
 *We can have more than one <canvas> in a single page, and canvases will be manipulated with JavaScript like other elements in the DOM.*

For example with:

	var canvas = document.getElementById("myCanvas");
	
... or with the querySelector() method introduced by HTML5, that use the CSS selector syntax for selecting elements:

3 - get a "2D context" associated with the canvas, useful for drawing and setting drawing properties (color, etc.)

Once we have a pointer to the <canvas>, we can get a "context".

This particular object is the core of the canvas JavaScript API.

It provides methods for drawing, like fillRect(x, y, width, height) for example, that draws a filled rectangle, and properties for setting the color, shadows, gradients, etc.

*Getting the context (do this only once):*

	var ctx=canvas.getContext('2d');
	
*Set the color for drawing filled shapes*

	ctx.fillStyle='red';
	
*Draw a filled rectangle:*

	ctx.fillRect(0,0,80,100);


Explanation

Only access elements when the DOM is ready:

Notice that we wrote an "init" function (line 12) that is called only when the page has been entirely loaded (we say "when the DOM is ready"). There are several ways to do this. In this example we used the <body onload="init();"> method, at line 32.

It's good practice to have such a function, as we cannot access the elements of the page before the page has been loaded entirely and before the DOM is ready.

Another way is to put the JavaScript code at the end of the document (between <script>...</script>), right before the </body>. In this case when the JavaScript code is executed, the DOM has already been constructed.

Start by getting the canvas and the context:

Before drawing or doing anything interesting with the canvas, we must first get its drawing "context". The drawing context defines the drawing methods and properties we can use.

Good practice is to get the canvas, the context, the width and height of the canvas and other global objects in this "init" function.

The example shows the use of the fillStyle property at line 27 - useful for specifying the way shapes will be filled. In our case this line indicates the color of all the filled shapes we are going to draw:

	ctx.fillStyle='#FF0000';
	
The context property named fillStyle is used here. This property can be set with a color, a gradient, or a pattern. We will see examples of these later on in the course.

When we set it with a color, we use the CSS3 syntax.

The example says that all filled shapes will use the color "#FF0000", which corresponds to a pure red color using the CSS RGB hexadecimal encoding (we could also have used ctx.fillStyle='red');

Then we can draw:

	ctx.fillRect(0,0,80,100);
	
This line is a call to the method fillRect(top left X coordinate, top left Y coordinate, width, height), which draws a filled rectangle.

This line is a call to the method fillRect(top left X coordinate, top left Y coordinate, width, height), which draws a filled rectangle.

SUMMARY OF THE DIFFERENT STEPS

Declare the canvas, remembering to add an id attribute, and fallback content:  

	<canvas id="myCanvas" width="200" height="200">
		...fallback content...
	</canvas>

 Get a reference to the canvas in a JavaScript variable using the DOM API: 
 
	var canvas=document.getElementById('myCanvas');

Get the context for drawing in that canvas:

	var ctx=canvas.getContext('2d');
	
Specify some drawing properties (optional): 

	ctx.fillStyle='#FF0000';
	Draw some shapes: 
	ctx.fillRect(0,0,80,100);
	
Drawing principles

MORE ABOUT THE "CONTEXT" OBJECT

Before we go on, we should take some time to clarify the way we draw on HTML5 canvases. We already mentioned that we use a graphic context for all the main operations. Whenever a shape, a text, or an image is drawn, the current values of the different properties of the graphic context are taken into account. Some are relevant only for certain kinds of shapes or drawing modes, but you must be aware that it is always the current values of these drawing properties that are used.

Later on we'll see that there are ways to save and restore this whole set of values, but for now, let's examine in greater detail some of the properties and methods we've already encountered, and introduce new ones.


MORE ABOUT PROPERTIES AND METHODS OF THE CONTEXT OBJECT

fillStyle is a property of the context, similar in a way to a CSS property.

Its value can be one of the following:

a color,
a pattern (texture), or
a gradient.

The default value is the color black. Any kind of drawing in "fill mode" will use the value of this property to determine how to render the "filled part" of the drawing: any filled rectangle will be filled black by default, any filled circle will be filled in black, and so on.

As long as we don't modify the value of this property, all drawing commands for filled shapes will use the current value.

Note that we will study in detail how to use colors, gradients and patterns later, but for now we introduce some properties and values so that you can understand the principles of canvas drawing.

fillStyle and the other context properties can be considered to be "global variables" of the context.

fillRect(x, y, width, height):  a call to this method draws a filled rectangle.

The two first parameters are the coordinates of the top left corner of the rectangle. This method uses the current value of the filledStyle property to determine how to fill the rectangle.

	ctx.fillStyle='pink';
	ctx.fillRect(10,10,200,200);
	
##strokeStyle is a property of the context similar to fillStyle, but this time for indicating how the shape's outline should be rendered.

The possible values are the same as those for the fillStyle property: a color, a pattern, or a gradient. This property will be taken into account when wireframe shapes are drawn.

strokeRect(x, y, width, height): like fillRect(...), but instead of drawing a filled rectangle the rectangle is drawn in wireframe mode.

	ctx.strokeStyle='blue';
	ctx.strokeRect(10,10,200,200);
	
Only the outline of the rectangle will be drawn, and it will be drawn using the value of the strokeStyle property.

##clearRect(x, y, width, height): a call to this method erases the specified rectangle.

Actually it draws it in a color called "transparent black" (!) that corresponds to the initial state of the rectangle as if no drawing had occurred.

##LET'S SEE SOME SIMPLE EXAMPLES...

Draw a wireframe red rectangle, width lineWidth = 3 pixels.

Extract from the source code (the part that draws the rectangle):

	function drawSomething() {
     		// draw a red rectangle, line width=3 pixels
     		ctx.lineWidth=3;
     		ctx.strokeStyle='red';
     		ctx.strokeRect(10,10,80,100);
 	}
 	
Here, we used "stroke" instead of "fill" in the property and method names (lines 4 and 5): strokeStyle instead of fillStyle, strokeRect(...) instead of fillRect(...).

We also introduced a new property of the context, that applies only when drawing in "stroke" mode, the lineWidth property (line 3), that is used for setting the width of the shape outline. The value is in pixels.

##DRAW 2 FILLED RED RECTANGLES WITH A BLUE OUTLINE OF 5 PIXELS AND SOME TEXT

Let's continue with another example. This time we will draw several shapes that share the same colors - they will be filled in red, with a blue outline. We also show how to draw a text message with a given font.

	 function drawSomething() {
     		// set the global context values
    		ctx.lineWidth=5;
    		ctx.fillStyle='red';
    		ctx.strokeStyle='blue'
    		// font for all text drawing
    		ctx.font = 'italic 20pt Calibri';
    		// Draw the two filled red rectangles
    		ctx.fillRect(10, 30, 70, 150);
    		ctx.fillRect(110, 30, 70, 150);
    		// Draw the two blue wireframe rectangles
    		ctx.strokeRect(10, 30, 70, 150);
    		ctx.strokeRect(110, 30, 70, 150);
    		// Draw a message above the rectangles
    		ctx.fillText("hello", 70, 22);
 	}
 	
 This example shows the "global" nature of the context properties. Once you set the filled color to red, any shapes you draw in filled mode will be red. This is true for all the context properties. We set some of these properties in lines 3-7, and all following calls to context methods for drawing rectangles or text will depend on them. The two filled rectangles at lines 10-11 will be red, the two wireframe rectangles drawn at lines 14-15 will be blue, etc.

Line 18 shows how to draw a text message at an X position of 70 and a Y position of 22. The font is set at line 7 using the font property of the context.  The syntax is the same we use in CSS for using "system fonts".

If you would like to draw the filled text message in green, for example, you should set the ctx.fillStyle property to "green" after you draw the rectangles and before you draw the text (i.e just before line 18).

SUMMARY OF WHAT WE LEARNED

"stroke" means "wireframe" or "outlined", it is a prefix for setting properties or calling methods that will affect wireframe shapes, "fill" is a prefix for filled shapes.

To set the properties of wireframe shapes use ctx.strokeStyle= ..., for filled shapes use ctx.fillStyle=... So far the values we have used are colors, expressed as strings. Example: ctx.strokeStyle  = 'blue';

To draw a wireframe rectangle use ctx.strokeRect(x, y, width, height), to draw a filled rectangle use ctx.fillRect(x, y, width, height);

To set the line width of wireframe shapes, use the ctx.lineWidth property. Example ctx.lineWidth = 10; ctx.strokeRect(0, 0, 100, 100);  will draw a 100x100 rectangle in wireframe mode, with an outline width of 10 pixels.

To draw a text message use ctx.strokeText(message, x, y) or ctx.fillText(message, x, y), for wireframe text or filled text respectively.

To set the character font use the ctx.font property; the value is a font in CSS syntax, for example:  ctx.font = 'italic 20pt Calibri'

##2D transformations: changing the coordinate system

INTRODUCTION

In this part of the course, we introduce the basics of 2D transformations, a powerful tool that will make things easier as soon as you have to:

* Draw complex shapes at given positions, with given orientations and sizes,
* Draw shapes relative to one another.

Let's start with some simple examples before looking at how we use 2D transforms.

LET'S DRAW THREE RECTANGLES!

If we draw three rectangles of size 100x200 in a 400x400 canvas, one at (0, 0) and another at (150, 0), and a third at (300, 0), here is the result and the corresponding code:

	function drawSomething() {
     		ctx.fillStyle='lightgreen';
 
     		ctx.fillRect(0,0,100,200);
     		ctx.fillRect(150,0,100,200);
     		ctx.fillRect(300,0,100,200);
 	}
 	
 LET'S MODIFY THE CODE SO THAT WE CAN DRAW THESE RECTANGLES AT ANY X AND Y POSITION
 
 What if we wanted to draw these 3 rectangles at another position, as a group? We would like to draw all of them a little closer to the bottom, for example... Let's add some parameters to the function:  the X and Y position of the rectangles.
 
 	 var canvas, ctx;
 	function init() {
    		// This function is called after the page is loaded
    		// 1 - Get the canvas
    		canvas = document.getElementById('myCanvas');
    		// 2 - Get the context
    		ctx=canvas.getContext('2d');
    		// 3 - we can draw
    		drawSomething(0, 100);
 	}
 	function drawSomething(x, y) {
    		// draw 3 rectangles
    		ctx.fillStyle='lightgreen';
    		ctx.fillRect(x,y,100,200);
    		ctx.fillRect(x+150,y,100,200);
    		ctx.fillRect(x+300,y,100,200);
 	}

At line 10, we called the drawSomething(...) function with 0 and 100 as parameters, meaning "please add an offset of 0 in X and 100 in Y directions to what is drawn by the function...

If you look at the code of the modified function, you will see that each call to fillRect(...) uses the x and y parameters instead of hard coded values. In this way, if we call it with parameters (0, 100), then all rectangles will be drawn 100 pixels to the bottom (offset in y). Here is the result:

##OK, NOW LET'S DRAW A SMALL MONSTER'S HEAD WITH RECTANGLES

	function drawMonster(x, y) {
   		// head
   		ctx.fillStyle='lightgreen';
   		ctx.fillRect(x,y,200,200);
   		// eyes
   		ctx.fillStyle='red';
   		ctx.fillRect(x+35,y+30,20,20);
   		ctx.fillRect(x+140,y+30,20,20);
   		// interior of eye
   		ctx.fillStyle='yellow';
   		ctx.fillRect(x+43,y+37,10,10);
   		ctx.fillRect(x+143,y+37,10,10);
   		// Nose
   		ctx.fillStyle='black';
   		ctx.fillRect(x+90,y+70,20,80);
   		// Mouth
   		ctx.fillStyle='purple';
   		ctx.fillRect(x+60,y+165,80,20);
 	}
 	
 As you can see, the code uses the same technique, becomes less and less readable. The Xs and Ys at the beginning of each call makes understanding the code harder, etc.

However, there is a way to simplify this => 2D geometric transformations! 

##GEOMETRIC TRANSFORMATIONS: CHANGING THE COORDINATE SYSTEM

*The idea behind 2D transformations is that instead of modifying all the coordinates passed as parameters to each call to drawing methods like fillRect(...), we will keep all the drawing code "as is". For example, if the monster of our previous example was drawn at (0, 0), we could just translate (or rotate, or scale) the original coordinate system.*

Let's take a piece of code that draws something corresponding to the original coordinate system, located at the top left corner of the canvas:

	 function drawMonster(x, y) {
   		// head
   		ctx.fillStyle='lightgreen';
   		ctx.fillRect(0,0,200,200);
   		// eyes
   		ctx.fillStyle='red';
   		ctx.fillRect(35,30,20,20);
   		ctx.fillRect(140,30,20,20);
   		// interior of eye
   		ctx.fillStyle='yellow';
   		ctx.fillRect(43,37,10,10);
   		ctx.fillRect(143,37,10,10);
   		// Nose
   		ctx.fillStyle='black';
   		ctx.fillRect(90,70,20,80);
   		// Mouth
   		ctx.fillStyle='purple';
   		ctx.fillRect(60,165,80,20);
   		// coordinate system at (0, 0)
   		drawArrow(ctx, 0, 0, 100, 0, 10, 'red');
   		drawArrow(ctx, 0, 0, 0, 100, 10, 'red');
	}
	
	
This code is the just the same as in the previous example except that we removed all Xs and Yx in the code. We also added at the end (lines 25-26) two lines of code that draw the coordinate system. The drawArrow(startX, startY, endX, endY, width, color) function is a utility function that we will present later. You can see it in the source code of the complete online example on JS Bin: look in the JavaScript tab.

##Translation using ctx.translate(offsetX, offsetY)

Now, instead of simply calling drawMonster(0, 0), we will call first ctx.translate(100, 100), and look at the result (online code: http://jsbin.com/yuhamu/2/edit)

	ctx.translate(100, 100);
	drawMonster(0, 0);
	
Line 1 changes the position of the coordinate system, line 2 draws a monster in the new translated coordinate system. All subsequent calls to drawing methods will be affected and will work in this new system too.

##OTHER TRANSFORMATIONS: ROTATE, SCALE

There are other transformations available:

ctx.rotate(angle), with angle in radians. Note that the order of transformations is important: usually we translate, then rotate, then scale... If you change this order, you need to know what you are doing...

ctx.scale (sx, sy), where scale(1, 1) corresponds to "no zoom", scale(2, 2) corresponds to "zooming 2x" and scale(0.5, 0.5) corresponds to zooming out to see the drawings half as big as before. If you do not use the same values for sx and sy, you do "asymmetric scaling", you can distort a shape horizontally or vertically. Try changing the values in the source code of the next online examples.

Here is the previous example, but this time we translated the coordinate system, then rotated it with an angle equal to PI/4 , then we scaled it so that units are half as big (see the example online):

And here is the code of the transformations we used, followed by the call to the function that draws the monster:

	ctx.translate(100, 100);
	ctx.rotate(Math.PI/4);
	ctx.scale(0.5, 0.5);
 	
	drawMonster(0, 0);
	
BEWARE: ALL DRAWINGS TO COME WILL BE IN THAT MODIFIED COORDINATE SYSTEM!

If we draw two shapes at two different positions, they will be relative to this new coordinate system

HOW CAN WE RESET THE COORDINATE SYSTEM, HOW CAN WE GO BACK TO THE PREVIOUS ONE?

Aha, this is a very interesting question... we will give the answer very soon in the section on saving/restoring the context :-)

##Saving and restoring the context

There are two methods for saving and restoring the context properties: ctx.save()and ctx.restore().

What will be saved: fillStyle and strokeStyle, lineWidth, previous coordinate system, etc., that is ALL properties that affect drawing!

A call to ctx.save() will probably save the context property values in a hardware register on your graphics card. Multiple contexts can be saved consecutively and restored.

Contexts saved will be stacked, the last one that has been saved will be restored by the next call to restore(), so it is very important to have one restore for each save.

	Best practice: save the context at the beginning of any function 
	that changes the context, restore it at the end of the function!

EXAMPLE OF A FUNCTION THAT CHANGES THE CONTEXT AND RESTORES IT AFTER EXECUTION

We took the last example we saw (the one with the monster, from the previous page of the course), and slightly modified the function that draws the monster:

We added parameters for setting the position and orientation of the monster, and added calls to ctx.translate(x, y) and ctx.rotate(angle) in the function.

We added parameters for the head color and eye color.

We saved the context at the beginning of the function (BEST PRACTICE),

We restored it at the end (BEST PRACTICE).

Source code extract of this function: notice at lines 3 and 26 how we save/restore the context at the beginning/end. Right after saving the context, we modify the coordinate system (lines 7-8). The rest of the code is nearly the same as in the last version of the monster example.

	function drawMonster(x, y, angle, headColor, eyeColor) {
    		// BEST PRACTICE : SAVE CONTEXT AND RESTORE IT AT THE END
    		ctx.save();
    		// Moves the coordinate system so that the monster is drawn
    		// at position (x, y)
    		ctx.translate(x, y);
    		ctx.rotate(angle);
    		// head
    		ctx.fillStyle=headColor;
    		ctx.fillRect(0,0,200,200);
    		// eyes
    		ctx.fillStyle='red';
    		ctx.fillRect(35,30,20,20);
    		ctx.fillRect(140,30,20,20);
    		// interior of eye
    		ctx.fillStyle=eyeColor;
    		ctx.fillRect(43,37,10,10);
    		ctx.fillRect(143,37,10,10);
 
    		...
    		// BEST PRACTICE!
    		ctx.restore();
 	}



#HTML5 FORMS

With HTML5, forms, which had shown little improvement since 1997, evolved considerably.  To achieve this, web developers relied on many popular JavaScript frameworks for validating input formats, providing various input GUIs, such as calendars for dates, sliders, etc. Frameworks such as jQueryUI, Dojo, and Sencha all provide a widget set for improving forms. Furthermore, it was time to take into account the specifics of mobile web applications, where the GUI of a date chooser cannot be the same as a 400x400 pixel wide calendar on a desktop. Contextual virtual keyboards provided the way forward on smartphones and tablets thanks to Apple, Google and others.

HTML5 took all this into account and now provides:


A new set of input fields that include a validation API and visual feedback, contextualized keyboards, etc. Of course the look and feel depends on the web browser's implementations, but the HTML5 forms specification introduced 13 new < input type=.../ > fields:  email, tel, color, url, date, datetime, datetime-local, month, week, time, range, number and search.

Built-in validation system: JavaScript API for custom validation, CSS pseudo classes that are useful for changing an input field style depending on the validity of the input.

Other goodies, such as the option to set an input field out of a < form >, new elements such as < datalist > for autocompletion, < output > for feedback, etc.

Examples of contextual keyboards are shown above; they differ depending on the type of  < input > fields in the < form >. In the example we can see: email, URL, and phone number. Look at the different keyboard layouts. The last picture is a date picker from an IOS phone.


##HTML5 form examples

INTRODUCTION

In this section, we will show you what can be achieved with recent HTML5 additions for forms. Try the examples, enter erroneous values, submit the forms, and see what happens.

There is a lot of course content covered this week, and before we get into all the details of the elements and attributes introduced by HTML5 we suggest playing with running examples of full featured forms.

THE EXAMPLES

These examples are creations by students from a previous version of this course, when it was hosted at the w3devcampus.com Web site (the W3C e-learning platform). They are given "as is". They use the geolocation API that will be presented in Week 6 for auto-filling the address input fields. This part will be explained next week.

Feel free to look at the source code, and do not hesitate to ask questions in the forum if you need explanations.

##Using input elements for a Web application GUI

This page's video shows that input elements, in particular the new elements introduced by HTML5, can be used as widgets to control the behavior of a Web application. In this situation, they do not need to be inside a <form> element. We just bind event listeners to them and we use them as client-side widgets.

##EXAMPLE 1: CHOOSE THE COLOR, LINE WIDTH AND SPEED OF AN ANIMATION

Bouncing rectangle without GUI (JS Bin) 
Bouncing rectangle with GUI (see screenshot at the top right of this page)
Same example as above, on JS Bin, that uses polyfills for IE and Safari (spectrum.js for making <input type=color> work, and a small JS polyfill for making Math.sign() work too...). This is a good example of using a polyfill.

##EXAMPLE 2: DATA VISUALIZATION CONTROL

*Forms are a way to get user input which is sent to a remote server. This section of the course focuses on the HTML5 additions to forms, and as such will only cover the client-side part.*

On the server side, you may have PHP, Java, C#, Ruby, Python, etc. components. There are several ways to collect server-side data from a form in a Web page: REST Web services, servlets, Microsoft ASP pages, etc.

On the client side, the forms indicate to which server and how the data should be sent,  using the action and method attributes respectively. A <button type="submit"> or an <input type=submit> field is used to submit the form content.

On the client side, the forms indicate to which server and how the data should be sent,  using the action and method attributes respectively. A < button type="submit" > or an < input type=submit > field is used to submit the form content.

For example: <form action="myServerCode.php" method="POST">...</form>. Here, we set the URL of the server side code (myServerCode.php), and the HTTP method that will be used by the browser for sending the form content (POST).

Another approach is to use JavaScript for sending the form content with Ajax.

This week, we will study the new elements and attributes offered by HTML5, and will also cover the new HTML5 form validation API.

##A FEW WORDS ABOUT PASSWORDS AND FORMS

Note: this part of the course has been added thanks to a contribution by one of the students: PaulObeda.

This course is about client side and HTML5. But we feel that it's important to give some advices when manipulating passwords. Between your browser and the server that will handle the data you entered in the input fields, there might be some proxies, some cache system: your passwords should not be stored there in plain text! We also recommend using HTTPS when your server sends an HTML page with a form that contains password fields, and we recommend that your server adds an encryption layer before storing the passwords in a database or in a file.

	The general rule for passwords is:  "Hash before send (client side)! Encrypt after receipt! (server side)"
	
This example loads publicly available cryptographic libraries, then applies an MD5 hash prior when the (login) form is submitted, returning true to continue normal form processing (submission to the server).

The server would still need to encrypt what it receives as it processed the form submission, but such a system ensures that what the user types as her password doesn't leave her computer, and what is received is further encrypted before being stored.

A secure connection (SSL / TLS) should still be used; hashing the password client side doesn't replace it. But there are cases where a proxy or firewall might be present in the connection, and hashing the password provides some additional privacy versus the password appearing in simple plaintext at that point.

The value is in making it harder to know the password clear text.

Enhancements could include using something known - perhaps a couple characters from the user name or id - as a salt to include in the hash. If the hash is salted, then even knowing the hash doesn't give access to other sites where the same technique (when the same password) is used.

##Creating accessible forms

*Forms are commonly used to enable user interaction in Web sites and Web applications. For example for login, registering, commenting, and purchasing*

Since HTML5 provides functionalities to assist with accessibility, developers should make a concerted effort to mark up Web based forms. The following two guidelines are to give you a good start to make your forms accessible:

For every form field, ensure that a descriptive label is provided and use the <label> element to identify each form control.

For larger or complex forms, use the <fieldset> and <legend> elements to respectively group and associate related form controls.

We will give usage examples for each of these two basic guidelines in the following pages.

FURTHER READING

The WAI Web site hosts a Forms tutorial where you will find more guidelines to follow in order to make your forms truly accessible: Form Instructions, Validating Input, User Notifications, Multi-Page Forms, and Custom Controls.

##Why is this important?

Forms can be visually and cognitively complex and difficult to use. Accessible forms are easier to use for everyone, including people with disabilities.

People with cognitive disabilities can better understand the form and how to complete it, as making forms accessible improves the layout structure, instructions, and feedback.

People using speech input can use the labels via voice commands to activate controls and move the focus to the fields that they need to complete.

People with limited dexterity benefit from large clickable areas that include the labels, especially for smaller controls, such as radio buttons and checkboxes.

People using screen readers can identify and understand form controls more easily because they are associated with labels, field sets, and other structural elements.

##Labeling controls

*LABELS NEED TO DESCRIBE THE PURPOSE OF THE FORM CONTROL*

Form fields and other form controls usually have visible labels, such as "E-mail Address:" as the label for a text field (see figure below).

When these labels are marked up correctly, people can interact with them using only the keyboard, using voice input, and using screen readers. Also, the label itself becomes clickable, which enables a person who has difficulty clicking on small radio buttons or checkboxes to click anywhere on the label text.

##ASSOCIATING LABELS EXPLICITLY

Whenever possible, use the label element to explicitly associate text with form elements. The for attribute of the label must exactly match the id of the form control. 

	<label for="first_name">Your First Name</label>
	<input id="first_name" type="text" name="fname"/>
	
Alternative example 1

Note that you can also include the <input> element inside the <label>...</label> element, and also add a <span lang="en"> for example, to indicate the language used in the label. Sometimes, nesting labels and inputs can also make CSS styling easier and produce better results with screen readers.

Source code (with <input> inside the <label>):

	<label for="first_name"><span lang:en">Your First Name</span>
		<input id="first_name" type="text" name="fname"/>
	</label>
	
Example 2 (click on the label "Subscribe to newsletter" to see the effect)

	<label for="firstname">First name:</label>
	<input type="text" name="firstname" id="firstname"><br>
	
	<label for="subscribe">Subscribe to newsletter</label>
	<input type="checkbox" name="subscribe" id="subscribe">
	
LABELING BUTTONS

The label of a < button > element is set inside the element and can include markup. This allows advanced accessibility hints to be included, such as marking up language change.

Example: < button >Mon < span lang="fr" >bouton</ span ></ button >, for a button with a label in French.

When using the <input> element to create buttons, the label is set in the value attribute of the element.

Example: <input type="submit" value="Please submit">, that will be rendered as a button.

Source code for an example of "Submit" and "Cancel" buttons:

	<button type="submit">Submit</button>
	<button type="button">Cancel</button>
 
	<input type="submit" value="Submit">
	<input type="button" value="Cancel">
	
#LABELING TEXT AREAS

	<label for="address">Enter your address:</label><br> <textarea id="address" name="addresstext"></textarea>
	
##Grouping controls
	

