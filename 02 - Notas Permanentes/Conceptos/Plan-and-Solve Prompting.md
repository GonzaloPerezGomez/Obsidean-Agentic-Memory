---
titulo: "Plan-and-Solve Prompting"
tags:
  - concepto
  - agentic-reasoning
  - prompting
aliases: ["PS Prompting", "PS+ Prompting", "Plan and Solve"]
fecha_creacion: "2026-09-30"
---

# Plan-and-Solve Prompting

## Definición

> Estrategia de prompting zero-shot que mejora el razonamiento de los LLMs introduciendo una fase explícita de **planificación** (dividir la tarea en subtareas) antes de la fase de **ejecución** (resolver las subtareas según el plan), eliminando la necesidad de ejemplos few-shot manuales.

## Explicación

Plan-and-Solve Prompting aborda una debilidad fundamental del Zero-shot-CoT ("Let's think step by step"): la tendencia a omitir pasos intermedios cruciales en cadenas de razonamiento largas. En lugar de pedir al modelo que simplemente "piense paso a paso", PS Prompting le instruye a primero *diseñar un plan* que divida el problema en subproblemas manejables, y luego *ejecutar ese plan* de forma ordenada. Su extensión PS+ refina esto añadiendo instrucciones específicas como "extrae las variables relevantes" y "calcula resultados intermedios", lo que guía al modelo hacia un razonamiento más completo y preciso. Este enfoque puede verse como un precursor de la planificación agéntica completa: introduce la descomposición de tareas como principio organizativo del razonamiento, aunque sin la interacción con el entorno que caracteriza a los agentes.

---

## Contexto

Se enmarca en la línea de estrategias de prompting para mejorar el razonamiento sin entrenamiento adicional ([[In-Context Reasoning]]). Junto con [[Least-to-Most Prompting]] y [[Chain of Thought]], forma parte de los métodos fundacionales que anticipan la planificación agéntica más sofisticada del [[Foundational Agentic Reasoning]].

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]]
- **Relacionado con**: [[Planning]], [[Least-to-Most Prompting]], [[In-Context Reasoning]]
- **Se extiende con**: [[ReAct]] (añadiendo interacción con el entorno)

---

## Referencias

- [[wangPlanandSolvePromptingImproving2023]] — Paper que introduce PS y PS+ Prompting
