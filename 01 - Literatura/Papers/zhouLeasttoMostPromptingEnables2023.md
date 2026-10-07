---
titulo: "Least-to-Most Prompting Enables Complex Reasoning in Large Language Models"
autores: "Denny Zhou, Nathanael Schärli, Le Hou, Jason Wei, Nathan Scales, Xuezhi Wang, Dale Schuurmans, Claire Cui, Olivier Bousquet, Quoc Le, Ed Chi"
año: "2023"
fuente: ""
DOI: "10.48550/arXiv.2205.10625"
citekey: "zhouLeasttoMostPromptingEnables2023"
zotero: "zotero://select/library/items/NDMEIF7M"
tags:
  - paper
  - agentic-reasoning
  - prompting
estado: "#estado/en-progreso"
fecha_lectura: "2026-09-30"
valoracion: ⭐⭐⭐⭐
---

# Least-to-Most Prompting Enables Complex Reasoning in Large Language Models

## Metadatos

- **Autores**: Denny Zhou, Nathanael Schärli, Le Hou, Jason Wei, Nathan Scales, Xuezhi Wang, Dale Schuurmans, Claire Cui, Olivier Bousquet, Quoc Le, Ed Chi
- **Año**: 2023
- **Publicación**: ICLR 2023
- **DOI**: [10.48550/arXiv.2205.10625](https://doi.org/10.48550/arXiv.2205.10625)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/NDMEIF7M)
- **Abstract**: Chain-of-thought prompting has demonstrated remarkable performance on various natural language reasoning tasks. However, it tends to perform poorly on tasks which requires solving problems harder than the exemplars shown in the prompts. To overcome this challenge of easy-to-hard generalization, we propose a novel prompting strategy, least-to-most prompting. The key idea in this strategy is to break down a complex problem into a series of simpler subproblems and then solve them in sequence. Solving each subproblem is facilitated by the answers to previously solved subproblems. Our experimental results on tasks related to symbolic manipulation, compositional generalization, and math reasoning reveal that least-to-most prompting is capable of generalizing to more difficult problems than those seen in the prompts.

---

## Resumen

Este paper propone **Least-to-Most Prompting**, una estrategia que permite a los LLMs resolver problemas más difíciles que los mostrados en los ejemplos del prompt. El método opera en dos etapas: primero descompone el problema complejo en subproblemas más simples (top-down), y luego los resuelve secuencialmente de más fácil a más difícil (bottom-up), donde cada solución alimenta la siguiente. Logra resultados notables, como 99% en SCAN con solo 14 ejemplos.

---

## Problema / Motivación

Chain-of-Thought prompting funciona bien cuando los problemas de test son de dificultad similar a los ejemplos del prompt, pero **falla en generalizar de fácil a difícil** — es decir, resolver problemas más complejos que los ejemplares demostrados. Esta limitación es crítica porque idealmente queremos que un modelo pueda aprender de ejemplos simples y transferir ese aprendizaje a problemas arbitrariamente complejos.

---

## Metodología

Least-to-Most Prompting consta de **dos etapas secuenciales**:

1. **Descomposición (top-down)**: El prompt contiene ejemplos de cómo descomponer problemas complejos en subproblemas. El modelo genera la cadena de subproblemas ordenados de más simple a más complejo.

2. **Resolución de subproblemas (bottom-up)**: El prompt incluye:
   - Ejemplos de cómo resolver subproblemas
   - Las respuestas a subproblemas previamente resueltos (contexto acumulativo)
   - El siguiente subproblema a resolver

Cada subproblema se facilita por las soluciones anteriores, creando una cadena incremental de resolución.

---

## Resultados Clave

- En **SCAN** (compositional generalization): 99% de accuracy con solo 14 ejemplos vs. 16% con CoT — superando modelos neuro-simbólicos entrenados con >15,000 ejemplos
- Generalización exitosa a problemas más difíciles que los del prompt en manipulación simbólica, generalización composicional y razonamiento matemático
- El contexto acumulativo (respuestas de subproblemas previos) es clave para el rendimiento

---

## Contribuciones Principales

1. Identificación del problema de **generalización fácil-a-difícil** como limitación fundamental de CoT
2. Propuesta de **Least-to-Most Prompting**: descomposición top-down + resolución bottom-up secuencial
3. Resultados que demuestran generalización composicional sin precedentes en prompting (99% en SCAN)

---

## Limitaciones

- Los prompts de descomposición **no generalizan bien entre dominios** — un prompt diseñado para matemáticas no sirve para sentido común
- Requiere ejemplos few-shot específicos del dominio para ambas etapas
- La comunicación unidireccional (prompting) no permite feedback inmediato; los autores sugieren evolucionar hacia conversaciones bidireccionales

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 2)
> Least-to-most prompting teaches language models how to solve a complex problem by decomposing it to a series of simpler subproblems. It consists of two sequential stages: 1. Decomposition. 2. Subproblem solving. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> Decomposition prompts typically don't generalize well across different domains. For instance, a prompt that demonstrates decomposing math word problems isn't effective for teaching large language models to break down common sense reasoning problems [#ffd400]

---

> [!quote] Resaltado (p. 9)
> We introduced least-to-most prompting to enable language models to solve problems that are harder than those in the prompt. This approach entails a two-fold process: a top-down decomposition of the problem and a bottom-up resolution generation [#ffd400]

---

> [!quote] Resaltado (p. 9)
> Prompting can be viewed as a unidirectional communication form in which we instruct a language model without considering its feedback. A natural progression would be to evolve prompting into fully bidirectional conversations, enabling immediate feedback to language models, thereby facilitating more efficient and effective learning. [#ffd400]

---

## Ideas y Conexiones

- La observación final sobre **prompting unidireccional → conversación bidireccional** es exactamente la transición hacia [[Agentic Reasoning]]: pasar de instruir al modelo a interactuar con él en un bucle de feedback
- La descomposición top-down + resolución bottom-up es una forma primitiva de [[Planning]] — comparte principio con [[Plan-and-Solve Prompting]] pero es más sofisticada en la acumulación de contexto
- El enfoque de contexto acumulativo (respuestas previas alimentan las siguientes) es un precursor de la [[Agentic Memory]] experiencial — cada sub-resolución se "recuerda" para las siguientes
- Limitación de no generalizar entre dominios sugiere la necesidad de meta-descomposición adaptativa, que es lo que logra [[Self-Evolving Agentic Reasoning]]

---

## Notas Relacionadas

- [[Chain of Thought]] — Base que Least-to-Most extiende
- [[Plan-and-Solve Prompting]] — Estrategia de planificación relacionada
- [[Planning]] — Concepto más general de planificación agéntica
- [[Agentic Reasoning]] — Marco donde evoluciona el prompting hacia interacción
- [[weiSurveyAgenticReasoning2026]] — Survey que cita este trabajo
- [[Least-to-Most Prompting]] — Nota de concepto
