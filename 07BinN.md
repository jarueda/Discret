
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

<p style="text-align: justify;">*Si me eres infiel una vez, la culpa es tuya. Si me eres infiel una segunda  vez, la culpa es mia*</p>

> *Si me eres infiel una vez, la culpa es tuya. Si me eres infiel una segunda  vez, la culpa es mia*.


$$\Omega_{Binomial ^{(-)}}=\{E, FE, FFE,..., \underbrace{FFF...FE}_{(x-1) \; ensayos, \\ \; 1  \;éxito}\} \; \text{cuando} \; r=1$$
A la variable aleatoria X se le puede describir la función de Masa de probabilidad de la siguiente forma:


|$X$    | 1  | 2   | 3    | 4      | ...| 
|---|---|---|---|---|---| 
|$P(x)$ | $p$| $qp$| $qqp$| $qqqp$ | ...| 

Tambien:

$$P(X=x)=p(1-p)^{x-1}=pq^{x-1} \; \text{para} \; x=\{1, 2, 3,...\}$$
Parámetros

$$E(X)= \frac{1}{p}$$
En la medida en que la probabilidad de éxito sea más pequeña, entonces la probabilidad de tener que realizar más ensayos será mayor. 


$$Var(X)=\sigma^2_x= \frac{(1-p)}{p^2}$$
---

- $r=2$

$$\Omega_{Binomial ^{(-)}}=\{E E, F E E, E F E,..., \underbrace{F F E F...F}_{(x-1) \; ensayos \\\;(2-1) \;éxitos}E\} \; \text{cuando} \; r=2$$


- $r=3$

$$\Omega_{Binomial ^{(-)}}=\{E E E, F E E E, E F E E,..., \underbrace{F F E E F...F}_{(x-2) \; ensayos \\\;(3-1) \;éxitos}E\} \; \text{cuando} \; r=3$$

_Observe_ la probabilidad de la cadena de eventos ocurridos antes del tercer éxito.  Esta probabilidad puede ser modelada usando un modelo binomial 

$$\binom{x-1}{3-1}p^{x-1}q^{3-1}$$



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

Para establecer la forma funcional del modelo, la cadena de eventos previa al r-ésimo éxito tiene la forma:

$$\binom{x-1}{r-1}p^{x-1}q^{r-1}$$

Con esto, la probabilidad del evento en que ocurren los r éxitos:

$$
P(X=x)=\binom{x-1}{r-1}p^{x-1}q^{x-1}p
$$



## Modelo Probabilístico



### Función de probabilidad

$$
P(X=x)=\binom{x-1}{r-1}p^rq^{x-1} \; \text{para} \; x=\{r, r+1, r+2, \dots\}
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

