---
titulo: "Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory"
autores: "Prateek Chhikara, Dev Khant, Saket Aryan, Taranjeet Singh, Deshraj Yadav"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2504.19413"
citekey: "chhikaraMem0BuildingProductionReady2025"
zotero: "zotero://select/library/items/T9JLMLEG"
tags:
  - paper
  - agentic-reasoning
  - memoria
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-01"
valoracion: ⭐⭐⭐⭐
---

# Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory

## Metadatos

- **Autores**: Prateek Chhikara, Dev Khant, Saket Aryan, Taranjeet Singh, Deshraj Yadav
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2504.19413](https://doi.org/10.48550/arXiv.2504.19413)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/T9JLMLEG)
- **Abstract**: Large Language Models (LLMs) have demonstrated remarkable prowess in generating contextually coherent responses, yet their fixed context windows pose fundamental challenges for maintaining consistency over prolonged multi-session dialogues. We introduce Mem0, a scalable memory-centric architecture that addresses this issue by dynamically extracting, consolidating, and retrieving salient information from ongoing conversations. Building on this foundation, we further propose an enhanced variant that leverages graph-based memory representations to capture complex relational structures among conversational elements.

---

## Resumen

Mem0 es una **arquitectura de memoria escalable** para agentes de IA que extrae, consolida y recupera dinámicamente información relevante de conversaciones en curso, superando las limitaciones de la ventana de contexto fija. Su variante Mem0g añade representaciones de memoria basadas en grafos para capturar estructuras relacionales complejas. Supera a todos los baselines (RAG, full-context, OpenAI) en el benchmark LOCOMO con un 91% menos de latencia y >90% de ahorro en tokens.

---

## Problema / Motivación

Los LLMs tienen **ventanas de contexto fijas** que impiden mantener coherencia en diálogos multi-sesión prolongados. Los enfoques existentes incluyen RAG (que carece de consolidación dinámica), full-context (que procesa todo el historial con coste prohibitivo) y sistemas de memoria propietarios (que no alcanzan rendimiento óptimo). Se necesita una arquitectura que combine memoria persistente escalable con eficiencia práctica para despliegue en producción.

---

## Metodología

**Mem0** opera en tres fases:

1. **Extracción**: Un LLM extrae hechos atómicos de cada conversación, identificando entidades, preferencias y relaciones clave
2. **Consolidación**: Las memorias nuevas se comparan con las existentes, resolviéndose conflictos (actualización, fusión o eliminación de contradicciones) para mantener un estado coherente
3. **Recuperación**: Se usa búsqueda vectorial para encontrar memorias relevantes a la consulta actual

**Mem0g** (variante con grafos) extiende esto con:
- Extracción de tripletas (sujeto, predicado, objeto) como knowledge graph
- Búsqueda híbrida: vectorial sobre embeddings + travesalu sobre el grafo relacional
- Captura de relaciones complejas y dependencias temporales que la memoria plana no puede representar

---

## Resultados Clave

- **26% de mejora relativa** sobre OpenAI en la métrica LLM-as-a-Judge en LOCOMO
- Mem0g añade ~2% adicional sobre Mem0 base, especialmente en tareas temporales y open-domain
- **91% menos de latencia** (p95) comparado con full-context
- **>90% de ahorro en tokens** respecto a full-context, con rendimiento superior
- Supera a 6 categorías de baselines: memory-augmented systems, RAG, full-context, open-source, propietario, y plataformas de gestión de memoria

---

## Contribuciones Principales

1. **Mem0**: Arquitectura de memoria dinámica con extracción, consolidación y recuperación de hechos atómicos de conversaciones
2. **Mem0g**: Variante con memoria basada en grafos de conocimiento para capturar relaciones complejas y mejorar tareas temporales y multi-hop
3. **Evaluación exhaustiva** contra 6 categorías de baselines demostrando superioridad en 4 tipos de preguntas, con eficiencia práctica para producción

---

## Limitaciones

- La extracción de memorias depende de un LLM, lo que introduce latencia y coste adicional en el pipeline de escritura
- La consolidación de conflictos puede perder matices en contextos altamente ambiguos
- No se evalua integración con agentes de razonamiento complejo (solo diálogos conversacionales)

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We introduce Mem0, a scalable memory-centric architecture that addresses this issue by dynamically extracting, consolidating, and retrieving salient information from ongoing conversations. Building on this foundation, we further propose an enhanced variant that leverages graph-based memory representations to capture complex relational structures among conversational elements. [#ffd400]

---

> [!quote] Resaltado (p. 14)
> Mem0 achieves state-of-the-art performance across single-hop and multi-hop reasoning, while Mem0g's graph-based extensions unlock significant gains in temporal and open-domain tasks. [#ffd400]

---

## Ideas y Conexiones

- Mem0 implementa las tres operaciones clave de [[Agentic Memory]]: escritura (extracción), gestión (consolidación) y lectura (recuperación), moviéndose de buffer pasivo a gestión activa
- Mem0g (variante con grafos) es análogo conceptual al [[Mind-Map Agent]] de Wu et al. — ambos usan grafos de conocimiento como memoria estructurada, pero Mem0g se centra en persistencia conversacional mientras Mind-Map opera dentro de una cadena de razonamiento
- La fase de consolidación (resolver conflictos entre memorias nuevas y viejas) conecta con la gestión de memoria en [[Self-Evolving Agentic Reasoning]]: verificación, compresión y actualización continua
- El enfoque de "hechos atómicos" como unidad de memoria recuerda al principio de [[Agentic Memory]] factual descrito en el survey
- Sería interesante combinar Mem0 con [[Reflexion]] para que la consolidación incorpore reflexiones sobre la calidad del razonamiento

---

## Notas Relacionadas

- [[Agentic Memory]] — Concepto general de memoria agéntica
- [[Mind-Map Agent]] — Otro enfoque de memoria estructurada con grafos
- [[Agentic Search]] — Recuperación dinámica de memoria
- [[Self-Evolving Agentic Reasoning]] — Evolución de memoria a través de episodios
- [[weiSurveyAgenticReasoning2026]] — Survey que categoriza tipos de memoria agéntica
- [[gutierrezRAGMemoryNonParametric2025]] — HippoRAG 2, otro enfoque de memoria bio-inspirada
- [[liMemOSMemoryOS2025]] — MemOS, memoria como recurso de sistema operativo
