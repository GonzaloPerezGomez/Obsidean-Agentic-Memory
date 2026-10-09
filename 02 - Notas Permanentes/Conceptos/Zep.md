---
titulo: "Zep"
tags:
  - concepto
  - agentic-reasoning
  - memoria
aliases: ["Zep Architecture", "Graphiti"]
fecha_creacion: "2026-10-09"
---

# Zep

## Definición

> Servicio de capa de memoria basada en una **arquitectura de grafo de conocimiento temporal (Graphiti)**, que sintetiza dinámicamente datos conversacionales y estructurados manteniendo la temporalidad y estado histórico de los hechos.

## Explicación

Zep aborda las carencias del RAG estándar al lidiar con flujos de conversación largos. En un entorno empresarial, un hecho verdadero ayer puede ser falso hoy, y un chunk de texto estático no refleja esa evolución. A través de su motor Graphiti, Zep ingiere los datos brutos en un "subgrafo episódico", extrae entidades y sus relaciones semánticas en un "subgrafo semántico" y genera resúmenes en un "subgrafo de comunidad" (jerarquía tri-nivel). Lo distintivo es la incorporación de la validez temporal ($t_{valid}$, $t_{invalid}$) en los nodos, permitiendo al sistema recuperar el estado del mundo pertinente para el momento actual, superando enfoques episódicos planos (como MemGPT) en latencia y capacidad de respuesta.

---

## Contexto

Representa un paso en la evolución de las arquitecturas de memoria desde memorias puramente episódicas o vectoriales (flat memory) a memorias estructuradas mediante Knowledge Graphs. Es similar a [[HippoRAG]], pero diseñado específicamente para agentes a largo plazo en casos de uso de negocio con una gestión explícita del estado temporal.

---

## Relación con otros conceptos

- **Requiere**: Knowledge Graphs, LLMs extractores
- **Relacionado con**: [[Agentic Memory]], [[HippoRAG]]
- **Opuesto a**: Memoria episódica sin estructurar (baselines como MemGPT)

---

## Referencias

- [[rasmussenZepTemporalKnowledge2025]] — Paper original de la arquitectura Zep
