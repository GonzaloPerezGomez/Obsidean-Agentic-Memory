---
titulo: "MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents"
autores: "Zijian Zhou, Ao Qu, Zhaoxuan Wu, Sunghwan Kim, Alok Prakash, Daniela Rus, Jinhua Zhao, Bryan Kian Hsiang Low, Paul Pu Liang"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2506.15841"
citekey: "zhouMEM1LearningSynergize2025"
zotero: "zotero://select/library/items/J4JJVPC7"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - RL
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-05"
valoracion: ⭐⭐⭐⭐⭐
---

# MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents

## Metadatos

- **Autores**: Zijian Zhou, Ao Qu, Zhaoxuan Wu, Sunghwan Kim, Alok Prakash, Daniela Rus, Jinhua Zhao, Bryan Kian Hsiang Low, Paul Pu Liang
- **Año**: 2025
- **Publicación**: arXiv preprint (MIT / NUS)
- **DOI**: [10.48550/arXiv.2506.15841](https://doi.org/10.48550/arXiv.2506.15841)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/J4JJVPC7)
- **Abstract**: Modern language agents must operate over long-horizon, multi-turn interactions. Yet most LLM systems rely on full-context prompting, leading to unbounded memory growth and degraded reasoning. We introduce MEM1, an end-to-end RL framework that enables agents to operate with constant memory across long multi-turn tasks.

---

## Resumen

MEM1 es un framework de **aprendizaje por refuerzo end-to-end** que entrena a agentes para operar con **memoria constante** en tareas multi-turno de largo horizonte. En cada turno, el agente actualiza un estado interno compacto y compartido que soporta simultáneamente consolidación de memoria y razonamiento, integrando memoria previa con nuevas observaciones y descartando estratégicamente información irrelevante. MEM1-7B mejora el rendimiento 3.5x con 3.7x menos uso de memoria comparado con Qwen2.5-14B-Instruct.

---

## Problema / Motivación

Los agentes modernos deben operar en interacciones multi-turno de largo horizonte, pero la mayoría usa **full-context prompting** (añadir todos los turnos pasados al prompt), lo que causa: crecimiento de memoria ilimitado, costes computacionales crecientes, y **degradación del razonamiento** en longitudes fuera de distribución. Se necesita un sistema donde la memoria crezca de forma constante independientemente del número de turnos.

---

## Metodología

MEM1 unifica memoria y razonamiento en un **estado interno compartido** de tamaño constante:

### Estado interno compartido
- En cada turno, el agente recibe una nueva observación del entorno
- Genera un estado interno actualizado que consolida la memoria previa con la nueva información
- Descarta estratégicamente información redundante o irrelevante
- El mismo estado soporta tanto la consolidación de memoria como el razonamiento para responder

### Entrenamiento con RL end-to-end
- Entrenamiento directo con RL: el agente aprende qué recordar y qué olvidar guiado por la recompensa de la tarea
- Sin necesidad de supervisar explícitamente las operaciones de memoria
- La política de memoria emerge del proceso de optimización

### Construcción de entornos multi-turno
- Método escalable para componer datasets existentes en secuencias de tareas arbitrariamente complejas
- Permite entrenar en settings más realistas y composicionales

---

## Resultados Clave

- MEM1-7B mejora rendimiento **3.5x** con **3.7x menos memoria** vs. Qwen2.5-14B-Instruct en QA multi-hop de 16 objetivos
- Generaliza más allá del horizonte de entrenamiento (out-of-distribution en longitud)
- Rendimiento competitivo en 3 dominios: retrieval QA interno, web QA open-domain, y web shopping multi-turno
- Demuestra que la consolidación de memoria guiada por razonamiento es una alternativa escalable al full-context

---

## Contribuciones Principales

1. **MEM1**: Framework de RL end-to-end donde memoria y razonamiento comparten un estado interno compacto de tamaño constante
2. **Consolidación guiada por razonamiento**: La política de qué recordar/olvidar emerge del RL sin supervisión explícita de memoria
3. **Composición de entornos**: Método escalable para construir entornos multi-turno a partir de datasets existentes

---

## Limitaciones

- Requiere entornos con recompensas bien definidas y verificables (QA, matemáticas, navegación web)
- No evaluado en tareas abiertas con recompensas ambiguas o ruidosas
- El estado interno de tamaño fijo puede ser insuficiente para tareas que requieren retener grandes cantidades de información específica

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We introduce MEM1, an end-to-end reinforcement learning framework that enables agents to operate with constant memory across long multi-turn tasks. At each turn, MEM1 updates a compact shared internal state that jointly supports memory consolidation and reasoning. [#ffd400]

---

> [!quote] Resaltado (p. 10)
> MEM1 addresses the scalability challenges of prompt growth and achieves competitive performance with substantially reduced memory usage and inference latency. A promising future direction is to explore methods for training MEM1 agents in open-ended settings where reward signals are sparse, delayed, or implicit. [#ffd400]

---

## Ideas y Conexiones

- MEM1 es conceptualmente el descendiente directo de [[MemAgent]]: ambos usan RL end-to-end para aprender políticas de memoria, pero MEM1 unifica memoria y razonamiento en un único estado interno mientras MemAgent los trata como módulos separados (lectura + sobrescritura)
- La idea de un **estado compartido** para memoria y razonamiento conecta con la formalización POMDP del survey: el estado interno $z$ del agente es simultáneamente representación de memoria y base para la acción
- El hallazgo de que MEM1-7B supera a Qwen2.5-14B (un modelo 2x mayor) refuerza la tesis del survey: memoria agéntica bien gestionada > más parámetros
- La limitación de requerir recompensas verificables es la misma de [[DAPO]] y [[GRPO]] — un gap compartido por todo el post-training reasoning
- Conecta con [[MemOS]] en que ambos buscan eficiencia de memoria, pero MEM1 lo hace a nivel de política aprendida mientras MemOS lo hace a nivel de infraestructura

---

## Notas Relacionadas

- [[Agentic Memory]] — MEM1 como sinergia memoria-razonamiento
- [[MemAgent]] — Enfoque RL previo para memoria, pero con módulos separados
- [[Post-Training Reasoning]] — Paradigma de entrenamiento de MEM1
- [[DAPO]] — Algoritmo RL relacionado
- [[Self-Evolving Agentic Reasoning]] — Evolución de memoria entre episodios
- [[POMDP]] — Formalización del estado interno compartido
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza
