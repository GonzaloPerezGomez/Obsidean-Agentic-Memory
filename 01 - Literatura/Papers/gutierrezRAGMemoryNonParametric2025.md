---
titulo: "From RAG to Memory: Non-Parametric Continual Learning for Large Language Models"
autores: "Bernal Jiménez Gutiérrez, Yiheng Shu, Weijian Qi, Sizhe Zhou, Yu Su"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2502.14802"
citekey: "gutierrezRAGMemoryNonParametric2025"
zotero: "zotero://select/library/items/D66CE5AW"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - RAG
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-01"
valoracion: ⭐⭐⭐⭐⭐
---

# From RAG to Memory: Non-Parametric Continual Learning for Large Language Models

## Metadatos

- **Autores**: Bernal Jiménez Gutiérrez, Yiheng Shu, Weijian Qi, Sizhe Zhou, Yu Su
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2502.14802](https://doi.org/10.48550/arXiv.2502.14802)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/D66CE5AW)
- **Abstract**: Our ability to continuously acquire, organize, and leverage knowledge is a key feature of human intelligence that AI systems must approximate to unlock their full potential. Given the challenges in continual learning with large language models (LLMs), retrieval-augmented generation (RAG) has become the dominant way to introduce new information. However, its reliance on vector retrieval hinders its ability to mimic the dynamic and interconnected nature of human long-term memory. We propose HippoRAG 2, a framework that outperforms standard RAG comprehensively on factual, sense-making, and associative memory tasks.

---

## Resumen

HippoRAG 2 es un framework de **aprendizaje continuo no paramétrico** inspirado en la neurobiología de la memoria humana. Supera las limitaciones del RAG estándar (que solo hace recuperación vectorial sin consolidación) integrando un knowledge graph con Personalized PageRank, integración profunda de pasajes y uso online de LLMs. Logra mejoras del 7% en tareas de memoria asociativa sobre el SOTA, manteniendo superioridad en memoria factual y sense-making.

---

## Problema / Motivación

RAG se ha convertido en la forma dominante de introducir información nueva en LLMs, pero su dependencia de la **recuperación vectorial pura** limita su capacidad para imitar la naturaleza **dinámica e interconectada** de la memoria humana a largo plazo. Los enfoques recientes que añaden knowledge graphs a RAG mejoran la capacidad de "sense-making" y asociación, pero **deterioran el rendimiento en tareas factuales básicas** — un trade-off indeseable. Se necesita un sistema que sea superior en los tres tipos de memoria: factual, sense-making y asociativa.

---

## Metodología

**HippoRAG 2** se inspira en la neurobiología de la memoria humana con tres componentes análogos:

1. **Neocortex artificial (LLM)**: Procesa y genera conocimiento
2. **Hipocampo artificial (KG + Personalized PageRank)**: Refleja las cualidades auto-asociativas del hipocampo
   - Construye un knowledge graph a partir de los documentos
   - Usa Personalized PageRank para propagación de activación sobre el grafo, encontrando conexiones no-obvias
3. **Región parahipocampal (retrieval encoder)**: Enlaza neocortex e hipocampo

Mejoras sobre HippoRAG 1:
- **Integración profunda de pasajes**: Los pasajes se integran más directamente en el grafo
- **Uso online de LLM**: El LLM refina queries y evalúa relevancia en tiempo de recuperación
- Esto evita el deterioro factual que otros métodos KG-augmented sufren

---

## Resultados Clave

- **7% de mejora en memoria asociativa** sobre el mejor modelo de embeddings SOTA
- **Superioridad comprehensiva** en los tres tipos de memoria (factual, sense-making, asociativa) — ningún baseline previo lograba esto
- Mejora la capacidad de establecer conexiones no-obvias entre información dispersa (asociación)
- Abre la vía hacia el **aprendizaje continuo no paramétrico**: adquisición, organización y uso de conocimiento sin modificar pesos

---

## Contribuciones Principales

1. **HippoRAG 2**: Framework neurobiológicamente inspirado que unifica recuperación factual, sense-making y asociativa sin trade-offs
2. **Solución al deterioro factual**: Demuestra que integración profunda de pasajes + uso online de LLM resuelve el problema de KG-augmented RAG
3. **Visión de RAG como memoria**: Reenmarca RAG no como herramienta de recuperación sino como sistema de **aprendizaje continuo no paramétrico** análogo a la memoria a largo plazo humana

---

## Limitaciones

- El uso online del LLM durante recuperación introduce latencia adicional comparado con RAG vectorial puro
- La construcción del knowledge graph requiere procesamiento previo que escala con el tamaño del corpus
- La analogía neurobiológica, aunque inspiradora, no está validada como modelo cognitivo real

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> Our ability to continuously acquire, organize, and leverage knowledge is a key feature of human intelligence that AI systems must approximate to unlock their full potential. RAG has become the dominant way to introduce new information. However, its reliance on vector retrieval hinders its ability to mimic the dynamic and interconnected nature of human long-term memory. [#ffd400]

---

> [!quote] Resaltado (p. 3)
> HippoRAG is a neurobiologically inspired long-term memory framework for LLMs in which each component is inspired by its neurobiological analog for human memory: 1) an LLM as artificial neocortex, 2) a KG and Personalized PageRank to mirror the hippocampus, and 3) a retrieval encoder reflecting parahippocampal regions. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> HippoRAG 2 opens new avenues for research in continual learning and long-term memory for LLMs by achieving comprehensive improvements over standard RAG methods across factual, sense-making, and associative memory tasks. [#ffd400]

---

## Ideas y Conexiones

- HippoRAG 2 materializa exactamente la transición de RAG estático a [[Agentic Search]] dinámico que el survey de Wei et al. describe: estructura + recuperación adaptativa
- La analogía neocortex/hipocampo/parahipocampo es un marco teórico poderoso para entender la [[Agentic Memory]] — sugiere que los sistemas de memoria agéntica necesitan componentes diferenciados para almacenamiento, asociación y interfaz
- La visión de "RAG como memoria" (no como herramienta) conecta directamente con el cambio de paradigma del survey: memoria como componente activo vs. buffer pasivo
- El Personalized PageRank como mecanismo de asociación podría integrarse en el [[Mind-Map Agent]] para mejorar la búsqueda multi-hop
- Contraste interesante con [[chhikaraMem0BuildingProductionReady2025]]: Mem0 se centra en memoria conversacional (extracción/consolidación de hechos), mientras HippoRAG 2 se centra en memoria de conocimiento (organización/asociación de documentos)

---

## Notas Relacionadas

- [[Agentic Memory]] — Marco conceptual de memoria agéntica
- [[Agentic Search]] — RAG dinámico como búsqueda agéntica
- [[Mind-Map Agent]] — Otro enfoque de memoria con grafo de conocimiento
- [[Self-Evolving Agentic Reasoning]] — Evolución de memoria entre episodios
- [[chhikaraMem0BuildingProductionReady2025]] — Mem0, enfoque complementario de memoria conversacional
- [[liMemOSMemoryOS2025]] — MemOS, memoria como recurso de sistema operativo
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza el campo
- [[HippoRAG]] — Nota de concepto
