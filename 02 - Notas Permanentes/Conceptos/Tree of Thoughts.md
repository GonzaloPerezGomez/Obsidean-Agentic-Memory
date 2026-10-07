---
titulo: "Tree of Thoughts"
tags:
  - concepto
  - agentic-reasoning
aliases: ["ToT", "Árbol de Pensamientos"]
fecha_creacion: "2026-09-29"
---

# Tree of Thoughts

## Definición

> Framework que generaliza [[Chain of Thought]] tratando los **pensamientos parciales como nodos de un árbol** que se explora mediante estrategias de búsqueda (BFS, DFS, MCTS) para encontrar caminos de razonamiento óptimos.

## Explicación

Mientras que CoT genera una única cadena lineal de razonamiento, Tree of Thoughts (ToT) permite al modelo explorar múltiples caminos de forma simultánea, evaluarlos y hacer backtracking cuando un camino no es prometedor. Cada nodo del árbol representa un estado de razonamiento parcial, y las estrategias de búsqueda (BFS para exploración amplia, DFS para profundización, MCTS para exploración guiada por simulación) determinan qué ramas expandir. Esto es especialmente valioso para problemas con múltiples soluciones posibles o donde las decisiones tempranas tienen impacto irreversible. Extensiones como Graph of Thoughts (GoT) generalizan la estructura a grafos, y Hypertree Planning (HTP) incorpora recuperación como herramienta de guía.

---

## Contexto

ToT es una de las estrategias de búsqueda en árbol más influyentes en el agentic planning. Combina la interpretabilidad de CoT con la robustez de la búsqueda combinatoria, permitiendo agentes que pueden "pensar antes de actuar" de forma más exhaustiva.

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]]
- **Relacionado con**: [[Planning]], [[Foundational Agentic Reasoning]]
- **Se extiende con**: Graph of Thoughts, Algorithm of Thoughts

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Mencionado en planificación y búsqueda (Sección 3.1)
