---
titulo: "PubMedQA"
tags:
  - dataset
  - recurso
  - clinical
  - biomedical
  - QA
fuente: "https://pubmedqa.github.io/"
fecha_creacion: "2026-10-22"
---

# PubMedQA

## Descripción

> Benchmark biomédico de preguntas y respuestas formuladas directamente a partir de títulos y resúmenes de investigaciones científicas indexadas en PubMed, diseñado para evaluar la capacidad de comprensión de lectura y razonamiento sobre evidencia científica.

A partir de la pregunta planteada y del texto del *abstract*, el modelo debe deducir una respuesta categórica estructurada (`yes`, `no` o `maybe`), acompañada de una justificación que sintetice la evidencia del estudio.

## Características Principales

- **Tamaño:** 1.000 preguntas anotadas por expertos humanos (*PQA-labeled*), 61.200 preguntas sin etiquetar (*PQA-unlabeled*) y 211.300 generadas artificialmente (*PQA-artificial*).
- **Formato:** Pregunta biomédica + Contexto (resumen de PubMed sin la conclusión) $\rightarrow$ Respuesta (`yes / no / maybe`) + Justificación larga.
- **Modalidad:** Texto biomédico especializado.

## Papers que lo utilizan en la bóveda

- [[tangMedAgentsLargeLanguage2024]] — Evaluación de consenso multidisciplinar en MedAgents sobre literatura biomédica.
- [[geClinicalAgentsMultiAgentOrchestration2026]] — Pruebas de generalización de razonamiento en ClinicalAgents.
