---
titulo: "AgentClinic: a multimodal agent benchmark to evaluate AI in simulated clinical environments"
autores: "Samuel Schmidgall, Rojin Ziaei, Carl Harris, Eduardo Reis, Jeffrey Jopling, Michael Moor"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2405.07960"
citekey: "schmidgallAgentClinicMultimodalAgent2025"
zotero: "zotero://select/library/items/8S3HSBMM"
tags:
  - paper
  - agentic-reasoning
  - benchmarks
  - multimodal
  - clinical
  - evaluation
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-21"
valoracion: ⭐⭐⭐⭐⭐
---

# AgentClinic: a multimodal agent benchmark to evaluate AI in simulated clinical environments

## Metadatos

- **Autores**: Samuel Schmidgall, Rojin Ziaei, Carl Harris, Eduardo Reis, Jeffrey Jopling, Michael Moor
- **Año**: 2025
- **Publicación**: arXiv preprint (Stanford / Johns Hopkins)
- **DOI**: [10.48550/arXiv.2405.07960](https://doi.org/10.48550/arXiv.2405.07960)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/8S3HSBMM)
- **Abstract**: Evaluating large language models (LLM) in clinical scenarios is crucial to assessing their potential clinical utility. Existing benchmarks rely heavily on static question-answering, which does not accurately depict the complex, sequential nature of clinical decision-making. Here, we introduce AgentClinic, a multimodal agent benchmark for evaluating LLMs in simulated clinical environments that include patient interactions, multimodal data collection under incomplete information, and the usage of various tools, resulting in an in-depth evaluation across nine medical specialties and seven languages. We find that solving MedQA problems in the sequential decision-making format of AgentClinic is considerably more challenging, resulting in diagnostic accuracies that can drop to below a tenth of the original accuracy. Overall, we observe that agents sourced from Claude-3.5 outperform other LLM backbones in most settings. Nevertheless, we see stark differences in the LLMs' ability to make use of tools, such as experiential learning, adaptive retrieval, and reflection cycles. Strikingly, Llama-3 shows up to 92% relative improvements with the notebook tool that allows for writing and editing notes that persist across cases. To further scrutinize our clinical simulations, we leverage real-world electronic health records, perform a clinical reader study, perturb agents with biases, and explore novel patient-centric metrics that this interactive environment firstly enables.

---

## Resumen

AgentClinic es el primer benchmark comprensivo diseñado para evaluar **agentes clínicos multimodales en entornos interactivos simulados**. Supera las evaluaciones clásicas de QA estático (como MedQA) al recrear consultas médicas realistas como procesos de decisión secuencial con información incompleta. El benchmark orquesta cuatro roles de agentes (Doctor, Paciente, Medición y Moderador) donde el agente evaluado debe dialogar, solicitar pruebas complementarias, interpretar imágenes médicas, utilizar herramientas (navegación, reflexión, cuaderno de notas persistente) y emitir un diagnóstico bajo posibles sesgos cognitivos del interlocutor.

---

## Problema / Motivación

La gran mayoría de benchmarks de IA médica (MedQA, PubMedQA, MMLU Medical) se estructuran como preguntas cerradas de opción múltiple con toda la información clínica ya digerida y servida en el enunciado. En la clínica real:
1. **La información es incompleta y activa**: El médico debe preguntar proactivamente para extraer la anamnesis.
2. **Las decisiones son secuenciales**: Se ordenan pruebas según las sospechas, interpretando resultados multimodales sobre la marcha.
3. **El rendimiento colapsa**: Cuando los LLMs que sacan >80% en MedQA se someten a este entorno interactivo secuencial, su precisión diagnóstica real llega a caer a menos de una décima parte.
4. **Faltan métricas centradas en el paciente**: No existía una forma de cuantificar la empatía, el trato clínico, el coste de las pruebas solicitadas innecesariamente o la resistencia a sesgos cognitivos.

---

## Metodología

### Arquitectura de Simulación Multi-Agente
El entorno simula una consulta clínica completa mediante cuatro agentes lingüísticos:
- **Doctor Agent**: El agente LLM bajo evaluación, encargado de interrogar, ordenar pruebas y diagnosticar.
- **Patient Agent**: Simula al paciente, revelando síntomas gradualmente solo si se le pregunta de forma apropiada.
- **Measurement Agent**: Actúa como el laboratorio/servicio de radiología, entregando resultados clínicos o imágenes diagnósticas únicamente si el agente doctor los solicita explícitamente.
- **Moderator**: Supervisa las reglas del juego, verifica el formato y valida la conclusión del encuentro clínico.

### Casos Clínicos y Cobertura Multimodal
- **120 agentes multimodales** (imágenes diagnósticas + texto clínico) y **215 agentes de texto** derivados de casos USMLE.
- **260 casos de pacientes** que abarcan 9 especialidades médicas.
- **749 casos clínicos multilingües** en 7 idiomas.
- Incorporación de registros reales de historias clínicas electrónicas (EHR).

### Uso de Herramientas Agénticas y Perturbaciones
- Los agentes pueden utilizar herramientas: navegación web, manuales médicos, ciclos de reflexión ([[Reflexion]]) y un **cuaderno de notas persistente** (*notebook tool*) que permite escribir y editar notas que persisten entre pacientes.
- **Perturbación de Sesgos Cognitivos**: Inyección deliberada de sesgos clínicos (ej. sesgo de anclaje, heurística de disponibilidad) para medir la susceptibilidad y robustez de los modelos.

### Métricas de Evaluación
- Precisión diagnóstica en decisión secuencial.
- Eficiencia diagnóstica (número de turnos y pruebas solicitadas).
- Métricas centradas en el paciente: empatía, claridad comunicativa y adecuación de costes.
- Estudio clínico de lectura (*reader study*) con médicos para validar la fidelidad de la simulación.

---

## Resultados Clave

- **Caída dramática del rendimiento**: Resolver casos clínicos en formato interactivo secuencial reduce drásticamente la precisión frente al formato estático (en algunos modelos, cae a menos del 10% de su precisión en MedQA original).
- **Rendimiento de modelos**: Los agentes basados en Claude-3.5 lideran en la mayoría de escenarios de decisión secuencial.
- **Impacto decisivo de la memoria persistente**: Modelos abiertos como Llama-3 logran hasta un **+92% de mejora relativa** al disponer de la herramienta de cuaderno (*notebook tool*) para registrar y reutilizar aprendizajes inter-casos.
- **Vulnerabilidad a sesgos**: Los sesgos cognitivos inducidos en el prompt reducen la exactitud diagnóstica en hasta un 26%.

---

## Contribuciones Principales

1. **Benchmark AgentClinic**: Plataforma estandarizada y abierta para evaluar agentes médicos en entornos de toma de decisiones secuencial interactiva.
2. **Entorno Multi-Agente Simulado**: Separación de roles (Doctor, Paciente, Medición, Moderador) que imita la recopilación activa de información bajo incertidumbre.
3. **Métricas holísticas de evaluación**: Incorporación de evaluación multimodal, uso de memoria/herramientas, susceptibilidad a sesgos y métricas centradas en el paciente.

---

## Limitaciones

- Los agentes simulados de paciente y medición dependen a su vez de LLMs, lo que puede introducir variabilidad o alucinaciones si el prompt del paciente no está rígidamente acotado.
- La evaluación de la empatía y habilidades de comunicación depende en parte de evaluadores LLM (*LLM-as-a-judge*), requiriendo calibración humana periódica.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 2)
> We allow doctor agents to use a variety of tools, such as browsing the web, textbooks, perform reflection cycles, take and edit notes in a notebook that persists over different patient scenarios. We show that current LLMs vastly differ in how much they benefit from these tools, with some models demonstrating large accuracy increases while others decrease in accuracy. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> Language agents. Four language agents are used in the AgentClinic benchmark: a patient agent, doctor agent, measurement agent, and a moderator. [#ffd400]

---

> [!quote] Resaltado (p. 3)
> Language agent biases. Previous work has indicated that LLMs can display racial biases and might also lead to incorrect diagnoses due to inaccurate patient feedback. Additionally, it has been found that the presence of prompts which induce cognitive biases can decrease the diagnostic accuracy of LLMs by as much as 26%. [#ffd400]

---

> [!quote] Resaltado (p. 11)
> In this work, we present AgentClinic: a multimodal agent benchmark for simulating clinical environments. We design 120 multimodal language agents which require an understanding of both language and images and 215 language agents based on cases from the USMLE. We also introduce 260 patient cases from 9 medical specialties and 749 patient cases from 7 multilingual environments. [#ffd400]

---

## Ideas y Conexiones

- AgentClinic es para la medicina lo que [[Evo-Memory]] es para el aprendizaje continuo de propósito general: el benchmark que fuerza al agente a salir del test estático y enfrentarse a un entorno dinámico interactivo.
- El hallazgo de que el cuaderno persistente mejora a Llama-3 en un 92% es una confirmación empírica directa de la importancia de la [[Agentic Memory]] y el test-time learning ([[Dynamic Cheatsheet]]).
- Conecta con [[ClinicalAgents]]: ClinicalAgents propone el orquestador MCTS para resolver este tipo de toma de decisiones clínicas secuenciales con backtracking.

---

## Notas Relacionadas

- [[AgentClinic]] — Nota conceptual del benchmark
- [[ClinicalAgents]] — Orquestación clínica multi-agente
- [[Evo-Memory]] — Benchmark de memoria auto-evolutiva
- [[Agentic Memory]] — Memoria externa persistente (notebook tool)
- [[MSM-Mem]] — Memoria clínica multimodal
- [[AMIE]] — Evaluación clínica de diagnóstico diferencial
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
