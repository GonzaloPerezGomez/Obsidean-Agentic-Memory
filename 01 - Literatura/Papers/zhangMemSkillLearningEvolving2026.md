---
titulo: "MemSkill: Learning and Evolving Memory Skills for Self-Evolving Agents"
autores: "Haozhen Zhang, Quanyu Long, Jianzhu Bao, Tao Feng, Weizhi Zhang, Haodong Yue, Wenya Wang"
año: "2026"
fuente: ""
DOI: "10.48550/arXiv.2602.02474"
citekey: "zhangMemSkillLearningEvolving2026"
zotero: "zotero://select/library/items/E4RNUFTP"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - self-evolving
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-07"
valoracion: ⭐⭐⭐⭐
---

# MemSkill: Learning and Evolving Memory Skills for Self-Evolving Agents

## Metadatos

- **Autores**: Haozhen Zhang, Quanyu Long, Jianzhu Bao, Tao Feng, Weizhi Zhang, Haodong Yue, Wenya Wang
- **Año**: 2026
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2602.02474](https://doi.org/10.48550/arXiv.2602.02474)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/E4RNUFTP)
- **Abstract**: Most LLM agent memory systems rely on static, hand-designed operations. We present MemSkill, which reframes memory operations as learnable and evolvable memory skills.

---

## Resumen

MemSkill reconceptualiza las operaciones de memoria (insertar, actualizar, eliminar, omitir) como **skills aprendibles y evolutivos** en lugar de procedimientos fijos diseñados manualmente. Un **controller** aprende a seleccionar skills relevantes del banco, un **executor** LLM los aplica para producir memorias guiadas, y un **designer** revisa periódicamente casos difíciles para refinar skills existentes y proponer nuevos. Forma un procedimiento de ciclo cerrado que mejora tanto la política de selección como el banco de skills.

---

## Problema / Motivación

La mayoría de sistemas de memoria para agentes LLM dependen de un **conjunto pequeño y estático de operaciones diseñadas manualmente** (insertar, actualizar, eliminar). Estos procedimientos codifican priors humanos rígidos sobre qué almacenar y cómo revisar memoria, haciendo al sistema inflexible ante patrones de interacción diversos e ineficiente en historiales largos. Se necesita un sistema donde las propias operaciones de memoria evolucionen y se adapten.

---

## Metodología

MemSkill se compone de tres componentes en ciclo cerrado:

### Skill Bank (banco de skills de memoria)
- Cada skill define una operación de memoria reutilizable con: (i) descripción corta para selección, (ii) especificación detallada para ejecución
- Inicializado con 4 primitivas básicas: INSERT, UPDATE, DELETE, SKIP
- Se expande progresivamente con skills más sofisticados

### Controller (selector de skills)
- Aprende a seleccionar un subconjunto pequeño de skills relevantes para cada contexto
- Entrenado para optimizar la calidad de las memorias resultantes

### Executor (ejecutor LLM)
- Un LLM que recibe los skills seleccionados y el contexto
- Produce memorias guiadas por los skills (extracción, consolidación, poda)

### Designer (diseñador evolutivo)
- Revisa periódicamente **casos difíciles** donde los skills seleccionados produjeron memorias incorrectas o incompletas
- Evoluciona el banco proponiendo **refinamientos y nuevos skills**
- Cierra el bucle: mejora la política de selección Y el conjunto de skills

---

## Resultados Clave

- Mejora el rendimiento sobre baselines fuertes en **LoCoMo, LongMemEval, HotpotQA y ALFWorld**
- Generaliza bien a través de settings y dominios distintos
- Los análisis muestran cómo los skills evolucionan: de primitivas básicas a operaciones especializadas y contextuales
- Demuestra que las operaciones de memoria no deben ser fijas sino adaptativas

---

## Contribuciones Principales

1. **Reconceptualización**: Las operaciones de memoria como skills aprendibles y evolutivos (no procedimientos fijos)
2. **Arquitectura controller-executor-designer**: Ciclo cerrado que mejora tanto la selección de skills como el banco de skills disponibles
3. **Validación empírica**: Mejoras consistentes y generalizables en 4 benchmarks con análisis de la evolución de skills

---

## Limitaciones

- El designer requiere acceso a ground truth o evaluación fiable para identificar "casos difíciles"
- La evolución del banco de skills depende de la calidad de la retroalimentación del designer
- No se explora la interacción con post-training (RL) para la optimización del controller

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> MemSkill reframes memory operations as learnable and evolvable memory skills, structured and reusable routines for extracting, consolidating, and pruning information from interaction traces. [#ffd400]

---

> [!quote] Resaltado (p. 3)
> MemSkill optimizes agent memory through two intertwined processes: it learns to use a given skill bank (controller + executor), and it improves the skill bank itself (designer that revises skills based on challenging cases). [#ffd400]

---

> [!quote] Resaltado (p. 3)
> We initialize the skill bank with four basic skills: INSERT, UPDATE, DELETE, and SKIP. The designer progressively refines existing skills and expands the bank by proposing new skills that address uncovered failure modes. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> MemSkill learns to select relevant skills for each context span and conditions an LLM executor on them to construct skill-guided memories, forming a closed-loop training procedure. [#ffd400]

---

## Ideas y Conexiones

- MemSkill es un ejemplo paradigmático de **evolución procedimental** del [[Self-Evolving Agentic Reasoning]]: las operaciones de memoria son una "biblioteca de habilidades" que crece y se refina, exactamente como Voyager con skills de acción
- El patrón controller-executor-designer mapea a roles multi-agente del [[Collective Multi-Agent Reasoning]]: Controller = Coordinator, Executor = Worker, Designer = Critic/Evolver
- Contraste con [[MemAgent]] y MEM1 que usan RL end-to-end para aprender qué recordar: MemSkill aprende *cómo* operar la memoria (las operaciones mismas), no solo qué recordar
- Complementario a [[MemEvolve]]: MemSkill evoluciona las *operaciones* de memoria, MemEvolve evoluciona la *arquitectura* completa del sistema de memoria
- La inicialización con INSERT/UPDATE/DELETE/SKIP y posterior evolución recuerda al proceso de emergencia de herramientas en [[Tool Use]]: de primitivas a operaciones especializadas

---

## Notas Relacionadas

- [[Self-Evolving Agentic Reasoning]] — Evolución procedimental de skills de memoria
- [[Agentic Memory]] — Marco conceptual de memoria activa
- [[MemAgent]] — Enfoque RL complementario (aprende qué recordar, no cómo)
- [[zhangMemEvolveMetaEvolutionAgent2025]] — MemEvolve: evoluciona la arquitectura, no las operaciones
- [[Reflexion]] — El designer usa feedback reflexivo para mejorar skills
- [[Tool Use]] — Analogía: operaciones de memoria como herramientas evolutivas
