---
titulo: "Agentic Search"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Búsqueda Agéntica", "Agentic RAG"]
fecha_creacion: "2026-09-29"
---

# Agentic Search

## Definición

> Sistemas de búsqueda y recuperación de información en los que un agente **controla dinámicamente cuándo, qué y cómo recuperar información** basándose en sus necesidades de razonamiento en tiempo real, superando las limitaciones de los pipelines RAG tradicionales de recuperación fija y one-shot.

## Explicación

A diferencia de los pipelines RAG convencionales que realizan una recuperación fija antes de la generación, los agentes de búsqueda agéntica integran la recuperación como parte activa del bucle de razonamiento. El agente decide autónomamente cuándo necesita información adicional, formula consultas adaptativas, y sintetiza evidencia de múltiples fuentes de forma iterativa. Existen tres estilos arquitectónicos: in-context agentic RAG (búsqueda intercalada con razonamiento vía prompting), post-training agentic RAG (modelos entrenados con SFT/RL para decidir cuándo y cómo recuperar), y structure-enhanced RAG (razonamiento sobre fuentes simbólicas como knowledge graphs). Los agentes más avanzados exhiben capacidades emergentes como descomposición iterativa, re-verificación de evidencia y planificación de recuperación.

---

## Contexto

Forma uno de los tres pilares del [[Foundational Agentic Reasoning]], junto con [[Planning]] y [[Tool Use]]. La búsqueda y la memoria evolucionan en un bucle co-evolutivo en la capa de self-evolving reasoning.

---

## Relación con otros conceptos

- **Requiere**: [[Retrieval Augmented Generation (RAG)]]
- **Relacionado con**: [[Tool Use]], [[Agentic Memory]]
- **Se usa en**: [[Foundational Agentic Reasoning]], [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 3.3: Agentic Search
