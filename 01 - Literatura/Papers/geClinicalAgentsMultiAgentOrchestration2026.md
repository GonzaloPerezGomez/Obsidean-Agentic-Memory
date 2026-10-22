---
titulo: "ClinicalAgents: Multi-Agent Orchestration for Clinical Decision Making with Dual-Memory"
autores: "Zhuohan Ge, Haoyang Li, Yubo Wang, Nicole Hu, Chen Jason Zhang, Qing Li"
año: "2026"
fuente: ""
DOI: "10.1145/3770855.3818931"
citekey: "geClinicalAgentsMultiAgentOrchestration2026"
zotero: "zotero://select/library/items/XX3GTI2Y"
tags:
  - paper
  - agentic-reasoning
  - multi-agent
  - memoria
  - clinical
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-20"
valoracion: ⭐⭐⭐⭐⭐
---

# ClinicalAgents: Multi-Agent Orchestration for Clinical Decision Making with Dual-Memory

## Metadatos

- **Autores**: Zhuohan Ge, Haoyang Li, Yubo Wang, Nicole Hu, Chen Jason Zhang, Qing Li
- **Año**: 2026
- **Publicación**: ACM Conference
- **DOI**: [10.1145/3770855.3818931](https://doi.org/10.48550/arXiv.3770855.3818931)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/XX3GTI2Y)
- **Abstract**: While Large Language Models (LLMs) have demonstrated potential in healthcare, they often struggle with the complex, non-linear reasoning required for accurate clinical diagnosis. Existing methods typically rely on static, linear mappings from symptoms to diagnoses, failing to capture the iterative, hypothesis-driven reasoning inherent in human clinicians. To bridge this gap, we introduce ClinicalAgents, a novel multi-agent framework designed to simulate the cognitive workflow of expert clinicians. Unlike rigid sequential chains, ClinicalAgents employs a dynamic orchestration mechanism modeled as a Monte Carlo Tree Search (MCTS) process. This allows an orchestrator to iteratively generate hypotheses, actively verify evidence, and trigger backtracking when critical information is missing. The foundation of this framework is a Dual-Memory architecture: a mutable working memory that maintains the evolving patient state for context-aware reasoning, and a static experience memory that retrieves clinical guidelines and historical cases via an active feedback loop. Extensive experiments demonstrate that ClinicalAgents achieves the best performance among evaluated baselines, significantly enhancing both diagnostic accuracy and explainability compared to strong single-agent and multi-agent baselines. Our code is released at https://github.com/ZhuohanGe/ClinicalAgents-Code.

---

## Resumen

ClinicalAgents es un framework multi-agente que modela el flujo de trabajo cognitivo de médicos especialistas mediante un **orquestador dinámico basado en Monte Carlo Tree Search (MCTS)** y una **arquitectura de Memoria Dual (Dual-Memory)**. Permite formular hipótesis diagnósticas de forma iterativa, verificar evidencia activa y realizar *backtracking* (retroceso reflexivo) cuando surgen incongruencias o falta información crítica, superando las limitaciones de los sistemas lineales tradicionales.

---

## Problema / Motivación

La toma de decisiones clínicas real es inherentemente no lineal, probabilística e iterativa: los médicos no realizan un mapeo directo de un solo paso de síntomas a diagnósticos, sino que exploran diagnósticos diferenciales, solicitan pruebas específicas, refinan sospechas y retroceden si una prueba contradice su hipótesis.
Sin embargo, los enfoques actuales basados en LLMs:
1. Emplean cadenas de razonamiento lineales y rígidas (pipelines estáticos de 1 pasada), que no admiten rectificación ante diagnósticos erróneos intermedios.
2. Carecen de sincronización de estado entre especialistas y de separación entre el historial contingente del paciente y el conocimiento médico consolidado.

---

## Metodología

ClinicalAgents estructura su sistema en tres componentes esenciales:

1. **Pool de Agentes Especializados (Agent Pool)**:
   - Agentes que simulan roles clínicos específicos: triaje y derivación (*Specialty Referral*), solicitud de pruebas (*Test Ordering*), interpretación de pruebas e imágenes diagnósticas (*Examination*), diagnóstico integrador (*Diagnosis*) y planificación terapéutica (*Treatment*).
2. **Clinical Orchestrator guiado por MCTS**:
   - Actúa como el controlador ejecutivo. Modela la formulación diagnóstica como un árbol de búsqueda (MCTS).
   - Genera múltiples hipótesis clínicas competitivas, selecciona ramas prometedoras, coordina a los agentes especializados para validar evidencia y ejecuta operaciones de **backtracking** para descartar hipótesis cuando los resultados de los análisis contradicen la sospecha clínica.
3. **Sistema de Memoria Dual (Dual-Memory System)**:
   - **Working Memory ($M_{work}$)**: Memoria mutable y dinámica que almacena el estado evolutivo del paciente actual a lo largo del proceso diagnóstico. Permite que todos los agentes del pool compartan un contexto sincronizado en tiempo real.
   - **Experience Memory ($M_{exp}$)**: Memoria estática e indexada que recupera guías de práctica clínica, protocolos médicos y casos históricos similares mediante un bucle de retroalimentación activa.

---

## Resultados Clave

- **Evaluación en [[MedChain]] (pipeline clínico de 5 etapas)**: Supera con holgura a baselines single-agent (ej. GPT-4) y multi-agent en las 5 etapas:
  - *Task 1 (Referral)*: Alta precisión de triaje y asignación de departamento (IoU).
  - *Task 2 (Test Ordering)*: Mayor cobertura y especificidad en pruebas solicitadas (IoU superior).
  - *Task 3 (Examination)*: Mayor fidelidad diagnóstica en informes de imágenes médicas evaluados con DocLens.
  - *Task 4 (Diagnosis)*: Máxima puntuación en corrección diagnóstica y coherencia argumental evaluada mediante LLM-as-a-Judge.
  - *Task 5 (Treatment)*: Planes de tratamiento con mayor solapamiento frente al estándar clínico de referencia.
- **Generalización**: Rendimiento superior mantenido en benchmarks médicos adicionales (MedDG, MedQA, PubMedQA, MedBullets y PathVQA).

---

## Contribuciones Principales

1. **Orquestación dinámica con MCTS**: Introducción de búsqueda en árbol y backtracking clínico para emular la deliberación de juntas médicas expertas.
2. **Arquitectura Dual-Memory**: Separación formal y sincronización entre memoria de trabajo mutable ($M_{work}$) y memoria de experiencia estática ($M_{exp}$).
3. **Validación integral en MedChain**: Demostración empírica de robustez y alta explicabilidad clínica a través de un flujo longitudinal multimodal completo.

---

## Limitaciones

- El algoritmo MCTS y el soporte de múltiples agentes especializados introduce un mayor coste computacional y de latencia que una inferencia zero-shot directa.
- En situaciones de urgencia crítica extrema donde se requiere respuesta en milisegundos, la búsqueda exhaustiva en árbol puede requerir heurísticas de poda agresivas.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 3)
> The architecture of ClinicalAgents is built around a diverse array of specialized doctor agents that encompass the entire clinical workflow, from the initial patient visit to the final diagnosis. As illustrated in Figure 1, the framework comprises three core components: • Agent Pool: This component contains specialized agents representing specific medical roles and tasks. • Clinical Orchestrator: Serving as the executive controller, it manages task distribution, information flow, and the execution of backtracking procedures. Details are discussed in Sec. 3.2. • Dual-Memory System: This system facilitates state synchronization across agents, consisting of a mutable Working Memory Mwork and a static Experience Memory Mexp. Sec. 3.3 elaborates on its design and functionality. [#ffd400]

---

> [!quote] Resaltado (p. 6)
> MedChain is organized as a sequential, interdependent clinical workflow: Task 1 → Task 2 → Task 3 → Task 4 → Task 5. Outputs from earlier stages are explicitly fed into subsequent ones, enforcing cross-stage correlation and sequential consistency across the pipeline. Concretely, the five stage-level tasks and their evaluation metrics are: Specialty Referral, Test Ordering, Examination, Diagnosis, and Treatment. [#ffd400]

---

## Ideas y Conexiones

- Se vincula directamente con la Capa 3 del survey de Wei et al. ([[Collective Multi-Agent Reasoning]]), ilustrando la diferenciación de roles funcionales (Leader/Orchestrator, Workers especializados y Critics evaluadores).
- La inclusión de MCTS conecta de lleno con [[Tree of Thoughts]] y [[Planning]]: el razonamiento clínico no es un camino greedy, sino un espacio combinatorio que exige poda y retroceso (*backtracking*).
- El concepto de memoria dual refleja la división biológica entre memoria de trabajo a corto plazo y memoria a largo plazo semántica/experiencial en [[Agentic Memory]].

---

## Notas Relacionadas

- [[Collective Multi-Agent Reasoning]] — Framework multi-agente
- [[ClinicalAgents]] — Nota conceptual del framework
- [[Planning]] — Planificación y búsqueda en árbol
- [[Tree of Thoughts]] — Búsqueda en árbol de pensamientos
- [[Agentic Memory]] — Arquitectura Dual-Memory
- [[MSM-Mem]] — Enfoque complementario de memoria médica estructurada
- [[weiSurveyAgenticReasoning2026]] — Taxonomía de roles y multi-agente
