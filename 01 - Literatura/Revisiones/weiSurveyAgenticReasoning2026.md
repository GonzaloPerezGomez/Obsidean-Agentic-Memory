---
titulo: "A Survey of Agentic Reasoning for Large Language Models: Towards Recursively Self-Improving and Collective Agents"
autores: "Tianxin Wei, Ting-Wei Li, Zhining Liu, Xuying Ning, Ze Yang, Jiaru Zou, Zhichen Zeng, Ruizhong Qiu, Xiao Lin, Dongqi Fu, Zihao Li, Mengting Ai, Duo Zhou, Wenxuan Bao, Yunzhe Li, Gaotang Li, Cheng Qian, Yu Wang, Xiangru Tang, Yin Xiao, Liri Fang, Hui Liu, Xianfeng Tang, Yuji Zhang, Chi Wang, Jiaxuan You, Heng Ji, Hanghang Tong, Jingrui He"
año: "2026"
fuente: ""
DOI: "10.48550/arXiv.2601.12538"
citekey: "weiSurveyAgenticReasoning2026"
zotero: "zotero://select/library/items/IGJNU437"
tags:
  - paper
  - agentic-reasoning
  - survey
estado: "#estado/en-progreso"
fecha_lectura: "2026-09-29"
valoracion: ⭐⭐⭐⭐⭐
---

# A Survey of Agentic Reasoning for Large Language Models: Towards Recursively Self-Improving and Collective Agents

## Metadatos

- **Autores**: Tianxin Wei, Ting-Wei Li, Zhining Liu, Xuying Ning, Ze Yang, Jiaru Zou, Zhichen Zeng, Ruizhong Qiu, Xiao Lin, Dongqi Fu, Zihao Li, Mengting Ai, Duo Zhou, Wenxuan Bao, Yunzhe Li, Gaotang Li, Cheng Qian, Yu Wang, Xiangru Tang, Yin Xiao, Liri Fang, Hui Liu, Xianfeng Tang, Yuji Zhang, Chi Wang, Jiaxuan You, Heng Ji, Hanghang Tong, Jingrui He
- **Año**: 2026
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2601.12538](https://doi.org/10.48550/arXiv.2601.12538)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/IGJNU437)
- **Abstract**: Reasoning is a fundamental cognitive process underlying inference, problem-solving, and decision-making. While large language models (LLMs) demonstrate strong reasoning capabilities in closed-world settings, they struggle in open-ended and dynamic environments. Agentic reasoning marks a paradigm shift by reframing LLMs as autonomous agents that plan, act, and learn through continual interaction. In this survey, we organize agentic reasoning along three complementary dimensions. First, we characterize environmental dynamics through three layers: foundational agentic reasoning, which establishes core single-agent capabilities including planning, tool use, and search in stable environments; self-evolving agentic reasoning, which studies how agents refine these capabilities through feedback, memory, and adaptation; and collective multi-agent reasoning, which extends intelligence to collaborative settings involving coordination, knowledge sharing, and shared goals. Across these layers, we distinguish in-context reasoning, which scales test-time interaction through structured orchestration, from post-training reasoning, which optimizes behaviors via reinforcement learning and supervised fine-tuning. We further review representative agentic reasoning frameworks across real-world applications and benchmarks, including science, robotics, healthcare, autonomous research, and mathematics. This survey synthesizes agentic reasoning methods into a unified roadmap bridging thought and action, and outlines open challenges and future directions, including personalization, long-horizon interaction, world modeling, scalable multi-agent training, and governance for real-world deployment.

---

## Resumen

Este survey proporciona un marco unificado para entender el **agentic reasoning** en LLMs, organizándolo en tres capas progresivas: razonamiento fundacional (planificación, uso de herramientas, búsqueda), razonamiento auto-evolutivo (feedback, memoria, adaptación) y razonamiento colectivo multi-agente (coordinación, roles, co-evolución). Además, distingue entre razonamiento in-context (en tiempo de inferencia) y post-training (mediante RL y SFT).

---

## Problema / Motivación

Los LLMs demuestran fuertes capacidades de razonamiento en entornos cerrados, pero fallan en escenarios abiertos y dinámicos. El **agentic reasoning** propone un cambio de paradigma: en lugar de generar secuencias pasivamente, los LLMs se reconceptualizan como **agentes autónomos** que planifican, actúan y aprenden a través de interacción continua con su entorno. No existía un framework unificado que organizara la creciente literatura en este campo.

---

## Metodología

Se trata de un **survey** que organiza el campo a lo largo de tres dimensiones complementarias:

1. **Dinámica del entorno** — Tres capas progresivas:
   - *Foundational Agentic Reasoning*: capacidades base de un solo agente ([[Planning]], [[Tool Use]], [[Agentic Search]])
   - *Self-Evolving Agentic Reasoning*: mejora continua mediante [[Reflective Feedback]], [[Agentic Memory]], adaptación paramétrica
   - *Collective Multi-Agent Reasoning*: inteligencia distribuida con roles, comunicación y memoria compartida

2. **Tipo de razonamiento** — In-context (orquestación en inferencia) vs. Post-training (RL/SFT)

3. **Aplicaciones** — Ciencia, robótica, salud, investigación autónoma, matemáticas

El entorno se modela formalmente como un **POMDP** con una variable de razonamiento interno para exponer la estructura "think–act".

---

## Resultados Clave

- El razonamiento agéntico fundacional se sustenta en tres pilares: **planificación** (workflow-based, tree-search, formalización), **uso de herramientas** (in-context, post-training, orquestación), y **búsqueda agéntica** (RAG adaptativo)
- La auto-evolución opera sobre tres tipos de estado: **verbal** (reflexiones textuales como Reflexion), **procedimental** (bibliotecas de habilidades como Voyager), y **estructural** (evolución del propio código como AlphaEvolve)
- Los sistemas multi-agente requieren **diferenciación de roles** (Leader, Worker, Critic, Memory Keeper, Communication Facilitator), **colaboración** (pipelines manuales vs. LLM-driven), y **co-evolución** de memorias, topologías y políticas
- La memoria evoluciona de buffers pasivos a **arquitecturas activas**: flat memory (factual, experiencial) → structured memory (grafos semánticos, workflows) → post-training memory control (optimización de lectura/escritura vía RL)
- GRPO se identifica como método dominante para RL en tareas de razonamiento, eliminando la necesidad de red de valor

---

## Contribuciones Principales

1. **Taxonomía en tres capas** del agentic reasoning: foundational → self-evolving → collective multi-agent
2. **Distinción transversal** entre in-context reasoning (test-time compute) y post-training reasoning (RL/SFT) a través de las tres capas
3. **Revisión comprensiva** de frameworks, aplicaciones (ciencia, salud, robótica) y benchmarks, con identificación de 6 problemas abiertos clave

---

## Limitaciones

- Al ser un survey, no introduce métodos nuevos sino que organiza los existentes
- Algunos campos de aplicación (robótica, salud) se cubren con menos profundidad que el razonamiento base
- El rápido avance del campo hace que algunos trabajos recientes puedan no estar incluidos

---

## Conceptos Clave Extraídos

| Concepto | Nota |
|---|---|
| [[Agentic Reasoning]] | Paradigma central del survey |
| [[Foundational Agentic Reasoning]] | Capa 1: planificación, herramientas, búsqueda |
| [[Self-Evolving Agentic Reasoning]] | Capa 2: feedback, memoria, adaptación |
| [[Collective Multi-Agent Reasoning]] | Capa 3: coordinación, roles, co-evolución |
| [[In-Context Reasoning]] | Razonamiento en tiempo de inferencia |
| [[Post-Training Reasoning]] | Internalización vía RL/SFT |
| [[ReAct]] | Framework think-act interleaved |
| [[Reflexion]] | Auto-crítica y refinamiento reflexivo |
| [[Chain of Thought]] | Razonamiento paso a paso |
| [[Tree of Thoughts]] | Búsqueda en árbol de pensamientos |
| [[Agentic Memory]] | Memoria como componente activo del razonamiento |
| [[Agentic Search]] | RAG adaptativo y dinámico |
| [[Tool Use]] | Uso de herramientas externas |
| [[Planning]] | Planificación agéntica |
| [[Multi-Agent Systems]] | Sistemas con múltiples agentes coordinados |
| [[GRPO]] | Group Relative Policy Optimization |
| [[POMDP]] | Formalización del entorno agéntico |
| [[Dec-POMDP]] | Extensión multi-agente del POMDP |
| [[Theory of Mind]] | Modelado de estados mentales entre agentes |

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 2)
> Agentic Reasoning: rather than passively generating sequences, LLMs are reframed as autonomous reasoning agents that plan, act, and learn through continual interaction with their environment. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> ReAct [5] interleave deliberation with environment interaction, tool-use frameworks enable self-directed API calling, and workflow-based agents dynamically orchestrate sub-tasks and verifiable actions [5, 6, 7] [#ff6666]

---

> [!quote] Resaltado (p. 3)
> Foundational Agentic Reasoning establishes the bedrock of core single-agent capabilities, including planning, tool use, and search, that enable operations within stable, albeit complex, environments. Here, agents act by decomposing goals, invoking external tools, and verifying results through executable actions [#ffd400]

---

> [!quote] Resaltado (p. 3)
> Self-Evolving Agentic Reasoning enables agents to improve continually through cumulative experience. Encompassing task-specific self-improvement (e.g., via iterative critique), this paradigm extends adaptation to include persistent updates of internal states like memory and policy. [#ffd400]

---

> [!quote] Resaltado (p. 3)
> Collective Multi-Agent Reasoning scales intelligence from isolated solvers to collaborative ecosystems. Rather than operating in isolation, multiple agents coordinate to achieve shared goals through explicit role assignment (e.g., manager–worker–critic), communication protocols, and shared memory systems [#ffd400]

---

> [!quote] Resaltado (p. 3)
> In-context Reasoning focuses on scaling inference-time compute: through structured orchestration, search-based planning, and adaptive workflow design [#ffd400]

---

> [!quote] Resaltado (p. 3)
> Post-training Reasoning targets capability internalization: it consolidates successful reasoning patterns or tool-use strategies into the model's weights via reinforcement learning and fine-tuning [#ffd400]

---

> [!quote] Resaltado (p. 8)
> We model the environment as a Partially Observable Markov Decision Process (POMDP) and introduce an internal reasoning variable to expose the "think–act" structure of agentic policies [#ffd400]

---

> [!quote] Resaltado (p. 9)
> Group Relative Policy Optimization (GRPO) eliminates the value network by constructing advantages from group-relative rewards [#ffd400]

---

> [!quote] Resaltado (p. 10)
> While foundational agents optimize reasoning z within an episode, self-evolving agents optimize the agent system itself across episodes [#ffd400]

---

> [!quote] Resaltado (p. 10)
> We categorize self-evolution by the nature of S: Verbal Evolution (textual reflections), Procedural Evolution (library of executable tools/skills), and Structural Evolution (agent's source code or architecture itself) [#ffd400]

---

## Ideas y Conexiones

- La taxonomía de tres capas (foundational → self-evolving → collective) recuerda a niveles de organización biológica (célula → organismo → ecosistema)
- La distinción in-context vs. post-training es análoga a System 1 vs. System 2 de Kahneman, pero a nivel de sistema
- El concepto de "Structural Evolution" (agentes que modifican su propio código) conecta con la idea de [[AutoGPT]] y meta-programación
- Interesante la formalización como POMDP — abre la puerta a aplicar toda la teoría clásica de RL
- La memoria agéntica como componente activo (no buffer pasivo) es un cambio fundamental que conecta con teorías de memoria en psicología cognitiva

---

## Notas Relacionadas

- [[MOC - Agentic Reasoning]]
- [[Agentic Reasoning]]
- [[Agentic Memory]]
- [[ReAct]]
- [[Reflexion]]
- [[Planning]]
- [[Multi-Agent Systems]]
