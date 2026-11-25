# Uso diario de internet en España (ESS)

Primera versión del proyecto de análisis de datos para Estadística II. La pregunta de trabajo provisional es:

> ¿Cómo varía el tiempo diario dedicado a internet entre las rondas 8 y 11 de la Encuesta Social Europea en España?

## Archivos del proyecto

- **analisis_ess_internet.Rmd**: preparación de datos, análisis descriptivo, gráficos y contrastes.
- **data/Datafile-subset.csv**: extracto ESS con 21.296 respuestas de España.
- **data/Datafile-subset codebook.html**: documentación de las variables, rondas y ediciones incluidas.

## Alcance y objetivos

La variable sustantiva disponible es **netustm**, minutos de uso de internet en un día típico. Hay respuestas analizables en las rondas 8 a 11; en las rondas 1 a 7 aparece vacía. El CSV no contiene edad, género ni otro factor explicativo, por lo que permite comparar rondas con un factor, pero no realizar un ANOVA bifactorial.

La pregunta **netustm** se formula a personas que declaran usar internet la mayoría de los días o todos los días. Los resultados describen a quienes cumplen ese filtro y dieron una respuesta válida; no representan a toda la población encuestada.

1. Describir el tiempo de uso diario por ronda con medias, medianas y medidas de dispersión.
2. Comparar las rondas 8 a 11 mediante ANOVA de un factor y Kruskal-Wallis.
3. Describir por ronda la proporción de respuestas válidas y de respuestas no válidas.

Los objetivos son provisionales y se pueden ajustar a lo acordado por el grupo.

## Resultados preliminares

- Hay 5.861 respuestas válidas entre las rondas 8 y 11.
- La media ponderada con **anweight** es aproximadamente 218,0 minutos en la ronda 8, 228,7 en la 9, 325,5 en la 10 y 282,4 en la 11.
- Las medianas sin ponderar son 120, 180, 240 y 240 minutos, respectivamente.
- Los contrastes iniciales detectan diferencias entre rondas. Brown-Forsythe también detecta varianzas distintas; por ello, la ANOVA se interpreta con cautela y se incluye Kruskal-Wallis como contraste complementario.

Son resultados exploratorios. Las rondas son muestras transversales y no permiten atribuir causalidad ni afirmar que se sigue a las mismas personas a lo largo del tiempo. Las medias descriptivas usan la ponderación ESS; los contrastes clásicos no incorporan el diseño muestral completo.

## Cómo abrir el análisis

Los archivos de datos ya están en la carpeta **data/**. Abre **analisis_ess_internet.Rmd** en RStudio desde la carpeta raíz del proyecto y pulsa **Knit** para generar el informe HTML.

## Datos ESS y atribución

El extracto y su codebook proceden del [ESS Data Portal](https://ess.sikt.no/en/series/321b06ad-1b98-4b7d-93ad-ca8a24e8788a). El codebook incluido identifica las ediciones y los DOI de las rondas utilizadas. Fuente: European Social Survey (ESS ERIC), datos integrados, rondas 1–11; extracto de España preparado para este proyecto.

Los datos ESS se publican bajo [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/), para usos no comerciales con atribución y compartir bajo la misma licencia. La documentación ESS se publica bajo [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Este trabajo no está respaldado por ESS ERIC ni por Sikt.

## Otras fuentes

- [Guía ESS sobre ponderaciones y diseño muestral](https://www.europeansocialsurvey.org/sites/default/files/2023-06/ESS_weighting_data_1_1.pdf)
