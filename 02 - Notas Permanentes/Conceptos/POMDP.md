---
titulo: "POMDP"
tags:
  - concepto
  - agentic-reasoning
  - formalismo
aliases: ["Partially Observable Markov Decision Process", "Proceso de Decisión de Markov Parcialmente Observable"]
fecha_creacion: "2026-09-29"
---

# POMDP

## Definición

> Formalismo matemático que modela entornos donde un agente debe **tomar decisiones secuenciales bajo observabilidad parcial**, sin acceso completo al estado del mundo, lo que requiere mantener creencias y razonar bajo incertidumbre.

## Explicación

El POMDP es el marco formal utilizado por Wei et al. (2026) para modelar el entorno agéntico. A diferencia de un MDP estándar donde el agente observa todo el estado, en un POMDP el agente solo recibe observaciones parciales y debe inferir el estado subyacente. En el contexto del agentic reasoning, se introduce una variable de razonamiento interno que expone la estructura "think-act" de las políticas agénticas: el agente primero genera un pensamiento (razonamiento interno) y luego una acción (interacción con el entorno), basándose en su historial de observaciones parciales. Esta formalización permite aplicar toda la teoría clásica de RL al diseño de agentes.

---

## Contexto

El POMDP es la base formal del agentic reasoning single-agent. Su extensión multi-agente, el [[Dec-POMDP]], formaliza los sistemas multi-agente donde cada agente tiene observabilidad parcial y se comunica a través de canales explícitos.

---

## Relación con otros conceptos

- **Requiere**: Teoría de decisión, Procesos de Markov
- **Relacionado con**: [[Agentic Reasoning]], Reinforcement Learning
- **Se extiende con**: [[Dec-POMDP]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 2: Formalización del entorno agéntico
