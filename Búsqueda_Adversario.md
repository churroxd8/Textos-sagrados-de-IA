# Juegos que no son juegos (Búsqueda adversarial)
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