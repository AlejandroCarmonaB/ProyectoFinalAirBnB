# Análisis de AairBnB en Madrid

## 1-. Introduccion.

Este ha sido mi primer proyecto de analisis de datos utilizando Paython y PowerBi. El objetivo de este informe es ver el estado actual
en el que se encuentra AirBnB en Madrid. Mi objetivo personal es aprender el proceso completo de realizar un EDA y pasarlo a un 
dashboard hecho en PowerBi,
He trabajado con un conjunto de datos de Airbnb en madrid que contiene informacion sobre los anuncios,disponibilidad,precios,reseñas,etc...

## 2-. Preparación y limpieza de datos en Python.

Al principio cargué el conjunto de datos utilizando pandas y lo primero que hice fue mirar como eran utilizando .info() y .head().
Esto me ha servido para entender:
  1-. Cuantas columnas habia.
  2-. Si habia valores nulos.
  3-. El tipo de dato de cada columna.

Me encontre con dos columnas vacias (price y adjust_price) que estaban completamente vacias en un dataframe.Como todos lo valores 
eran nulos, no tenia sentido conservarlas porque no aportaban nada asique decidi eliminarlas.
En este punto tuve dudas,porque pensaba que si luego podrían usarse juntandolas en otro set de datos. Pero como este set de datos 
era solo de disponibilidad y ya habia otro set de datos donde si estaba el precio, me decidi por borrarlas aqui.

Con .describe() miré las estadísticas basicas(media,minimo, máximo,percentiles). Esto me ayudo a detectar:
  1-. Valores muy grandes en minimum_nights o maximum_nights que parecían poco realistas, como estancias de miles de dias.
  2-. Distribuciones de precios algo extrañas en algunos casos.

Dado esto fui tomando decisiones como:
  1-. Filtrar valores demasiado extremos (outliers) en noches minimas/maximas.
  2-. Quitar columnas que no me servian para el analisis.
  3-. Preparar las fechas en el set de datos de reseñas.
No siempre estaba seguro de que hacer, pero intente pensar en lo mas sencillo y optar por eliminar lo que claramente no servia
y mantener lo que para mi parecia util.

## 3-. Análisis descriptivo y estadístico.

Con los datos ya limpios pase a analizarlos. En principio iba a calcular:
  1-. El numero de anuncios activos para ver cuantos alojamientos ofrece Airbnb en Madrid.
  2-. El precio mediano de los anuncios, porque el promedio se iba a ver influido por los outliers.
  3-. La tasa ded ocupacion calculada como porcentaje de dias disponibles/no disponibles.
  4-. Los ingresos mensuales haciendo una aproximacion utilizando precio y disponibilidad.
Al final decidi hacer esto en el dashboard de PowerBi, no se si de forma acertada o no, pero de esa forma lo utilice para los KPI´s.
Saque algunas gráficas con matplotlib y seaborn para visualizar:
  1-. La distribucion de precios, que resulto ser muy sesgada.
  2-. El numero de reseñas por mes(para ver la evolucion en el tiempo).
  3-. Comparaciones entre barrios.

## 4-. Dashboard en PowerBi

Despues de tener los datos limpios, exporte los archivos y los cargue en powerBi.Mi objetivo era crear un dashboard visual y
facil de entender.

Los pasos principales fueron:
--> KPI´s en la parte superior, que fueron:
  1-. Amuncios activos.
  2-. Precio mediano.
  3-. Ocupacion media.
  4-. Ingresos mensuales estimados.
  En este punto me costo dar formato a las tarjetas, pero al final logre que se vieran grandes y claras.

--> Grafico de barras de ocupacion por barrio:
  1-. Puse los barrios en el eje X y la ocupacion media en el eje Y.
  2-. Al principio me salia la suma de porcentajes, tuve que cambiarlo a promedio.

--> Distribucion de precios por zona:
  Aqui se podian ver algunos ouliers.

--> Incluimos un mapa de precios por barrio con su geolocalizacion:
  De esta forma no solo se diferenciaba por barrio,sino que tambien aparecian los lugares con sus precios.

--> Ocupacion mensual a lo largo del tiempo:
  De esta forma podemos ver la tendencia que hay a lo largo del tiempo.
  Aqui me aparecian los valores temporales desordenados, tuve que modificarlo para que saliesen ordenados temporalmente.

--> Precio medio por superhost(1)/host(0)/Desconocido(-1)
  Mediante este grafico de barras podemos ver si influia el precio de se superhost y se comparaba a los demas.

  --> Segmentadores:
  Añadi segmentadores por tipo de habitacion, por fecha y por barrio.
  Al principio quedaban mal con scroll, pero luego pude ajustarlos bien y probe con listas desplegables para que se viera mas
  limpio.

  ## 5-. Conclusiones.
  1-. La mayoria de anuncios de Madrid estan concentrados en barrios mas turisticos.
  2-. Los precios son muy variables, con algunos valores extremos que no parecen realistas. Siendo la zona centro la mas cara de 
      promedio.
  3-. La ocupacion mensual da una idea de la demanda, aunque son datos aproximados.Nos muestra que hubo una bajada abrupta pero
      poco a poco se va recuperando.


  ### Opinion personal.
  Al ser mi primer proyecto de 0, he aprendido mucho:
    1-. Como limpiar datos en Python con pandas.
    2-. La importancia de revisar valores nulos, tipos de datos y outliers.
    3-. Lo dificil que es tomar decisiones cuando no sabes si algo hay que borrarlo o conservarlo.
    4-. Como hacer un dashboard en PowerBi y los problemas tipicos de diseño(segmentadores, formatos,etc...).
  Se que mi analisis no es perfecto y he necesitado de mucha ayuda para poder hacer y montar todo,ademas de que se podrian utilizar 
  otro tipo de herramientas mas avanzadas para hacer un analisis mas eficiente, pero para ser la primera vez estoy contento porque 
  he podido seguir un orden mas o menos coherente,de los datos en crudo a un dashboard final,aprendiendo mucho en el proceso y 
  poco a poco enter el como y el porque de hacer ciertas cosas.

