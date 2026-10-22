---
titulo: "MedXpertQA"
tags:
  - concepto
  - agentic-reasoning
  - benchmarks
  - multimodal
  - clinical
aliases: ["MedXpertQA Benchmark"]
fecha_creacion: "2026-10-22"
---

# MedXpertQA

## Definición

> Benchmark de **evaluación médica multimodal de nivel especialista**, compuesto por 4.460 preguntas que abarcan 17 especialidades y 11 sistemas corporales, diseñado para evaluar conocimientos clínicos avanzados y razonamiento deductivo profundo en modelos fundacionales y de razonamiento (tipo o1).

## Explicación

A medida que los grandes modelos de lenguaje han avanzado, los benchmarks clínicos clásicos (como MedQA o PubMedQA) han sufrido un rápido efecto de saturación: los modelos punteros obtienen precisiones superiores al 90%, creando la falsa ilusión de que dominan la medicina humana. Además, los benchmarks multimodales previos dependían en gran medida de preguntas simplistas extraídas de pies de foto de artículos científicos, sin requerir una verdadera interpretación de la imagen en el contexto del paciente.

MedXpertQA aborda estas carencias elevando drásticamente el listón de dificultad. Sus preguntas están extraídas y adaptadas a partir de exámenes oficiales de certificación de subespecialidades médicas (*specialty board exams*), requiriendo diagnósticos diferenciales intrincados, cálculo de riesgos pronósticos y toma de decisiones terapéuticas no triviales. Su subconjunto multimodal vincula imágenes médicas reales de alta resolución (TACs, resonancias, cortes histológicos) con historias clínicas completas. Además, incorpora un subconjunto expresamente seleccionado para poner a prueba a los nuevos modelos de razonamiento profundo (*test-time compute*), demostrando que la deducción médica especializada es un terreno de evaluación tan exigente como las matemáticas o el código.

---

## Contexto

Publicado por Zuo et al. (Tsinghua University, 2025), MedXpertQA representa la referencia moderna para evitar el estancamiento de la evaluación médica estática, complementando a plataformas de interacción agéntica como [[AgentClinic]].

---

## Relación con otros conceptos

- **Mide a**: Modelos multimodales, LLMs de razonamiento (o1-like), pericia médica especializada
- **Difiere de**: MedQA (supera su baja dificultad y efecto techo)
- **Complementa a**: [[AgentClinic]] (evaluación estática de alta dificultad vs evaluación secuencial interactiva)

---

## Referencias

- [[zuoMedXpertQABenchmarkingExpertLevel2025]] — Paper original de MedXpertQA
