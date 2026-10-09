---
titulo: "Zep: A Temporal Knowledge Graph Architecture for Agent Memory"
autores: "Preston Rasmussen, Pavlo Paliychuk, Travis Beauvais, Jack Ryan, Daniel Chalef"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2501.13956"
citekey: "rasmussenZepTemporalKnowledge2025"
zotero: "zotero://select/library/items/D98KZLMJ"
tags:
  - paper
  - agentic-reasoning
  - memoria
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-09"
valoracion: ⭐⭐⭐⭐
---

# Zep: A Temporal Knowledge Graph Architecture for Agent Memory

## Metadatos

- **Autores**: Preston Rasmussen, Pavlo Paliychuk, Travis Beauvais, Jack Ryan, Daniel Chalef
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2501.13956](https://doi.org/10.48550/arXiv.2501.13956)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/D98KZLMJ)
- **Abstract**: We introduce Zep, a novel memory layer service for AI agents that outperforms the current state-of-the-art system, MemGPT. Zep addresses limitations of static RAG through its core component Graphiti -- a temporally-aware knowledge graph engine that dynamically synthesizes unstructured conversational data and structured business data while maintaining historical relationships.

---

## Resumen

Zep es un servicio de capa de memoria para agentes de IA que supera a MemGPT utilizando una **arquitectura de grafo de conocimiento temporal**. Su núcleo es *Graphiti*, un motor que sintetiza dinámicamente datos conversacionales no estructurados y de negocio estructurados, manteniendo un registro de la evolución de los hechos en el tiempo. Utiliza una estructura jerárquica de tres niveles (episodios, entidades semánticas y comunidades).

---

## Problema / Motivación

Los sistemas RAG convencionales están limitados a la recuperación estática de documentos. Sin embargo, en aplicaciones empresariales y agentes interactivos de largo recorrido, el conocimiento es dinámico: los hechos cambian con el tiempo, y el contexto evoluciona a lo largo de las conversaciones. Los sistemas previos (como MemGPT) sufren en tareas de razonamiento temporal complejo y síntesis de información a través de múltiples sesiones, mostrando latencia y falta de entendimiento cronológico.

---

## Metodología

La memoria en Zep se modela como un grafo de conocimiento temporal y dinámico $G = (N, E, \phi)$ compuesto por tres subgrafos jerárquicos:

1. **Episode Subgraph ($G_e$)**: Almacén sin pérdida de datos brutos (mensajes, texto, JSON). Mantiene la secuencia temporal estricta de las interacciones.
2. **Semantic Entity Subgraph ($G_s$)**: Nodos de entidades extraídas de los episodios y resoluciones (coreferences). Las aristas representan relaciones semánticas entre entidades. Incorpora marcas de tiempo de validez temporal (cuándo un hecho fue cierto).
3. **Community Subgraph ($G_c$)**: Clusters de entidades fuertemente conectadas que proveen resúmenes de alto nivel.

**Recuperación (Retrieval):**
El proceso de búsqueda $f(q)$ se divide en tres pasos:
1. *Search ($\phi$)*: Identifica subgrafos candidatos relevantes (aristas semánticas, nodos de entidad y comunidades).
2. *Reranker ($\rho$)*: Reordena los resultados según pertinencia.
3. *Constructor ($\chi$)*: Transforma los subgrafos relevantes en texto contextual inyectable en el prompt del LLM, incluyendo la cronología de validez ($t_{valid}$, $t_{invalid}$).

---

## Resultados Clave

- **Supera a MemGPT** en el benchmark Deep Memory Retrieval (DMR): 94.8% vs 93.4%.
- En LongMemEval (razonamiento temporal complejo), logra mejoras de exactitud de hasta un **18.5%**.
- Reduce la latencia de respuesta en un **90%** respecto a baselines.
- Excelente rendimiento en síntesis de información cross-session y mantenimiento de contexto a largo plazo.

---

## Contribuciones Principales

1. **Graphiti**: Un motor de knowledge graph con consciencia temporal que rastrea explícitamente cuándo los hechos pasan a ser ciertos o falsos.
2. **Jerarquía tri-nivel**: Separación limpia entre memoria episódica bruta, abstracción semántica y resúmenes de comunidad.
3. **Pipeline de Recuperación (Search-Rerank-Construct)**: Metodología estructurada para traducir subgrafos de conocimiento dinámico a contexto textual útil para LLMs.

---

## Limitaciones

- La extracción y mantenimiento continuo del grafo (entidades y relaciones) añade overhead computacional en tiempo de escritura.
- Depende de la capacidad del LLM extractor para identificar correctamente entidades y cambios de estado.

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> Zep addresses this fundamental limitation through its core component Graphiti—a temporally-aware knowledge graph engine that dynamically synthesizes both unstructured conversational data and structured business data while maintaining historical relationships. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> This graph comprises three hierarchical tiers of subgraphs: an episode subgraph, a semantic entity subgraph, and a community subgraph. [#ffd400]

---

## Ideas y Conexiones

- Conecta fuertemente con [[HippoRAG]] y [[Mind-Map Agent]] al utilizar grafos de conocimiento como sustrato de memoria, pero Zep añade explícitamente la **dimensión temporal** (algo crítico identificado en la taxonomía de [[Agentic Memory]]).
- Se posiciona como una evolución/alternativa a MemGPT y a [[Mem0]], pero con un enfoque más estructurado (grafos) que puramente vectorial/episódico.
- La jerarquía tri-nivel es un ejemplo perfecto de la evolución desde *Flat Memory* hacia *Structured Memory* descrita en el survey de Wei et al., [[weiSurveyAgenticReasoning2026]].

---

## Notas Relacionadas

- [[Agentic Memory]] — Memoria agéntica estructurada
- [[HippoRAG]] — Enfoque alternativo basado en Knowledge Graphs
- [[weiSurveyAgenticReasoning2026]] — Survey que teoriza sobre la evolución de la memoria
