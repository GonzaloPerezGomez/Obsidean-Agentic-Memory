---
titulo: "Reflective Feedback"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Feedback Reflexivo"]
fecha_creacion: "2026-09-29"
---

# Reflective Feedback

## Definición

> Mecanismo de mejora del razonamiento agéntico que **modifica las trayectorias de razonamiento en tiempo de inferencia** mediante pasos adicionales de evaluación y comparación, sin actualizar los parámetros del modelo.

## Explicación

El reflective feedback es uno de los tres regímenes de feedback agéntico (junto con parametric adaptation y validator-driven feedback). En este enfoque, los outputs intermedios de razonamiento — como cadenas de pensamiento o soluciones parciales — se exponen a pasos adicionales de evaluación que influyen directamente en cómo el modelo continúa su generación. El modelo puede generar múltiples candidatos y seleccionar el mejor, criticar su propia solución y proponer mejoras, o verificar pasos intermedios contra criterios de consistencia. Lo fundamental es que el feedback se usa para guiar la generación *dentro* de un episodio, mientras que los parámetros del modelo permanecen inalterados. Esto lo diferencia de la parametric adaptation (que modifica pesos) y del validator-driven feedback (que solo proporciona señales binarias de éxito/fracaso).

---

## Contexto

Forma parte del pilar de feedback en [[Self-Evolving Agentic Reasoning]]. [[Reflexion]] es el framework más representativo de este enfoque.

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]], capacidad de auto-evaluación
- **Relacionado con**: [[Reflexion]], [[Self-Evolving Agentic Reasoning]]
- **Complementario a**: Parametric Adaptation, Validator-Driven Feedback

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 4.1.1: Reflective Feedback
