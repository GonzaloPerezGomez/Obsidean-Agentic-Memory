---
titulo: "A-MEM"
tags:
  - concepto
  - agentic-reasoning
  - memoria
aliases: ["Agentic Memory Zettelkasten", "A-MEM System"]
fecha_creacion: "2026-10-20"
---

# A-MEM

## Definición

> Sistema de **memoria agéntica estructurada y auto-evolutiva** que organiza las experiencias de agentes LLM inspirándose en el método **Zettelkasten**, generando notas ricas en metadatos contextuales, enlaces dinámicos y actualizando retroactivamente las memorias del pasado cuando ingresa nueva información.

## Explicación

A-MEM transforma radicalmente el concepto de memoria en agentes. Los sistemas convencionales se limitan a guardar fragmentos planos de texto (o aplicar embeddings estáticos) que se acumulan sin relacionarse, provocando que la memoria antigua quede congelada en el tiempo y no se beneficie de lo aprendido después. 

A-MEM adopta la filosofía de las notas interconectadas (Zettelkasten): cada nueva interacción se sintetiza en una "nota" dotada de descripción contextual, palabras clave y etiquetas. Mediante razonamiento agéntico, el sistema identifica notas históricas afines y construye enlaces explícitos entre ellas, tejiendo una red de conocimiento. El rasgo más diferenciador es su **evolución retrospectiva**: cuando entra un nuevo dato que aclara, contradice o complementa un recuerdo antiguo, A-MEM actualiza los metadatos y representaciones de las notas previas vecinas. De este modo, la memoria no se limita a crecer en volumen, sino que madura cualitativamente, descubriendo patrones conceptuales de orden superior.

---

## Contexto

Propuesto por Xu et al. (2025), A-MEM se sitúa en la intersección entre la memoria estructurada y el [[Self-Evolving Agentic Reasoning]]. A diferencia de los grafos de conocimiento rígidos basados en tripletas predefinidas, A-MEM delega en el propio agente la decisión de cómo categorizar, enlazar y revisar las notas, permitiendo una adaptación flexible y autónoma en tareas conversacionales complejas de largo horizonte.

---

## Relación con otros conceptos

- **Requiere**: Modelos de lenguaje con capacidad de síntesis y razonamiento relacional
- **Relacionado con**: [[Agentic Memory]], [[Zep]], [[HippoRAG]], [[Mem0]]
- **Aplica**: Principios del método Zettelkasten y evolución no paramétrica
- **Se enmarca en**: [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[xuAMEMAgenticMemory2025]] — Paper original de A-MEM
- [[weiSurveyAgenticReasoning2026]] — Sección de Structured Memory y evolución de estados
