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

- En el **aprendizaje supervisado**, el agente observa pares de entradas y salidas, aprendiendo una función 