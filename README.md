# dpreview.com 

Práctica 2 de la asignatura *"Tipología y ciclo de vida de los datos"* del [Máster en Ciencia de Datos de la UOC](https://estudios.uoc.edu/es/masters-universitarios/data-science/presentacion)

Este respositorio se corresponde al entregable de la práctica 2 de la asignatura de la UOC Tipología y Ciclo de Vida de los Datos.

El entregable consiste en un análisis del *dataset* sobre los datos proporcionador por el scraper de cámaras digitales de dpreview.com que se realizó en la práctica anterior.
Limpieza de los datos proporcionados por el scraper de cámaras digitales de dpreview.com.

Se ha querido proseguir con el proyecto para realizar todo el ciclo de vida de un proyecto de análisis de datos, desde su captación hasta su análisis. Debido a esto, veremos que se ha realizado una extensa limpieza, para después realizar un breve análisis exploratorio junto a la aplicación de diversas pruebas estadísticas.

# Autores

* Miquel Rived 

# Ficheros del proyecto

En este repositorio se encuentran los siguientes ficheros:

* PRA2.rmd : El código fuente del *notebook* se puede consultar [aquí](https://github.com/miquelrivedmartinez/pra2_dpreview_cleaning/blob/main/PRA2.Rmd). 
* PRA2.pdf: El resultado de la ejecución del *notebook* se puede consultar [aquí](https://github.com/miquelrivedmartinez/pra2_dpreview_cleaning/blob/main/PRA2.pdf). En este archivo se pueden ver las respuestas a las preguntas dadas en el enunciado de la práctica
* dpreview.csv: El archivo csv a partir del cual se ha realizado la limpieza se puede consultar [aquí](https://raw.githubusercontent.com/miquelrivedmartinez/pra2_dpreview_cleaning/main/dpreview.csv)
* dpreview_clean.csv: El archivo csv limpio se puede consultar [aquí](https://github.com/miquelrivedmartinez/pra2_dpreview_cleaning/blob/main/dpreview_clean.csv)

# Descripción del dataset. ¿Por qué es importante y qué pregunta/problema pretende responder?

El dataset empleado en esta práctica es el obtenido en la PRA1 del semestre pasado y es el resultado de un proceso de *scraping* de la web de *reviews* de cámaras digitales dpreview.com. Contiene 2490 registros con 125 columnas de tipo numérico y categórico, representando cada fila una cámara digital. 

Lo más interesante del conjunto de datos extraído es la gran cantidad de especificaciones diferentes que se encuentran, así como el gran abanico de cámaras digitales que lo abarcan, además de que al haber sido extraídas de una web, constituyen datos reales referentes a cámaras.

En primer lugar se quiere analizar que características técnicas afectan más en el aumento de precio de una cámara digital.

Por otro lado, se tratará de determinar qué cámaras son las más valoradas por los usuarios o los expertos, por lo que se pretenderá analizar las marcas más valoradas, si el precio influye en la valoración final, o que tipo de especificaciones son las que buscan los usuarios en una cámara digital para realizar una valoración alta.

Los datos permiten responder a preguntas del tipo:

* ¿Cuál es la cámara mejor valorada por los usuarios?
* ¿Cuál es la cámara más cara y más ergónomica?
* ¿Qué cámara es capaz de disparar más fotografías en modo ráfaga?
* ¿Cuál es la cámara con GPS más ligera y mayor autonomía de batería?

Estas preguntas pueden variar a lo largo de las prácticas, ya que disponemos de una gran variedad de cámaras y campos para analizarlas que seguro que al visualizar con mayor detenimiento nos hacen hacernos nuevas preguntas.

La diferencia principal con los otros estudios encontrados de dpreview.com es la gran variedad de campos que hemos seleccionado para analizar las cámaras.

# Integración y selección de los datos de interés a analizar

Este ejercicio se ha resuelto en el fichero de código, dónde se puede ver como se han seleccionado los datos, para luego seleccionar las columnas que utilizaremos más adelante, dar el formato adecuado a estas columnas, y por último mostrar un breve resumen de las diferentes variables del dataset.

# Limpieza de Datos

Este ejercicio se ha resuelto en el fichero de código

## ¿Los datos contienen ceros o elementos vacíos? ¿Como gestionarías cada uno de estos casos?

Primero se han comprobado los elementos con valores vacíos, para a continuación asignarles un 'NA'.

Todas las variables con más de un 90% de valores NA han sido eliminadas, además de eliminar todas las filas cuyo precio sea nulo (ya que es la variable principal que se va a analizar).

En cuanto a valores vacíos, se ha imputado la media de la misma marca y tipo de cuerpo, en caso de que sigan siendo 'NA' se ha imputado la media de la marca, y en caso de seguir siendo NA, se ha imputado la media global.

## Identificación y tratamiento de valores extremos

Se han identificado los valores extremos, aunque se ha comprobado que son datos reales extraídos de la web, por lo que no se les ha hecho ningún tratamiento en particular.

# Análisis de los Datos

Este ejercicio se ha resuelto en el fichero del código

## Selección de los grupos de datos que se quieren analizar/comparar (planificación de los análisis a aplicar)

En primer lugar se seleccionan los datos que se quieren analizar/comparar. En este ejercicio, el objetivo es realizar los análisis exploratorios que se han determinado en el primer apartado.

Para ello se realizará la comprobación de normalidad y homogeneidad de la varianza.

Análisis estadístico para comparar los grupos de datos:
* Análisis del precio en función del tipo de cuerpo
* Análisis del tipo de sensor por fecha de lanzamiento
* Análisis de la evolución del tipo de cuerpo.
* Comparación de valoración de los usuarios entre cámaras Canon y Nicon
* Creación de modelo para predecir la puntuación general de una cámara
* Creación de modelo para predecir el precio de una cámara

## Comprobación de la normalidad y homogeneidad de la varianza

La comprobación de la normalidad es necesaria para poder realizar análisis posteriores como por ejemplo el contraste de hipótesis.
Para la comprobación de la normalidad nos basaremos en el teorema del límite central, según el cual una muestra mayor de 30 se podrá considerar que sigue una distribución normal.

Se ha comprobado la normalidad, viendo que todas las muestras superan las 30 muestras, y la homogeneidad de la varianza mediante el test de Barlett.

## Aplicación de pruebas estadísticas para comparar los grupos de datos. En función de los datos y el objetivo del estudio, aplicar pruebas de contraste de hipótesis, correlaciones, regresiones, etc. Aplicar al menos tres métodos de análisis diferentes.

El análisis y las pruebas se pueden ver en el fichero de código. Las pruebas que se han realizado son la correlación entre variables, un análisis exploratorio mediante gráficos, pruebas de hipótesis, regresiones lineales y correlaciones.

# Representación de los resultados a partir de tablas y gráficas

Los resultados se han ido representando a lo largo del código con tablas y gráficas.

# Resolución del problema. A partir de los resultados obtenidos, ¿Cuáles son las conclusiones? ¿Los resultados permiten responder al problema?

Creemos que el dataset con el que se ha trabajado en esta práctica resulta ideal para los objetivos de la misma. Es un *dataset* que requiere mucho tratamiento de limpieza, extracción de valores y conversión de tipos. El hecho de que no sea un *dataset* académico clásico imposibilita encontrar referencias de trabajos previos de limpieza.

Los datos, una vez tratados, nos han servido para elaborar modelos, que aunque con baja precisión, se podrían emplear para realizar predicciones.

En cuanto a las conclusiones que hemos obtenido a partir de los análisis realizados sobre los datos, a continuación las listamos:

* Las cámaras más caras son las SLR grandes, mientras que las más baratas son compactas, ultracompactas y cámaras de acción asequibles.
* El boom de las cámaras dígitales tuvo lugar entre 2014 y 2015, mientras que a partir de ahí los precios han ido disminuyendo como consecuencia de las mejoras en las cámaras de los móviles.
*Las cámaras compactas y ultracompactas prácticamente han desaparecido debido a la explosión de las cámaras en los teléfonos móviles, mientras que las cámaras profesionales se han mantenido.
* Se puede afirmar con un p-value de 4,2e-8 que no hay diferencias en las puntuaciones de las cámaras Canon y Nikon.
* Valores como el peso o el precio prácticamente no tienen relación con la puntuación general de la cámara, en cambio la ergonomía o las características de esta si que afectan de forma positiva, mientras que la precisión afecta de forma negativa.
* Mientras que la puntuación general de la cámara es inversamente proporcional al precio final de esta, el hecho de tener GPS aumenta 130 dólares el precio final, o el hecho de ser de cuerpo tipo "Large SLR" lo aumenta en 5.320 dólares.
*Aunque entre la mayoría de variables no existen correlaciones, podemos ver como si que existen entre la puntuación de las características y la puntuación del visor, entre el precio y la puntuación de ergonomía, y entre el precio y la puntuación de las características.

# Código: Hay que adjuntar el código, preferiblemente en R, con el que se ha realizado la limpieza, análisis y representación de los datos. Si lo preferís, también podéis trabajar en Python.

* PRA2.html: El resultado de la ejecución del *notebook* se puede consultar [aquí](https://htmlpreview.github.io/?https://github.com/pbenito1/dpreview_clean/blob/main/PRA2.html). En este archivo se pueden ver las respuestas a las preguntas dadas en el enunciado de la práctica
