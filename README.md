# Uso diario de internet en España (ESS)

Primera versión del proyecto de análisis de datos para Estadística II. La pregunta de trabajo provisional es:

> ¿Cómo varía el tiempo diario dedicado a internet entre las rondas 8 y 11 de la Encuesta Social Europea en España?

## Alcance de este archivo

El CSV contiene 21.296 respuestas de España, pero la variable sustantiva incluida es **netustm** (minutos de uso de internet en un día típico). Para esta variable hay respuestas utilizables en las rondas 8, 9, 10 y 11; las rondas 1 a 7 aparecen vacías y se excluyen. El archivo no incluye edad, género ni otra variable de grupo, así que esta versión permite comparar rondas con un factor, pero no hacer un ANOVA bifactorial.

**netustm** se pregunta a las personas que declaran usar internet la mayoría de los días o todos los días. Por eso, los resultados describen a quienes cumplen ese filtro y respondieron con un tiempo válido; no representan a todas las personas encuestadas.

## Objetivos provisionales

1. Describir el tiempo de uso diario entre las respuestas válidas de cada ronda, con media, mediana y dispersión.
2. Comparar las distribuciones entre las rondas 8 a 11 mediante ANOVA de un factor y Kruskal-Wallis.
3. Describir cómo cambia por ronda la proporción de respuestas válidas, no aplicables y sin respuesta.

Los objetivos se pueden ajustar si el grupo ya había acordado otros.

## Primeros resultados

- Hay 5.861 respuestas válidas entre las rondas 8 y 11.
- La media ponderada con **anweight** es 218,0 minutos en la ronda 8, 228,7 en la 9, 325,5 en la 10 y 282,4 en la 11.
- Las medianas sin ponderar son 120, 180, 240 y 240 minutos, respectivamente.
- Los contrastes iniciales detectan diferencias entre rondas. La prueba de Brown-Forsythe también detecta varianzas distintas, así que Kruskal-Wallis se presenta como contraste complementario y la ANOVA se interpreta con cautela.

Estos son resultados exploratorios. Las muestras son transversales y no permiten atribuir causalidad ni afirmar que se siga a las mismas personas con el paso del tiempo.

## Tratamiento de los datos

El codebook identifica **6666** como “no aplicable”, **7777** como “rechazo”, **8888** como “no sabe” y **9999** como “sin respuesta”. Se recodifican como valores ausentes para analizar minutos. Las respuestas de las rondas 1 a 7 están vacías en este archivo y no se interpretan como cero.

No se eliminan automáticamente valores extremos: 0 y 1.440 minutos se conservan como respuestas registradas y se revisan con gráficos. Se informa de la asimetría y se presentan medianas y Kruskal-Wallis.

Para los resúmenes ponderados se usa **anweight**, siguiendo la recomendación general de ESS. En un análisis de un solo país, **pspwght** debe dar estimaciones equivalentes. Los contrastes clásicos de esta versión no incorporan el diseño muestral completo, por lo que sus valores p se interpretan como exploratorios.

## Cómo abrir el análisis

1. Descomprime el archivo recibido y coloca **Datafile-subset.csv** en la carpeta **data/**.
2. Abre **analisis_ess_internet.Rmd** en RStudio desde la carpeta del proyecto.
3. Pulsa **Knit** para generar el informe HTML.

El CSV y el codebook se mantienen fuera de GitHub; el **.gitignore** evita que se añadan por accidente.

## Fuentes

- [ESS Data Portal](https://ess.sikt.no/en/series/321b06ad-1b98-4b7d-93ad-ca8a24e8788a)
- [Guía ESS sobre ponderaciones y diseño muestral](https://www.europeansocialsurvey.org/sites/default/files/2023-06/ESS_weighting_data_1_1.pdf)
