---
titulo: "Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory"
autores: "Mirac Suzgun, Mert Yuksekgonul, Federico Bianchi, Dan Jurafsky, James Zou"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2504.07952"
citekey: "suzgunDynamicCheatsheetTestTime2025"
zotero: "zotero://select/library/items/662DPP6Q"
tags:
  - paper
  - agentic-reasoning
  - test-time
  - memoria
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-09"
valoracion: ⭐⭐⭐⭐⭐
---

# Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory

## Metadatos

- **Autores**: Mirac Suzgun, Mert Yuksekgonul, Federico Bianchi, Dan Jurafsky, James Zou
- **Año**: 2025
- **Publicación**: arXiv preprint (Stanford)
- **DOI**: [10.48550/arXiv.2504.07952](https://doi.org/10.48550/arXiv.2504.07952)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/662DPP6Q)
- **Abstract**: Current LMs operate in a vacuum without retaining insights from previous attempts. We present Dynamic Cheatsheet (DC), a lightweight framework that endows a black-box LM with a persistent, evolving memory. DC enables models to store and reuse accumulated strategies, code snippets, and problem-solving insights at inference time.

---

## Resumen

Dynamic Cheatsheet (DC) es un framework ligero para **test-time learning** que dota a LLMs de caja negra con una memoria adaptativa y auto-curada. En lugar de procesar cada consulta de forma aislada (y cometer los mismos errores repetidamente), DC permite al modelo extraer heurísticas, estrategias abstractas o código validado de sus intentos exitosos y guardarlos en una "chuleta" persistente. Al enfrentarse a nuevos problemas, consulta su chuleta, logrando mejoras drásticas (ej. de 10% a 99% en Game of 24, el doble de precisión en AIME).

---

## Problema / Motivación

Los LLMs estándar sufren de "amnesia de inferencia": cada consulta se procesa desde cero en un vacío. El modelo no retiene lecciones de sus éxitos ni aprende de sus fracasos entre consultas independientes, redescubriendo soluciones lentamente o repitiendo errores aritméticos. Mientras que fine-tuning es costoso y los métodos RAG estáticos no adaptan habilidades sobre la marcha, se necesita un método en tiempo de inferencia que emule el aprendizaje acumulativo humano sin modificar parámetros subyacentes.

---

## Metodología

### Ciclo del Dynamic Cheatsheet (DC-Curated)
1. **Recuperación**: Ante una nueva consulta, el LLM revisa su memoria externa para extraer heurísticas, insights o código relevante previamente almacenado.
2. **Resolución**: El LLM combina los insights recuperados con su propio razonamiento interno para generar una respuesta.
3. **Fase de Curación (Self-Curation)**: Tras generar una respuesta, el modelo evalúa su utilidad.
   - Si el enfoque es exitoso y práctico, lo codifica abstractamente en la memoria.
   - Si se detecta un error, poda o revisa las heurísticas defectuosas en la memoria.

La memoria se estructura como fragmentos (snippets) concisos y transferibles en lugar de guardar historiales de chat literales.

---

## Resultados Clave

- **AIME (Matemáticas)**: La exactitud de Claude 3.5 Sonnet se **duplicó** al retener intuiciones algebraicas entre preguntas.
- **Game of 24**: El porcentaje de éxito de GPT-4o subió del **10% al 99%** al descubrir y reutilizar una solución basada en Python.
- **Balanceo de ecuaciones**: GPT-4o y Claude alcanzaron casi 100% de precisión reutilizando código validado (sus baselines se estancaban en 50%).
- **Tareas de conocimiento general**: Mejoras de 9% en GPQA-Diamond y 8% en MMLU-Pro.

---

## Contribuciones Principales

1. **Framework DC**: Un enfoque training-free (caja negra) para test-time learning mediante memoria abstracta y transferible.
2. **Self-Curation**: Mecanismo de auto-evaluación para que el modelo decida de forma autónoma qué heurísticas promover a la memoria y cuáles podar.
3. **Validación empírica extensa**: Demostración de que el caching de estrategias abstractas soluciona el "reinicio en frío" en razonamiento.

---

## Limitaciones

- **No soluciona carencias fundacionales**: Modelos pequeños (ej. GPT-4o-mini) se benefician muy poco porque no generan soluciones correctas iniciales para poblar la memoria; su memoria se llena de estrategias defectuosas.
- **Requisito de auto-evaluación**: Depende de que el modelo sea capaz de distinguir si un intento fue útil o erróneo para curar la chuleta.

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> Rather than repeatedly re-discovering or re-committing the same solutions and mistakes, DC enables models to store and reuse accumulated strategies, code snippets, and general problem-solving insights at inference time. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> DC is not a panacea. We found that smaller models, such as GPT-4o-mini, benefit from DC in limited amounts. These models generate too few correct solutions in these challenging tasks in the first place, leaving the memory populated with flawed or incomplete strategies. DC can amplify the strengths of models that can already produce high-quality outputs, but not fix foundational gaps in reasoning. [#ffd400]

---

## Ideas y Conexiones

- DC es un ejemplo de [[In-Context Reasoning]] aplicado a la memoria agéntica.
- Es complementario y análogo conceptualmente a la **Evolución Procedimental** (Procedural Evolution) mencionada en el survey (Wei et al.): crear librerías de habilidades. Sin embargo, DC también almacena heurísticas abstractas ("chuletas"), no solo código ejecutable.
- Su fase de curación guarda profunda conexión con [[Reflexion]], pero DC almacena la reflexión en una base global inter-tareas, en lugar de ser un loop intra-tarea.
- La limitación reportada con modelos pequeños es el clásico problema de *self-correction* en LLMs: si el modelo no puede resolver el problema, no puede generar buena memoria. "Amplifica, no arregla carencias base".

---

## Notas Relacionadas

- [[Agentic Memory]] — DC es un mecanismo de memoria evolutiva temporal
- [[In-Context Reasoning]] — El método opera puramente a nivel de inferencia/contexto
- [[Reflexion]] — Curación mediante reflexión sobre errores/éxitos
- [[Self-Evolving Agentic Reasoning]] — Evolución inter-episodios sin cambio de parámetros
