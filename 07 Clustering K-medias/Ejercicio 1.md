# Ejercicio 1 — Cambiar la imagen de predicción en YOLO

**1.-Enlace Colab**

**2.-Anexar archivos**

**3.-5 Centros y 5 STD**

**4.- Reporte de lo aprendido**

En el primer ejercicio se trabajó con cinco blobs, pero el resultado de las gráficas no indicó que cinco fuera la mejor opción. En la gráfica del codo se observó que el cambio más importante estaba en k=4, y la gráfica de silueta también tuvo su valor más alto en k=4, con aproximadamente 0.6. Esto se debe principalmente a que tres de los grupos originales estaban muy cerca entre sí. Los tres centros tenían la misma coordenada x = -2.8, por lo que sus puntos se mezclaban y K-means podía considerarlos como un solo grupo.

Para el segundo ejercicio mantuve los mismos parámetros y los mismos 2000 puntos, pero cambié la posición de los cinco centros para que estuvieran más separados. Con los nuevos centros, los cinco grupos se pueden distinguir mucho mejor en la gráfica. La inercia para k=3 fue 2109.319, para k=5 fue 215.915 y para k=8 fue 122.220. En la gráfica del codo se observa una caída muy grande al llegar a k=5 y después la reducción es mucho menor. Por esta razón, el codo indica k=5.

La gráfica de silueta también dio como resultado más alto k=5. Esto significa que, después de separar los blobs, tanto el codo como la silueta coinciden en que cinco grupos es una buena opción. En este caso, el resultado coincide con los cinco blobs que fueron generados originalmente.

Este ejercicio me permitió observar que no es suficiente con indicar cuántos centros se utilizaron para generar los datos. También es importante qué tan separados están los grupos y qué tan dispersos son sus puntos. Si el codo hubiera seguido indicando k=4, habría sido necesario separar todavía más los centros o hacer los grupos más compactos usando un blob_std menor.

