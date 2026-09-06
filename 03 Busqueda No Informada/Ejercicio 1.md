# Ejercicio 1 — Comparación de algoritmos de búsqueda no informada

**1.- Nueva Pareja de Ciudades**

**Origen:** Oradea

**Destino:** Hirsova

El grafo quedaría de la siguiente manera: (Perdon Profesor no soy muy bueno con ASCII y no se si se entienda el regreso de Arad) =D

                        Oradea
                           │
                          151
                           │
                          Sibiu
                        /  │    80
                      /    99     \
                    /      │        Rimnicu Vilcea
                    │    Fagaras\     97
                    │            │      \
                  140           211     Pitesti
                    │            │        101
                    │       Bucharest ─────│
                    │          /   │
                    │        101   85      
                    │        /     │
                    │    Pitesti   │
                    │       │      │
                    │      138     │
                    │       │      │
                    │    Craiova   │
                    │       │      │
                    │      120     │
                    │       │      │
                    │    Drobeta   │
                    │       │      │
                    │       75     │
                    │       │      │
                    │    Mehadia   │
                    │       │      │
                    │       70     │
                    │       │      │
                    │     Lugoj    │
                    │       │      │
                    │      111     │
                    │       │      │
                    │  Timisoara   │
                    │       │      │
                    │      118     │
                    │       │      │
                    └──── Arad    │
                                 / 
                               / 
                              / 
                             / 
                            │
                          Urziceni
                            │
                           98
                            │
                         Hirsova



**2. Tabla comparativa**

| Algoritmo | Status | Path | Depth | Cost | Expanded | Generated |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| **BFS** | success | Oradea -> Sibiu -> Fagaras -> Bucharest -> Urziceni -> Hirsova | 5 | 644 km | 13 | 34 |
| **UCS** | success | Oradea -> Sibiu -> Rimnicu Vilcea -> Pitesti -> Bucharest -> Urziceni -> Hirsova | 6 | 612 km | 15 | 39 |
| **DFS** | success | Oradea -> Sibiu -> Arad -> Timisoara -> Lugoj -> Mehadia -> Drobeta -> Craiova -> Pitesti -> Bucharest -> Urziceni -> Hirsova | 11 | 1207 km | 12 | 32 |
| **DLS, limit=2 y limit=4** | cutoff | No encontró solución | — | — | 3 / 14 | 9 / 40 |
| **DLS, limit=5** | success | Oradea -> Sibiu -> Fagaras -> Bucharest -> Urziceni -> Hirsova | 5 | 644 km | 11 | 24 |
| **IDS** | success | Oradea -> Sibiu -> Fagaras -> Bucharest -> Urziceni -> Hirsova | 5 | 644 km | 36 | 97 |

**3. Reporte de lo aprendido**

Si, BFS encontró una ruta de menos carreteras, mientras que UCS encontró una ruta con menos KMS. El resultado fue que BFS encontró una ruta de 5 carreteras y 644 km, mientras que UCS encontró una ruta de 6 carreteras y 612 km. En este caso, los algoritmos no coinciden porque buscan mejorar criterios diferentes: BFS busca minimizar el numero de carreteras y UCS busca optimizar el costo acumulado de cada carretera. Podemos observar que en este caso, la opción de menos carreteras no es la que tiene menos KMS, ya que UCS uso una carretera adicional pero en su recorrido en KMS fue menor. 

En el caso de DFS, si encontró un camino mucho mas largo para el mismo grafo. Su resultado fue de una ruta de 11 carreteras y 1207 km, considerablemente más larga y costosa que las rutas encontradas por BFS y UCS. El porque de esto es que para DFS busca explorar una rama antes de buscar otras alternativas y siguió un orden de expansión de las ciudades vecinas tomando una ruta que incluye Sibiu, Arad, Timisoara, Lugoj, Mehadia, Drobeta y Craiova antes de llegar a Hirsova. Da una solución válida pero no optimiza ni carreteras ni costo de kms. 


Para DLS con --limit 2, se produjo un resultado cutoff. Esto significa que el algoritmo alcanzó el límite de profundidad antes de poder encontrar Hirsova. Lo mismo nos pasa al poner con --limit4. Ahora bien, al aumentar el límite a --limit 5, se encontró una solución de 5 carreteras y 644 km, correspondiente al mismo camino encontrado por BFS. Entonces podemos decir que el limite de profundidad debe ser suficiente para alcanzar una solución. En este caso, una profundidad de 2 no fue suficiente, mientras que una profundidad de 5 sí.


IDS encontró una solución cuando alcanzó last_limit=5. El camino y la profundidad coincidieron con los obtenidos por BFS; es decir con 5 carreteras y 644 km.

Oradea → Sibiu → Fagaras → Bucharest → Urziceni → Hirsova

Esto muestra que IDS coincide con BFS en la profundidad de la solución. La diferencia está en que IDS realiza varias búsquedas con límites crecientes, por lo que terminó expandiendo más nodos, quedo en 36 frente a 13 de BFS.

Podemos ver con los resultados, que los algoritmos de búsqueda no informada pueden producir diferentes soluciones aun cuando utilizan exactamente el mismo mapa y el mismo problema. Es decir, que la estrategia de búsqueda determina que solución se genera y que quiere optimizar. 

BFS encontró el camino con menor número de carreteras, con una profundidad de 5. UCS encontró el camino de menor costo, con 612 km, aunque necesitó 6 carreteras. DFS encontró una solución válida, pero mucho más larga, con 11 carreteras y 1207 km, debido a que no garantiza optimalidad.


**4. Se anexan imágenes de los resultados de cada algoritmo**

                        
