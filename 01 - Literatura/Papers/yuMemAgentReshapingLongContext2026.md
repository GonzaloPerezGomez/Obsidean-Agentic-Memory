---
titulo: "MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent"
autores: "Hongli Yu, Tinghong Chen, Jiangtao Feng, Jiangjie Chen, Weinan Dai, Qiying Yu, Ya-Qin Zhang, Wei-Ying Ma, Jingjing Liu, Mingxuan Wang, Hao Zhou"
año: "2026"
fuente: ""
DOI: "10.48550/arXiv.2507.02259"
citekey: "yuMemAgentReshapingLongContext2026"
zotero: "zotero://select/library/items/FIUDRRK6"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - RL
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-05"
valoracion: ⭐⭐⭐⭐⭐
---

# MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent

## Metadatos

- **Autores**: Hongli Yu, Tinghong Chen, Jiangtao Feng, Jiangjie Chen, Weinan Dai, Qiying Yu, Ya-Qin Zhang, Wei-Ying Ma, Jingjing Liu, Mingxuan Wang, Hao Zhou
- **Año**: 2026
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2507.02259](https://doi.org/10.48550/arXiv.2507.02259)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/FIUDRRK6)
- **Abstract**: Despite improvements by length extrapolation, efficient attention and memory modules, handling infinitely long documents with linear complexity without performance degradation during extrapolation remains the ultimate challenge in long-text processing. We introduce MemAgent, which reads text in segments and updates the memory using an overwrite strategy. We extend the DAPO algorithm to facilitate training via independent-context multi-conversation generation. MemAgent extrapolates from 8K context trained on 32K text to a 3.5M QA task with performance loss <5%.

---

## Resumen

MemAgent es un **agente de memoria entrenado con RL** que permite a LLMs con contexto corto (8K) procesar documentos de hasta **3.5 millones de tokens** con <5% de pérdida de rendimiento. El agente lee el texto en segmentos, decide qué información es relevante, y actualiza una memoria compacta usando una estrategia de sobrescritura. El entrenamiento se realiza end-to-end mediante una extensión del algoritmo DAPO con generación multi-conversación de contexto independiente.

---

## Problema / Motivación

Manejar documentos infinitamente largos con **complejidad lineal** y sin degradación de rendimiento durante la extrapolación sigue siendo el desafío último del procesamiento de texto largo. Las soluciones existentes — extrapolación de longitud, atención eficiente, módulos de memoria — mejoran pero no resuelven el problema fundamental. Se necesita un sistema que pueda escalar a contextos de millones de tokens manteniendo rendimiento fiable, idealmente entrenado de forma end-to-end.

---

## Metodología

MemAgent introduce un **workflow agéntico** para procesar texto largo:

### Procesamiento por segmentos
- El texto se divide en segmentos de tamaño fijo (ej. 8K tokens)
- El agente lee cada segmento secuencialmente
- Tras leer cada segmento, el agente **decide qué información retener, actualizar o descartar**

### Estrategia de sobrescritura de memoria
- La memoria tiene una capacidad fija (ej. 8K tokens)
- Cuando se lee un nuevo segmento, el agente sobreescribe selectivamente partes de la memoria con información más relevante
- Esto mantiene la complejidad lineal independientemente de la longitud total del documento

### Entrenamiento con RL (DAPO extendido)
- Se extiende el algoritmo **DAPO** (una variante de RL para LLMs) para optimizar directamente la capacidad de memoria
- Entrenamiento end-to-end: el modelo aprende qué recordar y qué olvidar guiado por la recompensa de la tarea final
- **Multi-conversation generation**: generación de múltiples conversaciones con contextos independientes para estabilizar el entrenamiento

---

## Resultados Clave

- Entrenado en secuencias de 60K, extrapola el contexto efectivo a **3.5M tokens** con ventana de solo 8K — una relación de extrapolación de 437x
- **<5% de pérdida de rendimiento** al extrapolar de 8K a 3.5M en tareas QA
- **95%+ en el test RULER de 512K** tokens (needle-in-haystack)
- SOTA en múltiples tareas de contexto largo
- Los estudios de ablación revelan que el **entrenamiento con RL es crítico** — sin él, la memoria es significativamente menos efectiva

---

## Contribuciones Principales

1. **MemAgent**: Workflow agéntico que procesa texto en segmentos con memoria de sobrescritura, logrando complejidad lineal para contextos de millones de tokens
2. **Entrenamiento end-to-end con RL**: Extensión de DAPO para optimizar directamente la gestión de memoria, demostrando que RL es superior a SFT para aprender qué recordar
3. **Extrapolación extrema**: De 8K a 3.5M tokens (437x) con <5% de pérdida, estableciendo un nuevo estándar en escalabilidad de contexto

---

## Limitaciones

- El procesamiento secuencial de segmentos introduce latencia lineal con la longitud del documento
- La estrategia de sobrescritura puede perder información crítica en documentos con dependencias no lineales (ej. referencias cruzadas lejanas)
- No se evalúa en tareas de razonamiento multi-paso o agéntico complejo — solo en QA y needle-in-haystack

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> Despite improvements by length extrapolation, efficient attention and memory modules, handling infinitely long documents without performance degradation during extrapolation remains the ultimate challenge in long-text processing. To solve this problem, we introduce MEMAGENT, which processes text in segments and updates memory through an overwrite strategy. [#ffd400]

---

> [!quote] Resaltado (p. 10)
> When trained on 60K-length sequences, MEMAGENT exhibits remarkable extrapolation, extending its effective context to 3.5M tokens with only 8K context. Our ablation studies reveal the critical role of RL-based training in achieving these results. [#ffd400]

---

## Ideas y Conexiones

- MemAgent materializa exactamente el concepto de **post-training memory control** del survey de Wei et al. — un agente que aprende vía RL a optimizar sus operaciones de lectura/escritura de memoria
- La estrategia de sobrescritura es una política de **memory management** aprendida, conectando con lo que [[MemOS]] formaliza como lifecycle management (creación, actualización, archivado, eliminación)
- El hallazgo de que **RL es crítico** para la gestión de memoria valida la distinción [[In-Context Reasoning]] vs [[Post-Training Reasoning]]: la gestión de memoria efectiva no emerge solo de in-context learning, necesita optimización explícita
- Contraste con [[Titans (Arquitectura)]]: Titans resuelve el contexto largo a nivel de arquitectura interna (módulo neural), MemAgent lo resuelve a nivel de workflow agéntico (agente externo). Ambos logran extrapolación masiva pero por caminos complementarios
- La extrapolación 437x (8K→3.5M) sugiere que la gestión agéntica de memoria podría ser más escalable que simplemente ampliar la ventana de contexto

---

## Notas Relacionadas

- [[Agentic Memory]] — MemAgent como implementación de control de memoria post-training
- [[Post-Training Reasoning]] — RL como mecanismo de optimización de memoria
- [[GRPO]] — DAPO como método RL relacionado
- [[MemOS]] — Enfoque complementario de gestión de memoria como sistema operativo
- [[Titans (Arquitectura)]] — Enfoque alternativo de contexto largo a nivel arquitectónico
- [[Self-Evolving Agentic Reasoning]] — Aprendizaje de políticas de memoria entre episodios
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica post-training memory control como gap
- [[wangMIRIXMultiAgentMemory2025]] — MIRIX, sistema multi-agente de memoria estructurada
