---
titulo: "Reflexion"
tags:
  - concepto
  - agentic-reasoning
  - framework
aliases: ["Reflexion Framework"]
fecha_creacion: "2026-09-29"
---

# Reflexion

## Definición

> Framework de **feedback reflexivo** que permite a los agentes criticar y refinar sus propios procesos de razonamiento, sintetizando logs de errores en pistas lingüísticas que condicionan las políticas de razonamiento futuras.

## Explicación

Reflexion introduce un mecanismo de auto-mejora donde, tras completar (o fallar) una tarea, el agente genera una reflexión textual analizando qué salió mal y cómo mejorar. Estas reflexiones se almacenan como parte del estado evolutivo verbal del agente y se incluyen como contexto en intentos futuros, creando un ciclo de aprendizaje sin necesidad de actualizar los pesos del modelo. El agente efectivamente "aprende de sus errores" manteniendo una memoria de lecciones aprendidas que guían su comportamiento. Este enfoque es un ejemplo paradigmático de evolución verbal dentro del framework de self-evolving agentic reasoning.

---

## Contexto

Reflexion forma parte del reflective feedback, uno de los tres regímenes de feedback agéntico (junto con parametric adaptation y validator-driven feedback). Representa la capacidad metacognitiva de un agente de evaluar la calidad de su propio razonamiento.

---

## Relación con otros conceptos

- **Requiere**: [[ReAct]], [[Agentic Memory]]
- **Relacionado con**: [[Self-Evolving Agentic Reasoning]], [[Reflective Feedback]]
- **Opuesto a**: Enfoques sin auto-crítica (generación one-shot)

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 4.1.1: Reflective Feedback
