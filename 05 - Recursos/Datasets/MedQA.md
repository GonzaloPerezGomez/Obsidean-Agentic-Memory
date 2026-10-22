---
titulo: "MedQA"
tags:
  - dataset
  - recurso
  - clinical
  - QA
fuente: "https://github.com/jind11/MedQA"
fecha_creacion: "2026-10-22"
---

# MedQA

## Descripción

> Benchmark fundamental de preguntas y respuestas médicas de opción múltiple derivado de los exámenes oficiales de licenciatura médica (USMLE en EE.UU., Taiwán y China continental), considerado durante años el estándar de oro para medir la competencia médica general de los LLMs.

Evalúa la capacidad de los modelos para interpretar viñetas clínicas de pacientes, recordar conocimientos biomédicos y seleccionar el diagnóstico o conducta más apropiada entre 4 o 5 opciones posibles.

## Características Principales

- **Tamaño:** Más de 12.000 preguntas en inglés (USMLE), además de variantes en chino simplificado y tradicional.
- **Formato:** Preguntas de opción múltiple con viñeta clínica (MCQ con 4 o 5 opciones).
- **Modalidad:** Texto.
- **Especialidades:** Medicina interna, farmacología, patología, bioquímica, cirugía, psiquiatría y salud pública.

## Limitaciones Identificadas en Agentes

Como señalan papers recientes en nuestra bóveda:
- **Efecto techo:** Los LLMs de frontera superan el 90% de acierto estático, perdiendo capacidad discriminativa.
- **Formato estático:** En el benchmark original, toda la información está servida de antemano. Cuando se adapta a consultas interactivas con información oculta (como en [[AgentClinic]]), el rendimiento de los modelos cae drásticamente.

## Papers que lo utilizan en la bóveda

- [[tangMedAgentsLargeLanguage2024]] — Evaluación zero-shot de deliberación multi-agente en MedAgents.
- [[geClinicalAgentsMultiAgentOrchestration2026]] — Pruebas de generalización diagnóstica en ClinicalAgents.
- [[schmidgallAgentClinicMultimodalAgent2025]] — Conversión de casos USMLE a agentes de diálogo interactivo en AgentClinic.
