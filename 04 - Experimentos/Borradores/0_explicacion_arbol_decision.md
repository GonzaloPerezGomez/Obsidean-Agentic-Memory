
- **Etapa 1 (Ingesta):**
    - Evalúa la memoria de forma **intrínseca y directa**. Compara lo que el agente decidió guardar contra las entidades críticas anotadas en el dataset.
- **Etapa 2 (Pruebas Preliminares tras el _Wipe_):**
    - Evalúa si la memoria almacena suficiente señal para arrancar el protocolo clínico y si cita las entidades de justificación correctas (Grounding).
- **Etapa 3 (Bucle de Navegación del Árbol):**
    - **Teacher Forcing:** El simulador le da la prueba estándar y el resultado real del árbol (independientemente de si el agente acertó o no la prueba preliminar), garantizando que el agente siempre evalúe las bifurcaciones reales del caso.
    - **Consolidación en Memoria:** El agente debe integrar los nuevos resultados médicos en su base de datos.
    - **Siguiente Paso:** Tras otro borrado de chat, el agente decide la siguiente acción consultando su memoria actualizada. El bucle se repite hasta que el árbol de decisión concluye.


Problema:

En la primera etapa se evalúa también de forma directa el conocimineto medico del modelo. Esto podria interferir con la evaluacion de como de bien guarda el modelo la informacion