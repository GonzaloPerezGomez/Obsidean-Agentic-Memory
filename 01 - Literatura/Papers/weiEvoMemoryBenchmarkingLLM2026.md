---
titulo: "Evo-Memory: Benchmarking LLM Agent Test-time Learning with Self-Evolving Memory"
autores: "Tianxin Wei, Noveen Sachdeva, Benjamin Coleman, Zhankui He, Yuanchen Bei, Xuying Ning, Mengting Ai, Yunzhe Li, Jingrui He, Ed H. Chi, Chi Wang, Shuo Chen, Fernando Pereira, Wang-Cheng Kang, Derek Zhiyuan Cheng"
año: "2026"
fuente: ""
DOI: "10.48550/arXiv.2511.20857"
citekey: "weiEvoMemoryBenchmarkingLLM2026"
zotero: "zotero://select/library/items/5MGRRSLE"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - benchmarks
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-08"
valoracion: ⭐⭐⭐⭐⭐
---

# Evo-Memory: Benchmarking LLM Agent Test-time Learning with Self-Evolving Memory

## Metadatos

- **Autores**: Tianxin Wei, Noveen Sachdeva, Benjamin Coleman, Zhankui He, Yuanchen Bei, Xuying Ning, Mengting Ai, Yunzhe Li, Jingrui He, Ed H. Chi, Chi Wang, Shuo Chen, Fernando Pereira, Wang-Cheng Kang, Derek Zhiyuan Cheng
- **Año**: 2026
- **Publicación**: arXiv preprint (Google / UIUC / Penn State)
- **DOI**: [10.48550/arXiv.2511.20857](https://doi.org/10.48550/arXiv.2511.20857)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/5MGRRSLE)
- **Abstract**: Existing evaluations mostly focus on static conversational settings, where memory is passively retrieved from dialogue. We introduce Evo-Memory, a comprehensive streaming benchmark for evaluating self-evolving memory in LLM agents. We unify over 10 memory modules, propose ExpRAG (baseline) and ReMem (action-think-memory pipeline).

---

## Resumen

**Evo-Memory** es el primer benchmark comprensivo diseñado para evaluar la capacidad de **memoria auto-evolutiva** en LLMs frente a flujos de tareas continuos (streaming). Transforma datasets estáticos en secuencias donde el agente debe recuperar, integrar y actualizar conocimiento dinámicamente. Evalúa 10 módulos de memoria representativos e introduce **ExpRAG** (un baseline de recuperación de experiencia) y **ReMem** (un pipeline integrado que unifica razonamiento, acción y actualización activa de la memoria).

---

## Problema / Motivación

La evaluación tradicional de la "memoria" en LLMs suele medir recall estático sobre un contexto conversacional fijo ("encontrar la aguja en el pajar"). Sin embargo, los agentes del mundo real (asistentes, embodied agents) se enfrentan a un **flujo continuo de tareas (task streams)**. Un agente verdadero debe ser capaz de acumular experiencia, abstraer reglas, retener contexto a largo plazo y actualizar creencias (test-time learning). Antes de este benchmark, no existía una forma unificada de evaluar sistemáticamente si un LLM sabe "aprender de su propia experiencia sobre la marcha".

---

## Metodología

1. **Benchmark Evo-Memory**:
   - Transforma 10 datasets tradicionales (QA, reasoning, multi-turn goal-oriented) en *secuencias continuas de tareas*.
   - El agente procesa iterativamente: Tarea $t \rightarrow$ Interactúa $\rightarrow$ Recibe Feedback $\rightarrow$ **Actualiza Memoria** $\rightarrow$ Tarea $t+1$.
   - Unifica la API para más de 10 arquitecturas de memoria previamente aisladas en la literatura.

2. **ExpRAG (Baseline propuesto)**:
   - "Experience Retrieval-Augmented Generation". 
   - Codifica cada intento pasado (Input, Predicción, Feedback) como un texto estructurado en un vector store, recuperándolo cuando la tarea actual tiene similitud semántica.

3. **ReMem (Framework propuesto)**:
   - Combina el clásico bucle *ReAct* (razonamiento + acción) con una nueva dimensión: **memory reasoning**.
   - El agente puede *evaluar, reorganizar y evolucionar* su propia memoria activamente como si fuera una herramienta de primer nivel durante su proceso de resolución. (Action-Think-Memory refine).

---

## Resultados Clave

- Los agentes con memoria auto-evolutiva superan consistentemente a los agentes sin estado (stateless) en secuencias largas.
- Se demuestra que la memoria es fundamentalmente frágil: modelos fuertes en razonamiento *in-context* fallan sistemáticamente a la hora de decidir **qué** información extraer y abstraer para el futuro.
- ReMem mejora significativamente la estabilidad en la reutilización procedimental comparado con métodos pasivos como ExpRAG.

---

## Contribuciones Principales

1. **Benchmark Evo-Memory**: Estandarización de la evaluación de test-time learning con memoria.
2. **Unificación de algoritmos**: Implementación comparable de >10 arquitecturas de memoria.
3. **ReMem**: Pipeline superador que eleva la memoria de un almacén pasivo a un bucle activo de reflexión.

---

## Limitaciones

- La evaluación asume feedback ideal/verificable al final de cada episodio de tarea, lo cual en el mundo real suele ser ruidoso o retrasado.
- El costo computacional de evaluar múltiples trayectorias con inserciones vectoriales (o de grafos) continuas es significativamente mayor que en benchmarks estáticos.

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> In real-world environments such as interactive problem assistants or embodied agents, LLMs are required to handle continuous task streams, yet often fail to learn from accumulated interactions, losing valuable contextual insights, a limitation that calls for test-time evolution, where LLMs retrieve, integrate, and update memory continuously during deployment. [#ffd400]

---

> [!quote] Resaltado (p. 3)
> Evo-Memory structures datasets into sequential task streams, requiring LLMs to search, adapt, and evolve memory after each interaction. We unify and implement over ten representative memory modules. [#ffd400]

---

> [!quote] Resaltado (p. 5)
> We propose ReMem, a simple yet effective framework that unifies reasoning, action, and memory refinement within a single decision loop. Unlike conventional retrieval-augmented or ReAct-style methods that treat memory as static context, ReMem introduces a third dimension of memory reasoning. [#ffd400]

---

## Ideas y Conexiones

- El primer autor (Tianxin Wei) es también el autor del gran Survey [[weiSurveyAgenticReasoning2026]]. Este benchmark es literalmente la plataforma experimental diseñada para medir el [[Self-Evolving Agentic Reasoning]].
- El pipeline ReMem materializa el concepto del survey donde la memoria deja de ser un "buffer" y se convierte en un participante activo de la cadena de pensamiento (Action $\leftrightarrow$ Thought $\leftrightarrow$ Memory).
- Conecta con [[MemEvolve]], que utiliza EvolveLab; Evo-Memory podría usarse como la función objetivo de validación de entornos de entrenamiento de meta-memoria.

---

## Notas Relacionadas

- [[Self-Evolving Agentic Reasoning]] — Dimensión que evalúa
- [[Agentic Memory]] — Componente central evaluado
- [[ReAct]] — Base sobre la que se construye ReMem
- [[In-Context Reasoning]] — El nivel en el que opera la evolución evaluada
- [[weiSurveyAgenticReasoning2026]] — Survey teórico del mismo grupo
