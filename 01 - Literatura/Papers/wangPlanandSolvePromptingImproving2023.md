---
titulo: "Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning by Large Language Models"
autores: "Lei Wang, Wanyu Xu, Yihuai Lan, Zhiqiang Hu, Yunshi Lan, Roy Ka-Wei Lee, Ee-Peng Lim"
año: "2023"
fuente: ""
DOI: "10.48550/arXiv.2305.04091"
citekey: "wangPlanandSolvePromptingImproving2023"
zotero: "zotero://select/library/items/N7SXW3V3"
tags:
  - paper
  - agentic-reasoning
  - prompting
estado: "#estado/en-progreso"
fecha_lectura: "2026-09-30"
valoracion: ⭐⭐⭐⭐
---

# Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning by Large Language Models

## Metadatos

- **Autores**: Lei Wang, Wanyu Xu, Yihuai Lan, Zhiqiang Hu, Yunshi Lan, Roy Ka-Wei Lee, Ee-Peng Lim
- **Año**: 2023
- **Publicación**: ACL 2023
- **DOI**: [10.48550/arXiv.2305.04091](https://doi.org/10.48550/arXiv.2305.04091)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/N7SXW3V3)
- **Abstract**: Large language models (LLMs) have recently been shown to deliver impressive performance in various NLP tasks. To tackle multi-step reasoning tasks, few-shot chain-of-thought (CoT) prompting includes a few manually crafted step-by-step reasoning demonstrations which enable LLMs to explicitly generate reasoning steps and improve their reasoning task accuracy. To eliminate the manual effort, Zero-shot-CoT concatenates the target problem statement with "Let's think step by step" as an input prompt to LLMs. Despite the success of Zero-shot-CoT, it still suffers from three pitfalls: calculation errors, missing-step errors, and semantic misunderstanding errors. To address the missing-step errors, we propose Plan-and-Solve (PS) Prompting. It consists of two components: first, devising a plan to divide the entire task into smaller subtasks, and then carrying out the subtasks according to the plan. To address the calculation errors and improve the quality of generated reasoning steps, we extend PS prompting with more detailed instructions and derive PS+ prompting.

---

## Resumen

Este paper propone **Plan-and-Solve (PS) Prompting**, una estrategia de prompting zero-shot que mejora el razonamiento de los LLMs dividiendo explícitamente la tarea en subtareas antes de resolverlas. Su extensión PS+ añade instrucciones más detalladas para reducir errores de cálculo, superando consistentemente a Zero-shot-CoT y alcanzando rendimiento comparable al few-shot CoT con 8 ejemplos.

---

## Problema / Motivación

Zero-shot-CoT ("Let's think step by step") sufre de tres tipos de errores: **errores de cálculo**, **errores de pasos faltantes** (el modelo omite pasos intermedios necesarios) y **errores de comprensión semántica**. Estos problemas limitan la fiabilidad del razonamiento zero-shot, especialmente en tareas matemáticas y de razonamiento multi-paso. Los métodos few-shot-CoT requieren ejemplos manuales costosos de diseñar.

---

## Metodología

Proponen una estrategia de prompting en dos fases:

1. **Planificación**: El prompt instruye al modelo a "diseñar un plan para dividir la tarea en subtareas más pequeñas"
2. **Ejecución**: El modelo "lleva a cabo las subtareas según el plan"

La versión extendida **PS+** añade instrucciones más detalladas:
- "Extraer información y variables relevantes"
- "Calcular resultados intermedios"
- "Prestar atención al cálculo y la lógica"

Esto guía al LLM a generar pasos de razonamiento más completos y precisos sin necesidad de ejemplos manuales.

---

## Resultados Clave

- PS+ supera consistentemente a Zero-shot-CoT en **10 datasets** de 3 tipos de razonamiento (aritmético, de sentido común, simbólico)
- Rendimiento comparable o superior a Zero-shot-Program-of-Thought Prompting
- Rendimiento comparable al **8-shot CoT prompting** en problemas de razonamiento matemático, sin necesidad de ejemplos manuales

---

## Contribuciones Principales

1. Identificación de tres tipos de errores en Zero-shot-CoT (cálculo, pasos faltantes, comprensión semántica)
2. Propuesta de **Plan-and-Solve Prompting**: un enfoque zero-shot que introduce planificación explícita antes de la ejecución
3. Extensión **PS+** con instrucciones detalladas que mejora la calidad de los pasos de razonamiento

---

## Limitaciones

- Evaluado solo sobre GPT-3; la transferibilidad a otros modelos no está verificada
- Las instrucciones adicionales en PS+ fueron diseñadas manualmente, lo que introduce cierto sesgo de ingeniería
- No aborda errores de comprensión semántica directamente

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> To address the missing-step errors, we propose Plan-and-Solve (PS) Prompting. It consists of two components: first, devising a plan to divide the entire task into smaller subtasks, and then carrying out the subtasks according to the plan. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> Evaluation on ten datasets across three types of reasoning problems shows PS+ prompting outperforms the previous zero-shot baselines and performs on par with few-shot CoT prompting on multiple arithmetic reasoning datasets [#ffd400]

---

> [!quote] Resaltado (p. 9)
> Zero-shot PS+ prompting can generate a high-quality reasoning process than Zero-shot-CoT prompting since the PS prompts can provide more detailed instructions guiding the LLMs to perform correct reasoning; (b) Zero-shot PS+ prompting has the potential to outperform manual Few-shot CoT prompting [#ffd400]

---

## Ideas y Conexiones

- PS Prompting introduce una fase de **planificación explícita** que es un precursor directo de la [[Planning]] agéntica — la diferencia es que en PS la planificación ocurre solo a nivel de prompt, sin interacción con el entorno
- Conecta directamente con [[Least-to-Most Prompting]] — ambos descomponen problemas, pero Least-to-Most usa descomposición top-down con resolución bottom-up, mientras que PS planifica y luego ejecuta secuencialmente
- La extensión PS+ anticipa los enfoques de [[In-Context Reasoning]] más sofisticados: instrucciones más detalladas como sustituto del entrenamiento
- Podría combinarse con [[ReAct]] para añadir planificación explícita antes del ciclo think-act

---

## Notas Relacionadas

- [[Chain of Thought]] — Base sobre la que PS mejora
- [[Planning]] — PS como precursor de planificación agéntica
- [[Least-to-Most Prompting]] — Estrategia de descomposición relacionada
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza esta línea de trabajo
- [[Plan-and-Solve Prompting]] — Nota de concepto
