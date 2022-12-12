# Trabajo final

## Metodología 
Este trabajo tiene como propósito explicar de qué manera se realizaron las actividades de la asignatura Periodismo de Datos II, las cuales relacionan lenguajes Markdown y Python. Quedará en evidencia el avance que los estudiantes tuvimos con el desarrollo de los ejercicios durante el transcurso de la clase.

Es importante mencionar que el desarrollo de estas tareas derivó en la creación de una página HTML en la que se puede navegar y explorar el contenido. Algunos conocimientos previos durante el máster se complementaron de manera articulada para entregar el resultado. Este trabajo final se ha ido realizando de manera paralela con los demás ejercicios y recolecta lo mejor de lo aprendido. 

### Actividad Dirigida 1

La primera actividad dirigida consistió en realizar un **comentario crítico sobre una pieza de periodismo de datos, visualización de datos o infografía**. El reto fue comenzar a escribir en lenguaje Markdown y respetar la cantidad de palabras solicitadas (entre 300 y 500).

Debido a la falta de conocimiento sobre este tipo de sintaxis, tuve que [revisar las notas creadas por el profesor Adolfo Antón Bravo en Github](https://blog.infotics.es/2015/11/11/editor-de-textos/). De esta manera, adquirí cierto entendimiento para crear el texto. Para la visualización del texto descargué y utilicé Visual Studio Code, un editor de código fuente que permite, entre otras cosas, escribir y visualizar lenguaje Markdown.

En mi caso, [seleccioné un artículo del periódico El Espectador, de Colombia, titulado “Así vive la niñez en Colombia”,](https://www.elespectador.com/colombia/mas-regiones/infografia-asi-vive-la-ninez-en-colombia-article/#) el cual muestra a través de una infografía la cantidad de menores de edad que viven en situación de vulnerabilidad en el país. 
Con el desarrollo de esta actividad **aprendí sobre la sintaxis de este lenguaje**. Puntualmente, pude utilizar encabezados de primer, segundo y tercer nivel con numerales; poner negritas con asteriscos; embeber imágenes en el artículo y enlazar textos.

El escrito original lo redacté en Word y después lo copié en la plataforma [GitHub](https://github.com/), utilizando la sintaxis mencionada anteriormente. Cabe mencionar que este portal funciona como un repositorio online gratuito que sirve para gestionar diferentes proyectos y controlar versiones de códigos fuente, por lo que **funciona para escribir lenguaje Markdown**.

Con la ad1, como se llamó la primera actividad, pudimos crear un documento de extensión .md y conseguimos familiarizarnos con la plataforma. A través de esta práctica también aprendimos a manipular el archivo README.md, el cual contiene información acerca de otros archivos en el directorio.

[Dé clic aquí para ver la Actividad Dirigida 1](https://nebrijas.github.io/2022online-sebasherrera2/ad1.html).

### Actividad Dirigida 2

La segunda actividad fue similar a la primera, solo que en esta ocasión ya teníamos algunas bases para escribir un texto mejor y con una sintaxis más limpia. Consistió en realizar **un comentario en leguaje Markdown de 500 a 700 palabras** de un artículo o reportaje de periodismo y visualización de datos.

En esta ocasión analicé un reportaje de datos titulado [“Radiografía del VIH en Colombia: 134 mil personas viven con el virus”](https://www.eltiempo.com/datos/dia-del-vih-datos-de-la-enfermedad-en-colombia-y-en-el-mundo-722330) de El Tiempo, de Colombia, en donde se hablaba del panorama que vive el país frente a este virus. La pieza periodística **ostraba cifras, información de fuentes oficiales y gráficos por cada región del país**. 

Nuevamente los estudiantes tuvimos que subir la ad2 Github con el propósito de seguir retroalimentando nuestro repositorio. Con el fin de demostrar un mayor conocimiento respecto a la actividad anterior, decidí hacer una mayor utilización de los enlaces, las fuentes oficiales y las imágenes de referencia.

[Dé clic aquí para ver la Actividad Dirigida 2](https://nebrijas.github.io/2022online-sebasherrera2/ad2.html).

### Actividad Dirigida 3

Luego de adquirir algunos conocimientos sobre el Markdown y conocer la plataforma Github, entramos en un lenguaje más complejo. Tuvimos que transformar uno de los ejercicios que se hicieron en programación, un código de Python para lograr un scraping de una web, **en un ejercicio de programación literaria con [Jupyter](https://jupyter.org/)**.

Lo primero para realizar la tercera actividad fue instalar el programa **Anaconda**, desde allí pudimos ingresar al programa Júpiter y realizar el ejercicio de programación literaria. La idea fue crear una hoja de ruta de fácil lectura sobre un texto tipo código que el profesor nos entregó en clase. 

El scraping que se utilizó fue el del diario [El País](https://elpais.com/?ed=es). El objetivo final era encontrar el resultado mejor posicionado en dicha web, dependiendo la búsqueda que se hacía en ella y basándose en los tags que se usan al momento de publicar contenido en un medio de comunicación.

El desarrollo de esta actividad me permitió saber qué **librerías existían**, las cuales permiten leer código Python. Algunas de ellas fueron: 

**csv**: Valores Separados por Comas es un formato habitual que se utiliza para importar y exportar hojas de cálculo y bases de datos. Es común trabajarlos en Excel. 

**re**: Proporciona operaciones de coincidencia de expresiones regulares similares a las encontradas en Perl.

**time**: Permite varias funciones relacionadas con el tiempo. Para la funcionalidad relacionada, consulte también los módulos datetime y calendar.

**os**: Rrovee una manera versátil de usar funcionalidades dependientes del sistema operativo.


**termcolor**: Es una biblioteca que sirve para imprimir mensajes de colores en el terminal.

**bs4**: Funciona como una biblioteca de la cual podemos obtener datos en formato HTML y XML.


**requests**: Se utiliza para hacer solicitudes y peticiones a la página de la que extraeremos datos.


**Pandas**: Es una herramienta de análisis de datos de código, de lectura rápida en el lenguaje de programación de Python.

A continuación, se muestra cómo se instalaron las librerías:


```python
!pip install requests bs4 pandas termcolor
```

    Requirement already satisfied: requests in c:\users\windows\anaconda3\lib\site-packages (2.28.1)
    Requirement already satisfied: bs4 in c:\users\windows\anaconda3\lib\site-packages (0.0.1)
    Requirement already satisfied: pandas in c:\users\windows\anaconda3\lib\site-packages (1.4.4)
    Requirement already satisfied: termcolor in c:\users\windows\anaconda3\lib\site-packages (2.1.1)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\windows\anaconda3\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\windows\anaconda3\lib\site-packages (from requests) (1.26.11)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\windows\anaconda3\lib\site-packages (from requests) (2022.9.14)
    Requirement already satisfied: charset-normalizer<3,>=2 in c:\users\windows\anaconda3\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: beautifulsoup4 in c:\users\windows\anaconda3\lib\site-packages (from bs4) (4.11.1)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: pytz>=2020.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2022.1)
    Requirement already satisfied: six>=1.5 in c:\users\windows\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
    Requirement already satisfied: soupsieve>1.2 in c:\users\windows\anaconda3\lib\site-packages (from beautifulsoup4->bs4) (2.3.1)
    

Posteriormente, tuvimos que crear una variable, según el código fuente. En este caso, a la variable se le llamó resultado, sin embargo, teniendo en cuenta que esta puede cambiar, podía tener el nombre que se quisiera. Después agregamos requests.get, una función que permite arrastrar los resultados de El País.

Adicionalmente, utilizamos la librería Beautiful Soup, la cual contribuye a extraer datos de archivos como HTML y XML y proporciona formas de navegar, buscar y modificar la información obtenida si es instalada correctamente en nuestro documento Python. Nuevamente subimos el ejercicio a Github.

[Dé clic aquí para ver la Actividad Dirigida 3](https://nebrijas.github.io/2022online-sebasherrera2/ad3.html).

### Actividad Dirigida 4

La cuarta y última actividad consistía en trabajar con los [datos de la API de datos del COVID-19](https://covid19api.com/). A través de esta práctica pudimos crear tablas y gráficos en Jupyter. 

Debíamos analizar los datos de Colombia, España, Ecuador y República Dominicana. Posteriormente, realizar gráficos donde se podía visualizar el crecimiento de los casos COVID para las fechas 2021-2022. Así se realizó el trabajo:

**Primer paso**: Importar las librerías Pandas 


```python
!pip install pandas
```

    Requirement already satisfied: pandas in c:\users\windows\anaconda3\lib\site-packages (1.4.4)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2022.1)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: six>=1.5 in c:\users\windows\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
    

**Segundo paso**: Configurar Pandas con pd.



```python
import pandas as pd

miurl = "https://api.covid19api.com/countries"
```

**Tercer paso**: Ejecutar Pandas y generar el dataframe. La abreviatura de dataframe es df. Con función read_json() que lee el formato json. Dentro del paréntesis ponemos lo que queremos leer. 


```python
df = pd.read_json(miurl)
```

**Cuarto paso**: Crear los gráficos, elegir los datos que se usarán, ubicar la fecha en un vector y el número de casos en la otra. El último paso para el gráfico consiste en darle a nuestros dos ejes seleccionados la función plot para que se ilustren. para finalizar, le damos a los 2 ejes la función plot para hacer la graficación.

**Quinto paso**: El último paso es titular nuestro gráfico con title=.


[Dé clic aquí para ver la Actividad Dirigida 4](https://nebrijas.github.io/2022online-sebasherrera2/ad4.html).


```python

```
