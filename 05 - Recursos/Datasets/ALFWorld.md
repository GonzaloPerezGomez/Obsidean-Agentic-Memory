---
titulo: "ALFWorld"
tags:
  - dataset
  - recurso
  - embodied
  - interactive
  - decision-making
fuente: "https://alfworld.github.io/"
fecha_creacion: "2026-10-22"
---

# ALFWorld

## Descripción

> Entorno de simulación de toma de decisiones interactivas en texto basado en el simulador ALFRED, donde un agente debe navegar por habitaciones de un hogar virtual e interactuar con objetos cotidianos mediante comandos de texto para cumplir objetivos complejos (ej. *"limpiar una manzana y ponerla en la nevera"*).

Exige planificar secuencias de acciones, explorar el entorno bajo observabilidad parcial, interpretar observaciones y recuperarse de errores o bloqueos.

## Características Principales

- **Modalidad:** Texto interactivo (bucle `Acción` $\rightarrow$ `Observación`).
- **Tareas:** 6 tipos de objetivos (recogida y colocación, calentar y enfriar objetos, limpieza, uso de recipientes, examen bajo luz).
- **Métrica:** Tasa de éxito (*success rate*) en completar la tarea en un número finito de pasos.

## Papers que lo utilizan en la bóveda

- [[yaoReActSynergizingReasoning2023]] — Utilizado en ReAct, logrando un 34% más de éxito que métodos basados en aprendizaje por refuerzo e imitación gracias al razonamiento intercalado.
