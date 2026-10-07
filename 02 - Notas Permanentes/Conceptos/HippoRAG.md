---
titulo: "HippoRAG"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - RAG
aliases: ["HippoRAG 2", "Hippocampal RAG"]
fecha_creacion: "2026-10-01"
---

# HippoRAG

## Definición

> Framework de memoria a largo plazo para LLMs **inspirado en la neurobiología del hipocampo humano**, que combina un knowledge graph con Personalized PageRank para lograr capacidades de memoria factual, sense-making y asociativa que superan al RAG estándar.

## Explicación

HippoRAG reimagina RAG no como una simple herramienta de recuperación, sino como un sistema de **aprendizaje continuo no paramétrico** análogo a la memoria humana a largo plazo. Su arquitectura refleja tres componentes neurobiológicos: un LLM como neocortex artificial (procesamiento de conocimiento), un knowledge graph con Personalized PageRank como hipocampo artificial (almacenamiento auto-asociativo que permite encontrar conexiones no-obvias entre información dispersa), y un retrieval encoder como región parahipocampal (interfaz entre procesamiento y almacenamiento). HippoRAG 2 mejora el framework original con integración más profunda de pasajes y uso online del LLM durante la recuperación, resolviendo el trade-off que otros métodos KG-augmented sufren entre memoria asociativa y factual.

---

## Contexto

Representa una de las implementaciones más sofisticadas de [[Agentic Memory]] estructurada, posicionándose en la intersección entre [[Agentic Search]] y memoria persistente. A diferencia de [[Mind-Map Agent]] (que opera dentro de una sesión de razonamiento) o Mem0 (centrado en conversación), HippoRAG se enfoca en la **organización y asociación de conocimiento documental** a largo plazo.

---

## Relación con otros conceptos

- **Requiere**: Knowledge Graphs, [[Retrieval Augmented Generation (RAG)]]
- **Relacionado con**: [[Agentic Memory]], [[Agentic Search]], [[Mind-Map Agent]]
- **Se inspira en**: Neurobiología del hipocampo (memoria asociativa humana)

---

## Referencias

- [[gutierrezRAGMemoryNonParametric2025]] — Paper que introduce HippoRAG 2
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza memoria estructurada
