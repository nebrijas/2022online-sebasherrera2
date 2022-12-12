# Actividad dirigida 3

A continuación, haremos un ejercicio de programación literaria utilizando un código de programación con Python que ya existe. A través de esta actividad nos adentraremos al mundo del *web scraping*.

## ¿Qué es *Web Scraping*?

El Web Scraping permite **analizar o manipular los datos extraidos más significativos de una o varias páginas web**. Lo anterior con el objetivo de crear una base de datos, generar alertas, analizar los enlaces de un sitio web, hacer una migración de un sitio web a otro, entre otros.

Algunas páginas entre más datos relevantes tengan, más rigurosos son al momento de dejar visible la información para evitar el web scraping, debido a que esta actividad puede considerarse "ilegal" ya que es información que se usa para el beneficio de quien la extrae.

## Instalación de librerías

Para realizar con éxito el web scraping lo primero que tenemos que hacer es instalar la librería con la función "!pip".


```python
!pip install requests bs4 pandas termcolor
```

    Requirement already satisfied: requests in c:\users\windows\anaconda3\lib\site-packages (2.28.1)
    Requirement already satisfied: bs4 in c:\users\windows\anaconda3\lib\site-packages (0.0.1)
    Requirement already satisfied: pandas in c:\users\windows\anaconda3\lib\site-packages (1.4.4)
    Requirement already satisfied: termcolor in c:\users\windows\anaconda3\lib\site-packages (2.1.1)
    Requirement already satisfied: charset-normalizer<3,>=2 in c:\users\windows\anaconda3\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\windows\anaconda3\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\windows\anaconda3\lib\site-packages (from requests) (1.26.11)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\windows\anaconda3\lib\site-packages (from requests) (2022.9.14)
    Requirement already satisfied: beautifulsoup4 in c:\users\windows\anaconda3\lib\site-packages (from bs4) (4.11.1)
    Requirement already satisfied: pytz>=2020.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2022.1)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\windows\anaconda3\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: six>=1.5 in c:\users\windows\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
    Requirement already satisfied: soupsieve>1.2 in c:\users\windows\anaconda3\lib\site-packages (from beautifulsoup4->bs4) (2.3.1)
    

## Librerías

Ahora, importaremos las librerías de la siguiente manera:

Importamos de la librería la función requests para hacer peticiones de datos:


```python
import requests
```

Importamos time para el tiempo horario y hacer peticiones en tiempos determinados:


```python
import time
```

Importamos la función csv para leer y escribir datos tabulares:


```python
import csv
```

Importamos la función re, es decir, patrones de coincidencia de texto descritos con una sintaxis formal:


```python
import re
```

Importamos la función BeautifulSoup para extraer datos de archivos HTML y XML:


```python
from bs4 import BeautifulSoup
```

Importamos la función os, la cual provee una manera versátil de usar funcionalidades dependientes del sistema operativo:


```python
import os
```

Importamos la librería Pandas con el abreviado estándar para hacer referencia a pandas as:


```python
import pandas as pd
```

Importamos desde termcolor la función colored que permite imprimir texto en color:


```python
from termcolor import colored
```

## Crear variable

Crearemos una variable para tener control de nuestros resultados. Las variables se asignan con el símbolo "=". En este caso se denominará "resultados". Cabe mencionar que los corchetes ([]), que van despúes de "=", se usan para la definición de listas, para el acceso de lectura a los elementos de listas, y para el acceso de escritura a listas y diccionarios. También para la definición de funciones e invocación.


```python
resultados = []
```

## Acceso a los datos

A continuación, haremos una petición para obtener los datos y de esa manera avanzar con el *scraping*. En este caso se descargará únicamente la información de El País. Para ello utilizaremos la función requests.get.


```python
req = requests.get("https://resultados.elpais.com")
```

## Condicional

Ahora, le pondremos un condicional con el que nos aseguraremos que los resultados que pedimos sean los que queremos. En este caso le estamos pidiendo que el valor de regreso que no sea 200 nos arroje un error.


```python
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
```

## Agregamos librería

La librería Beautiful Soup de Python sirve para analizar documentos HTML. Esta biblioteca crea un árbol con todos los elementos del documento y puede ser utilizado para extraer información. Además utilizaremos una variable denominada "soup".


```python
soup = BeautifulSoup(req.text, 'html.parser')
```

Agregaremos una nueva variable para que traiga únicamente la información que le solicitamos. Esta vez queremos encontrar todas las etiquetas "h2".


```python
tags = soup.findAll("h2")
```

De la siguiente manera le pediremos que nos imprima los textos que necesitamos. Además, agregaremos "resultados.append(h2.text)" con el cual se añaden todos los textos dentro de las etiquetas a la lista que hemos creado.


```python
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    El Mundial, en vivo
    Universo Mundial
    El calendario a seguir desde América
    ¿Quién va a ganar? Simulador y pronóstico de cada selección 
    La ‘newsletter’
    Radiografía del descontento chino
    El Metro de Bogotá pone la primera piedra tras mil proyectos, cero estaciones y una discusión eterna
    Lula da a su esposa Rosangela Silva protagonismo en la transición en Brasil
    Radiografía a Carabineros de Chile tres años después del estallido social
    El régimen de excepción de Nayib Bukele asfixia a las pandillas: “Policías y soldados tienen poder absoluto” 
    Una esperanza bajo tierra: tras el último rastro de los migrantes desaparecidos rumbo a Estados Unidos
    La reinvención de la extrema derecha en América Latina
    Las mareas subterráneas de la ola rosa latinoamericana
    Messi lleva a hombros a Argentina ante Australia (2-1)
    Al estilo argentino
    Rashford quiere volver a los penaltis
    Tuteladas, discriminadas: así vive la mujer de Qatar
    Una nueva generación de escritores latinoamericanos restablece los puentes con España
    Las nuevas voces que se abren paso en la FIL de Guadalajara
    Un libro en las manos para no sentirse solo
    Cuáles son las opciones para una negociación entre Rusia y Ucrania
    La caravana de la muerte de Kurilivka: una superviviente relata la matanza de 26 civiles que huían de la guerra
    “Jugamos al rugby para transformar vidas”: el deporte que desarticuló 11 bandas delictivas de Venezuela
    Un discurso de Allende para las nuevas generaciones
    La filósofa Amia Srinivasan: “Las mujeres deben ser iguales... ¿a qué clase de hombres?
    Ciencia a toda velocidad: los años increíbles en los que hubo más coches eléctricos que de gasolina
    Oriol Vinyals: “Nuestra generación verá una inteligencia artificial que iguale o supere a la del ser humano”
    Las mentiras que dinamitaron la carrera de The Doors
    Ideas de regalos para el jardinero
    Guía de regalos para el ‘foodie’
    La supervivencia de la sabana brasileña se decide en los despachos de Bruselas
    El ‘palacio’ de la familia Orbán se erige como símbolo de la corrupción en Hungría
    Los libaneses ‘roban’ su propio dinero en los bancos a punta de pistola y con bidones de gasolina
    Cuba, el precipicio y el cambio pendiente
    Marcela Ángel: “Tenemos que cerrar la brecha entre academia y territorio”
    El exitoso colegio chileno que forma “agentes frente al cambio climático”
    Pacientes de VIH contra Guatemala: “Si fuera por el Estado, estaríamos muertos”
    José Antonio Marina: “Que se haya puesto de moda la felicidad es catastrófico”
    El Padre, El Hijo y El Espíritu Santo de ella
    El trágico final de Gérard Philipe, el ‘príncipe de actores’ al que la Nouvelle Vague ninguneó
    Las vidas largas
    Historia de un robo: así se recuperó un manuscrito firmado por Hernán Cortés hace casi 500 años
    ¿Selfie sí o selfie no en Art Basel?
    De las galerías a las calles: así se hizo importante Miami para el arte del mundo
    Cómo el pacto de dos amigas logró que Fleetwood Mac sobreviviera al caos, el sexismo y la cocaína
    La vida bajo los focos de Sadie Sink: una infancia en Broadway y una adolescencia en ‘Stranger Things’
    Todos quieren a Dwayne Johnson
    Shakira niega una relación sentimental con su instructor de surf: “No tengo ninguna pareja”
    El ‘conseguidor’ español que sedujo a las constructoras en América
    Las islas del Caribe colombiano que desaparecen por el cambio climático
    La tragedia en la frontera de Melilla: el papel de Marruecos y España en las muertes del 24-J
    Un tatuaje y un bebé en el nombre de Mircea Cărtărescu
    Qatar 2022, el único Mundial donde es posible ver dos partidos en un mismo día
    ¿Qué estrella tuvo el mejor debut en el Mundial? El ‘tier list’ de Jesús Gallego, Bruno Alemany y Aritz Gabilondo
    Enredados en el Mundial | Los jugadores iraníes vuelven a cantar el himno y ha nacido una estrella en EE UU
    El negocio de la nostalgia del fútbol en Colombia
    ‘Tu opinión es una mierda’: la campaña que alerta sobre los peligros de la polarización
    Venezuela tiene escasez de sacerdotes
    Why Russia-Ukraine peace talks won’t be happening anytime soon  
    Following the FTX bankruptcy, an expert liquidator has been searching for all the missing money 
    How Nazi propaganda dehumanized Jews to facilitate the Holocaust
    Joseph Henrich, evolutionary anthropologist: ‘The best antidote to white supremacy is more science’   
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Toda la actualidad científica en el boletín de Materia
    Letras Americanas: la actualidad literaria de un continente vista por el escritor Emiliano Monge
    Ideas: reportajes y entrevistas para entender el mundo
    China relaja las medidas anticovid en Guangzhou para frenar nuevas protestas
    Hungría evita la confrontación con Bruselas y confía en desbloquear los fondos europeos en 2023 
    Muere el expresidente de China Jiang Zemin
    López Obrador da su aprobación para que ‘el rey del cobre’ Germán Larrea compre Banamex
    Los desafíos al proceso de transición ecológica
    Estos picos han enamorado al chef José Andrés y están hasta en las mesas de Corea del Sur
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Mirian Galán, una de las mejores profesoras del mundo: “El niño no falla. Si suspende, ha suspendido el docente” 
    ¿Adiós a los anuncios con coches para niños y cocinas para niñas? Los jugueteros pactan desterrar los estereotipos sexistas en la publicidad
    La respuesta a la guerra en Ucrania también es literaria
    Lo más escuchado en Spotify en 2022: solo Rosalía se coloca en España en una lista dominada por hombres latinos
    Muere Christine McVie, cantante y teclista de la legendaria banda Fleetwood Mac, a los 79 años
    Bill Hansson, experto en olfato: “No compres feromonas para intentar conseguir sexo, no funciona. Mejor trabaja en tu personalidad”
    Javier de Felipe, neurocientífico: “Me encantaría ser un perro durante un par de minutos” 
    Un proyecto enseña a los robots a crear nuevas herramientas, como los primeros humanos
    Haliburton alumbra Indiana
    ‘Vivir con miedo’, por Daniel Verdú
    Brasil entierra un tabú homófobo de casi un siglo y alinea a un futbolista con el 24
    El medio ambiente tensiona a los socios del Gobierno valenciano 
    Los drones que sobrevuelan el futuro de la agricultura
    100 euros por un caballo viejo para hacerlo filetes: la Guardia Civil desarticula una red que producía carne equina no apta para consumo
    Oriol Vinyals: “Nuestra generación verá una inteligencia artificial que iguale o supere a la del ser humano”
    “Ser malos”, Sam Va Lentín y el hilo de Bartual: los tuits que merecen pasar a la historia de internet
    Desafíos criptográficos: epílogo y solución del último reto
    La Policía señala Valladolid como posible provincia de origen de los seis sobres con artefactos pirotécnicos 
    Las discrepancias en seis artículos ralentizan el tramo final de la reforma de la ‘ley mordaza’
    El nombramiento del exministro Campo que el PP denuncia ante Bruselas es común en Francia, Alemania, Italia y Bélgica
    ‘Masterchef’ contra el teletrabajo
    Belén Barenys, protagonista de ‘Autodefensa’: “Ninguna de mis amigas tiene una relación normal con el sexo o con los hombres”
    ‘MasterChef’ cocina con la polémica como ingrediente estrella
    Shakira y Piqué sellan su acuerdo de separación en Barcelona ante el juez
    Los actores de ‘Love Actually’ se reencuentran: ¿qué ha sido de ellos 19 años después?
    Acuerdo de divorcio entre Kim Kardashian y Kanye West: custodia compartida y 200.000 dólares de pensión
    Becky G: cómo alcanzar el sueño americano cantando en español
    Un viaje por el Maine de Stephen King
    La polarización es como las drogas: engancha
    Descansar está mal visto: el arte perdido del reposo
    Madrid, la nueva Miami: así se han hecho con la capital los ricos latinoamericanos
    Si no tiene ahorros, esta es una de las pocas alternativas para comprar casa
    Roe Ethridge, el fructífero intercambio entre el arte y el comercio
    ‘La última vez’, de Guillermo Martínez: un laberinto con final milagrosamente imprevisible
     “En Somalia, cuando aún estamos tratando de reponernos de un golpe, enseguida nos viene el siguiente”
    Una agricultura climáticamente inteligente para resistir a las turbulencias económicas y sociales  
    Oyambre, Son Bou y otras nueve playas españolas para un baño de historia
    Cómo actuar ante el caos de los aeropuertos: qué hacer frente a retrasos y cancelaciones de un vuelo
    El lamentable caso de Anne Hathaway o por qué se odia a algunas famosas sin justificación ninguna
    Samantha Hudson: “Me va bien económicamante, pero no soy Paula Echevarría”
    “Tobogán de piojos”, “genocida de oxígeno”... Por qué cada Mundial recuerda el poderío del español como idioma para insultar
    Alejandro Jato, el actor que será Camilo Sesto: “Da pena la imagen que los jóvenes tienen de él, con lo grande que fue”
    Menú semanal de El Comidista (5 a 11 de diciembre)
    Té para todos: 13 tiendas especializadas donde comprarlo en España
    Inversión verde: pros y contras de una estrategia en revisión
    Iturralde González explica el segundo gol de Japón: “Las imágenes que salen son muy tramposas”
    'The Economist' sorprende al analizar así la situación política de España y decir esto de Sánchez
    Cunha, rumbo a la Premier
    Twitter, TikTok y el algoritmo polarizador. nostalgia de la cámara de eco
    Las mejores películas de la Historia del Cine según la mítica revista del BFI
    

## Repetición

Este mismo proceso se repetirá en las diferentes secciones de las que queremos extraer la información. Por ejemplo, sección "internacional".


```python
req2 = requests.get("https://elpais.com/internacional")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup2 = BeautifulSoup(req2.text, 'html.parser')

tags = soup2.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    Radiografía del descontento chino
    La caravana de la muerte de Kurilivka: una superviviente relata la matanza de 26 civiles que huían de la guerra en Ucrania
    Los libaneses ‘roban’ su propio dinero en los bancos a punta de pistola y con bidones de gasolina
    ¿‘Nuestros’ principios o los de todos?
    China hierve contra la covid cero
    Una globalización centrada en los seres humanos
    Autocracia en crisis
    “¿De qué color es el hambre, mamá?”
    El régimen de excepción de Nayib Bukele asfixia a las pandillas: “Policías y soldados tienen poder absoluto” 
    El ‘palacio’ de la familia Orbán se erige como símbolo de la corrupción en Hungría
    Por qué la negociación para la paz en Ucrania queda lejos
    La UE acuerda imponer un tope de 60 dólares al petróleo ruso para golpear las finanzas del Kremlin
    Más de 400 rusos buscan protección en España: “No quiero formar parte de este crimen contra Ucrania”
    El tope al petróleo ruso: un golpe más para Moscú, pero lejos de ser letal
    Zelenski pide prohibir en Ucrania la Iglesia ortodoxa apadrinada por Rusia
    Rusia apunta en su primera lista negra a las organizaciones LGTBI e incluirá a los críticos con el alistamiento militar 
    El boyante negocio de vender equipación militar en Ucrania: “Lo que más compran es ropa térmica; ya hace frío”
    Las protestas en China se refugian en las redes sociales de Occidente
    Corea del Norte vive un frenesí armamentístico con el lanzamiento de casi 70 misiles en 2022
    Nueva York, el gran supermercado legal de la marihuana
    Cuba, el precipicio y el cambio pendiente
    Lula negocia con el Congreso de Brasil cómo pagar su gran promesa electoral
    Reaparece el fantasma del control de precios en Venezuela con el repunte de la inflación
    El feminicidio de García Belsunce sigue impune: la justicia argentina absuelve al imputado
    

También lo podríamos hacer con la sección de "opinión".


```python
req3 = requests.get("https://elpais.com/opinion")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup3 = BeautifulSoup(req3.text, 'html.parser')

tags = soup3.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    China se mueve 
    El malestar de los médicos
    Naufragios de la ciencia española
    El castigo a Ucrania
    ‘A compás’
    La ciudad cambia o caduca
    Feijóo: luna decreciente
    ¿‘Nuestros’ principios o los de todos?
    Newman, Marías, la posteridad
    ¡Al suelo!
    Saquen a la cultura del lodazal
    Hungría: democracia o multa
    Repatriación urgente de las familias de yihadistas
    En el espejo del cine
    El sexo (todavía) importa (demasiado)
    El Roto
    Flavita Banana
    Riki Blanco
    Peridis
    Sciammarella
    Envía tu carta
    Protestas en China e Irán
    La salud es más importante que la báscula
    Así funciona la corrupción
    Noticias positivas en tiempos caóticos
    Bomba nuclear en Barcelona
    Una maldita lista en tiempos airados
    El defensor del lector contesta
    

## Limpieza de la pantalla

Usaremos la función "os.system(clear)" para que se haga una limpieza después del *scraping*. Este paso es necesario para que el trabajo de impresión se haga de manera adecuada.


```python
os.system("clear")
```




    1



Posteriormente, jugaremos un poco con el estilo. Todos los titulares que tengan la palabra “Feminismo” tendrán un color verde y **negrita**. Utilizaremos la función **join**, la cual convierte una lista en una cadena formada por los elementos de la lista separados por comas.


```python
print(colored("A continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:", 'blue', attrs=['bold']))
print(colored("Feminismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "feminismo" in s]
print("\n".join(str_match))
```

    A continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:
    Feminismo
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    

Este proceso se puede repetir con las demás palabras que se requieran en secciones específicas.


```python
print(colored("Igualdad", 'green', attrs=['bold']))

str_match = [s for s in resultados if "igualdad" in s]
print("\n".join(str_match))

print(colored("Mujeres", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujeres" in s]
print("\n".join(str_match))

print(colored("Mujer", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujer" in s]
print("\n".join(str_match))

print(colored("Brecha salarial", 'green', attrs=['bold']))

str_match = [s for s in resultados if "brecha salarial" in s]
print("\n".join(str_match))

print(colored("Machismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "machismo" in s]
print("\n".join(str_match))

print(colored("Violencia", 'green', attrs=['bold']))

str_match = [s for s in resultados if "violencia" in s]
print("\n".join(str_match))

print(colored("Maltrato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "maltrato" in s]
print("\n".join(str_match))

print(colored("Homicidio", 'green', attrs=['bold']))

str_match = [s for s in resultados if "homicidio" in s]
print("\n".join(str_match))

print(colored("Género", 'green', attrs=['bold']))

str_match = [s for s in resultados if "género" in s]
print("\n".join(str_match))

print(colored("Asesinato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "asesinato" in s]
print("\n".join(str_match))

print(colored("Sexo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "sexo" in s]
print("\n".join(str_match))
```

    Igualdad
    
    Mujeres
    La filósofa Amia Srinivasan: “Las mujeres deben ser iguales... ¿a qué clase de hombres?
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    La filósofa Amia Srinivasan: “Las mujeres deben ser iguales... ¿a qué clase de hombres?
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Mujer
    Tuteladas, discriminadas: así vive la mujer de Qatar
    La filósofa Amia Srinivasan: “Las mujeres deben ser iguales... ¿a qué clase de hombres?
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Tuteladas, discriminadas: así vive la mujer de Qatar
    La filósofa Amia Srinivasan: “Las mujeres deben ser iguales... ¿a qué clase de hombres?
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Brecha salarial
    
    Machismo
    
    Violencia
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Maltrato
    
    Homicidio
    
    Género
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Para acabar con la violencia de género, necesitamos más mujeres en posiciones de poder 
    Asesinato
    
    Sexo
    Bill Hansson, experto en olfato: “No compres feromonas para intentar conseguir sexo, no funciona. Mejor trabaja en tu personalidad”
    Belén Barenys, protagonista de ‘Autodefensa’: “Ninguna de mis amigas tiene una relación normal con el sexo o con los hombres”
    Bill Hansson, experto en olfato: “No compres feromonas para intentar conseguir sexo, no funciona. Mejor trabaja en tu personalidad”
    Belén Barenys, protagonista de ‘Autodefensa’: “Ninguna de mis amigas tiene una relación normal con el sexo o con los hombres”
    El sexo (todavía) importa (demasiado)
    

### Conclusiones: 
Esta actividad nos ha permitido extraer información de El País de manera rápida y sencilla. Hemos utilizado y combinado los lenguajes Python y Markdown que permiten utilizar la interfaz web de código abierto Jupyter.

Esta técnica es muy útil para recopilar datos de contacto o información especial con gran rapidez. Funciona muy bien si queremos desarrollar un proyecto en poco tiempo y estar por encima de nuestra competencia. 

Finalmente, cabe mencionar que el scraping es muy importantes para mantener la historia de Internet. Las iniciativas de archivado web se basan mayoritariamente en esta técnica.
