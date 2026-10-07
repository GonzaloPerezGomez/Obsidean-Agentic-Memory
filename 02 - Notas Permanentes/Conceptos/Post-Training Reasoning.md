---
titulo: "Post-Training Reasoning"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Razonamiento Post-Training"]
fecha_creacion: "2026-09-29"
---

# Post-Training Reasoning

## Definición

> Enfoque de razonamiento agéntico que **internaliza capacidades de razonamiento en los pesos del modelo** mediante reinforcement learning (RL) y supervised fine-tuning (SFT), consolidando patrones exitosos para uso futuro.

## Explicación

Mientras que el in-context reasoning opera sobre un modelo congelado, el post-training reasoning modifica permanentemente los parámetros del modelo para que incorpore habilidades de razonamiento, uso de herramientas y búsqueda. El proceso típico sigue una progresión: primero SFT (bootstrapping) para imitar demostraciones curadas de razonamiento con herramientas, y luego RL (mastery) para superar la imitación mediante optimización basada en recompensas. El SFT proporciona competencia inicial pero sufre de sobreajuste a los patrones del dataset; el RL — particularmente [[GRPO]] — permite que el modelo descubra estrategias adaptativas y generalizables que transfieren a dominios nuevos.

---

## Contexto

Este enfoque es esencial cuando se necesitan capacidades robustas y generalizables que funcionen de manera consistente sin depender de prompts elaborados. Se aplica tanto al uso de herramientas como a la búsqueda agéntica y la memoria controlada.

---

## Relación con otros conceptos

- **Requiere**: [[GRPO]], SFT, RL
- **Relacionado con**: [[Self-Evolving Agentic Reasoning]], [[Reflexion]]
- **Opuesto a**: [[In-Context Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Secciones 3.2.2, 3.3.2, 4.1.2
