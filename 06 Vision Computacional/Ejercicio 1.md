# Ejercicio 1 — Cambiar la imagen de predicción en YOLO

**1.-Anexar archivos**

Se adjunta archivo IPYNB

**2.-Capturas**

Se adjuntan capturas de los resultados de CLI Zidane, Model Bus y CLI Mi Imagen y Model Mi imagen

**3.- Reporte de lo aprendido**

Se realizó el análisis con YOLO y en la fotografía de Ultralytics llamada zidane el modelo encontró o detectó a 2 personas y una corbata. Ahora bien en mi fotografía llamada Mi Imagen igual fue correcto y detectó 1 persona, 1 automóvil y una corbata.  Ahora bien, hice una segunda prueba y en CLI en mi segunda imagen detecto dos autos, pero no el tiburón que estaba ahí. Este objeto que no fue detectado, se debe a que en la base de datos con la que entrena YOLO que es limitado, no hay un objeto que coincida ya que no hay variables que estuviera oculto o muy pequeño lo cual también puede afectar, es por ello que un objeto puede estar presente en la imagen pero no aparecer entre los resultados.

Ahora bien comparando los análisis de CLI y la realizada mediante model('mi_foto.jpg', save=True) sí coinciden. La CLI detectó 1 persona, 1 automóvil y 1 corbata, y la ejecución de model(...) produjo exactamente las mismas detecciones: 1 person, 1 car y 1 tie, es decir el mismo resultado para la misma foto. 
