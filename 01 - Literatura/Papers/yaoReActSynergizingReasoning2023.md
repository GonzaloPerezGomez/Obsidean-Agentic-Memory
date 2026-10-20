---
titulo: "ReAct: Synergizing Reasoning and Acting in Language Models"
autores: "Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, Yuan Cao"
año: "2023"
fuente: ""
DOI: "10.48550/arXiv.2210.03629"
citekey: "yaoReActSynergizingReasoning2023"
zotero: "zotero://select/library/items/ETU2PNCW"
tags:
  - paper
  - agentic-reasoning
  - framework
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-20"
valoracion: ⭐⭐⭐⭐⭐
---

# ReAct: Synergizing Reasoning and Acting in Language Models

## Metadatos

- **Autores**: Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, Yuan Cao
- **Año**: 2023
- **Publicación**: ICLR 2023
- **DOI**: [10.48550/arXiv.2210.03629](https://doi.org/10.48550/arXiv.2210.03629)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/ETU2PNCW)
- **Abstract**: While large language models (LLMs) have demonstrated impressive capabilities across tasks in language understanding and interactive decision making, their abilities for reasoning (e.g. chain-of-thought prompting) and acting (e.g. action plan generation) have primarily been studied as separate topics. In this paper, we explore the use of LLMs to generate both reasoning traces and task-specific actions in an interleaved manner, allowing for greater synergy between the two: reasoning traces help the model induce, track, and update action plans as well as handle exceptions, while actions allow it to interface with external sources, such as knowledge bases or environments, to gather additional information. We apply our approach, named ReAct, to a diverse set of language and decision making tasks and demonstrate its effectiveness over state-of-the-art baselines, as well as improved human interpretability and trustworthiness over methods without reasoning or acting components. Concretely, on question answering (HotpotQA) and fact verification (Fever), ReAct overcomes issues of hallucination and error propagation prevalent in chain-of-thought reasoning by interacting with a simple Wikipedia API, and generates human-like task-solving trajectories that are more interpretable than baselines without reasoning traces. On two interactive decision making benchmarks (ALFWorld and WebShop), ReAct outperforms imitation and reinforcement learning methods by an absolute success rate of 34% and 10% respectively, while being prompted with only one or two in-context examples. Project site with code: https://react-lm.github.io

---

## Resumen

ReAct es el paper fundacional que unifica la generación de trazas de razonamiento y la ejecución de acciones en modelos de lenguaje mediante un bucle intercalado (*think-act-observe*). Al permitir que el LLM alterne entre deliberar en lenguaje natural e interactuar con fuentes externas o entornos interactivos, resuelve la desconexión histórica entre el razonamiento estático (propenso a alucinaciones) y la actuación ciega (carente de planificación y gestión de excepciones).

---

## Problema / Motivación

Antes de ReAct, las capacidades de razonamiento (como [[Chain of Thought]]) y de actuación interactiva (generación de planes o llamadas a APIs) se estudiaban de forma aislada:
1. **Razonamiento aislado (CoT)**: Es un proceso puramente interno de caja negra/generación abierta sin interacción con el entorno; sufre de alucinaciones factuales, deriva semántica y acumulación de errores al no poder consultar ni verificar datos externos.
2. **Actuación aislada (Action-only)**: Carece de reflexión abstracta, dificultando la formulación de submetas, el rastreo de planes y la recuperación tras observar resultados inesperados o errores de ejecución.

Se necesitaba un paradigma formal que integrara pensamiento y acción de forma sinérgica dentro de un único proceso de toma de decisiones.

---

## Metodología

ReAct formula el problema ampliando el espacio de acciones del agente a $\hat{\mathcal{A}} = \mathcal{A} \cup \mathcal{L}$, donde $\mathcal{A}$ es el conjunto de acciones ejecutables en el entorno y $\mathcal{L}$ es el espacio del lenguaje:

1. **Thoughts (Acciones en $\mathcal{L}$)**: Trazas de razonamiento libre en lenguaje natural que no alteran el estado del entorno externo y no devuelven observaciones, pero sirven para:
   - Descomponer objetivos complejos e inducir planes.
   - Extraer y sintetizar entidades clave de observaciones previas.
   - Ajustar hipótesis y diagnosticar excepciones.
2. **Actions (Acciones en $\mathcal{A}$)**: Comandos ejecutables dirigidos a APIs externas, bases de conocimiento o entornos simulados (ej. `search[entity]`, `lookup[string]`, `finish[answer]`).
3. **Observations**: Respuestas proporcionadas por el entorno tras cada acción en $\mathcal{A}$, que se concatenan dinámicamente al contexto para el siguiente paso reflexivo.

El método se implementa mediante prompting few-shot (con 1 o 2 trayectorias anotadas) sin requerir re-entrenamiento del LLM.

---

## Resultados Clave

- **HotpotQA y FEVER**: ReAct supera ampliamente a los métodos sin razonamiento y mitiga la propagación de errores y alucinaciones de CoT, gracias al grounding dinámico obtenido mediante consultas a la API de Wikipedia.
- **ALFWorld (navegación y manipulación interactiva)**: Logra una tasa de éxito absoluta superior en **+34%** respecto a modelos entrenados con aprendizaje por imitación y aprendizaje por refuerzo tradicional.
- **WebShop (navegación web orientada a compra)**: Supera los métodos basados en RL e imitación en un **+10%** de tasa de éxito absoluta utilizando solo 1 o 2 ejemplos in-context.
- **Interpretabilidad**: Las trayectorias resultantes son transparentes y fácilmente diagnosticables por humanos, facilitando la supervisión y edición humana en tiempo de ejecución.

---

## Contribuciones Principales

1. **Paradigma ReAct**: Primera formalización explícita de la sinergia entre razonamiento (*thought*) y acción (*action*) intercalados para LLMs.
2. **Aumento del espacio de decisión**: Extensión del espacio de acciones al incluir el lenguaje natural $\mathcal{L}$ como acción interna no efectora.
3. **Demostración de generalización**: Validación en cuatro benchmarks heterogéneos (QA multi-hop, fact verification, entornos embodied de texto y comercio web interactivo), estableciendo el estándar de los agentes LLM modernos.

---

## Limitaciones

- Puede entrar en bucles repetitivos si las observaciones del entorno son ambiguas o si la API devuelve errores imprevistos.
- Depende de la longitud de la ventana de contexto, ya que las trazas acumuladas crecen rápidamente con múltiples interacciones.
- No incluye un mecanismo persistente de auto-corrección entre episodios diferentes (lo que posteriormente resolverían frameworks como [[Reflexion]]).

---

## Resaltados y Anotaciones

> [!quote] Resaltado (p. 3)
> The idea of ReAct is simple: we augment the agent’s action space to Aˆ = A ∪ L, where L is the space of language. An action aˆt ∈ L in the language space, which we will refer to as a thought or a reasoning trace, does not affect the external environment, thus leading to no observation feedback [#ffd400]

---

## Ideas y Conexiones

- ReAct es el punto de partida histórico del **[[Agentic Reasoning]]** moderno y la base operativa de [[Foundational Agentic Reasoning]].
- Inspiró directamente a frameworks evolutivos como [[Reflexion]] (que añade reflexión inter-episódica y crítica retrospectiva) y [[Tree of Thoughts]] (que explora árboles de pensamientos en lugar de una cadena lineal greedy).
- Se conecta con la formalización de [[POMDP]] adoptada por Wei et al. (2026), donde la variable de razonamiento interno modela exactamente el paso `thought` de ReAct.

---

## Notas Relacionadas

- [[Agentic Reasoning]] — Paradigma central
- [[ReAct]] — Nota conceptual del framework
- [[Chain of Thought]] — Precursor lineal de razonamiento
- [[Tool Use]] — Invocación de herramientas dentro del bucle
- [[Reflexion]] — Extensión con auto-crítica y memoria de errores
- [[Foundational Agentic Reasoning]] — Capa 1 de la taxonomía
- [[weiSurveyAgenticReasoning2026]] — Survey fundacional
