---
titulo: "GRPO"
tags:
  - concepto
  - agentic-reasoning
  - RL
aliases: ["Group Relative Policy Optimization"]
fecha_creacion: "2026-09-29"
---

# GRPO

## Definición

> Método de optimización de políticas para RL en tareas de razonamiento que **elimina la necesidad de una red de valor** construyendo ventajas (advantages) a partir de recompensas relativas dentro de un grupo de muestras.

## Explicación

GRPO (Group Relative Policy Optimization) es una alternativa eficiente a métodos como PPO para entrenar modelos de razonamiento. En lugar de mantener una red de valor separada (que es costosa y difícil de entrenar para LLMs), GRPO genera un grupo de respuestas para cada prompt, las puntúa con una función de recompensa, y calcula la ventaja de cada respuesta de forma relativa al grupo (por ejemplo, normalizando respecto a la media y desviación del grupo). Esto simplifica enormemente el pipeline de entrenamiento y ha demostrado ser ampliamente efectivo para optimizar políticas de razonamiento, uso de herramientas y búsqueda en el contexto agéntico.

---

## Contexto

GRPO se ha convertido en el método dominante para post-training reasoning en el ecosistema agéntico. Se utiliza tanto en entrenamiento single-agent como en multi-agent RL, y ha sido adoptado en frameworks como DeepSeek-R1.

---

## Relación con otros conceptos

- **Requiere**: RL, funciones de recompensa
- **Relacionado con**: [[Post-Training Reasoning]], PPO
- **Se usa en**: [[Self-Evolving Agentic Reasoning]], [[Collective Multi-Agent Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 2.2, mencionado como método ampliamente usado para reasoning tasks
