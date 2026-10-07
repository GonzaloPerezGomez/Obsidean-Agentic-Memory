---
titulo: "Mind-Map Agent"
tags:
  - concepto
  - agentic-reasoning
  - memoria
aliases: ["Mind-Map", "Agente Mind-Map", "Knowledge Graph Agent"]
fecha_creacion: "2026-09-30"
---

# Mind-Map Agent

## Definición

> Agente especializado que construye y mantiene un **grafo de conocimiento estructurado** como memoria durante el razonamiento del LLM, almacenando contexto, rastreando relaciones lógicas y asegurando la coherencia en cadenas de razonamiento largas con uso extensivo de herramientas.

## Explicación

El Mind-Map Agent es una implementación concreta de memoria agéntica estructurada propuesta por Wu et al. (2025). A diferencia de la memoria plana (buffers de texto o listas de hechos), el Mind-Map construye un grafo de conocimiento donde los nodos representan entidades, conceptos o hechos descubiertos durante el razonamiento, y las aristas capturan relaciones lógicas entre ellos. Cuando el LLM genera un token especial de Mind-Map durante su cadena de razonamiento, el proceso se pausa momentáneamente: el agente recibe la query junto con el contexto de razonamiento actual, consulta o actualiza el grafo, y devuelve información estructurada que se reintegra en la cadena. Esto resuelve un problema crítico de los reasoning models: la pérdida de coherencia en cadenas de pensamiento muy largas, donde el modelo puede contradecirse o perder el hilo de razonamiento sin un mecanismo de memoria explícita.

---

## Contexto

El Mind-Map Agent es un ejemplo de lo que Wei et al. (2026) categorizan como **structured memory** dentro de la [[Agentic Memory]] — específicamente, una representación basada en grafos de conocimiento que permite búsqueda multi-hop y razonamiento composicional. Se sitúa en la capa de [[Foundational Agentic Reasoning]] ya que no incorpora mecanismos de auto-evolución inter-episódica.

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Memory]], grafos de conocimiento
- **Relacionado con**: [[Agentic Search]], [[Tool Use]], [[ReAct]]
- **Implementa**: Structured Memory (del survey de Wei et al.)

---

## Referencias

- [[wuAgenticReasoningStreamlined2025]] — Paper que introduce el Mind-Map Agent
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza este tipo de memoria estructurada
