---
titulo: "Theory of Mind"
tags:
  - concepto
  - agentic-reasoning
  - multi-agent
aliases: ["ToM", "Teoría de la Mente"]
fecha_creacion: "2026-09-29"
---

# Theory of Mind

## Definición

> Capacidad de un agente para **inferir y razonar sobre las creencias, intenciones y estados mentales de otros agentes**, permitiendo colaboración más sofisticada en sistemas multi-agente.

## Explicación

La Theory of Mind (ToM) en el contexto del agentic reasoning extiende el concepto de la psicología cognitiva al dominio de los agentes LLM. Un agente con ToM no solo razona sobre la tarea, sino que modela internamente lo que otros agentes "saben", "creen" o "intentan hacer". Esto permite colaboración más eficiente: el agente puede anticipar las acciones de sus pares, ajustar su comunicación al nivel de conocimiento del receptor, y resolver conflictos entendiendo las perspectivas divergentes. En sistemas multi-agente LLM, la ToM se implementa típicamente como una capa de razonamiento adicional que toma como entrada la historia de comunicaciones y las acciones observadas de otros agentes para construir un modelo de sus estados internos.

---

## Contexto

Se enmarca dentro de la colaboración in-context en [[Collective Multi-Agent Reasoning]]. Es particularmente importante en escenarios con información asimétrica, donde diferentes agentes tienen acceso a datos distintos y deben inferir qué saben los demás.

---

## Relación con otros conceptos

- **Requiere**: [[Multi-Agent Systems]], [[Dec-POMDP]]
- **Relacionado con**: [[Collective Multi-Agent Reasoning]], colaboración
- **Origen**: Psicología cognitiva (Premack & Woodruff, 1978)

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 5.2.1: Theory-of-Mind-Augmented Collaboration
