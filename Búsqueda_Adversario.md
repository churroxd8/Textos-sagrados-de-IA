# Juegos que no son juegos
Podríamos empezar definiendo un juego más en el sentido como un "puzzle" donde se encuentra involucrado más de un agente. Es importante hacernos las siguientes preguntas:
- ¿Es determinista o estocástico?
- ¿Qué tanta información se tiene? (En referencia a totalmente observable)
- ¿Dos, tres o más jugadores?
- ¿Juego en equipo o juego individual?
- ¿Basado en turnos o simultáneos?
- ¿Es forzosamente de suma cero o no?
## Juegos deterministas
Existen varias posibles formalizaciones, una puede ser:
- Conjunto de estados $S$ con $s_0$ como inicial. Es importante decir que $s_0\in S$.
- Cuento con un conjunto de acciones $A$.
- Cuento con un grupo de jugadores $P=\{1,2,...,N\}$
- Las acciones legales se definen como $S \times P \rightarrow P(A)$
- Nuestras transiciones se definen como $S \times A \times P \rightarrow S$
- ¿Es terminal? $S \rightarrow \{T,F\}$
- Nuestra ganancia: $S \times P \rightarrow \reals$
- Las políticas (no de los partidos políticos): $\pi_{p}=S \rightarrow A$

## Un código en Python
```python
class ModeloJuegoDetTZ2:
    def inicializa(self):
        return (so,s)
    def acciones_legales(self,s,j):
        return {a1,a1,...}
    def transicion(self,s,a,j):
        return s
    def terminal(self,s):
        return bool
    def ganancia(self,s):
        return ganancia de 1
```
## Vamos a jugar al gato
Los posibles estado del juego del gato pueden ir desde $x[0],x[1],x[2],...,x[8]$.

El agente que inicia el juego, cuenta con 9 acciones legales posibles, donde lo podemos representar de la siguiente manera a continuación:
$$\begin{cases}
    0 & 1\\
    1 & 9\\
    2 & 9 \times 8\\
    3 & 9 \times 8 \times 7\\
    ...\\
\end{cases}$$
Nos podemos dar cuenta que la profundidad de la búsqueda en las jugadas en el gato equivale a $9!=9\times 8\times 7\times 6\times...\times 2\times 1=362,880$. Pero si somos realistas, podemos concluir también que debido a la naturaleza del juego, no necesariamente significa que llegaremos a lo más profundo de los nodos, por lo que podríamos tener una búsqueda relativamente corta con simplemente ganar el juego fácilmente.

## Minimax
Podemos definir la búsqueda adversarial (conocida como Minimax) de la siguiente manera:
- Un árbol de búsqueda de espacio-estado.
- Los jugadores realizan acciones en sus respectivos turnos.
- La labor de cómputo para el valor minimax de cada nodo es: La utilidad fácilmente posible en contra de la racionalidad (concepto de óptimo). Parecido al pensamiento de como los ludopatas de los casinos o de la bolsa de valores piensan que van a "chingarse" al sistema.

### Una posible implementación de Minimax
```
def max-value(state):
    initialize v = //aquí va menos infinito hipotético
    for each successor of state:
        v = max(v, min-value(successor))
    return v

def min-value(state):
    initialize v = //aquí va más infinito hipotético
    for each successor of state:
        v = min(v, max-value(successor))
```
Esto también lo podemos ver de la siguiente manera:
$$V(s)=max\space \text{donde}\space s^{\shortmid}\in successors(s)\space V(s^{\shortmid})$$
$$V(s^{\shortmid})=min\space \text{donde}\space s\in successors(s^{\shortmid})\space V(s)$$

## Implementación de dispatch para el Minimax
```
def value(state):
    si el estado es un estado terminal: regresamos la utilidad del estado
    si el siguiente nodo es MAX: regresamos max-value(state)
    si el siguiente nodo es MIN: regresamos min-value(state)

def max-value(state):
    inicializamos v = menos infinito
    for each successor of state:
        v = max(v, value(sucessor))
    return v

def min-value(state):
    inicializamos v = más infinito
    for each successor of state:
        v = min(v, value(sucessor))
    return v
```
## La eficiencia del minimax
Si bien la idea del minimax puro (hago incapié en puro) es bonita, en un caso real, solamente nos serviría para árboles bastante pequeños debido a que realiza todo el recorrido del árbol.

Por ejemplo, en el ajedrez tenemos que $b \approx 35$, $m \approx 100$, es necesario realizar las siguientes anotaciones:
- La resolución de una partida de ajedrez no se da en 100 turnos, es decir, una partida puede acabar en menos turnos. Un dato curioso, es que en normas oficiales, las partidas tienen límite de turnos y en caso de no haber un jugador victorioso, se declara empate.
- Esto nos hace hacernos la siguiente pregunta, ¿es necesario recorrer todo un árbol de posibles jugadas?

Esto de primera mano, no es para nada eficente, por lo que es necesario implementar maneras de que el minimax realice su recorrido dentro del árbol de búsqueda de forma eficiente.

### La poda alfa beta
Para iniciar, debemos mencionar que el orden de generación de los datos contenidos en el árbol es bastante importante, debido a que determina el resultado después de aplicar la poda alfa beta dentro del minimax.