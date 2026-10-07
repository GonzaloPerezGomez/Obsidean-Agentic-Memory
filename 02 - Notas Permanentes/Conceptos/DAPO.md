---
titulo: "DAPO"
tags:
  - concepto
  - agentic-reasoning
  - RL
  - reasoning
aliases: ["Decoupled Clip and Dynamic Sampling Policy Optimization", "Algoritmo DAPO"]
fecha_creacion: "2026-10-05"
---

# DAPO

## Definición

> Algoritmo y sistema de optimización de políticas para aprendizaje por refuerzo en LLMs (**Decoupled Clip and Dynamic Sampling Policy Optimization**) diseñado para estabilizar y escalar el entrenamiento de razonamiento complejo mediante el desacoplamiento del clipping de política y el muestreo dinámico de trayectorias.

## Explicación

El entrenamiento de modelos de razonamiento (como los observados en OpenAI o1 o DeepSeek-R1) depende de la optimización por refuerzo sobre cadenas de pensamiento extensas. Sin embargo, algoritmos tradicionales como PPO sufren inestabilidad numérica, gradientes desproporcionados y colapso de políticas al enfrentarse a secuencias largas y recompensas dispersas. DAPO resuelve esto mediante dos innovaciones estructurales: en primer lugar, aplica un mecanismo de **Decoupled Clipping** que restringe la actualización de la política evitando oscilaciones catastróficas; en segundo lugar, implementa un **muestreo dinámico** que prioriza consultas y trayectorias con alta varianza de recompensa (problemas donde el modelo todavía puede aprender), reduciendo el cómputo desperdiciado en casos triviales o imposibles. Este algoritmo actúa como motor para internalizar capacidades de razonamiento profundo y políticas de memoria activa en modelos agénticos.

---

## Contexto

DAPO se sitúa dentro de la dimensión de [[Post-Training Reasoning]], junto a metodologías como [[GRPO]]. Es un componente clave tanto para reasoning models puros como para agentes especializados; por ejemplo, en [[yuMemAgentReshapingLongContext2026]] (MemAgent), una extensión de DAPO se emplea para entrenar agentes que deciden cuándo retener o sobrescribir memoria durante la lectura de documentos infinitos.

---

## Relación con otros conceptos

- **Requiere**: Reinforcement Learning (RL), funciones de recompensa verificables
- **Relacionado con**: [[GRPO]], [[Post-Training Reasoning]], [[Chain of Thought]]
- **Se aplica en**: [[MemAgent]] (entrenamiento de agentes de memoria), reasoning models a gran escala
- **Alternativa a**: PPO estándar, DPO

---

## Referencias

- [[yuDAPOOpenSourceLLM2025]] — Paper que introduce el algoritmo y sistema abierto DAPO
- [[yuMemAgentReshapingLongContext2026]] — Extensión de DAPO para agentes de memoria
- [[weiSurveyAgenticReasoning2026]] — Survey que aborda el entrenamiento post-training en agentes
