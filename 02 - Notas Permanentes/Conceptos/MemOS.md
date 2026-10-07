---
titulo: "MemOS"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - sistemas
aliases: ["Memory Operating System", "Sistema Operativo de Memoria", "MemCube"]
fecha_creacion: "2026-10-01"
---

# MemOS

## Definición

> **Sistema operativo de memoria para LLMs** que trata la memoria como un recurso gestionable del sistema, unificando la representación, scheduling y evolución de tres tipos heterogéneos de memoria (plaintext, activaciones y parámetros) bajo una abstracción común llamada MemCube.

## Explicación

MemOS propone una analogía profunda entre la gestión de memoria en sistemas operativos clásicos y la gestión de conocimiento en LLMs. Así como un OS gestiona RAM, disco y caché con políticas de scheduling y lifecycle, MemOS gestiona tres "capas" de memoria de un LLM: plaintext memory (texto explícito como hechos o documentos, análoga a archivos en disco), activation memory (KV cache y hidden states, análoga a RAM), y parameter memory (pesos del modelo como LoRA adapters, análoga a firmware). La unidad básica es el **MemCube**, que encapsula contenido de memoria junto con metadatos de procedencia y versionado, permitiendo componer, migrar y fusionar memorias entre tipos. Esta abstracción habilita transiciones fascinantes: conocimiento textual puede "compilarse" gradualmente en parámetros a medida que se estabiliza, o conocimiento paramétrico puede externalizarse como texto consultable. MemOS es primariamente un framework arquitectónico/conceptual que establece la infraestructura fundacional para aprendizaje continuo personalizado.

---

## Contexto

MemOS aborda el gap que el survey de Wei et al. identifica en **post-training memory control** para sistemas multi-agente. Su enfoque de tratar memoria como recurso de sistema lo diferencia de enfoques como Mem0 (práctico, centrado en conversación), [[HippoRAG]] (bio-inspirado, centrado en asociación) o [[Mind-Map Agent]] (dentro de una cadena de razonamiento). MemOS aspira a ser la **infraestructura subyacente** sobre la que se podrían construir todos estos sistemas.

---

## Relación con otros conceptos

- **Requiere**: [[Agentic Memory]], infraestructura de LLMs
- **Relacionado con**: [[Self-Evolving Agentic Reasoning]], [[Post-Training Reasoning]], [[In-Context Reasoning]]
- **Complementario a**: Mem0 (práctico), [[HippoRAG]] (bio-inspirado), [[Mind-Map Agent]] (razonamiento)

---

## Referencias

- [[liMemOSMemoryOS2025]] — Paper que introduce MemOS y MemCube
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica gaps en memory management
