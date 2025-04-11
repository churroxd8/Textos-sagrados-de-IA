# Satisfacción de restricciones

## Introducción
Es ahora el momento en el que nos toca explorar el caso en el que los problemas pueden tener una resolución mediante la búsqueda de un espacio estado, esto es: Un grafo donde sus nodos son estados y sus esquinas son acciones,existe una heurística de dominio específico que pudiera estimar el costo de llegar a una meta de un estado dado, siendo desde el punto de vista de un algoritmo de búsqueda, varios estados atómicos o indivisibles —como una caja negra sin estructura interna. Para cada problema, necesitamos crear código de dominio específico que describa la transición entre estos estados.

Esto quiere decir, que nos toca abrir la caja negra mediante una **representación factorizada** para cada estado, siendo esto un conjunto de variables donde cada una cuenta con un valor. Un problema es resuelto cuando cada variable tiene un valor que satisface todas las restricciones de la variable. La descripción de este problema es conocida como el **problema de satisfacción de restricciones**, o **CSP** por sus siglas en inglés (Constraint Satisfaction Problem).

Los algoritmos de búsqueda CSP toman ventaja de la estructura de los estados y el uso *general* en lugar de las heurísticas de dominio específico para permitir la solución de problemas complejos. La idea principal es eliminar grandes porciones de espacios de búsqueda mediante la identificación de combinaciones de variables/valores que violan estas restricciones. Los CSPs cuentan con una ventaja adicional en la que las acciones y los modelos de transición pueden ser deducidos de la descripción del problema.

## Definiendo los problemas de satisfacción de restricciones
Un problema de satisfacción de restricciones consiste en tres componentes, $\chi$, $\mathcal{D}$, y $\mathcal{C}$:

$\chi$ es un conjunto de variables, $\{X_{1},...,X_{n}\}$

$\mathcal{D}$ es un conjunto de dominios, $\{D_1,...,D_{n}\}$, uno para cada variable.

$\mathcal{C}$ es un conjunto de restricciones que especifican combinaciones permitidas de valores.

Un dominio, $D_{i}$, consiste en un conjunto de valores permitidos, $\{v_{1},...,v_{n}\}$, para una variable $X_{i}$. Por ejemplo, una variable booleana tendría el dominio $\{true,false\}$. Las diferentes variables pueden tener diferentes dominios de diferentes tamaños. Cada restricción $\mathcal{C}_{j}$ consiste en un par $\lang scope,rel \rang$, donde *scope* es una tupla de variables que participan en una restricción y *rel* es una **relación** que define los valores que esas variables pueden tomar. Una relación puede ser representada como un conjunto explícito de tuplas de valores que satisfacen la restricción, o como una función que puede calcular cuando una tupla es miembro de una relación. Por ejemplo, si $X_{1}$ y $X_{2}$ comparten el dominio $\{1,2,3\}$, entonces la restricción que dice que $X_{1}$ debe de ser mayor que $X_{2}$ puede ser escrita como $\lang (X_{1},X_{2}),\{(3,1),(3,2),(2,1)\}\rang$ o como $\lang (X_{1},X_{2}),X_{1}>X_{2}\rang$.

Los CSPs realizan el manejo de las asignaciones de los valores en las variables , $\{X_{i}=v_{1},X_{j}=v_{j,...}\}$. Una asignación que no viola una restricción se le conoce como **consistente** o asignación legal. Una **asignación completa** es una en la que cada variable es asignada a un valor, y una **solución** a un CSP es una asignación completa y consistente. Una **asignación parcial** es una que deja algunas variables sin asignar y esa misma **asignación parcial**, mientras que una **solución parcial** es una asignación parcial que es consistente. Resolver un CSP es en general un problema np-completo, aunque existen algunas subclases importantes de CSPs que pueden ser resueltos de forma eficiente.