---
titulo: "MemEvolve: Meta-Evolution of Agent Memory Systems"
autores: "Guibin Zhang, Haotian Ren, Chong Zhan, Zhenhong Zhou, Junhao Wang, He Zhu, Wangchunshu Zhou, Shuicheng Yan"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2512.18746"
citekey: "zhangMemEvolveMetaEvolutionAgent2025"
zotero: "zotero://select/library/items/AAGCMDTW"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - self-evolving
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-07"
valoracion: ⭐⭐⭐⭐⭐
---

# MemEvolve: Meta-Evolution of Agent Memory Systems

## Metadatos

- **Autores**: Guibin Zhang, Haotian Ren, Chong Zhan, Zhenhong Zhou, Junhao Wang, He Zhu, Wangchunshu Zhou, Shuicheng Yan
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2512.18746](https://doi.org/10.48550/arXiv.2512.18746)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/AAGCMDTW)
- **Abstract**: Self-evolving memory systems are reshaping LLM-based agents. However, the memory architecture itself remains static. We propose MemEvolve, a meta-evolutionary framework that jointly evolves agents' experiential knowledge and their memory architecture. We also introduce EvolveLab, a unified codebase distilling 12 representative memory systems.

---

## Resumen

MemEvolve es un framework de **meta-evolución** que va un paso más allá de la auto-evolución convencional: no solo evoluciona la experiencia acumulada del agente, sino también la **propia arquitectura del sistema de memoria**. Mientras que sistemas previos evolucionan *qué* se almacena, MemEvolve evoluciona *cómo* se codifica, almacena, recupera y gestiona. Introduce EvolveLab, un codebase unificado que modulariza 12 sistemas de memoria representativos en un espacio de diseño (encode, store, retrieve, manage) para experimentación controlada.

---

## Problema / Motivación

Los sistemas de memoria auto-evolutivos permiten a los agentes acumular experiencia, destilar conocimiento y sintetizar herramientas reutilizables. Sin embargo, están **fundamentalmente limitados por la estaticidad de la arquitectura de memoria misma**: mientras la memoria facilita la evolución del agente, la arquitectura subyacente no puede meta-adaptarse a contextos de tarea diversos. Se necesita un framework que evolucione no solo el contenido de la memoria, sino también su estructura y operaciones.

---

## Metodología

### EvolveLab: Espacio de diseño modular
Descompone cualquier sistema de memoria $\Omega$ en cuatro componentes:
- **Encode (E)**: Transforma experiencias crudas en representaciones estructuradas
- **Store (U)**: Integra experiencias codificadas en la memoria persistente
- **Retrieve (R)**: Recupera contenido relevante para la tarea actual
- **Manage (G)**: Operaciones de consolidación, abstracción y olvido selectivo

12 sistemas representativos se implementan modularmente en este espacio.

### MemEvolve: Proceso de evolución dual
Dos bucles anidados:

**Inner Loop (Evolución de Experiencia):**
- Para cada arquitectura candidata $\Omega_j^{(k)}$, ejecuta el agente y acumula experiencia
- Evalúa rendimiento según métricas (éxito, consumo de tokens, latencia)

**Outer Loop (Evolución Arquitectónica):**
- Rankea arquitecturas candidatas por rendimiento
- Retiene las top-K
- Genera nuevas variantes modificando o recombinando los 4 componentes (E, U, R, G)
- Produce la siguiente generación de candidatos

El proceso alterna entre evolucionar la base de experiencia (bajo arquitecturas fijas) y evolucionar las arquitecturas (basado en rendimiento observado).

---

## Resultados Clave

- Mejora frameworks como SmolAgent y Flash-Searcher hasta un **17.06%**
- **Generalización cross-task y cross-LLM**: las arquitecturas evolucionadas transfieren entre benchmarks y modelos backbone distintos
- Los sistemas evolucionados revelan principios de diseño emergentes: mayor involucramiento agéntico, organización jerárquica, abstracción multi-nivel
- EvolveLab unifica 12 sistemas en un espacio de diseño comparable

---

## Contribuciones Principales

1. **MemEvolve**: Primer framework de meta-evolución que evoluciona conjuntamente experiencia y arquitectura de memoria
2. **EvolveLab**: Codebase unificado con espacio de diseño modular (encode, store, retrieve, manage) para 12 sistemas de memoria
3. **Principios emergentes**: Revela que las arquitecturas óptimas tienden a mayor involucramiento agéntico, jerarquía y abstracción multi-nivel

---

## Limitaciones

- La búsqueda de arquitecturas óptimas es computacionalmente costosa (múltiples iteraciones con evaluación completa)
- El espacio de diseño de 4 componentes puede no capturar todas las dimensiones relevantes
- La evolución arquitectónica depende de un meta-operador F que es a su vez un LLM, introduciendo posible sesgo

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> While memory facilitates agent-level evolving, the underlying memory architecture cannot be meta-adapted to diverse task contexts. MemEvolve jointly evolves agents' experiential knowledge and their memory architecture. [#ffd400]

---

> [!quote] Resaltado (p. 4)
> We propose a modular design space that decomposes any memory system into four components: Encode, Store, Retrieve, and Manage. [#ffd400]

---

> [!quote] Resaltado (p. 5)
> A dual-evolution process jointly evolves (i) the agent's memory base and (ii) the underlying memory architectures: Inner Loop for experience evolution, Outer Loop for architectural evolution. [#ffd400]

---

> [!quote] Resaltado (p. 12)
> Analysis of automatically evolved memory systems reveals instructive design principles: increased agentic involvement, hierarchical organization, and multi-level abstraction. [#ffd400]

---

## Ideas y Conexiones

- MemEvolve es la materialización más directa de la **evolución estructural** del [[Self-Evolving Agentic Reasoning]]: no solo evoluciona experiencia o skills, sino la propia arquitectura del sistema (como AlphaEvolve para código)
- El espacio de diseño (encode, store, retrieve, manage) es una formalización más granular que la de [[MemOS]] (plaintext, activation, parameter): MemOS diferencia por *tipo* de representación, MemEvolve por *operación funcional*
- Complementario a MemSkill: MemSkill evoluciona las *operaciones individuales*, MemEvolve evoluciona la *configuración completa* del sistema. Podrían combinarse: MemEvolve busca la arquitectura óptima y MemSkill refina sus operaciones
- El hallazgo de que las arquitecturas evolucionadas tienden a mayor "involucramiento agéntico" valida la tesis central del survey: la memoria debe pasar de buffer pasivo a componente activo del razonamiento
- La generalización cross-LLM sugiere que los principios de diseño de memoria son parcialmente independientes del modelo

---

## Notas Relacionadas

- [[Self-Evolving Agentic Reasoning]] — Evolución estructural de la arquitectura
- [[Agentic Memory]] — Marco conceptual de memoria activa
- [[MemOS]] — Enfoque complementario por tipo de representación
- [[zhangMemSkillLearningEvolving2026]] — MemSkill: evoluciona operaciones, no arquitectura
- [[shaoYourAgentMay2026]] — Misevolution: riesgos de la auto-evolución
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza evolución estructural
- [[MemEvolve]] — Nota de concepto
