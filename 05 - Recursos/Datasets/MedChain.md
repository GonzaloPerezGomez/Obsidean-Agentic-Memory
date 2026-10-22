---
titulo: "MedChain"
tags:
  - dataset
  - recurso
  - clinical
  - multimodal
  - sequential
fuente: "https://github.com/ZhuohanGe/ClinicalAgents-Code"
fecha_creacion: "2026-10-22"
---

# MedChain

## Descripción

> Benchmark clínico estructurado como un flujo de trabajo secuencial e interdependiente de 5 etapas, donde el resultado de cada fase condiciona a las posteriores, imitando el ciclo completo de atención hospitalaria real de un paciente.

A diferencia de los benchmarks estáticos de opción múltiple, MedChain obliga al agente a encadenar decisiones a lo largo de todo el proceso asistencial: desde la llegada del paciente hasta el tratamiento final.

## Estructura de las 5 Etapas y Métricas

1. **Task 1: Specialty Referral (Derivación y Triaje):** Determina la urgencia y remite al paciente al departamento adecuado.
   - *Métrica:* Accuracy para el departamento de nivel 1 e **IoU (*Intersection over Union*)** para subespecialidades de nivel 2.
2. **Task 2: Test Ordering (Solicitud de Pruebas):** Prescribe las exploraciones y analíticas necesarias bajo sospecha clínica.
   - *Métrica:* **IoU** entre las pruebas solicitadas y las recomendadas por guías clínicas (penaliza tanto la omisión como el sobrediagnóstico).
3. **Task 3: Examination (Interpretación de Exploraciones e Imagen):** Resume los hallazgos y redacta el informe radiológico o anatomopatológico a partir de imágenes médicas.
   - *Métrica:* **DocLens** para evaluar la fidelidad diagnóstica de los informes generados.
4. **Task 4: Diagnosis (Diagnóstico Integrador):** Sintetiza las pruebas de las etapas 1 a 3 para emitir el diagnóstico definitivo.
   - *Métrica:* **LLM-as-a-Judge** para corrección clínica y coherencia del razonamiento.
5. **Task 5: Treatment (Plan de Tratamiento):** Diseña el plan terapéutico individualizado.
   - *Métrica:* **IoU** sobre el conjunto de fármacos y pautas clínicas prescritas.

## Características Principales

- **Tamaño:** 12.163 casos clínicos.
- **Modalidad:** Multimodal (Texto clínico + Imágenes médicas).
- **Formato:** Pipeline dependiente de 5 etapas.

## Papers que lo utilizan en la bóveda

- [[geClinicalAgentsMultiAgentOrchestration2026]] — Benchmark primario para evaluar la orquestación MCTS y la arquitectura Dual-Memory de ClinicalAgents.
