---
titulo: "Towards accurate differential diagnosis with large language models"
autores: "Daniel McDuff, Mike Schaekermann, Tao Tu, Anil Palepu, Amy Wang, Jake Garrison, Karan Singhal, Yash Sharma, Shekoofeh Azizi, Kavita Kulkarni, Le Hou, Yong Cheng, Yun Liu, S. Sara Mahdavi, Sushant Prakash, Anupam Pathak, Christopher Semturs, Shwetak Patel, Dale R. Webster, Ewa Dominowska, Juraj Gottweis, Joelle Barral, Katherine Chou, Greg S. Corrado, Yossi Matias, Jake Sunshine, Alan Karthikesalingam, Vivek Natarajan"
año: "2025"
fuente: "Nature"
DOI: "10.1038/s41586-025-08869-4"
citekey: "mcduffAccurateDifferentialDiagnosis2025"
zotero: "zotero://select/library/items/BHXDQKP9"
tags:
  - paper
  - agentic-reasoning
  - clinical
  - evaluation
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-21"
valoracion: ⭐⭐⭐⭐⭐
---

# Towards accurate differential diagnosis with large language models

## Metadatos

- **Autores**: Daniel McDuff, Mike Schaekermann, Tao Tu, Anil Palepu, Amy Wang, Jake Garrison, Karan Singhal, Yash Sharma, Shekoofeh Azizi, Kavita Kulkarni, Le Hou, Yong Cheng, Yun Liu, S. Sara Mahdavi, Sushant Prakash, Anupam Pathak, Christopher Semturs, Shwetak Patel, Dale R. Webster, Ewa Dominowska, Juraj Gottweis, Joelle Barral, Katherine Chou, Greg S. Corrado, Yossi Matias, Jake Sunshine, Alan Karthikesalingam, Vivek Natarajan
- **Año**: 2025
- **Publicación**: Nature (Vol. 638, pp. 748–756)
- **DOI**: [10.1038/s41586-025-08869-4](https://doi.org/10.1038/s41586-025-08869-4)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/BHXDQKP9)
- **Abstract**: A comprehensive differential diagnosis is a cornerstone of medical care that is often reached through an iterative process of interpretation that combines clinical history, physical examination, investigations and procedures. Interactive interfaces powered by large language models present new opportunities to assist and automate aspects of this process. Here we introduce the Articulate Medical Intelligence Explorer (AMIE), a large language model that is optimized for diagnostic reasoning, and evaluate its ability to generate a differential diagnosis alone or as an aid to clinicians. Twenty clinicians evaluated 302 challenging, real-world medical cases sourced from published case reports. Each case report was read by two clinicians, who were randomized to one of two assistive conditions: assistance from search engines and standard medical resources; or assistance from AMIE in addition to these tools. All clinicians provided a baseline, unassisted differential diagnosis prior to using the respective assistive tools. AMIE exhibited standalone performance that exceeded that of unassisted clinicians (top-10 accuracy 59.1% versus 33.6%, P = 0.04). Comparing the two assisted study arms, the differential diagnosis quality score was higher for clinicians assisted by AMIE (top-10 accuracy 51.7%) compared with clinicians without its assistance (36.1%; McNemar’s test: 45.7, P < 0.01) and clinicians with search (44.4%; McNemar’s test: 4.75, P = 0.03). Further, clinicians assisted by AMIE arrived at more comprehensive differential lists than those without assistance from AMIE. Our study suggests that AMIE has potential to improve clinicians’ diagnostic reasoning and accuracy in challenging cases, meriting further real-world evaluation for its ability to empower physicians and widen patients’ access to specialist-level expertise.

---

## Resumen

Publicado en **Nature**, este trabajo presenta **AMIE** (*Articulate Medical Intelligence Explorer*), un sistema basado en LLM optimizado para el razonamiento diagnóstico diferencial (DDx) en medicina. A través de un riguroso ensayo clínico simulado aleatorizado con 20 médicos sobre 302 casos clínicos reales complejos de casos publicados (NEJM y similares), demuestra que AMIE no solo supera a médicos generalistas no asistidos en modo autónomo (59.1% vs 33.6% en top-10 accuracy), sino que, como herramienta de apoyo, eleva significativamente la precisión y exhaustividad diagnóstica de los facultativos frente al uso de motores de búsqueda estándar.

---

## Problema / Motivación

La elaboración del diagnóstico diferencial (DDx) es una de las tareas cognitivas más complejas en medicina: exige recopilar anamnesis, integrar hallazgos de exploración física y pruebas diagnósticas, y sopesar múltiples hipótesis bajo incertidumbre. 
Los errores diagnósticos representan una causa mayor de morbimortalidad evitable. Si bien los LLMs mostraban potencial en exámenes tipo test (como MedQA), existía una brecha enorme sobre:
1. Cómo interactúan los modelos en diálogos diagnósticos dinámicos.
2. Si un LLM puede asistir eficazmente a clínicos humanos en casos reales desafiantes sin inducir sesgos o errores.
3. La falta de ensayos metodológicamente rigurosos que comparen la asistencia de IA contra las herramientas clínicas actuales (búsqueda web/recursos médicos).

---

## Metodología

### Modelo y Optimización (AMIE)
- Basado en una arquitectura Transformer ajustada con datos del dominio médico y optimizada para diálogo diagnóstico interactivo, generación de preguntas aclaratorias e inducción de listas ponderadas de DDx.

### Diseño Experimental y Metodología de Evaluación
- **Cohorte de casos**: 302 casos clínicos reales desafiantes extraídos de reportes de casos médicos de revistas de alto impacto (ej. *New England Journal of Medicine* Clinicopathological Conferences).
- **Participantes**: 20 médicos clínicos generalistas.
- **Diseño cruzado aleatorizado**:
  - Cada caso fue evaluado independientemente por dos clínicos.
  - **Línea base unassisted**: El médico emite su primer DDx sin ninguna ayuda externa.
  - **Brazo Control Asistido**: Asistencia mediante motores de búsqueda estándar (Google, PubMed, UpToDate).
  - **Brazo AMIE Asistido**: Asistencia interactiva mediante AMIE además de herramientas de búsqueda.
  - **Evaluación autónoma (*standalone*)**: AMIE procesa el caso de forma completamente autónoma.
- **Métricas clínicas**:
  - *Top-10 y Top-3 DDx Accuracy*: Porcentaje de casos donde el diagnóstico definitivo de la autopsia/biopsia/patología figura en la lista diferencial.
  - *DDx Quality Score*: Puntuación estructurada de relevancia clínica y plausibilidad biológica evaluada a ciegas por especialistas.
  - *Exhaustividad y tamaño de la lista diferencial*.
  - Pruebas estadísticas pareadas de McNemar.

---

## Resultados Clave

- **Modo Standalone**: AMIE alcanzó un **59.1%** de precisión Top-10 frente al **33.6%** de los médicos no asistidos ($P = 0.04$).
- **Impacto Asistencial**: Los médicos asistidos por AMIE alcanzaron un **51.7%** de precisión Top-10, superando significativamente tanto su línea base sin asistencia (36.1%, $P < 0.01$) como la asistencia con búsqueda tradicional (44.4%, $P = 0.03$).
- **Listas diferenciales más exhaustivas**: Los médicos con AMIE consideraron diagnósticos relevantes poco frecuentes que de otro modo habrían omitido (reducción del sesgo de cierre prematuro).
- **Percepción clínica**: Los facultativos valoraron positivamente la utilidad de AMIE como herramienta de soporte a la deliberación y educación médica continua.

---

## Contribuciones Principales

1. **AMIE**: Sistema LLM puntero diseñado específicamente para la formulación de diagnósticos diferenciales clínicos.
2. **Estándar metodológico de evaluación de IA médica**: Diseño de un estudio ciego, aleatorizado y controlado con 20 médicos sobre casos reales, comparando IA autónoma vs médico vs médico asistido por búsqueda vs médico asistido por IA.
3. **Evidencia empírica en Nature**: Demostración estadística de que la colaboración humano-IA en medicina supera a la práctica humana estándar con herramientas de búsqueda.

---

## Limitaciones

- Basado en viñetas clínicas de casos publicados de alta complejidad (sesgo hacia presentaciones atípicas o raras).
- Evaluación en entorno experimental controlado; se requiere validación prospectiva en flujos de trabajo hospitalarios reales.
- El tiempo invertido por los clínicos en interactuar con el sistema puede ser un factor restrictivo en consultas de atención primaria de alta presión asistencial.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 7)
> Generating a DDx is a critical step in clinical case management, and the capabilities of LLMs present new opportunities for assistive tooling to help with this task. Our randomized study showed that AMIE was a helpful AI tool for DDx generation for generalist clinicians. Clinician participants indicated its utility for learning and education, and additional work is needed to understand its suitability for clinical settings. [#ffd400]

---

> [!quote] Resaltado (p. 8)
> Training an LLM for DDx. Our study introduces AMIE, a model that uses a transformer architecture (PaLM 2), fine-tuned on medical domain data; alongside an interface for enabling its use as an interactive assistant for clinicians. [#ffd400]

---

## Ideas y Conexiones

- Representa el patrón oro de evaluación empírica con **Human-in-the-Loop**, conectando de lleno con [[heEnablingSelfImprovingAgents2025]] (ARIA).
- A diferencia de benchmarks sintéticos, AMIE evalúa la **sinergia clínico-agente**: la métrica clave no es solo la precisión del modelo en solitario, sino el *delta* de ganancia diagnóstica del médico humano al ser asistido.
- Se complementa con [[geClinicalAgentsMultiAgentOrchestration2026]] (ClinicalAgents): mientras AMIE opera como un asistente conversacional interactivo experto, ClinicalAgents organiza la deliberación interna mediante MCTS multi-agente.

---

## Notas Relacionadas

- [[AMIE]] — Nota conceptual del sistema
- [[ClinicalAgents]] — Orquestación clínica multi-agente
- [[AgentClinic]] — Benchmark de simulación clínica interactiva
- [[MedAgents]] — Colaboración multi-disciplinar de agentes médicos
- [[Collective Multi-Agent Reasoning]] — Interacción y colaboración agente-humano
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
