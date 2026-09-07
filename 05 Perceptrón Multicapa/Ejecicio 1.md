**Reporte de lo aprendido**

Al correr las notebooks pudimos ver que el agregar dos capas adicionales no generó una mejora en el aprendizaje, en el notebook original NumPy, el error disminuye aproximadamente de 0.70 a 0.06 después de 500 épocas y se tuvo que la curva dió una reducción fuerte al inicio y continúa disminuyendo de manera gradual, lo que nos indica que la red sigue aprendiendo durante el entrenamiento. Ahora bien, en el notebook modificado, al agregar las dos capas, el error comienza alrededor de 0.72, baja rápidamente hasta aproximadamente 0.67 y después permanece constante durante en las demás épocas. Podemos ver que al final la red más profunda no logra seguir reduciendo el error y su desempeño es considerablemente peor que el de la arquitectura original. 

Con Keras se observa un comportamiento similar. La arquitectura 4×3×3 reduce el loss de 0.2646 en la primera época a 0.1627 en la época 500, mostrando un buen aprendizaje. En la arquitectura más profunda, 4×3×3×3×3, el loss pasa de 0.2264 a 0.2218, por lo que podemos decir que se quedó estancado. 

Comparación entre NumPy y Keras

Las curvas de NumPy y Keras presentan una tendencia general similar: la arquitectura más sencilla consigue aprender mejor que la arquitectura más profunda. Sin embargo, los valores exactos de error no son iguales. Esto es esperable porque las implementaciones pueden tener diferencias en la inicialización aleatoria de los pesos, el orden de los datos, la forma en que se realizan las actualizaciones de los pesos, el tamaño de los lotes, la tasa de aprendizaje y otros detalles de implementación.

Sí, las redes tienen una topología similar y a pesar de eso no van a generar curvas idénticas. En este caso ambas implementaciones muestran la misma tendencia general: al agregar capas, el entrenamiento se vuelve más difícil y el error deja de disminuir de manera significativa.

En cuanto al uso de la sigmoide, los gradientes pueden hacerse muy pequeños al propagarse hacia las primeras capas de la red lo que dificulta que una red más profunda actualice adecuadamente sus pesos.

En este ejemplo también vimos que al combinar MSE con la activación sigmoide, los gradientes tienden a hacerse muy pequeños durante el retro propagación  dificultando el aprendizaje de las capas iniciales, con lo que podemos entender por qué la red más profunda prácticamente se estancó, mientras que la arquitectura más sencilla logró reducir considerablemente el error. 

Al final vimos que tanto NumPy como Keras nos demuestran que agregar más capas en este ejemplo no mejoraron el aprendizaje así que podemos decir que una red con más capas no siempre es mejor y que la arquitectura, las funciones de activación y el método de entrenamiento deben elegirse de acuerdo con el problema. 



