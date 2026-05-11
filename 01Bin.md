# Binomial 

La distribución binomial tiene sus raíces en los trabajos pioneros del matemático suizo **Jacob Bernoulli** (1654-1705), quien en su obra póstuma *"Ars Conjectandi"* (1713) estableció los fundamentos de la teoría de la probabilidad moderna. Bernoulli estudió experimentos con solo dos resultados posibles, que hoy llamamos **ensayos Bernoulli**.

Posteriormente, el matemático francés **Abraham de Moivre** (1667-1754) formalizó la distribución binomial en su libro *"The Doctrine of Chances"* (1718), con lo cual se desarrolló el modelo que lleva el número combinatorio para calcular probabilidades.


## Función de probabilidad Binomial

Un experimento aleatorio consistente en la realización  de $n$ ensayos Bernoulli tales que:
 
- Cada ensayo realizado es Independiente
- Cada ensayo ocurre solo de dos formas denominadas **Exito** y **Fracaso**
- La probabilidad de que ocurra un éxito en cada ensayo se mantiene **constante** y de nota por $p$


### Definición de la variable aleatoria

Sea $X$ la v.a. que cuenta el número de éxitos cuando de realizan $n$ ensayos Bernoulli.

Entonces, 

Una variable aleatoria $X$ sigue una **distribución binomial** con parámetros $n$ y $p$, denotada como:

$$X \sim Bin(x,n, p)$$

si su función de probabilidad está dada por:

$$P(X = x) = \binom{n}{x} p^x (1-p)^{n-x} \;\;\text{para}\;\; x=\{0, 1, ...,n\}$$

donde:

- $n$ = número total de ensayos Bernoulli independientes

- $x$ = número de éxitos ($x = 0, 1, 2, \ldots, n$)

- $p$ = probabilidad de éxito en cada ensayo

- $\binom{n}{x} = \frac{n!}{x!(n-x)!}$ = coeficiente binomial


El **soporte** de una distribución es el conjunto de valores que puede tomar la variable aleatoria con probabilidad mayor que cero.

Para la binomial:
$$X = \{0, 1, 2, \ldots, n\}$$
---

La distribución binomial modela situaciones donde:

- Existe un número **fijo** de ensayos independientes

- Cada ensayo tiene **dos resultados posibles** (éxito/fracaso)

- La **probabilidad de éxito** ($p$) permanece constante

---



---

