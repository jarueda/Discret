---
output:
  pdf_document: default
  html_document: default
---

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


$$\Omega_{Binomial ^{(-)}}=\{E, FE, FFE,..., \underbrace{FFF...FE}_{x \; ensayos, \\ \; 1  \;éxito}\} \; \text{cuando} \; r=1$$
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

$$\Omega_{Binomial ^{(-)}}=\{E E E, F E E E, E F E E,..., \underbrace{F F E E F...F}_{(x-1) \; ensayos \\\;(3-1) \;éxitos}E\} \; \text{cuando} \; r=3$$

_Observe_ la probabilidad de la cadena de eventos ocurridos antes del tercer éxito.  Esta probabilidad puede ser modelada usando un modelo binomial 

$$\binom{x-1}{3-1}p^{r-1}q^{x-r}$$



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

$$\binom{x-1}{r-1}p^{r-1}q^{x-r}$$

Con esto, la probabilidad del evento en que ocurren los r éxitos:

$$
P(X=x)=\binom{x-1}{r-1}p^{r-1}q^{x-r}p
$$



## Modelo Probabilístico


$$
P(X=x)=\binom{x-1}{r-1}p^rq^{x-r} \; \text{para} \; x=\{r, r+1, r+2, \dots\}
$$

---

---

_Media y varianza_

$$
E[X] = ?
$$

$$
Var(X) = ?
$$

---

### Ejemplo

_Germinación de semillas_

En un laboratorio de agronomía, cada semilla de maíz tiene probabilidad (0.4) de germinar correctamente.

Se siembran semillas una por una hasta obtener **2 semillas germinadas**.

_Pregunta_

¿Cuál es la probabilidad de que se necesiten exactamente **5 semillas** para obtener las 2 germinaciones exitosas?

---


_Paso 1._ Identificar parámetros

* Número de éxitos requeridos:  $r=2$

* Probabilidad de éxito: $p=0.4$

* Número total de ensayos: $x=5$

---

_Paso 2._ Aplicar la fórmula

$$
P(X=5)=\binom{5-1}{2-1}(0.4)^2(0.6)^{5-2}
$$

---

_Paso 3._ Resolver el coeficiente combinatorio

$$\binom{4}{1}=4$$

---

_Paso 4._ Resolver potencias

$(0.4)^2=0.16$, $(0.6)^3=0.216$ 

---

_Paso 5._ Multiplicar 

$P(X=5)=4(0.16)(0.216)$

$$\boxed{P(X=5)=0.13824}$$

---

_Respuesta_

La probabilidad de necesitar exactamente 5 semillas para obtener 2 germinaciones exitosas es aproximadamente:

$\boxed{13.82\%}$

---

_Captura de insectos_

En un cultivo experimental, cada trampa instalada tiene probabilidad (0.4) de capturar un insecto benéfico.

Las trampas se revisan una por una hasta encontrar **2 capturas exitosas**.

_Pregunta_

¿Cuál es la probabilidad de que la segunda captura exitosa ocurra exactamente en la **cuarta trampa revisada**?

---

_Paso 1._ Identificar parámetros

$r=2$ , $p=0.4$, $x=4$

---

_Paso 2._ Aplicar la fórmula

$P(X=4)=\binom{4-1}{2-1}(0.4)^2(0.6)^{4-2}$

---
$$P(X=4)=0.1728$$

---

_Respuesta_ 

La probabilidad de que la segunda captura exitosa ocurra exactamente en la cuarta trampa es:

$$\boxed{17.28\%}$$

Si se necesita que genminen dos semillas...

$$
P(se \; tienen  \; que  \; realizar  \; más  \; de  \; 4  \; ensayos) = ?
$$

Resultado:

$$
P(X>4) =P(x=5)+P(x=6)+P(x=7)+ ...= 1-F(4)
$$

---


_Control de plagas_

- $p = 0.30$  
- $r = 10$  

---

#### Número esperado

$$
E[X] = ?
$$


---

_Varianza_

$$
\sigma^2 \approx ?
$$





---


_La distribución binomial negativa_ es útil en ciencias agrarias para modelar:

* germinación de semillas,
* aparición de plagas,
* capturas de insectos,
* detección de enfermedades vegetales,
* supervivencia de plantas,
* éxito reproductivo animal,
* monitoreo ambiental.

