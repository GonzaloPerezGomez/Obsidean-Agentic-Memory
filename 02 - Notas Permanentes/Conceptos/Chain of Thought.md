---
titulo: "Chain of Thought"
tags:
  - concepto
  - agentic-reasoning
aliases: ["CoT", "Cadena de Pensamiento"]
fecha_creacion: "2026-09-29"
---

# Chain of Thought

## Definición

> Técnica de prompting que induce al LLM a **generar pasos de razonamiento intermedios explícitos** antes de producir una respuesta final, mejorando la precisión en tareas de razonamiento complejo.

## Explicación

Chain of Thought (CoT) es un método fundamental que transforma la generación del modelo de un salto directo pregunta→respuesta a una secuencia de pasos lógicos encadenados. En el contexto del agentic reasoning, CoT sirve como la base sobre la que se construyen frameworks más sofisticados: ReAct extiende CoT añadiendo la capacidad de tomar acciones entre pasos de razonamiento; Tree of Thoughts generaliza CoT a un espacio de búsqueda ramificado; y ChatCoT combina CoT con invocaciones de herramientas. CoT puede considerarse el "sistema nervioso" del agentic reasoning — el mecanismo básico de articulación del pensamiento que posibilita planificación, reflexión y uso de herramientas.

---

## Contexto

Origina en la línea de investigación sobre razonamiento en LLMs (Wei et al., 2022). En el marco del agentic reasoning, CoT es la primitiva de razonamiento que habilita todas las capacidades superiores. Su limitación principal es que opera en un solo paso lineal sin interacción con el entorno.

---

## Relación con otros conceptos

- **Requiere**: Capacidad de generación de LLMs
- **Relacionado con**: [[ReAct]], [[In-Context Reasoning]]
- **Se extiende con**: [[Tree of Thoughts]], [[ReAct]], [[Reflexion]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Base del interleaving reasoning-action
