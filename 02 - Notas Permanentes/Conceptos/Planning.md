---
titulo: "Planning"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Planificación Agéntica", "Agentic Planning"]
fecha_creacion: "2026-09-29"
---

# Planning

## Definición

> Capacidad de un agente para **traducir razonamiento abstracto en acción estructurada** mediante la descomposición de objetivos, exploración de alternativas y uso de herramientas para ejecutar operaciones fundamentadas.

## Explicación

La planificación agéntica opera mediante tres enfoques complementarios. Los **enfoques workflow-based** estructuran el proceso en etapas explícitas (percepción, razonamiento, ejecución, verificación), proporcionando estructura interpretable con adaptación reactiva. Los **enfoques de búsqueda en árbol** (BFS, DFS, A*, MCTS, beam search) tratan los pensamientos parciales como nodos y buscan caminos óptimos, permitiendo backtracking y refinamiento antes de comprometerse con acciones irreversibles. La **formalización de procesos** codifica planes como artefactos de código o programas PDDL, garantizando composicionalidad y explicabilidad. Además, estrategias de **descomposición** modularizan la planificación compleja en componentes separables (reconocimiento de metas, recuperación de memoria, refinamiento de planes).

---

## Contexto

Es uno de los tres componentes fundamentales del [[Foundational Agentic Reasoning]], junto con [[Tool Use]] y [[Agentic Search]]. La planificación evoluciona de una rutina fija a una capacidad dinámica en [[Self-Evolving Agentic Reasoning]], donde los agentes generan autónomamente sus propias tareas y refinan estrategias.

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]], [[Tree of Thoughts]]
- **Relacionado con**: [[Foundational Agentic Reasoning]], [[Tool Use]]
- **Se evoluciona en**: [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 3.1: Agentic Planning
