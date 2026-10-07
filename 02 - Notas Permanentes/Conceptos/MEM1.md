---
titulo: "MEM1"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - RL
aliases: ["Memoria Consolidada Guiada por Razonamiento", "MEM1 Framework"]
fecha_creacion: "2026-10-07"
---

# MEM1

## Definición

> Framework de **aprendizaje por refuerzo end-to-end** que entrena agentes de lenguaje para operar con **memoria constante** en tareas multi-turno de largo horizonte, utilizando un estado interno compartido que unifica la consolidación de memoria y el razonamiento.

## Explicación

Los sistemas LLM tradicionales suelen emplear "full-context prompting", añadiendo continuamente el historial pasado al prompt. Esto causa un crecimiento ilimitado de memoria, eleva los costos computacionales y degrada la capacidad de razonamiento cuando el contexto excede la distribución de entrenamiento. MEM1 resuelve esto integrando la consolidación de memoria y el razonamiento en un **único estado interno compacto y compartido** que se actualiza en cada turno. El agente recibe una observación, y guiado exclusivamente por la recompensa final (RL end-to-end), aprende a retener información crítica, abstraer conceptos y descartar lo irrelevante. En lugar de tener heurísticas explícitas sobre qué recordar, la política de memoria emerge como un subproducto de la optimización del rendimiento en la tarea, logrando operar eficientemente sobre interacciones virtualmente infinitas sin degradación del razonamiento.

---

## Contexto

MEM1 se clasifica bajo el paraguas de **post-training memory control** descrito en el framework de [[Agentic Memory]] por Wei et al. Aborda la escalabilidad temporal a través de compresión basada en RL, conectando teóricamente con la abstracción del estado interno ($z$) en un [[POMDP]]. A diferencia de enfoques arquitectónicos como [[Titans (Arquitectura)]], MEM1 confía en el entrenamiento de políticas del agente para gestionar el estado.

---

## Relación con otros conceptos

- **Requiere**: Reinforcement Learning, Tareas con recompensa evaluable
- **Relacionado con**: [[MemAgent]] (ambos usan RL para la memoria), [[Agentic Memory]], [[POMDP]]
- **Se opone a**: Full-context prompting, Memoria plana sin compresión

---

## Referencias

- [[zhouMEM1LearningSynergize2025]] — Paper original de MEM1
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica la necesidad de abstracción en memoria
