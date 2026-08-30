**Ejercicio 1 - Cambiar ubicación de Wumpus**

Se realizo una nueva cueva para Wumpus según las instrucciones, manteniendo al agente en la posición inicial [1,1] mirando hacia el este. 
Cambié la ubicación del Wumpus y de los pits. El Wumpus quedó en [4,3], los pits en [1,2], [3,1] y [1,4], y el oro en [2,4]. 
La configuración es válida porque todas las posiciones están dentro de la cuadrícula y no hay objetos incompatibles en la misma casilla.

Corri las pruebas de agentes, el agente de reflejo simple no logró obtener el oro y terminó después de 200 pasos con una puntuación de -200. El agente basado en modelo y el agente basado en objetivos también terminaron sin oro después de 200 pasos, con -200 puntos. El agente basado en utilidad murió después de 2 pasos sin obtener el oro, con una puntuación de -1002. En cambio, **el agente de aprendizaje** consiguió recoger el oro, regresar a la salida y subir después de 14 pasos, obteniendo una puntuación de 986.

El agente de reflejo simple considero que falla porque solamente utiliza reglas de condición-acción basadas en las percepciones actuales, es decir, ante una percepción especifica actua en consecuencia, no recuerda la cueva ni recuerda las decisiones anteriores, por lo que en mi caso se cicló. En mi prueba observé que repetía giros y terminó los 200 pasos sin conseguir el oro.

Por ultimo como se pidió probé al alejar un pit de la casilla inicial. En la configuración original había un pit en [1,2], inmediatamente junto a la posición inicial. Con esta configuración, el agente basado en modelo terminó sin oro después de 200 pasos y obtuvo -200 puntos. Moví ese pit a una posición más alejada, en [3,4], manteniendo los demás partes de la cueva y ya con esto el agente basado en modelo consiguió recoger el oro y salir de la cueva en 21 pasos, con una puntuación de 979. La ubicación de los pits SI afecta las percepciones iniciales y las decisiones del agente, entonces al alejar el pit de la salida, el agente tuvo una ruta más favorable y pudo encontrar un camino seguro hacia el oro y de regreso. 

