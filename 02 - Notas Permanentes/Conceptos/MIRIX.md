---
titulo: "MIRIX"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - multi-agent
aliases: ["MIRIX Memory System", "Sistema de Memoria MIRIX"]
fecha_creacion: "2026-10-05"
---

# MIRIX

## Definición

> Sistema de memoria **modular y multi-agente** con seis tipos de memoria especializados (Core, Episodic, Semantic, Procedural, Resource, Knowledge Vault), cada uno gestionado por un Memory Manager dedicado y coordinados por un Meta Memory Manager, con soporte nativo para experiencias multimodales.

## Explicación

MIRIX aborda la limitación fundamental de los sistemas de memoria existentes que usan almacenamiento plano indiferenciado. En su lugar, diferencia seis tipos de memoria inspirados en la psicología cognitiva: Core Memory (identidad persistente del agente y usuario), Episodic Memory (eventos con marca temporal), Semantic Memory (conocimiento abstracto y factual), Procedural Memory (workflows y scripts accionables), Resource Memory (documentos y archivos multimodales activos), y Knowledge Vault (información sensible y credenciales). Cada tipo tiene un agente Memory Manager especializado que sabe cómo leer, escribir y buscar en su dominio. Un Meta Memory Manager actúa como orquestador, decidiendo qué memorias consultar y actualizar en cada interacción. Esta separación de responsabilidades permite al sistema razonar con mayor precisión sobre qué información es relevante en cada momento, alcanzando SOTA en benchmarks de memoria tanto textuales como multimodales.

---

## Contexto

MIRIX representa la implementación más rica y diferenciada de [[Agentic Memory]] en la literatura actual. Su arquitectura multi-agente (Meta Manager + Memory Managers) es un ejemplo del patrón Manager-Workers del [[Collective Multi-Agent Reasoning]]. Se diferencia de Mem0 (memoria plana), [[HippoRAG]] (memoria asociativa), [[MemOS]] (infraestructura de sistema) y [[Mind-Map Agent]] (memoria dentro de una cadena de razonamiento) por su **diferenciación explícita de tipos cognitivos de memoria**.

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Memory]], [[Collective Multi-Agent Reasoning]]
- **Relacionado con**: [[MemOS]] (infraestructura), [[Self-Evolving Agentic Reasoning]] (procedural memory)
- **Supera a**: Mem0 (memoria plana), RAG estándar

---

## Referencias

- [[wangMIRIXMultiAgentMemory2025]] — Paper que introduce MIRIX
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza tipos de memoria agéntica
