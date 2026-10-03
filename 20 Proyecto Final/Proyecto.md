## Reporte Proyecto Final ##

Desarrollar un sistema RAG para consultar información de Land Rover, principalmente sobre garantías, mantenimiento y características de diferentes modelos.

El corpus está formado por **26 documentos PDF**, que fueron divididos en **222 chunks**. Para generar los embeddings se utilizó el modelo **`gemini-embedding-001`** de Google AI.

Los embeddings se almacenan en **ChromaDB**, que permite realizar búsquedas de los fragmentos más relacionados con cada pregunta.

Los documentos se dividieron en fragmentos de aproximadamente **300 palabras**, con un **overlap de 60 palabras** entre fragmentos. Se utilizó este solapamiento para evitar perder información cuando una idea queda dividida entre dos chunks y conservar parte del contexto entre fragmentos.

En cuanto al funcionamiento del RAG cuando el usuario realiza una pregunta, esta se convierte en un embedding y se utiliza para buscar en ChromaDB los fragmentos más relacionados.

Google AI realiza dos tareas diferentes:
* **`gemini-embedding-001`**: convierte los textos y las consultas en vectores para poder compararlos.
* **`gemini-3.5-flash`**: utiliza los fragmentos recuperados como contexto para generar la respuesta.

**ChromaDB** se encarga de almacenar los embeddings y realizar la búsqueda de los fragmentos similares.

Se hizo de manera que el sistema está configurado para no inventar información. Si los resultados recuperados no proporcionan evidencia suficiente para responder la pregunta, el sistema indica:
"No tengo evidencia suficiente en los documentos proporcionados para responder esta pregunta."

De esta forma, las respuestas se mantienen basadas en la información disponible en el corpus.

Al final, con el proyecto pudimos implementar un sistema RAG completo, desde el procesamiento de documentos hasta la búsqueda y generación de respuestas.

Las pruebas realizadas mostraron que el sistema puede responder preguntas relacionadas con el corpus y abstenerse cuando la información solicitada no está disponible.

La combinación de Google AI para embeddings y generación con ChromaDB para la búsqueda vectorial permite consultar de forma sencilla información específica de los documentos de Land Rover.


