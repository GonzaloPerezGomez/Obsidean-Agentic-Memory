---
titulo: "ReAct"
tags:
  - concepto
  - agentic-reasoning
  - framework
aliases: ["Reasoning and Acting", "ReAct Framework"]
fecha_creacion: "2026-09-29"
---

# ReAct

## Definición

> Framework que **intercala deliberación (razonamiento) con interacción con el entorno (acción)**, permitiendo al agente alternar entre pensar sobre el problema y ejecutar acciones concretas como consultas a APIs o búsquedas web.

## Explicación

ReAct implementa el ciclo fundamental del agentic reasoning: el agente genera un "pensamiento" (thought) que razona sobre la situación actual, luego ejecuta una "acción" (action) basada en ese razonamiento, observa el resultado, y genera un nuevo pensamiento incorporando esa observación. Técnicamente, ReAct realiza decodificación greedy sobre pensamientos z y acciones a alternados. Este patrón simple pero poderoso permite al modelo fundamentar su razonamiento en datos reales del entorno en lugar de depender únicamente de su conocimiento paramétrico, reduciendo así las alucinaciones y mejorando la fiabilidad en tareas que requieren información actualizada o cálculos precisos.

---

## Contexto

Es uno de los frameworks fundacionales del agentic reasoning. Numerosas extensiones se han construido sobre su patrón think-act, incluyendo [[Reflexion]] (que añade auto-crítica) y enfoques de búsqueda en árbol como [[Tree of Thoughts]] (que exploran múltiples caminos de razonamiento).

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]], [[Tool Use]]
- **Relacionado con**: [[Foundational Agentic Reasoning]], [[Agentic Search]]
- **Se extiende con**: [[Reflexion]], [[Tree of Thoughts]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Mencionado como framework fundacional en múltiples secciones
