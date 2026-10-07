---
titulo: "Agentic Memory"
tags:
  - concepto
  - agentic-reasoning
  - memoria
aliases: ["Memoria Agéntica"]
fecha_creacion: "2026-09-29"
---

# Agentic Memory

## Definición

> Sistema de memoria que funciona como **componente integral y activo del bucle de razonamiento agéntico**, utilizado para reflexionar sobre experiencias pasadas, guiar acciones futuras y adaptarse dinámicamente a tareas complejas de largo horizonte.

## Explicación

A diferencia de la memoria tradicional en LLMs (que simplemente extiende la ventana de contexto o almacena inputs históricos), la memoria agéntica es un componente dinámico e interactivo que participa directamente en el razonamiento. Un agente mantiene un módulo de memoria donde cada entrada puede ser una observación cruda, una trayectoria resumida, un sub-objetivo, o una traza de invocación de herramientas. La evolución de la memoria agéntica sigue una progresión: desde flat memory (factual y experiencial) hacia structured memory (grafos semánticos, workflows, árboles jerárquicos), hasta post-training memory control donde el propio agente aprende qué almacenar, cuándo recuperar y cómo interactuar con la memoria mediante políticas optimizadas por RL.

---

## Contexto

La memoria agéntica es uno de los dos pilares de la auto-evolución (junto con el feedback). En sistemas multi-agente, se extiende a memorias compartidas y distribuidas, con topologías de almacenamiento gobernadas y estrategias activas de gestión (compresión, verificación, actualización continua).

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Search]]
- **Relacionado con**: [[Self-Evolving Agentic Reasoning]], [[Retrieval Augmented Generation (RAG)]]
- **Tipos**: Factual Memory, Experience Memory, Structured Memory

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 4.2: Agentic Memory
