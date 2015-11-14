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
	
*El < summary > ... </ summary > está dentro de un < details > ... </ details > elemento. Al hacer clic en el icono a la izquierda del resumen, el contenido de la <details> valor se muestra / oculta.*

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
	
