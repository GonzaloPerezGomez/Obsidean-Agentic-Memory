---
titulo: "MedAgents: Large Language Models as Collaborators for Zero-shot Medical Reasoning"
autores: "Xiangru Tang, Anni Zou, Zhuosheng Zhang, Ziming Li, Yilun Zhao, Xingyao Zhang, Arman Cohan, Mark Gerstein"
año: "2024"
fuente: ""
DOI: "10.48550/arXiv.2311.10537"
citekey: "tangMedAgentsLargeLanguage2024"
zotero: "zotero://select/library/items/7GIWIPN2"
tags:
  - paper
  - agentic-reasoning
  - multi-agent
  - clinical
  - evaluation
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-22"
valoracion: ⭐⭐⭐⭐
---

# MedAgents: Large Language Models as Collaborators for Zero-shot Medical Reasoning

## Metadatos

- **Autores**: Xiangru Tang, Anni Zou, Zhuosheng Zhang, Ziming Li, Yilun Zhao, Xingyao Zhang, Arman Cohan, Mark Gerstein
- **Año**: 2024
- **Publicación**: arXiv preprint (Yale University)
- **DOI**: [10.48550/arXiv.2311.10537](https://doi.org/10.48550/arXiv.2311.10537)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/7GIWIPN2)
- **Abstract**: Large language models (LLMs), despite their remarkable progress across various general domains, encounter significant barriers in medicine and healthcare. This field faces unique challenges such as domain-specific terminologies and reasoning over specialized knowledge. To address these issues, we propose MedAgents, a novel multi-disciplinary collaboration framework for the medical domain. MedAgents leverages LLM-based agents in a role-playing setting that participate in a collaborative multi-round discussion, thereby enhancing LLM proficiency and reasoning capabilities. This training-free framework encompasses five critical steps: gathering domain experts, proposing individual analyses, summarising these analyses into a report, iterating over discussions until a consensus is reached, and ultimately making a decision. Our work focuses on the zero-shot setting, which is applicable in real-world scenarios. Experimental results on nine datasets (MedQA, MedMCQA, PubMedQA, and six subtasks from MMLU) establish that our proposed MedAgents framework excels at mining and harnessing the medical expertise within LLMs, as well as extending its reasoning abilities. Our code can be found at https://github.com/gersteinlab/MedAgents.

---

## Resumen

MedAgents es un framework *training-free* (sin re-entrenamiento) de **colaboración multidisciplinar multi-agente** para el razonamiento médico en configuración zero-shot. Simula un comité clínico donde múltiples agentes LLM asumen roles de especialistas médicos pertinentes para un caso determinado. A través de un protocolo estructurado en 5 pasos (reunión de expertos, análisis individual, informe de síntesis, debate multi-ronda iterativo y decisión consensuada), MedAgents extrae y depura el conocimiento latente del LLM, superando a las estrategias tradicionales de prompting CoT y Self-Consistency en 9 benchmarks médicos.

---

## Problema / Motivación

El razonamiento médico exige integrar conocimientos profundos y terminología especializada de múltiples disciplinas (ej. farmacología, patología, anatomía, medicina interna).
Los enfoques monomodelo tradicionales presentan fallos severos:
1. Tienden a alucinar o pasar por alto contraindicaciones sutiles cuando una pregunta abarca varias ramas médicas.
2. Los métodos de prompting unidisciplinares como [[Chain of Thought]] lineal no capturan la naturaleza colegiada del diagnóstico médico (donde las juntas de especialistas debaten casos complejos).
3. Muchos sistemas dependen de bases de conocimiento externas (RAG) que pueden ser costosas de curar o no estar disponibles en tiempo real.

---

## Metodología

### Protocolo de Deliberación en 5 Etapas
MedAgents estructura el razonamiento mediante un pipeline de deliberación colegiada:
1. **Gathering Domain Experts**: A partir de la consulta médica, el sistema determina dinámicamente qué especialidades son necesarias y genera prompts de role-playing para instanciar a dichos expertos.
2. **Proposing Individual Analyses**: Cada especialista analiza el problema de forma independiente desde su perspectiva disciplinar.
3. **Summarizing into a Report**: Un agente sintetizador compila las posturas y argumentos individuales en un informe integrado.
4. **Iterating Discussions for Consensus**: Los agentes participan en una discusión estructurada multi-ronda donde debaten discrepancias, revisan errores de sus pares y refinan sus juicios hasta alcanzar un consenso.
5. **Final Decision**: Se deduce la respuesta final fundada en el consenso alcanzado.

### Configuración Experimental y Evaluación
- **Modo Zero-shot**: Diseñado para no requerir ejemplos manuales previos ni bases de datos de apoyo.
- **9 Datasets evaluados**:
  - *MedQA* (USMLE en inglés)
  - *MedMCQA* (exámenes médicos de la India)
  - *PubMedQA* (razonamiento sobre literatura biomédica)
  - *6 subconjuntos médicos de MMLU* (Anatomía, Conocimiento Clínico, Medicina Universitaria, Genética Médica, Medicina Profesional y Biología Universitaria).
- **Baselines comparativos**:
  - Modelos sin CoT: Zero-shot, Few-shot.
  - Modelos con CoT: Zero-shot CoT ("Let's think step by step"), Few-shot CoT.
  - Modelos con Self-Consistency (SC): Muestreo múltiple y votación mayoritaria.
- **Análisis de errores humano**: Revisión manual y cualitativa de errores cometidos por los agentes para diagnosticar causas de fallo en el consenso.

---

## Resultados Clave

- **Superioridad en 9 benchmarks**: MedAgents supera de forma consistente a las estrategias estándar de Zero-shot CoT y alcanza un rendimiento comparable o superior al Few-shot CoT con ejemplos elaborados manualmente.
- **Eficacia del debate multi-ronda**: La ablación demuestra que la discusión iterativa depura alucinaciones individuales y corrige falsos positivos surgidos en la primera ronda.
- **Extracción de pericia latente**: Demuestra que los LLMs ya contienen conocimiento médico avanzado en sus pesos, pero necesitan estructuras conversacionales colaborativas para activarlo y coordinarlo sin cometer errores de sesgo unidisciplinar.

---

## Contribuciones Principales

1. **Framework MedAgents**: Primera arquitectura de role-playing colegiado multidisciplinar para razonamiento médico zero-shot.
2. **Protocolo en 5 pasos**: Estandarización de reunión, análisis independiente, síntesis, debate de consenso y decisión final.
3. **Evaluación comprehensiva**: Validación cruzada en 9 benchmarks clínicos reconocidos con análisis cualitativo de fallos.

---

## Limitaciones

- Aumento considerable del consumo de tokens y llamadas a la API debido al debate multi-agente en varias rondas.
- Riesgo de "falso consenso" (*groupthink* o conformidad de agentes) si un agente genera una justificación plausible pero clínicamente errónea que convence al resto del panel.
- No evalúa interacción multimodal directa con imágenes (se restringe a texto clínico y QA).

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. )
> This training-free framework encompasses five critical steps: gathering domain experts, proposing individual analyses, summarising these analyses into a report, iterating over discussions until a consensus is reached, and ultimately making a decision. [#ffd400]

---

> [!quote] Resaltado (p. )
> Experimental results on nine datasets (MedQA, MedMCQA, PubMedQA, and six subtasks from MMLU) establish that our proposed MEDAGENTS framework excels at mining and harnessing the medical expertise within LLMs, as well as extending its reasoning abilities. [#ffd400]

---

> [!quote] Resaltado (p. 5)
> Tasks and Datasets. We evaluate our MEDAGENTS framework on three benchmark datasets MedQA, MedMCQA, and PubMedQA, as well as six subtasks most relevant to the medical domain from MMLU datasets including anatomy, clinical knowledge, college medicine, medical genetics, professional medicine, and college biology. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> We present a novel medical QA framework that uses role-playing agents for multi-round discussions, offering greater reliability and clarity without prior training. Our method surpasses zeroshot baselines and matches few-shot baselines across nine datasets. Despite successes, human-based evaluations of errors have highlighted areas for refinement. [#ffd400]

---

## Ideas y Conexiones

- MedAgents es una materialización directa del concepto de **[[Collective Multi-Agent Reasoning]]** aplicado a la deliberación médica (comités clínicos).
- Se diferencia de [[ClinicalAgents]] en que MedAgents enfoca el problema como un **debate por consenso** para responder preguntas médicas (QA / decisiones diagnósticas en texto), mientras que ClinicalAgents usa **búsqueda en árbol MCTS y memoria dual** a lo largo de un flujo interactivo con pruebas y tratamiento.
- Su protocolo de discusión multi-ronda conecta con la literatura de *Multi-Agent Debate* en reasoning general.

---

## Notas Relacionadas

- [[MedAgents]] — Nota conceptual del framework
- [[Collective Multi-Agent Reasoning]] — Capa 3: coordinación multi-agente
- [[ClinicalAgents]] — Orquestación clínica alternativa con MCTS
- [[AgentClinic]] — Entorno interactivo para evaluar agentes como MedAgents
- [[Chain of Thought]] — Estrategia base que MedAgents supera
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
