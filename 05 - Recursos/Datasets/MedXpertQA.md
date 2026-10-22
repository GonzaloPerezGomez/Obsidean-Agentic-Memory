---
titulo: "MedXpertQA"
tags:
  - dataset
  - recurso
  - clinical
  - multimodal
  - benchmark
fuente: "https://github.com/TsinghuaC3I/MedXpertQA"
fecha_creacion: "2026-10-22"
---

# MedXpertQA

## Descripción

> Benchmark médico multimodal de nivel especialista, compuesto por 4.460 preguntas que abarcan 17 especialidades y 11 sistemas corporales, diseñado para evaluar conocimientos clínicos avanzados y razonamiento deductivo profundo en modelos fundacionales y de razonamiento (tipo o1).

Desarrollado para superar el estancamiento y la saturación de MedQA, incorpora preguntas de exámenes de certificación de subespecialistas (*specialty board exams*), viñetas multimodales completas con imágenes médicas reales (no simples pies de foto) y un subconjunto específico para evaluar razonamiento en inferencia (*test-time compute*).

## Características Principales

- **Tamaño:** 4.460 preguntas de alta complejidad.
- **Especialidades:** 17 ramas médicas (cardiología, neurología, oncología, dermatología, neumología, etc.) y 11 sistemas orgánicos.
- **Subconjuntos:**
  - *Subset Text:* Razonamiento verbal avanzado y juicio terapéutico.
  - *Subset MM (Multimodal):* Imágenes de alta resolución (TAC, resonancias, cortes histopatológicos, radiografías, ECGs) emparejadas con historiales clínicos y analíticas.
  - *Reasoning-oriented subset:* Diseñado expresamente para medir cadenas de deducción lógica profunda en modelos tipo OpenAI o1 o DeepSeek-R1.
- **Control de fuga (*data leakage*):** Reformulación sintética y múltiples rondas de verificación por facultativos especialistas.

## Papers que lo utilizan en la bóveda

- [[zuoMedXpertQABenchmarkingExpertLevel2025]] — Paper fundacional que introduce el benchmark.
