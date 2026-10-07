---
titulo: "MIRIX: Multi-Agent Memory System for LLM-Based Agents"
autores: "Yu Wang, Xi Chen"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2507.07957"
citekey: "wangMIRIXMultiAgentMemory2025"
zotero: "zotero://select/library/items/S3IKZDFK"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - multi-agent
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-05"
valoracion: ⭐⭐⭐⭐⭐
---

# MIRIX: Multi-Agent Memory System for LLM-Based Agents

## Metadatos

- **Autores**: Yu Wang, Xi Chen
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2507.07957](https://doi.org/10.48550/arXiv.2507.07957)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/S3IKZDFK)
- **Abstract**: Existing AI agent memory solutions remain fundamentally limited, relying on flat, narrowly scoped memory components. We introduce MIRIX, a modular, multi-agent memory system with six distinct memory types: Core, Episodic, Semantic, Procedural, Resource Memory, and Knowledge Vault, coupled with a multi-agent framework that dynamically controls updates and retrieval. On ScreenshotVQA, MIRIX achieves 35% higher accuracy than RAG while reducing storage by 99.9%. On LOCOMO, it attains SOTA of 85.4%.

---

## Resumen

MIRIX es un **sistema de memoria multi-agente modular** con seis tipos de memoria especializados (Core, Episodic, Semantic, Procedural, Resource, Knowledge Vault), cada uno gestionado por un Memory Manager dedicado bajo la coordinación de un Meta Memory Manager. Extiende la memoria más allá del texto para incluir experiencias **visuales y multimodales**. Logra SOTA en LOCOMO (85.4%) y 35% más de precisión que RAG en un benchmark multimodal con 20,000 screenshots, reduciendo almacenamiento un 99.9%.

---

## Problema / Motivación

Los sistemas de memoria existentes para agentes de IA son **fundamentalmente limitados**: dependen de componentes de memoria planos y de alcance estrecho, lo que impide personalizar, abstraer y recuperar fiablemente información específica del usuario a lo largo del tiempo. La mayoría se limita a texto, ignorando experiencias visuales y multimodales que son cruciales en escenarios reales (ej. actividad en pantalla del usuario). Se necesita un sistema que combine múltiples tipos de memoria diferenciados con gestión dinámica y soporte multimodal.

---

## Metodología

MIRIX organiza la memoria en **seis componentes especializados**, cada uno con un rol cognitivo distinto:

### Tipos de Memoria
1. **Core Memory**: Información persistente de alta prioridad siempre visible al agente. Dividida en bloques `persona` (identidad/tono del agente) y `human` (hechos duraderos del usuario: nombre, preferencias, atributos)
2. **Episodic Memory**: Eventos con marca temporal y actividades del usuario. Funciona como log/calendario estructurado para razonar sobre rutinas, recencia y seguimiento contextual
3. **Semantic Memory**: Conocimiento abstracto y factual independiente de eventos específicos. Base de conocimiento para conceptos generales, entidades y relaciones (incluido el grafo social del usuario)
4. **Procedural Memory**: Procesos estructurados orientados a objetivos: guías how-to, workflows operativos, scripts interactivos. Conocimiento *accionable* invocable para tareas complejas
5. **Resource Memory**: Documentos completos/parciales, transcripciones y archivos multimodales con los que el usuario está interactuando activamente
6. **Knowledge Vault**: Repositorio seguro para información sensible y verbatim: credenciales, direcciones, claves API, identificadores a largo plazo

### Arquitectura Multi-Agente
- Cada tipo de memoria tiene un **Memory Manager** dedicado (agente especializado)
- Un **Meta Memory Manager** coordina a todos los managers, decidiendo qué memoria consultar/actualizar para cada interacción
- El framework controla dinámicamente las actualizaciones y la recuperación

### Soporte Multimodal
- Trasciende el texto para incluir screenshots de alta resolución, imágenes y archivos multimodales
- La aplicación empaquetada monitoriza la pantalla en tiempo real, construyendo una base de memoria personalizada

---

## Resultados Clave

- **ScreenshotVQA** (benchmark multimodal con ~20,000 screenshots): 35% más de precisión que RAG baseline, con **99.9% menos de almacenamiento** requerido
- **LOCOMO** (conversación de larga duración): **85.4% SOTA**, superando ampliamente a todos los baselines existentes (incluyendo Mem0)
- Ningún sistema de memoria previo podía aplicarse al benchmark ScreenshotVQA — MIRIX es el primero
- Demostración de que la diferenciación de tipos de memoria mejora significativamente la recuperación y el razonamiento

---

## Contribuciones Principales

1. **Arquitectura de 6 memorias**: Taxonomía de Core, Episodic, Semantic, Procedural, Resource y Knowledge Vault con roles cognitivos diferenciados
2. **Framework multi-agente**: Memory Managers especializados + Meta Memory Manager para coordinación dinámica de actualización y recuperación
3. **Primer sistema de memoria multimodal**: Capaz de procesar y razonar sobre screenshots y experiencias visuales, no solo texto

---

## Limitaciones

- La complejidad del sistema (6 tipos de memoria + múltiples agentes) puede introducir overhead significativo de coordinación
- La generalización más allá de los dos benchmarks evaluados no está demostrada
- El Meta Memory Manager podría ser un cuello de botella si no escala bien con la cantidad de tipos de memoria

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> MIRIX consists of six distinct, carefully structured memory types: Core, Episodic, Semantic, Procedural, Resource Memory, and Knowledge Vault, coupled with a multi-agent framework that dynamically controls and coordinates updates and retrieval. [#ffd400]

---

> [!quote] Resaltado (p. 6)
> Core Memory stores high-priority, persistent information. Episodic Memory captures time-stamped events. Semantic Memory maintains abstract knowledge. Procedural Memory stores goal-directed processes. Resource Memory handles documents and multi-modal files. Knowledge Vault serves as a secure repository for sensitive information. [#ffd400]

---

> [!quote] Resaltado (p. 13)
> Unlike existing memory systems that rely on flat storage or limited memory types, MIRIX leverages a structured and compositional approach, incorporating six specialized memory components managed by dedicated Memory Managers under the coordination of a Meta Memory Manager. [#ffd400]

---

## Ideas y Conexiones

- La taxonomía de 6 memorias de MIRIX puede mapearse a la estructura del survey de Wei et al.: Core ≈ in-context always-on, Episodic ≈ experience memory, Semantic ≈ factual memory, Procedural ≈ skill library ([[Self-Evolving Agentic Reasoning]]), Resource ≈ plaintext memory ([[MemOS]]), Knowledge Vault ≈ parametric secrets
- La arquitectura de **Memory Managers especializados + Meta Manager** es exactamente el patrón de roles multi-agente del survey: Manager (Meta Memory Manager) + Workers (Memory Managers) del [[Collective Multi-Agent Reasoning]]
- Contraste con Mem0: MIRIX tiene 6 tipos de memoria diferenciados mientras Mem0 tiene memoria plana (facts atómicos). MIRIX es más expresivo pero más complejo; en LOCOMO, MIRIX (85.4%) supera a Mem0
- La **Procedural Memory** (workflows, scripts) conecta directamente con la evolución procedimental del [[Self-Evolving Agentic Reasoning]] — una biblioteca de habilidades persistente
- El soporte multimodal (screenshots) es pionero y conecta con la observación del survey sobre benchmarks multimodales para memoria
- Sería interesante combinar MIRIX con [[MemOS]] para que los 6 tipos de memoria se gestionen como MemCubes con lifecycle management formal

---

## Notas Relacionadas

- [[Agentic Memory]] — Marco conceptual; MIRIX es la implementación más rica
- [[Collective Multi-Agent Reasoning]] — Patrón Manager-Workers para gestión de memoria
- [[Self-Evolving Agentic Reasoning]] — Procedural Memory como evolución de skills
- [[MemOS]] — Enfoque complementario de infraestructura de memoria
- [[chhikaraMem0BuildingProductionReady2025]] — Mem0, competidor con memoria plana
- [[HippoRAG]] — Enfoque bio-inspirado centrado en memoria semántica/asociativa
- [[yuMemAgentReshapingLongContext2026]] — MemAgent, enfoque RL para gestión de memoria
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza tipos de memoria
- [[MIRIX]] — Nota de concepto
