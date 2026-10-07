---
titulo: "MemSkill"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - self-evolving
aliases: ["Memory Skills", "Skills de Memoria"]
fecha_creacion: "2026-10-07"
---

# MemSkill

## Definición

> Framework que reconceptualiza las operaciones de memoria de agentes LLM como **skills aprendibles y evolutivos** — rutinas estructuradas y reutilizables para extraer, consolidar y podar información — en lugar de procedimientos fijos diseñados manualmente.

## Explicación

La mayoría de sistemas de memoria para agentes dependen de operaciones estáticas predefinidas (insertar, actualizar, eliminar). MemSkill rompe con esta rigidez al tratar cada operación de memoria como un "skill" aprendible, análogo a las habilidades de acción en agentes como Voyager. Un **controller** selecciona qué skills aplicar según el contexto actual, un **executor** LLM produce memorias guiadas por los skills seleccionados, y un **designer** revisa periódicamente los fallos para refinar y crear nuevos skills. Este ciclo cerrado permite que las propias capacidades de gestión de memoria evolucionen junto con la experiencia del agente: de primitivas básicas (INSERT/UPDATE/DELETE/SKIP) a operaciones cada vez más sofisticadas y especializadas para el dominio.

---

## Contexto

MemSkill se sitúa en la intersección de [[Self-Evolving Agentic Reasoning]] (evolución procedimental) y [[Agentic Memory]] (gestión activa de memoria). Se complementa con enfoques como [[MemAgent]] (que aprende *qué* recordar vía RL) y MemEvolve (que evoluciona la *arquitectura* del sistema). MemSkill se enfoca específicamente en evolucionar el *cómo*: las operaciones mismas de gestión de memoria.

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Memory]], [[Self-Evolving Agentic Reasoning]]
- **Relacionado con**: [[Reflexion]] (feedback para mejorar skills), [[Tool Use]] (analogía operaciones→herramientas)
- **Complementario a**: [[MemAgent]] (qué recordar), MemEvolve (arquitectura de memoria)

---

## Referencias

- [[zhangMemSkillLearningEvolving2026]] — Paper que introduce MemSkill
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza evolución procedimental
