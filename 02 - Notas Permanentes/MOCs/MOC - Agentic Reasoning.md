---
titulo: "MOC — Agentic Reasoning"
tags:
  - MOC
  - agentic-reasoning
fecha_creacion: "2026-09-22"
---

# 🗺️ MOC — Agentic Reasoning

> Índice central de la investigación en Agentic Reasoning y Agentic Memory.

---

## Conceptos Fundamentales

- [[Agentic Reasoning]]
- [[Agentic Memory]]
- [[Tool Use]]
- [[Chain of Thought]]
- [[ReAct]]
- [[Reflexion]]
- [[Planning]]
- [[Multi-Agent Systems]]

## Taxonomía del Agentic Reasoning (Wei et al., 2026)

### Capa 1: Razonamiento Fundacional
- [[Foundational Agentic Reasoning]]
- [[Planning]] — Workflow-based, tree-search, formalización
- [[Tool Use]] — In-context, post-training, orquestación
- [[Agentic Search]] — RAG adaptativo y dinámico

### Capa 2: Razonamiento Auto-Evolutivo
- [[Self-Evolving Agentic Reasoning]]
- [[Reflective Feedback]] — Auto-crítica sin cambio de parámetros
- [[Agentic Memory]] — Memoria activa en el bucle de razonamiento
- [[Reflexion]] — Evolución verbal mediante reflexiones

### Capa 3: Razonamiento Colectivo Multi-Agente
- [[Collective Multi-Agent Reasoning]]
- [[Theory of Mind]] — Modelado de estados mentales entre agentes
- [[Dec-POMDP]] — Formalización multi-agente

### Dimensiones Transversales
- [[In-Context Reasoning]] — Escalado de cómputo en inferencia
- [[Post-Training Reasoning]] — Internalización vía RL/SFT
- [[GRPO]] — Optimización de políticas sin red de valor
- [[DAPO]] — Optimización de políticas con decoupled clipping y dynamic sampling
- [[POMDP]] — Formalización del entorno agéntico

## Temas Clave

### Estrategias de Prompting (precursores del Agentic Reasoning)
- [[Chain of Thought]]
- [[Tree of Thoughts]]
- [[Plan-and-Solve Prompting]] — Planificación zero-shot antes de ejecución
- [[Least-to-Most Prompting]] — Descomposición top-down + resolución bottom-up
- [[Self-Consistency]]
- [[Metacognición en Agentes]]

### Memoria
- [[Agentic Memory]]
- [[Mind-Map Agent]] — Memoria estructurada como grafo de conocimiento
- [[HippoRAG]] — Memoria bio-inspirada con knowledge graph + PageRank
- [[MemOS]] — Sistema operativo de memoria (plaintext/activation/parameter)
- [[Titans (Arquitectura)]] — Memoria neural interna: atención (short-term) + módulo neural (long-term)
- [[MIRIX]] — Sistema modular multi-agente con 6 memorias y soporte multimodal
- [[MemAgent]] — Agente de memoria optimizado con RL (DAPO) para contextos de millones de tokens
- [[MEM1]] — Estado interno compartido guiado por razonamiento para memoria constante
- [[MemSkill]] — Operaciones de memoria aprendibles y evolutivas
- [[MemEvolve]] — Meta-evolución de la arquitectura del sistema de memoria
- [[Zep]] — Arquitectura de grafo de conocimiento temporal jerárquico
- [[Dynamic Cheatsheet]] — Test-time learning con chuletas auto-curadas
- [[ARIA]] — Agente adaptativo con test-time learning y human-in-the-loop
- [[A-MEM]] — Memoria agéntica auto-organizada basada en principios de Zettelkasten
- [[MSM-Mem]] — Memoria médica multimodal estructurada (semántica, episódica, visual)
- [[Memoria a Largo Plazo (Long-term Memory)]]
- [[Retrieval Augmented Generation (RAG)]]
- [[Memory Architectures]]

### Planificación y Acción
- [[Planning]]
- [[Tool Use]]
- [[Agentic Search]]
- [[Code Generation como Razonamiento]]
- [[Grounding]]

### Arquitecturas de Agentes
- [[ReAct]]
- [[Reflexion]]
- [[ClinicalAgents]] — Orquestación MCTS con memoria dual para diagnóstico clínico
- [[MedAgents]] — Colaboración multidisciplinar multi-agente en comités médicos
- [[AMIE]] — Agente conversacional interactivo para diagnóstico diferencial (DDx)
- [[AutoGPT]]
- [[LangChain Agents]]
- [[Multi-Agent Debate]]

### Seguridad y Riesgos
- [[Misevolution]] — Riesgos emergentes en la auto-evolución (modelo, memoria, herramientas, workflow)

### Benchmarks y Evaluaciones
- [[Evo-Memory]] — Evaluación de memoria auto-evolutiva en task streams
- [[AgentClinic]] — Benchmark interactivo multimodal en consultas clínicas simuladas
- [[MedXpertQA]] — Benchmark médico multimodal de nivel subespecialista y razonamiento o1-like

### Formalismos y Algoritmos RL
- [[POMDP]]
- [[Dec-POMDP]]
- [[GRPO]]
- [[DAPO]]

## Papers Clave

- [[weiSurveyAgenticReasoning2026]] — ⭐ Survey comprehensivo del campo (Wei et al., 2026)
- [[mcduffAccurateDifferentialDiagnosis2025]] — AMIE: diagnóstico diferencial clínico interactivo en Nature (McDuff et al., 2025)
- [[schmidgallAgentClinicMultimodalAgent2025]] — AgentClinic: benchmark multimodal en clínicas simuladas (Schmidgall et al., 2025)
- [[geClinicalAgentsMultiAgentOrchestration2026]] — ClinicalAgents: orquestación MCTS y Dual-Memory clínica (Ge et al., 2026)
- [[tangMedAgentsLargeLanguage2024]] — MedAgents: deliberación colegiada de agentes médicos (Tang et al., 2024)
- [[zuoMedXpertQABenchmarkingExpertLevel2025]] — MedXpertQA: benchmark médico de alta dificultad y razonamiento (Zuo et al., 2025)
- [[jabinMSMMemUniversalMedical2019]] — MSM-Mem: memoria médica multimodal estructurada (Jabin et al., 2019)
- [[yaoReActSynergizingReasoning2023]] — ReAct: sinergia de razonamiento y acción en LLMs (Yao et al., 2023)
- [[xuAMEMAgenticMemory2025]] — A-MEM: memoria agéntica estructurada estilo Zettelkasten (Xu et al., 2025)
- [[shaoYourAgentMay2026]] — Misevolution: riesgos emergentes en agentes auto-evolutivos (Shao et al., 2026)
- [[weiEvoMemoryBenchmarkingLLM2026]] — Evo-Memory: benchmark para memoria auto-evolutiva (Wei et al., 2026)
- [[rasmussenZepTemporalKnowledge2025]] — Zep: arquitectura de grafo de conocimiento temporal (Rasmussen et al., 2025)
- [[suzgunDynamicCheatsheetTestTime2025]] — Dynamic Cheatsheet: test-time learning (Suzgun et al., 2025)
- [[heEnablingSelfImprovingAgents2025]] — ARIA: test-time learning con human-in-the-loop (He et al., 2025)
- [[wuAgenticReasoningStreamlined2025]] — Framework con Mind-Map + Web-Search agents (Wu et al., 2025)
- [[gutierrezRAGMemoryNonParametric2025]] — HippoRAG 2: de RAG a memoria bio-inspirada (Gutiérrez et al., 2025)
- [[liMemOSMemoryOS2025]] — MemOS: memoria como recurso de sistema operativo (Li et al., 2025)
- [[chhikaraMem0BuildingProductionReady2025]] — Mem0: memoria escalable para agentes en producción (Chhikara et al., 2025)
- [[behrouzTitansLearningMemorize2024]] — Titans: memoria neural a largo plazo en test-time (Behrouz et al., 2024)
- [[wangMIRIXMultiAgentMemory2025]] — MIRIX: memoria multi-agente modular y multimodal (Wang & Chen, 2025)
- [[yuMemAgentReshapingLongContext2026]] — MemAgent: agente de memoria entrenado con RL (Yu et al., 2026)
- [[zhouMEM1LearningSynergize2025]] — MEM1: RL para sinergia de memoria y razonamiento (Zhou et al., 2025)
- [[zhangMemSkillLearningEvolving2026]] — MemSkill: operaciones de memoria como skills (Zhang et al., 2026)
- [[zhangMemEvolveMetaEvolutionAgent2025]] — MemEvolve: meta-evolución de memoria (Zhang et al., 2025)
- [[yuDAPOOpenSourceLLM2025]] — DAPO: sistema RL a escala para reasoning models (Yu et al., 2025)
- [[wangPlanandSolvePromptingImproving2023]] — Plan-and-Solve zero-shot prompting (Wang et al., 2023)
- [[zhouLeasttoMostPromptingEnables2023]] — Least-to-Most Prompting (Zhou et al., 2023)

## Experimentos Relacionados

> Enlazar experimentos desde `04 - Experimentos/`

## Preguntas de Investigación

- ¿Cómo pueden los agentes LLM razonar de manera más robusta?
- ¿Qué arquitecturas de memoria son más efectivas para agentes?
- ¿Cómo evaluar la capacidad de razonamiento agéntico?
- ¿Cuál es el rol de la reflexión y autocorrección?

### Problemas Abiertos (Wei et al., 2026)

- ¿Cómo personalizar el razonamiento agéntico al usuario individual?
- ¿Cómo asignar crédito a lo largo de tokens, tool calls, skills y memory updates en tareas de largo horizonte?
- ¿Cómo entrenar, actualizar y evaluar world models conjuntamente con agentes en entornos no estacionarios?
- ¿Cómo aprender políticas de colaboración multi-agente adaptativas e interpretables bajo observabilidad parcial?
- ¿Cómo hacer el razonamiento agéntico latente (en espacios internos) efectivo y auditable?
- ¿Cómo gobernar sistemas agénticos que operan autónomamente en entornos reales?

## Recursos

### Datasets y Benchmarks Médicos
- [[MedChain]] — Benchmark clínico interdependiente de 5 etapas (12k casos)
- [[AgentClinic-Benchmark]] — Entorno interactivo de simulación clínica con información incompleta
- [[MedXpertQA]] — Benchmark médico multimodal de nivel subespecialista (4.460 preguntas)
- [[NEJM-CPC]] — Casos clínicos de diagnóstico diferencial de alta complejidad (ensayo AMIE en Nature)
- [[MIMIC-CXR]] — Base de datos masiva de radiografías de tórax e informes (Beth Israel / MIT)
- [[MedQA]] — Exámenes de licenciatura médica (USMLE)
- [[PubMedQA]] — Preguntas de razonamiento basadas en resúmenes biomédicos
- [[MedMCQA]] — Exámenes de acceso a especialidad médica en la India (194k preguntas)
- [[MMLU-Medical]] — Subconjuntos de medicina y biología de MMLU
- [[MedDG]] — Diálogos clínicos reales paciente-médico (gastroenterología)
- [[PathVQA]] — Preguntas y respuestas visuales en anatomía patológica
- [[MedBullets]] — Viñetas clínicas de casos de estudio paso a paso

### Datasets y Benchmarks de Razonamiento Agéntico y Memoria
- [[Evo-Memory-Benchmark]] — Benchmark de secuencias continuas de tareas y memoria auto-evolutiva
- [[LOCOMO]] — Benchmark de memoria conversacional a largo plazo
- [[ALFWorld]] — Toma de decisiones interactiva en entornos embodied de texto
- [[HotpotQA]] — Preguntas y respuestas con razonamiento multi-salto sobre Wikipedia
