---
titulo: "Dynamic Cheatsheet"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - test-time
aliases: ["DC", "Chuleta Dinámica"]
fecha_creacion: "2026-10-09"
---

# Dynamic Cheatsheet

## Definición

> Framework de **aprendizaje en tiempo de inferencia (test-time learning)** que dota a modelos de caja negra con una memoria persistente y auto-curada, donde almacenan y reutilizan heurísticas abstractas, estrategias y código validado ("chuletas") descubiertos en interacciones previas.

## Explicación

Dynamic Cheatsheet aborda la "amnesia de inferencia" de los LLMs. En lugar de procesar cada prompt desde cero (redescubriendo soluciones laboriosamente o repitiendo los mismos errores), el agente evalúa sus respuestas exitosas y abstrae los principios o código que funcionaron. Estos fragmentos (snippets) se guardan en un repositorio central. Cuando el agente enfrenta una tarea nueva, primero recupera contenido relevante de esta chuleta dinámica y combina la estrategia pre-validada con su razonamiento actual. A su vez, mecanismos de auto-curación (*self-curation*) le permiten podar o corregir heurísticas defectuosas en la memoria. Funciona puramente *in-context* sin necesidad de fine-tuning.

---

## Contexto

DC forma parte de la revolución del test-time compute. A nivel taxonómico (según Wei et al.), es una forma de [[In-Context Reasoning]] orientada a [[Self-Evolving Agentic Reasoning]]. Constituye una memoria procedimental y semántica de rápida evolución que demuestra ser crítica para lograr generalización en razonamiento matemático y algorítmico entre episodios. Como limitación, solo sirve como amplificador: si el modelo base es incapaz de generar una solución correcta inicial, la chuleta se poblará de heurísticas incorrectas.

---

## Relación con otros conceptos

- **Requiere**: Un modelo base competente capaz de auto-evaluar sus estrategias
- **Relacionado con**: [[Reflexion]] (feedback reflexivo), [[Agentic Memory]]
- **Opuesto a**: Razonamiento stateless (en el vacío)

---

## Referencias

- [[suzgunDynamicCheatsheetTestTime2025]] — Paper original de Dynamic Cheatsheet
