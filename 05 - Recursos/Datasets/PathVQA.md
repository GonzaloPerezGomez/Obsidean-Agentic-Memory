---
titulo: "PathVQA"
tags:
  - dataset
  - recurso
  - clinical
  - multimodal
  - pathology
  - VQA
fuente: "https://github.com/UCSD-AI4H/PathVQA"
fecha_creacion: "2026-10-22"
---

# PathVQA

## Descripción

> Primer dataset de preguntas y respuestas visuales (*Visual Question Answering*) dedicado a la anatomía patológica, diseñado para evaluar la capacidad de los modelos multimodales para interpretar imágenes microscópicas e histopatológicas y responder interrogantes diagnósticos.

A diferencia de la radiología general, la patología exige reconocer alteraciones morfológicas microscópicas sutiles a nivel celular e histológico (núcleos atípicos, mitosis anormales, patrones de invasión tisular).

## Características Principales

- **Tamaño:** 32.799 pares de pregunta-respuesta basados en 4.998 imágenes de patología médica.
- **Tipos de preguntas:** Preguntas abiertas y preguntas cerradas binarias (`yes / no`).
- **Modalidad:** Imagen histopatológica de alta resolución + Texto clínico.

## Papers que lo utilizan en la bóveda

- [[geClinicalAgentsMultiAgentOrchestration2026]] — Subconjunto de 3.362 muestras utilizado en ClinicalAgents para evaluar la generalización de la interpretación visual diagnóstica en patología.
