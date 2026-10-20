---
titulo: "ClinicalAgents"
tags:
  - concepto
  - agentic-reasoning
  - multi-agent
  - memoria
  - clinical
aliases: ["ClinicalAgents Framework"]
fecha_creacion: "2026-10-20"
---

# ClinicalAgents

## Definición

> Framework multi-agente para la toma de decisiones clínicas que combina una **orquestación dinámica modelada como Monte Carlo Tree Search (MCTS)** con una **arquitectura de Memoria Dual (Dual-Memory)** para simular el razonamiento no lineal, la verificación iterativa de hipótesis y el *backtracking* propios de los médicos especialistas.

## Explicación

El diagnóstico médico rara vez sigue una secuencia lineal fija de síntomas a enfermedad; requiere formular sospechas preliminares, solicitar pruebas complementarias, interpretar hallazgos multimodales y, con frecuencia, retroceder cuando los resultados descartan la hipótesis inicial. Los sistemas LLM tradicionales fallan en este ámbito porque ejecutan pipelines rígidos de una sola pasada.

ClinicalAgents resuelve este problema asignando roles médicos especializados a un pool de agentes (triaje, analítica, radiología, diagnóstico y terapia) coordinados por un *Clinical Orchestrator*. Este orquestador utiliza MCTS para explorar el espacio de decisiones como un árbol de hipótesis diagnósticas, permitiendo volver sobre sus pasos (*backtracking*) si la evidencia refuta una línea de investigación. Todo el proceso está sustentado por una arquitectura Dual-Memory: una **Working Memory ($M_{work}$)** mutable que mantiene sincronizado el estado actual del paciente entre todos los especialistas, y una **Experience Memory ($M_{exp}$)** estática que provee guías clínicas y casos pasados indexados.

---

## Contexto

Presentado por Ge et al. (2026), ClinicalAgents representa un avance clave en la aplicación de [[Collective Multi-Agent Reasoning]] y búsqueda en árbol en entornos de alta exigencia como la medicina. Demuestra que la combinación de especialización de roles, búsqueda en árbol y sincronización de memoria compartida supera ampliamente a los modelos monolíticos en tareas clínicas complejas de extremo a extremo (como las evaluadas en el benchmark MedChain).

---

## Relación con otros conceptos

- **Requiere**: [[Tree of Thoughts]], [[Planning]], [[Multi-Agent Systems]]
- **Relacionado con**: [[Collective Multi-Agent Reasoning]], [[Agentic Memory]], [[MSM-Mem]]
- **Implementa**: Búsqueda MCTS con backtracking y memoria dual (working / experience memory)

---

## Referencias

- [[geClinicalAgentsMultiAgentOrchestration2026]] — Paper que introduce ClinicalAgents
- [[weiSurveyAgenticReasoning2026]] — Taxonomía de sistemas multi-agente y planificación
