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
	
*El vídeo de YouTube embebido en esta página el código de seguridad: es HTML5, pero no es un elemento < video > directamente insertado en el HTML de esta página, es un <iframe>:*

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
