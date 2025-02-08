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

## Conceptos basicos en laspruebas de significancia de la hipótesis nula
Topicos: comparacion de grupos

Inferencia: busca conocer las caracteristicas de una población a partir de las caracteristicas de una muestra
Articulo de tipos de muestreo: 

- Intervalos de confianza (regresiones)
- Test de significancia de la hipótesis nula

1. Especificar las hipótesis (nula y alterna)
2. Elegir un nivel de significancia (arbitrario 0.05)
3. Realizar la prueba de hipótesis (aplicar el test estadistico)
4. Comparar el valor p y nivel alfa (valor teorico vs valor empirico)
5. Decidir si rechazar o no la Hipótesis nula

A qué hace referencia la hipótesis nula y alterna? Son conjeturas acerca de un modelo estadísticop de la población basado en una muestra de la misma. 
La H0 habitualmente afirma que algo de interés es igual a 0, mientras que la hipótesis alterna suele expresar lo contrario.
H0: No hay diferencia
H1: Hay diferencia

Valor p: 
- mientras mas pequeño va a haber una mayor discrepancia con la hipótesis nula
- Probabilidad de que la hipótesis nula sea cierta en la población 
Si p< 0.05 es poco probable que la hipótesis nula sea cierta en la población (resultado estadisticamente significativo)

<0.05 : estadisticamente significativa
>= : no existe una asociación "estadisticamente"

- Crisis de replicabilidad
- Valor p

Pruebas parametricas: Se cumplen cuando las variabls cumplen ciertos requisitos en relación al tamaño de muestra y la distribución (trabaja con datos numéricos)
Pruebas no parametricas: se emplean cuando las variables no cumplen con los requisitos para el empleo de las pruebas paramétricas (trabajan con datos categóricos)

Cat v cat 
No parametrica: trabajan con variables categóricas
Chi-cuadrado: chisq.test(cat1, cat2)
Fisher: fisher.test(cat1, cat2)


Prueba de Chi- cuadrado
    Se utiliza cuando menos del 20% de celdas tienen frecuencias esperadas menores a 5.

Prueba de Fisher
    Se utilizan cuando 20% o más de celdas tienen frecuencias esperadas menores a 5. 

Hipótesis para ambas pruebas:
La proporción de muerte en fumadores es diferente que en no fumadores?
H0: La proporcion de muerte es igual en no fumadores que en fumadores
H1: La proporcion de muerte es diferente en fumadores que en no fumadores

H0: La proporcion de personas con depresión no es difrente entre V y M
H1: La proporcion de personas con depresion es diferente en M y V 

La frecuecua esperada es el valor que esperamos obtener en caso no hubiera diferencia
Usamos los datos de frecuencia observada 
(Fumador total * no muerio total)/total total
(Fumador total*murio)/ total total 


Tabla 2x2 cada uno 25% = basta con que una tenga menos de 5 para que no se cumpla chi
tabla 2*3 cada uno 16.7% = dos celdas tengas valor de 5 o menos para usar la prueba de fisher 
tabla 2*4  cada uno tiene 12.5% = dos celdas tengas frecuencias esperadas menores a 5

Primero se almacena los analisis dentro de un objeto para ver la frecuencia esperada y de alli decidir si se usa chi o Fisher


Numerica vs Categórica:
Una variable numérica en dos grupos independientes
- Paramétrica
    T student para grupos independientes
    T de Welch
- No paramétrica
    U de Mann-Whitney

Si vemos que el tamaño de muestra en un grupo es mayor o igual a 30 continuamos evaluando la normalidad y homocedasticidad

Si - Ttudent
Usamos la media
H0: media es igual en M y V (No hay diferencias estadisticamente significativa)
H1: media es diferente M y V (Hay diferencias estadisticamente significativa)

No - TWelch
Si vemos que el tamaño de muestra en un grupo es menor o igual a 30 aplicamos el estadistico de U de Mann-Whitney 
Usamos la mediana
H0: mediana igual en M y V (No hay diferencias estadisticamente significativa)
H1: mediana diferente en M y V (Hay diferencias estadisticamente significativa)

Normalidad
H0: Los datos tienden a una distribución normal
H1: Los datos no tienen una distribución normal 

Asimetrí(Skewnnes):  -0.5 a 0.5                     
Kurtosis: 2.5 a 3.5  

Levene test (Homocedasticidad)
H0: El grupo de adolescentes y jóvenes presentan varianzas iguales
H1: El grupo de adolescentes y jóvenes no presentan varianzas iguales

Si vemos que el tamaño de muestra en un grupo es menor a 30 o no es normal usamos U-Mann-Whitney


Una variable numérica en dos grupos pareados
- Paramétrica
    T de Student para grupos pareados
- No paramétrica
    Rangos con signo de Wilcoxon

Una variable numérica en más de dos grupos independientes
- Paramétrica
    Anova de Fisher
    Anova de Welch
- No paramétrica
    Kruskal-Waillis 


Numerica vs numérica
Dos variables numéricas en grupos independientes
- Paramétrica
    Pearson
- No paramétrica
    Spearman

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

## Regresiones

Y = CONS + B1*X 
Y: Valor numérico de V.D
X: Valor numerico de V.I
B1: pendiente o coeficiente 
B0 o intercepto: valor de "y" cuando "x" es cero 

# Regresiones lineales con VI (numerica)

Estandar VI(numerica): 
En la población por cada unidad adicional de la VI, la VD (desenlace)
fue en promedio (coeficiente de regresión lineal) mayor/menor. 
Este resultado fue estadisticamente signifixativo.

En la población, por cada cm de incremento en el PA (unidad adicional 
de la variable independiente - VI), la IMC (desenlace -VD) fue en 
promedio 0.5 Kg (coeficiente de regresión lineal) mayor o menor (signo).
Este resultado fue estadisticamente significativo.

Esquema del comando: 
Función de regresion lineal 
variable dependiente
Variable independiente
Nombre de la base de datos

Resultado:
1. Coeficientes
2. Error stándar de los Coef.
3. Valor t: Coef/Se

Intervalo de confianza
Beta debe estar dentro del intervalo de confianza

## Regresión lineal con VI dicotómica

Categorias: 
cat de referencia = 0 
cat de exposicion = 1 

La persona A tiene mas edad con respecto a la B
La persona A tiene mas edad respecto a quien tiene menor edad 

Cuando evaluo la regresion en variables categoricas se halla un promedio
en ambas categorias y se compara. 

Y = CONS + B1*X 

El B1 es el promedio de "Y" en cat.Exposición - promedio de "Y" 
en cat. Referencia   
El intercepto es la nota promedio en la categoría de referencia

### Interpretacion:
En la población evaluada, la media de la nota en el sexo femenino fue 
2.3 puntos menos en comparación al sexo masculino.
El resultado fue estadisticamente significativo.

En la población, la media de la nota en quienes tienen obesidad
fue 0.36 puntos menos en comparación a quienes tienen peso normal.
Este resultado fue/no fue estadisticamente significativo. 



# Interpretacion (residuos - Coeficiente de determinación)
R2: Determina el grado de variabilidad (el ancho) de la distribución
de los datos en el eje Y que puede ser explicada por la variable X
En regresiones lineales el R de pearson es igual a R2 



## Normalidad de residuos 
Explicar mejor el skewness, (no normal)
Asumiremos como normal -0.5 a 0.5 
No nomral: menores a -0.5 o mayores a 0.5 

Kurtosis
Asumiremos como normal 2.5 a 3.5 
No normal: mayor a 3.5 o menor a 2.5 

