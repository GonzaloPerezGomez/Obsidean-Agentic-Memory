---
titulo: "Agentic Reasoning: A Streamlined Framework for Enhancing LLM Reasoning with Agentic Tools"
autores: "Junde Wu, Jiayuan Zhu, Yuyuan Liu, Min Xu, Yueming Jin, Wanxiang Che, Joyce Nabende, Ekaterina Shutova, Mohammad Taher Pilehvar"
año: "2025"
fuente: ""
DOI: "10.18653/v1/2025.acl-long.1383"
citekey: "wuAgenticReasoningStreamlined2025"
zotero: "zotero://select/library/items/GAJUC3R6"
tags:
  - paper
  - agentic-reasoning
  - framework
estado: "#estado/en-progreso"
fecha_lectura: "2026-09-30"
valoracion: ⭐⭐⭐⭐⭐
---

# Agentic Reasoning: A Streamlined Framework for Enhancing LLM Reasoning with Agentic Tools

## Metadatos

- **Autores**: Junde Wu, Jiayuan Zhu, Yuyuan Liu, Min Xu, Yueming Jin, Wanxiang Che, Joyce Nabende, Ekaterina Shutova, Mohammad Taher Pilehvar
- **Año**: 2025
- **Publicación**: ACL 2025
- **DOI**: [10.18653/v1/2025.acl-long.1383](https://doi.org/10.18653/v1/2025.acl-long.1383)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/GAJUC3R6)
- **Abstract**: We introduce Agentic Reasoning, a framework that enhances large language model (LLM) reasoning by integrating external tool-using agents. Agentic Reasoning dynamically leverages web search, code execution, and structured memory to address complex problems requiring deep research. A key innovation in our framework is the Mind-Map agent, which constructs a structured knowledge graph to store reasoning context and track logical relationships, ensuring coherence in long reasoning chains with extensive tool usage. Additionally, we conduct a comprehensive exploration of the Web-Search agent, leading to a highly effective search mechanism that surpasses all prior approaches.

---

## Resumen

Este paper presenta un framework de **Agentic Reasoning** que mejora el razonamiento de LLMs integrando agentes especializados de herramientas: un **Mind-Map agent** (grafo de conocimiento estructurado como memoria), un **Web-Search agent** (búsqueda web optimizada) y un **Code agent** (ejecución de código). Desplegado sobre DeepSeek-R1, alcanza SOTA entre modelos públicos, comparable a OpenAI Deep Research.

---

## Problema / Motivación

Los LLMs de razonamiento (reasoning models como DeepSeek-R1) generan cadenas de pensamiento largas y profundas, pero están limitados a su conocimiento paramétrico. Cuando las tareas requieren **investigación profunda** — información actualizada, cálculos precisos o integración de múltiples fuentes — el razonamiento puro es insuficiente. Además, las cadenas largas de razonamiento pierden coherencia sin un mecanismo de memoria estructurada.

---

## Metodología

El framework integra **tres agentes especializados** en el bucle de razonamiento del LLM:

1. **Mind-Map Agent**: Construye un **grafo de conocimiento estructurado** que almacena el contexto de razonamiento y rastrea relaciones lógicas. Cuando el LLM genera un token especial de Mind-Map, el agente actualiza o consulta el grafo para mantener coherencia en cadenas largas.

2. **Web-Search Agent**: Cuando el LLM genera tokens de búsqueda web, el agente recibe la query + contexto de razonamiento y devuelve resultados pertinentes. Su diseño incluye exploración comprehensiva de estrategias de búsqueda.

3. **Code Agent**: Para cálculos precisos, el LLM genera tokens de código que se ejecutan externamente.

El proceso es **iterativo**: el LLM razona, invoca agentes cuando lo necesita mediante tokens especiales, recibe resultados, y continúa el razonamiento con conocimiento actualizado. El ciclo se repite hasta alcanzar una respuesta final.

---

## Resultados Clave

- **SOTA entre modelos públicos** en QA de nivel experto y tareas de investigación profunda cuando se despliega sobre DeepSeek-R1
- Rendimiento **comparable a OpenAI Deep Research** (modelo propietario líder) en evaluaciones humanas y benchmarks
- Estudios de ablación confirman que **Mind-Map + Web-Search** es la combinación más efectiva; el Mind-Map es clave para mantener coherencia en cadenas largas
- El Web-Search agent supera todos los enfoques previos de búsqueda en el contexto de reasoning models

---

## Contribuciones Principales

1. Framework **Agentic Reasoning** que integra agentes de herramientas en el bucle de razonamiento de LLMs mediante tokens especiales
2. **Mind-Map agent**: innovación clave que usa un grafo de conocimiento estructurado como memoria para mantener coherencia en razonamiento largo
3. **Web-Search agent** optimizado que supera todos los enfoques previos de búsqueda agéntica

---

## Limitaciones

- Dependencia de DeepSeek-R1 como modelo base; la generalización a otros reasoning models no está plenamente demostrada
- El overhead computacional de mantener el grafo de conocimiento y múltiples agentes no se analiza en detalle
- No incluye mecanismos de auto-evolución o aprendizaje inter-episódico — los agentes son estáticos

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We introduce Agentic Reasoning, a framework that enhances large language model (LLM) reasoning by integrating external tool-using agents. A key innovation in our framework is the Mind-Map agent, which constructs a structured knowledge graph to store reasoning context and track logical relationships, ensuring coherence in long reasoning chains with extensive tool usage. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> In the overall process, we deploy a Web-Search agent and a Code agent as problem-solving tools, along with a knowledge-graph agent, called Mind-Map, to serve as memory. Specifically, the reasoning LLM can dynamically determine when to call external agentic tools during its reasoning process. When needed, it embeds specialized tokens into its reasoning sequence, categorizing them as websearch tokens, coding tokens, or Mind-Map calling tokens. [#ffd400]

---

> [!quote] Resaltado (p. 8)
> Agentic Reasoning outperforms existing methods in both quantitative benchmarks and human evaluations. Future work will explore task-specific tools integration and test-time computing to further enhance AI's reasoning capabilities. [#ffd400]

---

## Ideas y Conexiones

- El Mind-Map agent es un ejemplo concreto de [[Agentic Memory]] **estructurada** — implementa exactamente lo que el survey de Wei et al. describe como "structured memory" usando grafos de conocimiento
- La invocación dinámica de agentes mediante **tokens especiales** es una variante elegante del [[ReAct]] pattern: en lugar de alternar texto de pensamiento y acciones, el modelo embebe tokens de control en su flujo de razonamiento
- Combina los tres pilares del [[Foundational Agentic Reasoning]]: [[Planning]] (implícita en el razonamiento de R1), [[Tool Use]] (Web-Search + Code agents), y [[Agentic Search]] (Web-Search agent)
- La falta de auto-evolución lo sitúa firmemente en la primera capa del framework de Wei et al.; para escalar necesitaría mecanismos de [[Reflective Feedback]] y [[Self-Evolving Agentic Reasoning]]
- Sería interesante combinar Mind-Map con [[Reflexion]] para que el grafo evolucione entre episodios

---

## Notas Relacionadas

- [[Agentic Reasoning]] — Concepto general
- [[Agentic Memory]] — Mind-Map como implementación de memoria estructurada
- [[Tool Use]] — Web-Search y Code como uso de herramientas
- [[Agentic Search]] — Web-Search agent como búsqueda agéntica
- [[ReAct]] — Patrón de razonamiento-acción que este framework extiende
- [[Foundational Agentic Reasoning]] — Capa donde se sitúa este framework
- [[Mind-Map Agent]] — Nota de concepto
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza el campo
