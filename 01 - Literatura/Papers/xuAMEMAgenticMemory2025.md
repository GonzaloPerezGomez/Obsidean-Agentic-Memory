---
titulo: "A-MEM: Agentic Memory for LLM Agents"
autores: "Wujiang Xu, Zujie Liang, Kai Mei, Hang Gao, Juntao Tan, Yongfeng Zhang"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2502.12110"
citekey: "xuAMEMAgenticMemory2025"
zotero: "zotero://select/library/items/IP3XBLPB"
tags:
  - paper
  - agentic-reasoning
  - memoria
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-14"
valoracion: ⭐⭐⭐⭐⭐
---

# A-MEM: Agentic Memory for LLM Agents

## Metadatos

- **Autores**: Wujiang Xu, Zujie Liang, Kai Mei, Hang Gao, Juntao Tan, Yongfeng Zhang
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2502.12110](https://doi.org/10.48550/arXiv.2502.12110)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/IP3XBLPB)
- **Abstract**: While large language model (LLM) agents can effectively use external tools for complex real-world tasks, they require memory systems to leverage historical experiences. Current memory systems enable basic storage and retrieval but lack sophisticated memory organization, despite recent attempts to incorporate graph databases. Moreover, these systems' fixed operations and structures limit their adaptability across diverse tasks. To address this limitation, this paper proposes a novel agentic memory system for LLM agents that can dynamically organize memories in an agentic way. Following the basic principles of the Zettelkasten method, we designed our memory system to create interconnected knowledge networks through dynamic indexing and linking. When a new memory is added, we generate a comprehensive note containing multiple structured attributes, including contextual descriptions, keywords, and tags. The system then analyzes historical memories to identify relevant connections, establishing links where meaningful similarities exist. Additionally, this process enables memory evolution - as new memories are integrated, they can trigger updates to the contextual representations and attributes of existing historical memories, allowing the memory network to continuously refine its understanding. Our approach combines the structured organization principles of Zettelkasten with the flexibility of agent-driven decision making, allowing for more adaptive and context-aware memory management. Empirical experiments on six foundation models show superior improvement against existing SOTA baselines. The source code for evaluating performance is available at https://github.com/WujiangXu/A-mem, while the source code of the agentic memory system is available at https://github.com/WujiangXu/A-mem-sys.

---

## Resumen

A-MEM es un sistema de **memoria agéntica estructurada y evolutiva** inspirado en los principios del método **Zettelkasten**. En lugar de almacenar fragmentos de texto pasivos o depender de grafos estáticos predefinidos, A-MEM genera notas estructuradas ricas en metadatos (descripción contextual, palabras clave, etiquetas) y establece enlaces bidireccionales dinámicos entre ellas. Crucialmente, la llegada de nuevas memorias desencadena un proceso de **evolución y actualización retroactiva** de las notas históricas asociadas, permitiendo que la red de conocimiento del agente se refine y abstraiga patrones de orden superior de forma continua.

---

## Problema / Motivación

Los sistemas de memoria para agentes actuales adolecen de dos limitaciones centrales:
1. **Falta de organización sofisticada**: Suelen limitarse a buffers planos o almacenes vectoriales de recuperación básica (*flat memory*), sin capturar relaciones semánticas profundas o asociaciones conceptuales complejas.
2. **Estructuras y operaciones rígidas**: Los intentos recientes basados en bases de datos de grafos imponen esquemas o tripletas fijas que restringen la adaptabilidad del agente frente a tareas abiertas y variadas.
3. **Ausencia de evolución retrospectiva**: Cuando entra información nueva en un sistema tradicional, las memorias antiguas permanecen inalteradas, impidiendo que el agente actualice su comprensión o descubra conexiones a posteriori con el paso del tiempo.

---

## Metodología

Inspirado en la metodología **Zettelkasten** de gestión de conocimiento personal, A-MEM estructura su arquitectura en torno a tres operaciones agénticas fundamentales:

1. **Creación de Notas de Memoria Estructuradas**:
   - Cada nueva experiencia o interacción se transforma en una nota estructurada que contiene: contenido en bruto, descripción contextual sintetizada, conjunto de palabras clave y etiquetas temáticas.
2. **Indexación y Enlazado Dinámico (Dynamic Linking)**:
   - Utilizando representaciones densas vectoriales y razonamiento agéntico, el sistema identifica notas históricas semánticamente próximas (conjunto $M_{near}$) y genera conexiones explícitas basadas en relaciones lógicas o temáticas, tejiendo una red interconectada.
3. **Evolución Retrospectiva de la Memoria (Memory Evolution)**:
   - Al incorporar la nueva nota, el agente examina las notas vecinas $m_j \in M_{near}$ y evalúa si su contexto, palabras clave o etiquetas deben actualizarse a la luz del nuevo conocimiento ($m_j \rightarrow m_j^*$). Esto permite refinar comprensiones pasadas y abstraer conceptos de orden superior.
4. **Recuperación Sensible al Contexto (Context-Aware Retrieval)**:
   - Durante la inferencia, la consulta actual se proyecta al espacio vectorial y se recuperan los $k$ nodos y subredes más relevantes para construir el prompt enriquecido.

---

## Resultados Clave

- **Evaluación sobre 6 modelos fundacionales**: A-MEM supera de forma consistente a baselines del estado del arte (incluyendo RAG estándar, memoria conversacional plana y sistemas basados en grafos) en tareas conversacionales de largo horizonte.
- **Formación de estructuras de conocimiento superiores**: Los análisis de visualización de grafos confirman que A-MEM genera clusters temáticos modulares y coherentes, facilitando la navegación de conocimiento multi-hop.
- **Robustez y adaptación**: Demuestra capacidad para refinar su representación interna sin intervención humana a medida que se acumulan más episodios interactivos.

---

## Contribuciones Principales

1. **Arquitectura Zettelkasten para Agentes**: Primera adaptación formal de los principios de notas interconectadas (slip-box) a la memoria de agentes LLM.
2. **Mecanismo de Evolución Retrospectiva**: Innovación clave donde la memoria no es de sólo adición, sino que las experiencias nuevas reescriben y enriquecen la semántica de experiencias pasadas.
3. **Código y Sistema Abierto**: Liberación tanto del framework de evaluación (`A-mem`) como del motor del sistema de memoria (`A-mem-sys`).

---

## Limitaciones

- Requiere múltiples llamadas al LLM (para estructurar la nota, evaluar enlaces y evolucionar vecinos), lo que introduce sobrecoste de latencia y tokens durante la fase de escritura.
- Requiere estrategias de poda o consolidación jerárquica cuando la cantidad de notas crece a gran escala para evitar degradación en la búsqueda de vecinos cercanos.

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 4)
> After creating links for the new memory, A-MEM evolves the retrieved memories based on their textual information and relationships with the new memory. For each memory mj in the nearest neighbor set Mn near, the system determines whether to update its context, keywords, and tags [#ffd400]

---

> [!quote] Resaltado (p. 5)
> The evolved memory m∗ j then replaces the original memory mj in the memory set M. This evolutionary approach enables continuous updates and new connections, mimicking human learning processes. As the system processes more memories over time, it develops increasingly sophisticated knowledge structures, discovering higher-order patterns and concepts across multiple memories. This creates a foundation for autonomous memory learning where knowledge organization becomes progressively richer through the ongoing interaction between new experiences and existing memories. [#ffd400]

---

> [!quote] Resaltado (p. 5)
> In each interaction, our A-MEM performs context-aware memory retrieval to provide the agent with relevant historical information. Given a query text q from the current interaction, we first compute its dense vector representation using the same text encoder used for memory notes [#ffd400]

---

> [!quote] Resaltado (p. 9)
> In this work, we introduced A-MEM, a novel agentic memory system that enables LLM agents to dynamically organize and evolve their memories without relying on predefined structures. Drawing inspiration from the Zettelkasten method, our system creates an interconnected knowledge network through dynamic indexing and linking mechanisms that adapt to diverse real-world tasks. [#ffd400]

---

## Ideas y Conexiones

- ¡Conexión natural con **Obsidian** y el método Zettelkasten! El propio repositorio de investigación en el que estamos trabajando opera bajo los mismos principios que A-MEM propone para los agentes (notas atómicas, enlaces bidireccionales, etiquetas y evolución continua).
- En el marco del survey de Wei et al. ([[weiSurveyAgenticReasoning2026]]), A-MEM se sitúa perfectamente en la intersección de **Structured Memory** (capa de grafos y enlaces) y **[[Self-Evolving Agentic Reasoning]]** (evolución del estado interno del agente a través de episodios).
- Complementa a [[Zep]] y [[HippoRAG]], pero mientras Zep prioriza marcas temporales de validez y HippoRAG recurre a PageRank biomimético, A-MEM confía en el razonamiento agéntico para enriquecer retroactivamente las notas pasadas.

---

## Notas Relacionadas

- [[Agentic Memory]] — Memoria agéntica estructurada
- [[A-MEM]] — Nota conceptual de A-MEM
- [[Self-Evolving Agentic Reasoning]] — Capa de auto-evolución
- [[Zep]] — Enfoque alternativo con grafos temporales
- [[HippoRAG]] — Memoria estructurada con knowledge graphs
- [[Mem0]] — Memoria escalable con extracción de hechos atómicos
- [[weiSurveyAgenticReasoning2026]] — Survey que teoriza sobre memoria activa
