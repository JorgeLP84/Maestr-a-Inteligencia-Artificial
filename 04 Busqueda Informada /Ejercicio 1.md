# Ejercicio 1 — Comparar Greedy y A* en el mapa de Rumania

**1.- Nueva Pareja de Ciudades**

**Origen:** Timisoara

**Destino:** Bucharest

El grafo quedaría de la siguiente manera: 

**2.- Tabla Comparativa**

| Algoritmo | Heurística | Path | Depth | Cost | Expanded |
|---|---|---|---:|---:|---:|
| Greedy Best-First | Distancia en línea recta a Bucharest (AIMA) | Timisoara → Lugoj → Mehadia → Drobeta → Craiova → Pitesti → Bucharest | 6 roads | 615 km | 6 |
| A* | Distancia en línea recta a Bucharest (AIMA) | Timisoara → Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucharest | 5 roads | 536 km | 10 |

**3.- Reporte de lo Aprendido**

Compraramos los dos algoritmosc Greedy y A* utilizando la nueva pareja de ciudades que son Timisoara y Bucharest, así como la misma heurística de distancia en línea recta de la tabla de AIMA. En este caso, podemos ver dos resultados de caminos diferentes. Greedy encontró la ruta Timisoara → Lugoj → Mehadia → Drobeta → Craiova → Pitesti → Bucharest, con un costo de 615 km, mientras que A* encontró Timisoara → Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucharest, con un costo de 536 km.

Así que A* generó una ruta de 79 km menos y esto es porque en el caso de Greedy usamos nodos utilizando h(n), lo que lo hace buscar en primera instancia la ciudad que parece estar más cerca del destino; mientras que  A* utiliza f(n)=g(n)+h(n), por lo que considera tanto el costo acumulado de KM como el costo restante, lo que le permite que A* descarte algunas rutas que pueden parecer mejores según la heurística pero que pueden conducir a una ruta más costosa.

Igual considerar que en cuanto a uso de recursos, Greedy expandió solo 6 nodos y generó 15, mientras que A* expandió 10 y generó 27; así que en este caso podemos decir que  Greedy trabajó menos pero dio una solución que podemos decir que no es óptima. 

Definimos que Greedy no necesariamente encuentra el camino más porque solo se fija en qué tan cerca parece estar del destino y no toma en cuenta cuánto se ha recorrido hasta ese momento, a diferencia de A* considera tanto la distancia recorrida como la distancia que falta, por lo que puede encontrar el camino de menor costo. 

**4.- Se adjuntan evidencias**


