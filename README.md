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

Con los datos ya limpios

