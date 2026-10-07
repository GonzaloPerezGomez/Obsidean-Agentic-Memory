---
titulo: "Dec-POMDP"
tags:
  - concepto
  - agentic-reasoning
  - multi-agent
  - formalismo
aliases: ["Decentralized POMDP", "POMDP Descentralizado"]
fecha_creacion: "2026-09-29"
---

# Dec-POMDP

## Definición

> Extensión multi-agente del [[POMDP]] que formaliza entornos donde **N agentes toman decisiones de forma descentralizada bajo observabilidad parcial**, con la observación de cada agente ampliada para incluir un canal de comunicación con los demás agentes.

## Explicación

El Dec-POMDP (Decentralized Partially Observable Markov Decision Process) es el marco formal para los sistemas multi-agente agénticos. Cada agente i tiene su propia política πi, y su observación incluye explícitamente los mensajes comunicativos generados por los demás agentes. La distinción crucial es que en el agentic MARL, la comunicación no es mera transmisión de señales sino una extensión del proceso de razonamiento: la acción externa de un agente puede actuar como prompt que activa una cadena de razonamiento interno en otro agente. El desafío central pasa de la planificación single-agent al diseño de mecanismos: optimizar la topología de comunicación y las estructuras de incentivos para alinear los procesos de razonamiento descentralizados hacia un objetivo global coherente.

---

## Contexto

Marcos como CTDE (Centralized Training/Decentralized Execution) se usan para estabilizar la emergencia de comportamientos cooperativos en Dec-POMDPs. Frameworks como AutoGen y CAMEL implementan instancias de Dec-POMDPs con role-playing estático.

---

## Relación con otros conceptos

- **Requiere**: [[POMDP]], [[Multi-Agent Systems]]
- **Relacionado con**: [[Collective Multi-Agent Reasoning]], CTDE, [[Theory of Mind]]
- **Opuesto a**: Planificación centralizada

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 2: Formalización multi-agente
