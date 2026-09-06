# Ejercicio 1 — Comparar Greedy y A* en el mapa de Rumania

**1.- Nueva Pareja de Ciudades**

**Origen:** Timisoara

**Destino:** Bucharest

Dividi en dos grafos, por cada resultado:

### Grafo - Greedy

```text
Timisoara [h=329]
     |
     | 111 km
     v
Lugoj [h=244]
     |
     | 70 km
     v
Mehadia [h=241]
     |
     | 75 km
     v
Drobeta [h=242]
     |
     | 120 km
     v
Craiova [h=160]
     |
     | 138 km
     v
Pitesti [h=100]
     |
     | 101 km
     v
Bucharest [h=0]

Costo total: 615 km
```

### Grafo - A*

```text
Timisoara [h=329]
     |
     | 118 km
     v
Arad [h=366]
     |
     | 140 km
     v
Sibiu [h=253]
     |
     | 80 km
     v
Rimnicu Vilcea [h=193]
     |
     | 97 km
     v
Pitesti [h=100]
     |
     | 101 km
     v
Bucharest [h=0]

Costo total: 536 km
```


**2.- Tabla Comparativa**

| Algoritmo | Heurística | Path | Depth | Cost | Expanded |
|---|---|---|---:|---:|---:|
| Greedy Best-First | Distancia en línea recta a Bucharest (AIMA) | Timisoara → Lugoj → Mehadia → Drobeta → Craiova → Pitesti → Bucharest | 6 roads | 615 km | 6 |
| A* | Distancia en línea recta a Bucharest (AIMA) | Timisoara → Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucharest | 5 roads | 536 km | 10 |

**3.- Reporte de lo Aprendido**

Compraramos los dos algoritmosc Greedy y A* utilizando la nueva pareja de ciudades que son Timisoara y Bucharest, así como la misma heurística de distancia en línea recta de la tabla de AIMA. En este caso, podemos ver dos resultados de caminos diferentes. Greedy encontró la ruta Timisoara → Lugoj → Mehadia → Drobeta → Craiova → Pitesti → Bucharest, con un costo de 615 km, mientras que A* encontró Timisoara → Arad → Sibiu → Rimnicu Vilcea → Pitesti → Bucharest, con un costo de 536 km.

A* encontró una ruta 79 km más corta. Esto se debe a que Greedy se fija principalmente en h(n), es decir, en qué ciudad parece estar más cerca del destino. En cambio, A* utiliza f(n)=g(n)+h(n), por lo que toma en cuenta tanto los kilómetros recorridos como los que faltan. De esta manera, A* puede evitar rutas que parecen buenas al principio, pero que terminan siendo más largas. 

Igual considerar que en cuanto a uso de recursos, Greedy expandió solo 6 nodos y generó 15, mientras que A* expandió 10 y generó 27; así que en este caso podemos decir que  Greedy trabajó menos pero dio una solución que podemos decir que no es óptima. 

Definimos que Greedy no necesariamente encuentra el camino más porque solo se fija en qué tan cerca parece estar del destino y no toma en cuenta cuánto se ha recorrido hasta ese momento, a diferencia de A* considera tanto la distancia recorrida como la distancia que falta, por lo que puede encontrar el camino de menor costo. 

**4.- Se anexan imágenes de los resultados de cada algoritmo**
