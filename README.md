## Rstudio_anotaciones

### Modulo 2

¿Qué hacer cuando hay datos perdidos?
Cómo se realiza la imputación de datos(tipos, ejemplos)

https://www.linkedin.com/advice/0/how-can-you-impute-missing-data-regression-analysis?lang=es&originalSubdomain=es
https://www.appsilon.com/post/imputation-in-r
https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-024-02173-x
https://www.sciencedirect.com/science/article/pii/S2772662223001819
https://www.tandfonline.com/doi/full/10.1080/08839514.2019.1637138#d1e110

A qué análisis afecta los datos perdidos en R: 
- Media, mediana, moda, desviación estándar
- Los modelos lineales (lm, glm) eliminan por defecto las filas con datos faltantes antes de ajustar el modelo.
- Pruebas como la t de Student o ANOVA pueden fallar o producir resultados incorrectos si no se manejan los valores faltantes.
- Los gráficos como ggplot2 omiten por defecto los valores perdidos

Qué articulos definen el tamaño de muestra adecuado
- Muestreo probabilístico:  https://www.elsevier.es/es-revista-investigacion-educacion-medica-343-pdf-S2007505713727157
- Muestreo no probabilístico:  https://online.ucpress.edu/collabra/article/8/1/33267/120491/Sample-Size-Justification 
- Error tipo I y tipo II: https://support.minitab.com/es-mx/minitab/help-and-how-to/statistics/basic-statistics/supporting-topics/basics/type-i-and-type-ii-error/ 


Hipótesis nula (H₀):
No hay diferencia significativa entre los resultados de la prueba diagnóstica y el verdadero estado de salud del paciente en cuanto a la detección de cáncer.
Hipótesis alterna (H₁):
Existe una diferencia significativa entre los resultados de la prueba diagnóstica y el verdadero estado de salud del paciente en cuanto a la detección de cáncer.


Error de tipo I (Falso positivo)
Si usted rechaza la hipótesis nula cuando es verdadera, comete un error de tipo I 

Error de tipo II (falso negativo)
Cuando la hipótesis nula es falsa y usted no la rechaza, comete un error de tipo II.


El análisis de poder a priori se utiliza en el diseño de estudios para determinar el tamaño de muestra necesario para detectar un efecto específico con una probabilidad de éxito (poder estadístico) predeterminada. Este enfoque es fundamental para garantizar que un estudio tenga la capacidad suficiente para identificar efectos reales, evitando tanto errores tipo I como errores tipo II.
Análisis de poder estadístico a priori, a partir del cual obtienes un tamaño de muestra mínimo para que la prueba estadística detecte un efecto real con cierta probabilidad, usualmente 80% (o dicho de otro modo, la probabilidad de no cometer el error de tipo II).

Poder estadístico (1−𝛽): Es la probabilidad de rechazar correctamente la hipótesis nula cuando esta es falsa.
Valores comunes: 0.80 o 0.90

Qué articulo dice que estadisticos son mas confiables
La prueba de Shapiro-Wilk se basa en la correlación entre los datos y las puntuaciones normales correspondientes (10) y proporciona mejor potencia que la prueba K-S incluso después de la corrección de Lilliefors (12). La potencia es la medida más frecuente del valor de una prueba de normalidad: la capacidad de detectar si una muestra procede de una distribución no normal (11). Algunos investigadores recomiendan la prueba de Shapiro-Wilk como la mejor opción para comprobar la normalidad de los datos (11).
https://pmc.ncbi.nlm.nih.gov/articles/PMC3693611/ 

Explicar mejor el skewness, (no normal)
Asumiremos como normal -0.5 a 0.5 
No nomral: menores a -0.5 o mayores a 0.5 

Kurtosis
Asumiremos como normal 2.5 a 3.5 
No normal: mayor a 3.5 o menor a 2.5 

Linea y curva

