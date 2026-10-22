---
titulo: "MedXpertQA: Benchmarking Expert-Level Medical Reasoning and Understanding"
autores: "Yuxin Zuo, Shang Qu, Yifei Li, Zhangren Chen, Xuekai Zhu, Ermo Hua, Kaiyan Zhang, Ning Ding, Bowen Zhou"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2501.18362"
citekey: "zuoMedXpertQABenchmarkingExpertLevel2025"
zotero: "zotero://select/library/items/HY4I5XBS"
tags:
  - paper
  - agentic-reasoning
  - benchmarks
  - multimodal
  - clinical
  - evaluation
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-22"
valoracion: ⭐⭐⭐⭐⭐
---

# MedXpertQA: Benchmarking Expert-Level Medical Reasoning and Understanding

## Metadatos

- **Autores**: Yuxin Zuo, Shang Qu, Yifei Li, Zhangren Chen, Xuekai Zhu, Ermo Hua, Kaiyan Zhang, Ning Ding, Bowen Zhou
- **Año**: 2025
- **Publicación**: arXiv preprint (Tsinghua University)
- **DOI**: [10.48550/arXiv.2501.18362](https://doi.org/10.48550/arXiv.2501.18362)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/HY4I5XBS)
- **Abstract**: We introduce MedXpertQA, a highly challenging and comprehensive benchmark to evaluate expert-level medical knowledge and advanced reasoning. MedXpertQA includes 4,460 questions spanning 17 specialties and 11 body systems. It includes two subsets, Text for text evaluation and MM for multimodal evaluation. Notably, MM introduces expert-level exam questions with diverse images and rich clinical information, including patient records and examination results, setting it apart from traditional medical multimodal benchmarks with simple QA pairs generated from image captions. MedXpertQA applies rigorous filtering and augmentation to address the insufficient difficulty of existing benchmarks like MedQA, and incorporates specialty board questions to improve clinical relevance and comprehensiveness. We perform data synthesis to mitigate data leakage risk and conduct multiple rounds of expert reviews to ensure accuracy and reliability. We evaluate 18 leading models on the benchmark. Moreover, medicine is deeply connected to real-world decision-making, providing a rich and representative setting for assessing reasoning abilities beyond mathematics and code. To this end, we develop a reasoning-oriented subset to facilitate the assessment of o1-like models. Code and data are available at: https://github.com/TsinghuaC3I/MedXpertQA

---

## Resumen

MedXpertQA es un **benchmark multimodal de nivel especialista** diseñado para evaluar el conocimiento médico avanzado y el razonamiento complejo en modelos fundacionales y de razonamiento (como OpenAI o1 y DeepSeek-R1). Con **4.460 preguntas** que cubren 17 especialidades médicas y 11 sistemas corporales, supera la saturación y la insuficiente dificultad de benchmarks clásicos (como MedQA) al incorporar exámenes de certificación médica de subespecialidad (*specialty board exams*), viñetas multimodales completas con imágenes clínicas reales (no meros pies de foto) y un subconjunto específico orientado a evaluar razonamiento deductivo profundo.

---

## Problema / Motivación

La evaluación de modelos en medicina enfrentaba una crisis de validez:
1. **Saturación de benchmarks clásicos**: Los modelos de frontera alcanzan más del 90% en MedQA (USMLE básico), lo que genera un "efecto techo" que oculta su incompetencia en medicina especializada real.
2. **Superficialidad de los benchmarks multimodales existentes**: La mayoría de datasets multimodales médicos previos se crearon a partir de pares pregunta-respuesta triviales extraídos de pies de figuras de artículos científicos, sin requerir verdadera interpretación de imágenes ni integración con historias clínicas.
3. **Falta de evaluación para modelos de razonamiento (o1-like)**: La mayor parte de benchmarks para modelos de razonamiento largo (*test-time reasoning*) se centran en matemáticas competitivas y programación, obviando la medicina como el campo por excelencia donde el razonamiento diagnóstico deductivo es crítico.
4. **Fuga de datos (*data leakage*)**: Muchas preguntas de exámenes públicos han sido absorbidas en los corpus de preentrenamiento.

---

## Metodología

### Estructura del Dataset
- **4.460 preguntas médicas de alta dificultad**:
  - Abarcan **17 especialidades clínicas** (cardiología, neurología, oncología, dermatología, etc.) y **11 sistemas orgánicos**.
  - Derivadas de exámenes de certificación de especialistas y casos de residencia avanzada.
- **Dos subconjuntos complementarios**:
  1. **Subset Text**: Evaluación de razonamiento clínico verbal avanzado y juicio terapéutico.
  2. **Subset MM (Multimodal)**: Integra imágenes médicas reales de alta resolución (TAC, resonancias magnéticas, histopatología, radiografías, ECGs) acompañadas de historias clínicas completas, antecedentes y analíticas de laboratorio.
- **Subconjunto orientado a razonamiento (*Reasoning-oriented subset*)**: Específicamente filtrado para poner a prueba cadenas de deducción profunda y evaluar modelos tipo OpenAI o1.

### Control de Calidad y Mitigación de Fuga
- **Síntesis y reescritura de datos**: Transformación sintética controlada de enunciados para evitar la memorización directa del preentrenamiento.
- **Revisión por panel de expertos**: Múltiples rondas de verificación manual por médicos especialistas para asegurar la exactitud de las respuestas correctas y la plausibilidad de los distractores.

---

## Resultados Clave

- **Evaluación de 18 modelos punteros**: Revela una brecha sustancial frente a benchmarks tradicionales. Modelos que obtienen >90% en MedQA caen sensiblemente en MedXpertQA, especialmente en el subconjunto multimodal.
- **Rendimiento de modelos de razonamiento**: Modelos de razonamiento en tiempo de inferencia (o1-like) exhiben una ventaja notable sobre LLMs estándar en las preguntas que exigen deducción clínica multi-paso, confirmando que la medicina es un banco de pruebas de primer nivel para el *test-time compute*.
- **Complejidad multimodal confirmada**: El subconjunto MM resulta considerablemente más difícil que el subset textual, evidenciando que la integración de imágenes diagnósticas con antecedentes clínicos sigue siendo un reto abierto.

---

## Contribuciones Principales

1. **Benchmark MedXpertQA**: Plataforma de evaluación médica de nivel especialista (4.460 preguntas en 17 especialidades).
2. **Estándar multimodal riguroso**: Superación de los datasets basados en pies de foto mediante viñetas clínicas completas acopladas a imágenes médicas reales.
3. **Banco de pruebas para modelos de razonamiento**: Demostración de la utilidad del razonamiento largo en problemas de decisión clínica especializada.

---

## Limitaciones

- Formato de respuesta cerrada (opción múltiple), lo que no evalúa directamente la habilidad conversacional con pacientes ni la interacción abierta en el flujo hospitalario.
- Mayoritariamente enfocado en estándares médicos de certificación anglosajones e internacionales.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. )
> a highly challenging and comprehensive benchmark to evaluate expert-level medical knowledge and advanced reasoning. MedXpertQA includes 4, 460 questions spanning 17 specialties and 11 body systems. It includes two subsets, Text for text evaluation and MM for multimodal evaluation. Notably, MM introduces expert-level exam questions with diverse images and rich clinical information, including patient records and examination results, setting it apart from traditional medical multimodal benchmarks with simple QA pairs generated from image captions. [#ffd400]

---

## Ideas y Conexiones

- MedXpertQA representa la **nueva generación de benchmarks médicos estáticos avanzados**, resolviendo el agotamiento de MedQA/PubMedQA.
- Complementa directamente a **[[AgentClinic]]**: mientras MedXpertQA mide la pericia diagnóstica estática de nivel subespecialista y multimodal, AgentClinic mide la competencia interactiva secuencial y el uso de herramientas en consultas simuladas.
- Sirve como la herramienta idónea para medir el impacto de arquitecturas de razonamiento como [[Tree of Thoughts]], [[ClinicalAgents]] o agentes con memoria multimodal como [[MSM-Mem]].

---

## Notas Relacionadas

- [[MedXpertQA]] — Nota conceptual del benchmark
- [[AgentClinic]] — Benchmark interactivo complementario
- [[MSM-Mem]] — Agente de memoria médica multimodal
- [[ClinicalAgents]] — Orquestación clínica multi-agente
- [[Evo-Memory]] — Benchmarking general de agentes
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
