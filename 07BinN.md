
# Binomial Negativa


Suponga que se realizan una serie de experimentos aleatorios _Bernoulli_ Independientes hasta que aparece el primer éxito.


> ¿Cuántos ensayos se necesitan para obtener un número fijo de éxitos?

---

Si se realizan ensayos Bernoulli independientes, uno a una hasta obtener una cantidad fija de éxitos, $r$.

### Variable aleatoria

Cuando se define la v.a. $X$ como la v.a. que cuenta el número de ensayos Bernoulli independientes que se tienen que realizar para obtener $r$ éxitos.

$$
x = \{r, r+1, r+2, \dots\}
$$

El espacio muestral asociado a este tipo de experimentos aleatorios tiene la forma general:  (E: representa el evento "ocurre un éxito"; F: ocurre un fracaso)



## Distribución Geomética o de Pascal

- Si $r=1$

> *Si me eres infiel una vez, la culpa es tuya. Si me eres infiel una segunda  vez, la culpa es mia*.


$$\Omega_{Binomial ^{(-)}}=\{E, FE, FFE,..., \underbrace{FFF...FE}_{(x-1) fracasos, \;un \;éxito}\} \; \text{cuando} \; r=1$$
A la variable aleatoria X se le puede describir la función de Masa de probabilidad de la siguiente forma:


|$X$    | 1  | 2   | 3    | 4      | ...| 
|---|---|---|---|---|---| 
|$P(x)$ | $p$| $qp$| $qqp$| $qqqp$ | ...| 

Tambien:

$$P(X=x)=p(1-p)^{x-1}=pq^{x-1} \; \text{para} \; x=\{1, 2, 3,...\}$$
Parámetros

$$E(X)= \frac{1}{p}$$
$$Var(X)=\sigma^2_x= \frac{(1-p)}{p^2}$$
---

- $r=2$

$$\Omega_{Binomial ^{(-)}}=\{E E, F E E, E F E,..., \underbrace{F F E F...F}_{(x-2) \; fracasos \\\;(2-1) \;éxitos}E\} \; \text{cuando} \; r=2$$





### Comparación

| Característica | Binomial | Binomial Negativa |
|--|--|--|
| Fijo | $n$ | $r$ |
| Variable | éxitos | ensayos o fracasos |
| Pregunta | éxitos en $n$ | ensayos para $r$ |
| Soporte | $0,\dots,n$ | infinito |

---


---







### Probabilidad 

$$
P(X=x)=\binom{x-r}{r-1}p^{x-r}q^{r-1}p
$$



## Modelo Probabilístico



### Función de probabilidad

$$
P(X=x)=\binom{x-r}{r-1}p^rq^{r-1} \; \text{para} \; x=\{r, r+1, \dots\}
$$

---

---

### Media y varianza

$$
E[X] = ?
$$

$$
Var(X) = ?
$$

---

## Ejemplo

### Datos

- $r = 2$  
- $p = 0.40$  

---

### Probabilidad puntual

$$
P(se \; tienen  \; que  \; realizar  \; más  \; de  \; 4  \; ensayos) = ?
$$

Resultado:

$$
P(X>4) =P(x=5)+P(x=6)+P(x=7)+ ...= 1-F(4)
$$

---


#### Control de plagas

- $p = 0.30$  
- $r = 10$  

---

#### Número esperado

$$
E[X] = ?
$$


---

#### Varianza

$$
\sigma^2 \approx ?
$$

