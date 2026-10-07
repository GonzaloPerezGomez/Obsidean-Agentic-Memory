---
titulo: "Collective Multi-Agent Reasoning"
tags:
  - concepto
  - agentic-reasoning
  - multi-agent
aliases: ["Razonamiento Colectivo Multi-Agente"]
fecha_creacion: "2026-09-29"
---

# Collective Multi-Agent Reasoning

## Definición

> Tercera capa del agentic reasoning que **escala la inteligencia de agentes individuales a ecosistemas colaborativos**, donde múltiples agentes se coordinan mediante roles especializados, protocolos de comunicación y sistemas de memoria compartida para alcanzar objetivos comunes.

## Explicación

En lugar de tratar a los agentes como solucionadores homogéneos, los sistemas multi-agente asignan roles complementarios: un Leader/Coordinador que descompone tareas y mantiene la coherencia global, Workers/Executors que ejecutan acciones concretas, Critics/Evaluators que verifican calidad y factualidad, un Memory Keeper que gestiona el conocimiento persistente, y un Communication Facilitator que optimiza el flujo de información. El sistema se formaliza como un Dec-POMDP (POMDP parcialmente observable descentralizado), donde la comunicación entre agentes no es mera transmisión de señales sino una extensión del propio proceso de razonamiento. La evolución multi-agente incluye co-optimización de memorias compartidas, topologías de comunicación y políticas de colaboración.

---

## Contexto

Frameworks como AutoGen y CAMEL representan el role-playing estático con políticas fijas, mientras que enfoques más recientes como GPTSwarm utilizan RL multi-agente para optimizar la distribución de razonamiento conjunta.

---

## Relación con otros conceptos

- **Requiere**: [[Self-Evolving Agentic Reasoning]], [[Multi-Agent Systems]], [[Dec-POMDP]]
- **Relacionado con**: [[Theory of Mind]], [[Agentic Memory]]
- **Incluye roles**: Leader, Worker, Critic, Memory Keeper, Communication Facilitator

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 5: Collective Multi-Agent Reasoning
