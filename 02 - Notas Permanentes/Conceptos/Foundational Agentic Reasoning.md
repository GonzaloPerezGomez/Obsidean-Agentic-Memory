---
titulo: "Foundational Agentic Reasoning"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Razonamiento Agéntico Fundacional"]
fecha_creacion: "2026-09-29"
---

# Foundational Agentic Reasoning

## Definición

> Primera capa del agentic reasoning que establece las **capacidades base de un agente individual**: planificación, uso de herramientas y búsqueda, permitiendo operar en entornos estables pero complejos.

## Explicación

El foundational agentic reasoning es la base sobre la que se construyen capacidades más avanzadas. Un agente en esta capa descompone objetivos complejos en sub-tareas manejables, invoca herramientas externas (APIs, buscadores, intérpretes de código) para ejecutar acciones concretas, y verifica resultados mediante acciones ejecutables. Los enfoques incluyen planificación basada en workflows (etapas secuenciales como percepción → razonamiento → ejecución → verificación), búsqueda en árbol (BFS, DFS, MCTS, beam search) como andamiaje de planificación, y formalización de planes como artefactos de código o programas PDDL para garantizar composicionalidad e interpretabilidad.

---

## Contexto

Representa la primera de las tres capas definidas por Wei et al. (2026). Los agentes en esta capa operan en entornos estables — el agente no evoluciona ni se coordina con otros, sino que aplica sus capacidades base de forma eficiente.

---

## Relación con otros conceptos

- **Requiere**: [[Planning]], [[Tool Use]], [[Agentic Search]]
- **Relacionado con**: [[ReAct]], [[Chain of Thought]], [[Tree of Thoughts]]
- **Se extiende con**: [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 3: Foundational Agentic Reasoning
