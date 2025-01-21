# Aprendizaje máquina

## Motivación

Es jodidamente difícil escribir programas que resuelvan problemas complejos como reconocer objetos en tres dimensiones, desde una perspectiva diferente y con condiciones de luz diferentes.

- No podemos escribir el programa porque no tenemos idea de como procesa nuestro cerebro ese tipo de información.

- Aunque supieramos como escribirlo, el programa estaría de la chingada.

Es difícil escribir un programa que calcule la probabilidad que una transacción en línea sea fraudulenta (la gente está cabrona wey):

- No existen reglas simples y confiables en este caso. Es necesario escribir una gran cantidad de reglas.

- Aún existiendo, el fraude es un proceso dinámico, y hay que estar actualizando las reglas continuamente.

## La solución

En lugar de escribir un programa específico a cada tarea, podemos recolectar muchos ejemplos que especifiquen la respuesta correcta en cada caso.

Enviamos los datos a un algoritmo de *aprendizaje máquina* el cual nos devuelve un **programa**:

- El programa producido es muy diferente a un programa hecho a mano.

- Si está bien hecho, debe funcionar para nuevos casos con cierto margen de confianza.

- Si los datos cambian, es posible cambiar el programa.

Grandes cantidades de datos, y capacidad masiva de computo es más económico actualmente que expertos en tareas específicas.

## Primera definición

> Machine Learning: Field of study that gives computers the ability to learn without being explicitly programmed. A. Samuel (1959)

## Segunda definición

> Well-posed Learning Problem: A computer program is said to learn from experience **E** with respect to some task **T** and some performance measure **P**, if its performance on **T**, as measured by **P**, improves with experience **E**.