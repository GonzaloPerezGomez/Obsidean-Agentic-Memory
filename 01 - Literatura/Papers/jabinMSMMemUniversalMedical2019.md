---
titulo: "MSM-Mem: A Universal Medical Structured Multimodal Memory Framework for Medical AI Agents"
autores: "Md Asaduzzaman Jabin, Khoa Le, Lin Zhao, Tianming Liu"
año: "2019"
fuente: ""
DOI: "10.48550/arXiv.1905.02269"
citekey: "jabinMSMMemUniversalMedical2019"
zotero: "zotero://select/library/items/D97CRY7S"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - multimodal
  - clinical
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-20"
valoracion: ⭐⭐⭐⭐
---

# MSM-Mem: A Universal Medical Structured Multimodal Memory Framework for Medical AI Agents

## Metadatos

- **Autores**: Md Asaduzzaman Jabin, Khoa Le, Lin Zhao, Tianming Liu
- **Año**: 2019
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.1905.02269](https://doi.org/10.48550/arXiv.1905.02269)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/D97CRY7S)
- **Abstract**: Clinical decision-making is inherently experience-driven: physicians progressively refine their reasoning by synthesizing patient history, multimodal observations, and prior diagnostic experiences across interactions. In contrast, current multimodal large language model (MLLM)-based medical AI agents largely operate as stateless inference systems, generating decisions independently for each interaction without retaining or internalizing experiential knowledge. This discrepancy limits their ability to progressively improve reasoning reliability through usage and adapt to longitudinal patient contexts in real-world clinical workflows. In this study, we propose Medical Structured Multimodal Memory (MSM-Mem), an agentic memory framework that enables medical AI agents to evolve through accumulated clinical experiences. MSM-Mem organizes heterogeneous clinical experiences into semantic, episodic, and visual memory and incrementally updates them during inference, allowing the agent to retrieve prior experiences to inform current reasoning and progressively refine decision-making over time. Evaluations on MoE-LLaVA backbones demonstrate consistent performance improvements with further gains observed through continued usage. In general, MSM-Mem offers a viable pathway toward medical AI agents capable of evolving their reasoning competence in a manner analogous to the way clinicians learn from practice over time.

---

## Resumen

MSM-Mem es un framework de **memoria agéntica multimodal estructurada** diseñado para agentes médicos de inteligencia artificial. Supera la limitación de los modelos multimodales (MLLM) que operan sin estado (*stateless*), dotándolos de un almacén tripartito de memorias: semántica (resumen diagnóstico longitudinal del paciente), episódica (interacciones pasadas y razonamientos clínicos) y visual (prototipos de observaciones perceptivas/imágenes médicas). El sistema se actualiza incrementalmente durante la inferencia, permitiendo al agente mejorar su competencia diagnóstica con el uso continuado.

---

## Problema / Motivación

En la práctica clínica real, los médicos refinan progresivamente su pericia acumulando experiencia a través de múltiples interacciones: relacionan el historial previo del paciente con hallazgos visuales y recuerdos de casos anteriores.
Por el contrario, los agentes médicos basados en MLLM operan típicamente como **sistemas de inferencia sin estado**:
- Procesan cada encuentro de forma aislada sin retener ni internalizar lecciones experienciales.
- No logran mantener la coherencia en seguimientos longitudinales de pacientes a lo largo del tiempo.
- Pierden la capacidad de comparar visualmente hallazgos actuales (ej. radiografías sucesivas) con patrones patológicos aprendidos.

---

## Metodología

MSM-Mem descompone la evidencia clínica heterogénea en un almacén de memoria estructurado $\mathcal{M} = \{M_S, M_E, M_V\}$ con tres módulos complementarios:

1. **Memoria Semántica ($M_S$)**:
   - Mantiene una abstracción longitudinal específica de cada paciente.
   - Agrega de forma determinista los resultados e impresiones de consultas pasadas para generar un resumen diagnóstico compacto de la evolución del paciente.
2. **Memoria Episódica ($M_E$)**:
   - Modela cómo las interacciones previas entre paciente y clínico fueron interpretadas.
   - Almacena trayectorias de interacción completas (síntomas observados $\rightarrow$ razonamiento intermedio $\rightarrow$ decisión final tomada) para guiar decisiones ante casos análogos.
3. **Memoria Visual ($M_V$)**:
   - Preserva representaciones compactas (embeddings visuales y prototipos) de observaciones perceptivas previas (ej. radiografías de tórax, tomografías).
   - Permite recuperación y comparación a nivel de prototipo visual independiente del texto de la interacción.
4. **Actualización Incremental en Inferencia**:
   - Durante cada consulta clínica, el agente recupera información relevante de $M_S, M_E, M_V$, la integra en el razonamiento actual y, tras emitir el juicio clínico, actualiza los tres módulos de memoria sin re-entrenar los pesos del modelo base.

---

## Resultados Clave

- **Evaluación en MIMIC-CXR curado**: Pruebas con radiografías de tórax emparejadas con informes radiológicos, pies de imagen clínicos y preguntas-respuestas sobre razonamiento diagnóstico.
- **Mejora progresiva en MoE-LLaVA**: Desplegado sobre arquitecturas MoE-LLaVA, MSM-Mem muestra mejoras consistentes en precisión diagnóstica.
- **Efecto de acumulación (*continual usage*)**: A diferencia de los modelos sin memoria, el rendimiento de MSM-Mem sigue aumentando a medida que procesa más consultas, emulando la curva de aprendizaje de un médico en activo.

---

## Contribuciones Principales

1. **Taxonomía de memoria multimodal clínica**: Formalización de tres capas diferenciadas ($M_S, M_E, M_V$) para datos médicos longitudinales y perceptivos.
2. **Evolución sin fine-tuning**: Aprendizaje continuo no paramétrico durante la inferencia para agentes médicos multimodales.
3. **Validación multimodal**: Demostración empírica de retención y comparación visual de patologías en radiología.

---

## Limitaciones

- Centrado primordialmente en estudios de tórax (MIMIC-CXR); se requiere evaluar su escalabilidad a historiales clínicos electrónicos (EHR) multihospitalarios con decenas de modalidades.
- El almacenamiento y recuperación eficiente de memorias visuales a gran escala requiere técnicas de indexación vectorial multimodal optimizadas.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 3)
> MSM-Mem factorizes these complementary evidence types into structured memory components and maintains a structured memory store defined as M = {MS, ME, MV }, where MS is semantic memory, ME is episodic memory, and MV is visual memory. [#ffd400]

---

> [!quote] Resaltado (p. 4)
> Episodic Memory. To simulate this interaction-driven learning mechanism, MSM-Mem represents prior patient–clinician interactions as episodic memory, capturing how observed evidence was previously interpreted and translated into downstream decisions. [#ffd400]

---

> [!quote] Resaltado (p. 4)
> Visual Memory. To preserve the perceptual evidence independently of interaction-level decision context, MSM-Mem maintains a visual memory module that stores compact representations of previously encountered visual observations for prototype-level retrieval and comparison. [#ffd400]

---

> [!quote] Resaltado (p. 4)
> Semantic Memory. Semantic memory maintains a per-patient longitudinal abstraction of prior diagnostic outcomes through deterministic aggregation of recent episodic impressions. [#ffd400]

---

## Ideas y Conexiones

- Se conecta fuertemente con [[MIRIX]] al formalizar una memoria explícitamente multimodal (no sólo textual), abordando una de las carencias típicas de la memoria agéntica.
- Ejemplifica el aprendizaje continuo no paramétrico analizado en [[gutierrezRAGMemoryNonParametric2025]] (HippoRAG 2), pero extendido al dominio multimodal clínico.
- Forma una sinergia perfecta con [[ClinicalAgents]]: mientras ClinicalAgents aporta la orquestación multi-agente y la búsqueda MCTS, MSM-Mem aporta la descomposición de la memoria en semántica, episódica y prototípica visual.

---

## Notas Relacionadas

- [[Agentic Memory]] — Memoria agéntica estructurada
- [[MSM-Mem]] — Nota conceptual del framework
- [[MIRIX]] — Memoria agéntica multimodal
- [[ClinicalAgents]] — Orquestación clínica multi-agente
- [[Self-Evolving Agentic Reasoning]] — Evolución continua de memoria
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
