---
titulo: "MemOS: A Memory OS for AI System"
autores: "Zhiyu Li, Chenyang Xi, Chunyu Li, Ding Chen, Boyu Chen, Shichao Song, Simin Niu, Hanyu Wang, Jiawei Yang, Chen Tang, Qingchen Yu, Jihao Zhao, Yezhaohui Wang, Peng Liu, Zehao Lin, Pengyuan Wang, Jiahao Huo, Tianyi Chen, Kai Chen, Kehang Li, Zhen Tao, Huayi Lai, Hao Wu, Bo Tang, Zhengren Wang, Zhaoxin Fan, Ningyu Zhang, Linfeng Zhang, Junchi Yan, Mingchuan Yang, Tong Xu, Wei Xu, Huajun Chen, Haofen Wang, Hongkang Yang, Wentao Zhang, Zhi-Qin John Xu, Siheng Chen, Feiyu Xiong"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2507.03724"
citekey: "liMemOSMemoryOS2025"
zotero: "zotero://select/library/items/SHF8DQDT"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - sistemas
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-01"
valoracion: ⭐⭐⭐⭐⭐
---

# MemOS: A Memory OS for AI System

## Metadatos

- **Autores**: Zhiyu Li et al. (39 autores)
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2507.03724](https://doi.org/10.48550/arXiv.2507.03724)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/SHF8DQDT)
- **Abstract**: Large Language Models (LLMs) have become an essential infrastructure for AGI, yet their lack of well-defined memory management systems hinders the development of long-context reasoning, continual personalization, and knowledge consistency. We propose MemOS, a memory operating system that treats memory as a manageable system resource. It unifies the representation, scheduling, and evolution of plaintext, activation-based, and parameter-level memories, enabling cost-efficient storage and retrieval.

---

## Resumen

MemOS propone una **analogía radical**: tratar la memoria de los LLMs como un **recurso gestionable de sistema operativo**, de forma análoga a como un OS gestiona la memoria RAM/disco. Unifica tres tipos heterogéneos de memoria (plaintext, activaciones, parámetros) bajo una abstracción común llamada **MemCube**, con módulos de scheduling, lifecycle management, almacenamiento estructurado y augmentación transparente. Establece la infraestructura fundacional para aprendizaje continuo y modelado personalizado en LLMs.

---

## Problema / Motivación

Los LLMs carecen de **sistemas de gestión de memoria bien definidos**. Dependen de parámetros estáticos y estados contextuales efímeros, lo que impide: razonamiento de contexto largo, personalización continua y consistencia de conocimiento. RAG es un parche sin estado que carece de control de ciclo de vida e integración con representaciones persistentes. Investigación reciente muestra que introducir una **capa de memoria explícita** entre la memoria paramétrica y la recuperación externa reduce sustancialmente los costes de entrenamiento e inferencia. Pero el problema fundamental es que la información está distribuida sobre múltiples escalas temporales y fuentes, requiriendo gestión de conocimiento heterogéneo.

---

## Metodología

**MemOS** trata la memoria como recurso de sistema con los siguientes componentes:

### MemCube (unidad básica de memoria)
- Encapsula **contenido de memoria + metadatos** (procedencia, versionado, tipo)
- Soporta tres tipos de memoria:
  - **Plaintext memory**: Texto explícito (hechos, reglas, contexto)
  - **Activation memory**: Estados de activación intermedios (KV cache, hidden states)
  - **Parameter memory**: Pesos del modelo (LoRA adapters, pesos fine-tuneados)
- Los MemCubes se pueden **componer, migrar y fusionar** entre tipos de memoria

### Módulos del sistema
- **Memory Scheduling**: Decide qué memorias cargar/descargar según relevancia y coste
- **Lifecycle Management**: Control del ciclo de vida (creación, actualización, archivado, eliminación)
- **Structured Storage**: Almacenamiento eficiente con índices y búsqueda
- **Transparent Augmentation**: Integración transparente de memorias en el pipeline de inferencia

Esto permite **transiciones flexibles entre tipos de memoria**: por ejemplo, conocimiento textual puede "compilarse" en parámetros, o activaciones frecuentes pueden externalizarse como texto.

---

## Resultados Clave

- Establece un **marco teórico unificado** para los tres tipos de memoria en LLMs (plaintext, activaciones, parámetros)
- La abstracción MemCube permite **interoperabilidad** entre representaciones de memoria que antes estaban aisladas
- Las transiciones entre tipos de memoria (text ↔ activation ↔ parameter) abren nuevas posibilidades: compilar conocimiento textual en pesos, externalizar pesos como texto consultable
- Framework de gestión con scheduling, lifecycle y storage proporciona controlabilidad, plasticidad y evolucionabilidad

---

## Contribuciones Principales

1. **MemOS**: Primer sistema operativo de memoria para LLMs que trata la memoria como recurso gestionable, unificando plaintext, activaciones y parámetros
2. **MemCube**: Unidad estandarizada de memoria con contenido + metadatos (procedencia, versionado) que permite composición, migración y fusión entre tipos
3. **Marco de gestión**: Módulos de scheduling, lifecycle management, almacenamiento estructurado y augmentación transparente para memoria de LLMs

---

## Limitaciones

- Paper primariamente conceptual/arquitectónico — los resultados empíricos son limitados comparados con la ambición del framework
- La transición entre tipos de memoria (ej. text → parameter) es computacionalmente costosa y su eficacia depende del dominio
- La complejidad del sistema puede dificultar adopción práctica comparado con soluciones más simples como Mem0 o RAG

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> LLMs have become an essential infrastructure for AGI, yet their lack of well-defined memory management systems hinders the development of long-context reasoning, continual personalization, and knowledge consistency. RAG introduces external knowledge in plain text but remains a stateless workaround without lifecycle control. [#ffd400]

---

> [!quote] Resaltado
> We propose MemOS, a memory operating system that treats memory as a manageable system resource. It unifies the representation, scheduling, and evolution of plaintext, activation-based, and parameter-level memories. [#ffd400]

---

> [!quote] Resaltado (p. 31)
> MemOS provides a unified abstraction and integrated management framework for heterogeneous memory types. We propose a standardized memory unit, MemCube, and implement key modules for scheduling, lifecycle management, structured storage, and transparent augmentation. [#ffd400]

---

## Ideas y Conexiones

- MemOS aborda frontalmente el problema que el survey de Wei et al. identifica como gap: **post-training memory control** — pero lo hace a nivel de infraestructura de sistema, no de política de agente
- La distinción plaintext/activation/parameter memory es una formalización más rigurosa de la jerarquía de memoria que [[Agentic Memory]] describe informalmente
- El concepto de MemCube (contenido + metadatos con procedencia y versionado) es poderoso para **multi-agent memory management**: cada agente podría tener sus propios MemCubes con procedencia rastreable, abordando el problema de [[Collective Multi-Agent Reasoning]]
- La idea de transiciones entre tipos de memoria (text → parameter) conecta con la distinción [[In-Context Reasoning]] vs [[Post-Training Reasoning]]: ¿se puede "compilar" memoria textual en pesos cuando se vuelve suficientemente estable?
- Comparar con [[chhikaraMem0BuildingProductionReady2025]]: Mem0 es práctico y production-ready; MemOS es ambicioso y fundacional. Son complementarios: Mem0 podría ser un módulo de plaintext memory dentro de MemOS

---

## Notas Relacionadas

- [[Agentic Memory]] — Concepto general que MemOS formaliza como infraestructura
- [[Self-Evolving Agentic Reasoning]] — Evolución de memoria como recurso
- [[Collective Multi-Agent Reasoning]] — Gestión de memoria multi-agente
- [[In-Context Reasoning]] — Plaintext/activation memory como in-context
- [[Post-Training Reasoning]] — Parameter memory como post-training
- [[chhikaraMem0BuildingProductionReady2025]] — Mem0, enfoque práctico complementario
- [[gutierrezRAGMemoryNonParametric2025]] — HippoRAG 2, enfoque bio-inspirado
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica gaps en memory management
- [[MemOS]] — Nota de concepto
