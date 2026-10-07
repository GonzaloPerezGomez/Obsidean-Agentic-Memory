---
titulo: "In-Context Reasoning"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Razonamiento In-Context", "In-Context Learning"]
fecha_creacion: "2026-09-29"
---

# In-Context Reasoning

## Definición

> Enfoque de razonamiento agéntico que **escala el cómputo en tiempo de inferencia** mediante orquestación estructurada, planificación basada en búsqueda y diseño adaptativo de workflows, sin modificar los parámetros del modelo.

## Explicación

El in-context reasoning aprovecha la capacidad de aprendizaje in-context de los LLMs modernos para empoderarlos con nuevas capacidades sin entrenamiento adicional. Mediante instrucciones cuidadosamente diseñadas, ejemplos few-shot e información contextual proporcionada directamente en el prompt, un modelo congelado puede ejecutar tareas complejas como uso de herramientas, planificación multi-paso y razonamiento interleaved (como en ReAct). Este paradigma es altamente flexible y desplegable inmediatamente, pero su rendimiento está limitado por las capacidades inherentes del LLM congelado y la longitud de su ventana de contexto.

---

## Contexto

Se contrapone al [[Post-Training Reasoning]]. Cada una de las tres capas del agentic reasoning tiene variantes in-context y post-training. En el uso de herramientas, por ejemplo, el in-context tool integration incluye métodos como ReAct, ART y ChatCoT.

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]]
- **Relacionado con**: [[ReAct]], [[Tool Use]]
- **Opuesto a**: [[Post-Training Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Distinción transversal en todas las secciones
