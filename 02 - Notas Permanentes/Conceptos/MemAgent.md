---
titulo: "MemAgent"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - RL
aliases: ["Agente MemAgent", "Memory Agent"]
fecha_creacion: "2026-10-05"
---

# MemAgent

## Definición

> Agente de memoria optimizado mediante **aprendizaje por refuerzo (RL)** end-to-end que procesa textos masivos por segmentos y gestiona dinámicamente una memoria compacta con estrategia de sobrescritura, permitiendo extrapolar contextos de 8K a millones de tokens con mínima degradación de rendimiento.

## Explicación

MemAgent aborda la limitación de escalabilidad en modelos de contexto largo sin incurrir en costes cuadráticos ni depender de atención infinita. El agente fragmenta documentos de gran extensión en bloques manejables (ej. 8K tokens) y, tras procesar cada segmento de forma secuencial, decide de manera autónoma qué información retener, actualizar o descartar en un buffer de memoria de tamaño fijo. La clave radica en su entrenamiento mediante una extensión de DAPO (Direct Alignment/Policy Optimization): en lugar de depender de heurísticas manuales o supervisión estática, el agente aprende mediante recompensas orientadas a la tarea qué datos son indispensables recordar. Esto le permite generalizar a longitudes extremas (hasta 3.5M tokens) conservando la complejidad lineal del sistema.

---

## Contexto

MemAgent representa una realización práctica de **post-training memory control** categorizada en la taxonomía de [[Agentic Memory]] (Wei et al., 2026). Mientras que arquitecturas como [[Titans (Arquitectura)]] abordan la memoria a largo plazo a nivel de capas internas del modelo y sistemas como [[MemOS]] o [[MIRIX]] lo hacen mediante arquitecturas modulares o de sistema operativo, MemAgent implementa una política agéntica aprendida para la manipulación activa del flujo de memoria.

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Memory]], [[Post-Training Reasoning]], Aprendizaje por Refuerzo (RL / DAPO)
- **Relacionado con**: [[MemOS]] (gestión del ciclo de vida), [[Titans (Arquitectura)]] (contexto extremo), [[In-Context Reasoning]]
- **Se diferencia de**: Enfoques de memoria estáticos o basados exclusivamente en prompts sin entrenamiento de políticas.

---

## Referencias

- [[yuMemAgentReshapingLongContext2026]] — Paper que introduce MemAgent
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica el control de memoria post-training
