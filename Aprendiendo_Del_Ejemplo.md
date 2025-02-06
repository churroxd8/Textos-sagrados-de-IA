# Aprendiendo del ejemplo
> Aquí vamos a describir agentes que pueden mejorar su comportamiento mediante el estudio diligente de experiencias pasadas y predicciones acerca del futuro.

Quiero partir con las notas de esta semana con lo siguiente: "Un **agente** está aprendiendo si mejora su desempeño después de realizar observaciones del mundo". Esto lo menciono porque el concepto de aprendizaje tiene un amplio rango de posibilidades: desde algo trivial como realizar una lista para el supermercado, hasta cosas más profundas, como comprender una teoría acerca del origen del universo realizada por Albert Einstein. Cuando el agente es una computadora, esto lo llamamos **machine learning** (aprendiendo machin para los compas): una computadora observa datos, crea un **modelo** basado en los datos y usa estos para realizar tanto una **hipótesis** acerca del mundo y una pieza de software que puede resolver un problema.

## Formas de aprendizaje
Cualquier componente de un agente puede ser mejorado mediante *machine learning*. Tanto las mejoras como las técnicas para lograr esto, dependen de los siguientes factores:

- ¿Qué *componentes* tiene que ser mejorado?
-  ¿Qué *conocimiento previo* tiene el agente, lo que tiene influencia en el *modelo* a crear?
- ¿Qué *datos* y *retroalimentación* sobre los datos está disponible?

Partiendo de estas preguntas. Los **componentes** de estos agentes incluyen:

1. Un mapeo directo de las condiciones sobre el estado actual de las acciones.
2. Medios para inferir las propiedades relevantes del entorno (el mundo) desde la secuencia de percepción.
3. Información acerca de como el entorno evoluciona y sobre los resultados de las posibles acciones que el agente puede realizar.
4. Información de utilidad que indique el deseo de los estados del entorno.
5. Información que las acciones valiosas que indiquen el deseo de los estados.
6. Metas que describan los estados más deseables.
7. Un generador de problemas, crítico y con un elemento de aprendizaje que permita mejorar al sistema.

En este caso, asumimos que tenemos **poco concimiento previo** para el agente: empieza desde cero y aprende de los datos. Esto no quiere decir que existen maneras de transferir un conocimiento previo de un agente a otro, conocido como **transferencia del conocimiento**, lo cual permite el aprendizaje con mayor rapidez y con una menor cantidad de datos.

Partir desde un conjunto específico de observaciones hacia una regla general se le conoce como **inducción**; desde las observaciones como por ejemplo, que el sol se ocultó el día de ayer, podemos inducir que el sol saldrá el día de mañana (de lo contrario pues estamos fritos, ¿verdad?). Esto difiere del concepto de **deducción** debido a que una conclusión inductiva puede ser incorrecta, pero una conclusión deductiva tiene una forma *garantizada* de ser correcta si y solo sí las premisas son correctas.

Vamos a concentrarnos en problema en donde lo que recibimos es una **representación factorizada**, es decir, un vector con valores de atributo. Es posible también que lo que recibimos podría ser alguna estructura de datos, tanto atómica como relacional.

Cuando lo que obtenemos es uno de los valores de un conjunto de valores (por ejemplo: *soleado/nublado/lluvioso* o *verdadero/falso*), estamos ante un problema que se le conoce como **clasificación**. Cuando es un número (como la temperatura del día siguiente, con una medición realizada con mediante enteros o números reales), el problema de aprendizaje tiene como nombre de **regresión**.

Existen tres maneras de **retroalimentación** que acompañan a las entradas, y eso es lo que determina los tres tipos principales de aprendizaje:

- En el **aprendizaje supervisado**, el agente observa pares de entradas y salidas, aprendiendo una función que toma dada una entrada y una salida. Un ejemplo de esto es el siguiente: un dato de entrada podría ser las fotografías de una cámara, cada una con una salida con la leyenda "autobús" o "peatón", etc. Una salida se le conoce como **etiqueta**.
- En el **aprendizaje no supervisado**, el agente aprende patrones en las entradas sin ninguna retroalimentación. La tarea más común del aprendizaje no supervisado es lo que en inglés se le conoce como *clustering*: la detección de clústers útiles en un conjunto de entradas de ejemplo. Un caso de esto sería cuando mostramos millones de imágenes tomadas del Internet en donde un sistema de visión por computadora puede identificar un clúster amplio de imágenes similares de lindos gatitos (llamados así por los seres humanos).
- En el **aprendizaje por refuerzo** el agente aprende de una serie de *refuerzos*: Premios o castigos (bastante binario el pedo). Un ejemplo, al final de una partida de ajedrez se le notifica al agente que ha ganado (un premio) o a perdido (un castigo). Es menester del agente decidir cual de las acciones previo al refuerzo fue el más responsable, además de alterar sus acciones en pro de obtener más premios en el futuro.

## Aprendizaje supervisado
~~Aquí vienen las matemáticas duras de toda la carrera, para que te acuerdes de ellas y porque debiste poner más atención.~~ Digo, nunca es tarde para practicar en pro de tener una buena comprensión.

Formalmente, la tarea del aprendizaje supervisado es la siguiente:

Dado un **conjunto de entrenamiento** $N$ ejemplos de parejas de entradas y salidas:

$$(x_1,y_1),(x_2,y_2),...(x_N,y_N)$$

donde cada par fue generado por una función desconocida $y=f(x)$, se descubre una función $h$ que se aproxima a la verdadera función $f$.

La función $h$ se le conoce como la **hipótesis** acerca del entorno. Parte de un **espacio hipotético** $\mathcal{H}$ de posibles funciones. Por ejemplo, el espacio hipotético puede ser un conjunto de polinomios de grado 3; o un conjunto de funciones de Javascript, etc.

Con un vocabulario alternativo, podemos decir que $h$ es un **modelo** de los datos, partiendo de una **clase modelo** $\mathcal{H}$, o podemos decir que es una **función** que parte de una **clase función**. Le llamamos a la salida $y_i$ a la **verdad de tierra xD (ground truth en inglés para decirlo correctamente)** el cual es la respuesta verdadera que le estamos pidiendo a nuestro modelo predecir.

¿Cómo escogemos un espacio hipotético? Podríamos tener un conocimiento previo acerca de los procesos que generaron ese dato. En caso contrario, podemos realizar un **anlásis exploratorio de datos**: examinando los datos mediante exámenes estadísticos y visualizaciones como histogramas, diagramas de dispersión, diagramas de caja con tal de tener una sensación de los datos además de tener una noción sobre cuál hipótesis pudiera ser la apropiada. ~~O podemos realizar pinche fuerza bruta explorando espacio hipotético por espacio hipotético y evaluar el más chingón suponiendo que no nos traen camotes~~.

¿Cómo podemos escogar una buena hipótesis dado el espacio hipotético? Podríamos tener la esperanza de contar con una **hipótesis consistente**: una $h$ tal que cada $x_i$ en el conjunto de entrenamiento tiene $(h_i)=y_i$. Con salidas continuamente valuadas no podemos esperar un acercamiento absoluto al *ground truth*. A lo que realmente podemos aspirar es a una **función que se vea lo suficientemente bien** que no sea ni muy simple (chafona) ni muy compleja (un pinche cagadero).

## Árboles de decisión
Un **árbol de decisión** es una representación de una función que ubica a un vector de valores de atributo a una sola salida, es decir, una "decisión". Un árbol de decisión alcanza *la capacidad de decidir* mediante la realización de exámenes secuenciales , iniciando desde la raíz siguiendo una rama apropiada hasta que una hoja sea alcanzada. Cada nodo interno en el árbol corresponde a un examen de una de las entradas de atributos, las ramas del nodo se encuentran etiquetadas con todos los posibles valores del atributo, el nodo hoja especifica que valores van a ser regresados por la función.

En general, los valores de entrada y salida pueden ser discretos o continuos (por mientras vemos los discretos). En el caso de los discretos, significa que sus entradas son discretas produciendo salidas que resultan en *verdadero* (un **ejemplo positivo**) o en *falso* (un **ejemplo negativo**), esto se le conoce como **clasificación booleana**.

### Expesividad de los árboles de decisión
Un árbol de decisión booleano es equivalente a la siguiente afirmación lógica de la forma:
$$Output\leftrightarrow(Path_1 \vee Path_2 \vee ...)$$

donde cada $Path_i$ es una conjunción de la forma $(A_m=v_x \vee A_n=v_y \vee ...)$ de los exámenes de valor-atributo correspondientes a un camino desde la raíz hacia una *hoja* verdadera. Sin embargo, toda la expresión se encuentra en forma normal disjuntiva, lo que significa que cualquier función de lógica proposicional puede ser expresada como un árbol de decisión.

Para muchos problemas, el formato de un árbol de decisión forma un resultado bonito, conciso y entendible. Inclusive, los manuales para reparar autos se consideran como *árboles de decisión escritos*. Pero algunas funciones no pueden ser representadas de forma concisa.