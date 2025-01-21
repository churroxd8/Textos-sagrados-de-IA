# Introducción a la Inteligencia Artificial

## Nota del editor

Las notas de esta semana quiero centrarlas principalmente en el ámbito histórico de la inteligencia artificial, ya que es realmente interesante
como partiendo de diferentes conceptos que a primeras no lo asociariamos con la materia, sirven como un punto de partida para la concepción
de lo que actualmente conocemos como Inteligencia Artificial. Al ser notas de caracter personal, me gusta agregar un poco de humor ácido
para sacarle risas al Luis Mario del futuro y tal vez a algún curioso que lea esto.


## Introducción

Nos hacemos llamar *Homo sapiens* es decir, hombre sabio porque la inteligencia es bastante importante para nosotros como seres humanos.
A lo largo de los años, hemos querido entender el *como pensamos y actuamos* a pesar de que nuestro cerebro es una masa orgánica que puede
percibir, entender, predecir y manipular un mundo que es complejo.

La **inteligencia artificial** es uno de los campos que ha tenido un crecimiento exponencial a lo largo del tiempo, llegando a facturar
alrededor de un trillón de dólares en ganancias. Si bien, se tiene la creencia que la inteligencia artificial actúa como un campo en solitario,
la realidad es que esta se divide en varios subcampos, desde un ámbito general (aprendizaje, razonamiento, percepción, etc.) a cosas más específicas
como jugar al ajedrez, demostrar teoremas matemáticos, escribir poesía, manejar un auto o diagnosticar enfermedades; haciendola relevante para cualquier
tarea intelectual, llegando a un campo universal.

## Pero, ¿qué es la inteligencia artificial?

Diversos intelectuales a lo largo de la historia, han desarrollado diferentes puntos de vista con respecto a la inteligencia artificial
mediante diferentes definiciones de inteligencia. Algunos se han inclinado por el lado del *desempeño humano*, mientras que otros
han optado por una definición más abstracta y formal. El concepto de *racionalidad*, informalmente lo podemos entender como:
"hacer lo correcto" (esta frase meramente Kantiana da para un debate interminable). Otros, han considerado el concepto de inteligencia
como *una propiedad de los procesos internos del pensamiento*, otros decidieron enfocarse en el *comportamiento* inteligente observable, es decir,
una característica externa.

Podemos generalizar dos dimensiones por parte de estos intelectuales, una que decide ir de lo humano a lo racional y otra que va del pensamiento
al comportamiento, lo cual produce una combinación de enfoques:

- Actuar como humanos
- Pensar como humanos
- Pnesar racionalmente
- Actuar racionalmente

Vamos a intentar comprender estos conceptos.


### Actuar como humanos

Un cierto matemático inglés con un característico humor negro de nombre Alan Turing, propone un experimento mental llamado Juego de Imitación
(posteriormente prueba de Turing), que parte de un cuestionamiento filosófico "¿Puede una máquina pensar?". La computadora tiene que pasar un interrogatorio hecho por un ser humano, en donde mediante preguntas escritas. Si las respuestas obtenidas por el interrogador no pueden ser distinguidas entre un ser humano o una computadora, 
la computadora ha pasado la prueba.

El programar una computadora para pasar la prueba de Turing es un reto, ya que se ocupan algunos dotes como los siguientes:

- **Procesamiento de lenguaje natural** para responder las preguntas del interrogatorio policial al que será sometido la computadora.
- **Representación del conocimiento** para poder almacenar lo escuchado y lo que sabe.
- **Razonamiento automatizado** para responder las preguntas del interrogatorio.
- **Aprendizaje automático** para adaptarse a diferentes circunstancias y cagarla menos básicamente (cagarla menos significa detectar y establecer patrones).

Si bien esta prueba fue diseñada hace bastante tiempo y pues no tenemos un Delorean para llevarle nuestro hackeo a Turing, no se consideró esencial la *simulación física*
para demostrar que la máquina aparte de razonar, es inteligente, han surgido variantes del juego de imitación que requieren interacción con el mundo real, por lo que
es necesario de herramientas adicionales como:

- **Visión artificial** para que vea el mundo
- **Reconocimiento de audio y voz** para escuchar al mundo y las sandeces del interrogador.
- **Robótica** para manipular objetos y moverse.

### Pensar como humanos

Si queremos que un programa piense como un ser humano, debemos de comprender como el ser humano piensa. Podemos comprender el pensamiento humano de estas tres maneras:

- **Introspección**: Captar nuestros pensamientos conforme vienen.
- **Experimentos psicológicos**: Observar a alguien en acción.
- **Neuroimagen**: Observar el cerebro en acción.

Una vez que hemos comprendido como está el pedo con nuestra mente, es posible expresarlo de forma teórica en un programa de computadora. Si el comportamiento de
entrada-salida de nuestro programa coincide con el comportamiento humano, es una evidencia de que los mecanismos del programa también operan en humanos.
Un ejemplo de esto es el desarrollo del "Solucionador General de Problemas" por Allen Newell y Herbert Simon (GPS) en 1961. Si bien, el solucionador se
rifaba resolviendo problemas de forma correcta, Newell y Simon estaban preocupados por comparar la secuencia y el tiempo de sus pasos de razonamiento
con los de los sujetos humanos que se encontraban resolviendo los mismos problemas. El campo interdisciplinario de la **ciencia cognitiva** reúne modelos
informáticos de la inteligencia artificial y algunas técnicas experimentales de la psicología para poder construir teorías precisas y comprobables de la
mente humana.

### Pensar racionalmente

El filósofo griego Aristóteles fue de los primeros en codificar el concepto de "pensamiento correcto", es decir, un proceso de razonamiento irrefutable.
Los **silogismos** de Aristóteles proporcionaron patrones para la estructuración de argumentos en donde se arrojaban conclusiones correctas cuando se 
patría de una premisa correcta. Supuestamente, estas leyes del pensamiento gobernaban el funcionamiento de la mente y su estudio inició el campo que 
actualmente llamamos **lógica**.

En el siglo 19, ~~unos batos que no tenían tele, pero curiosos a morir~~ los lógicos desarrollaron una notación precisa para enunciados acerca de los
*objetos en el mundo y sus relaciones entre sí*. Pisandole el acelerador, en 1965 los programas podían, en principio, *resolver cualquier problema soluble descrito en notación lógica*. La tradición **logicista** dentro de la inteligencia artificial aspira a la construcción sobre tales programas para crear sistemas inteligentes.

La lógica tradicional exige el *conocimiento certero del mundo*, donde siendo realistas es poco común. Haciendo la diferencia de cosas como el ajedrez o la aritmética,
cosas como la política o la guerra son bien inciertas. Pero para llenarnos el vacío tenemos a la **probabilidad**, permitiendo el razonamiento riguroso con información
incierta. La probabilidad nos permite construir modelos que, a partir de información percibida, ayuda a comprender el mundo e incluso predecir el futuro. Sin embargo,
no se garantiza la generación de *comportamiento* inteligente (no hace milagros, pues).

### Actuar racionalmente

Un **agente** es simplemente un wey que actúa. En el contexto de la inteligencia artificial, los agentes de computadora cargan con la expectativa de operar de manera
autónoma, percibiendo su entorno, persistiendo sobre periodos de tiempo prolongado, adaptándose al cambio, creando objetivos y persistiendo en lograr metas. Un **agente racional** es uno que actúa para obtener el resultado más chingón que se espera de el.

El enfoque logicista de la inteligencia artificial se centra en realizar inferencias correctas. Aunque esto lo podemos relacionar con un agente racional, existen formas de actuar racionalmente que no implican inferencias. Por ejemplo, andar en la pendeja y poner la mano en una estufa caliente para quitarla en chinga porque sino te quemas,
es un reflejo inconsciente (porque luego salen ampollas bien culeras) pero efectivo, que realizar una acción profunda y tener una quemadura por seguir en la pendeja, pero
de forma lógica y racional (no lo intentes en casa por favor).

Todas las habilidades que se necesitan para la prueba de Turing también permiten a un agente actuar de forma racional. La representación de conocimiento y el razonamiento permite que los agentes tomen buenas decisiones. Tenemos que generar enunciados comprensibles en lenguaje natural para sobrevivir en una sociedad compleja. También necesitamos aprender para poder generar comportamiento efectivo, especialmente en circunstancias nuevas.

El enfoque de los agentes racionales para la inteligencia artificial ha sido utilizado bastante en la historia, ya que fueron construidos sobre fundamentos lógicos y construían planes específicos para lograr metas específicas. Posteriormente, métodos basados en la teoría de la probabilidad y aprendizaje automático permitieron la creación de agentes que pueden tomar decisiones bajo incertidumbre para alcanzar el mejor resultado esperado.

La inteligencia artificial se ha enfocado en el estudio y construcción de agentes que **hacen lo correcto**. A lo que nos refiramos con ello definido por un objetivo que se provee al agente.

### Beneficiar al humano

~~Para que los teoricos de la conspiración no se espanten o se espanten más~~
El modelo estándar no es probablemente el adecuado a largo plazo, principalmente porque supone que podeemos proveer un objetivo completamente especificado a la máquina. La complejidad de los problemas del mundo real (ya ven como son los políticos) dificulta la especificación completa y precisa de un objetivo para la inteligencia artificial.

El desafío de asegurar las preferencias humanas es reflejado en los objetivos de la inteligencia artificial como el **problema de alineación de valores**. El hecho de resolverlo implica que los valores y objetivos de la máquina están alineados con los de los humanos.

Un ejemplo de lo que estoy diciendo es *construir un coche autónomo* (como el waymo que se puso a dar vueltas en circulos así bien cagado) (https://edition.cnn.com/2025/01/07/business/waymo-circles-delay/index.html). El objetivo es **llegar al objetivo de forma segura**. Pero al conducir por cualquier carretera significa estar en riesgo de un accidiente por diferentes factores como: conductores erráticos, fallos eléctricos, mecánicos, etc.; por lo tanto, un objetivo de seguridad sería mantener el coche estacionado. Exsite la disyuntiva entre avanzar hacia el destino e incurrir posibles lesiones. ¿Cómo podemos resolver esto? ¿Hasta que punto podemos permitir que el coche realice acciones que *molesten a otros conductores*? ¿Qué tan rápido o lento puede ir el coche? ¿Cómo debe de moderar su aceleración, dirección y frenado para evitar dejar mareado al pasajero?.

Incluso si planteamos algo más tranquilo como **ganar una partida de ajedrez**, considerando que la máquina está bien pesada (suficientemente inteligente) como para razonar y actuar más allá del espacio del tablero. En este caso, podría realizar acciones como aumentar sus posibilidades de ganar mediante trampas o movimientos ilegales o *chantajear al competidor o sobornar a la audiencia* para que desconcentre al oponente. O de plano *secuestrar poder computacional* de otras computadoras para sí misma. Estos comportamientos no se considerarían "poco inteligentes o dementes"; son una consecuencia lógica de definir como ganar (tan general que es maquiavélico) el único objetivo de la máquina.

Si una máquina reconoce el desconocimiento del objetivo completo, tendrá incentivos para *actuar cautelosamente, pedir permiso, aprender nuestras preferencias* mediante la observación y *ceder el control* a los humanos cuando sea necesario. En última instancia, buscamos agentes que sean **demostrablemente beneficiosos** para la humanidad (y para que la gente no ande de ondiada pensando que se volveran Terminator y bye bye sociedad).

## Conclusiones

La primera semana estuvo bien cargada, pero se manejan conceptos interesantes que destruyen ciertos mitos sobre la inteligencia artificial. Me quise inclinar por algo más de choro porque pienso que es necesario comprender el camino recorrido antes de entrar al resto de temas que se encontraran en las notas de semanas posteriores.