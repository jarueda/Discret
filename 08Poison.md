# Distribución de Poisson

## 1. Definición 

La distribución de Poisson es un modelo probabilístico discreto diseñado para describir el número de ocurrencias de un evento en un intervalo fijo de tiempo, espacio o volumen. Se fundamenta en los supuestos estructurales: 

- (i) los eventos ocurren a una tasa media constante (λ)  

- (ii) las ocurrencias son mutuamente independientes.

- (iii) la tasa media de éxitos es proporcional al tamaño del intervalo considerado.



Su función de masa de probabilidad (FMP) se origina del límite:

$$lim_{n \rightarrow \infty \\ p \rightarrow 0} \binom{n}{x} p^x q^{n-x}$$


$$P(X = x) = \frac{λ^x e^{-λ}}{x!}, \; \text{para} \; x=\{0, 1, 2, 3, ...\}$$

donde:

- **X**: variable aleatoria que cuenta el número de eventos observados en el intervalo.

- **x**: número entero no negativo de ocurrencias (0, 1, 2, …).

- **λ**: parámetro de la distribución. tasa media de éxitos (> 0), que coincide con la esperanza matemática y la varianza de la distribución: $E[X] = λ$ y $Var(X) = λ$.
$$\lambda=np, \; \text{originado en la binomial}$$

- **e**: constante de Euler (≈ 2.71828).

Esta propiedad de equidispersión (media = varianza) es el núcleo teórico del modelo y, simultáneamente, su principal punto de vulnerabilidad en aplicaciones empíricas.

## Aplicaciones
Los datos de conteo son frecuentes y la distribución de Poisson ofrece un marco parsimonioso para su modelado. Su aplicabilidad se justifica cuando el fenómeno estudiado cumple con las siguientes características:

- **Unidades de muestreo delimitadas**: parcelas experimentales, cuadrantes vegetacionales, estaciones pluviométricas o transectos lineales.

- **Eventos discretos y relativamente escasos**: plagas por planta, plántulas por metro cuadrado, detecciones de especies amenazadas, eventos de erosión por ladera, o incidencias de contaminación por muestra.

- **Independencia operativa**: la presencia de un evento no altera significativamente la probabilidad de ocurrencia de otro en la misma unidad o intervalo.

*Intervención asistida por IA*: Las herramientas computacionales pueden automatizar la exploración de datos y la selección inicial de modelos. Sin embargo, el investigador debe validar que la tasa λ no varíe sistemáticamente por _covariables no medidas_ (heterogeneidad ambiental) y que no exista agregación espacial (clustering), ya que ambos escenarios violan la equidispersión y exigen modelos alternativos (Poisson inflado por ceros, Binomial Negativa, o modelos mixtos con efectos aleatorios).

## Relación Práctica con la Distribución Binomial

La conexión entre Poisson y Binomial trasciende lo teórico; tiene implicaciones directas en el diseño experimental y la eficiencia computacional.

La Binomial $B(n, p)$ modela éxitos en $n$ ensayos independientes con probabilidad constante $p$. Cuando se cumplen simultáneamente:

1. $n$ es grande (habitualmente ≥ 30 o ≥ 50),

2. $p$ es pequeña (≤ 0.10),

3. El producto $λ = n * p$ permanece finito y constante,

entonces `B(n, p)` converge a `Poisson(λ)`. Este resultado se conoce como **Teorema de Poisson** o ley de los eventos raros.

**Consecuencias metodológicas**:

- *Simplificación analítica*: evita el cálculo de factoriales y coeficientes binomiales elevados, reduciendo errores de redondeo y tiempo de cómputo.

- *Límite superior*: la Binomial está acotada por `n`, mientras que Poisson no tiene cota superior. Si el conteo real puede acercarse al tamaño muestral, la aproximación pierde precisión.

- *Violaciones comunes*: en campo, la independencia rara vez es perfecta. 

* Si existe dependencia espacial o temporal, o si la probabilidad de ocurrencia varía entre unidades, la varianza observada supera a la media (sobredispersión). 

* Tanto Binomial como Poisson subestiman entonces la incertidumbre, inflando los errores tipo I. La IA puede alertar mediante gráficos de residuos deviance vs. valores ajustados o mediante la prueba de razón de verosimilitud comparando Poisson con Binomial Negativa.

## Ejemplos 

### Ejemplo 1: 

**Contexto**: En un ensayo de manejo integrado, se registra una media de $λ = 3$ insectos defoliadores por planta. Calcule la probabilidad de encontrar exactamente 2 insectos en una planta seleccionada al azar.

**Paso 1. Identificar parámetros**: λ = 3, k = 2.

**Paso 2. Sustituir en la FMP**:

$P(X = 2) = (3^2 * e^{-3}) / 2!$

$P(X = 2) = (9 * 0.049787) / 2 ≈ 0.2240$

**Paso 3. Interpretación**: Existe un 22.40 % de probabilidad de observar exactamente 2 insectos por planta bajo las condiciones del estudio.

*Verificación computacional (R)*:
```r
dpois(x = 2, lambda = 3)
# Resultado: 0.2240418
```

### Ejemplo 2: Aproximación Poisson a Binomial

Si una v.a. $X \sim Bin(x;n;P)$, cuando $n \rightarrow \infty$, entonces la distribución de $X$ tiende a: $$ X \dot \sim Poisson(x; \lambda=np)$$

**Contexto**: En una plantación de 500 árboles (n = 500), la probabilidad histórica de infección por un hongo vasculares es p = 0.008. Calcule la probabilidad de que exactamente 3 árboles estén infectados.

**Paso 1. Verificar condiciones**: n es grande, p es pequeña, λ = n * p = 500 * 0.008 = 4. La aproximación es válida.

**Paso 2. Cálculo exacto (Binomial)**:
P(X = 3) = C(500,3) * (0.008)^3 * (0.992)^497 ≈ 0.1956

**Paso 3. Cálculo aproximado (Poisson)**:
P(X = 3) = (4^3 * e^(-4)) / 3! = (64 * 0.018316) / 6 ≈ 0.1954

**Paso 4. Comparación**: La diferencia absoluta es ≈ 0.0002, lo que confirma la utilidad práctica de la aproximación.


*Desarrolle de forma autónoma*

- Suponga que la abundancia de cierta especie en ecosistemas poco intervenidos se estima en  un individuo por hectárea y que ésta puede ser modelada por una v.a. Poisson.

Estime la probabilidad de que cuando se inspeccione un lote de cinco hectáreas se observen al menos cuatro individuos. 

- En otro territorio, por estudios previos, se estableció que la probabilidad de que no se encuentre individuo alguno en una hectárea cualquiera es de 0.001234.

Si se realizan observaciones en dicho territorio ¿cuál es la probabilidad de se observen más de siete individuos en una parcela de cuatro hectáreas?


*Verificación computacional (Python)*:
```python
from scipy.stats import binom, poisson

prob_bin = binom.pmf(k=3, n=500, p=0.008)
prob_pois = poisson.pmf(k=3, mu=4)

print(f"Binomial exacta: {prob_bin:.4f}")
print(f"Aprox. Poisson:  {prob_pois:.4f}")
# Salida esperada: Binomial exacta: 0.1956, Aprox. Poisson: 0.1954
```

## Recomendaciones Metodológicas

- **Diagnóstico de supuestos**: Antes de adoptar Poisson, grafique la relación media-varianza por unidad de muestreo. 

Si la razón Var/Media > 1.5, considere modelos de sobredispersión. 

Si los ceros son excesivos, evalúe Poisson inflado por ceros.


- **Preguntas**:

  1. ¿Cómo incorporaría la variabilidad entre parcelas (efecto aleatorio) sin violar la independencia dentro de cada unidad?
  
  2. ¿Qué prueba formal o gráfico residual utilizaría para distinguir entre sobredispersión y exceso de ceros?
  
  3. ¿En qué escenarios de monitoreo ambiental sería metodológicamente incorrecto reemplazar la Binomial por Poisson?

### Referencias 

- Agresti, A. (2018). *Statistical methods for the social sciences* (5.ª ed.). Pearson.

- Hilbe, J. M. (2014). *Modeling count data*. Cambridge University Press.

- R Core Team. (2025). *R: A language and environment for statistical computing*. R Foundation for Statistical Computing. https://www.R-project.org/

- SciPy Developers. (2025). *SciPy: Open source software for mathematics, science, and engineering*. https://scipy.org/

- Zar, J. H. (2010). *Biostatistical analysis* (5.ª ed.). Pearson Prentice Hall.

