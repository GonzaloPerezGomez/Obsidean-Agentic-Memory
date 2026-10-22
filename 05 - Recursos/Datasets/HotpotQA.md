---
titulo: "HotpotQA"
tags:
  - dataset
  - recurso
  - reasoning
  - multi-hop
  - QA
fuente: "https://hotpotqa.github.io/"
fecha_creacion: "2026-10-22"
---

# HotpotQA

## Descripción

> Benchmark de preguntas y respuestas en lenguaje natural que exige **razonamiento multi-salto (*multi-hop reasoning*)** sobre múltiples documentos de Wikipedia para deducir la respuesta final.

El agente no puede responder consultando un solo pasaje; debe encontrar un primer hecho clave, extraer una pista intermedia, formular una nueva búsqueda hacia un segundo documento no obvio y contrastar la evidencia combinada.

## Características Principales

- **Tamaño:** 113.000 pares de preguntas y respuestas recopilados a partir de artículos de Wikipedia.
- **Doble supervisión:** Además de la respuesta final, proporciona anotaciones de las oraciones exactas de apoyo (*supporting facts*) necesarias para justificar la deducción.
- **Modalidad:** Texto y llamadas a APIs de búsqueda (ej. Wikipedia API).

## Papers que lo utilizan en la bóveda

- [[yaoReActSynergizingReasoning2023]] — Utilizado en ReAct para demostrar cómo alternar pensamientos y consultas interactivas a Wikipedia supera la alucinación de Chain of Thought lineal.
