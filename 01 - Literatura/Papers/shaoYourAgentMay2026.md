---
titulo: "Your Agent May Misevolve: Emergent Risks in Self-evolving LLM Agents"
autores: "Shuai Shao, Qihan Ren, Chen Qian, Boyi Wei, Dadi Guo, Jingyi Yang, Xinhao Song, Linfeng Zhang, Weinan Zhang, Dongrui Liu, Jing Shao"
año: "2026"
fuente: ""
DOI: "10.48550/arXiv.2509.26354"
citekey: "shaoYourAgentMay2026"
zotero: "zotero://select/library/items/UG2FQSEI"
tags:
  - paper
  - agentic-reasoning
  - safety
  - self-evolving
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-07"
valoracion: ⭐⭐⭐⭐⭐
---

# Your Agent May Misevolve: Emergent Risks in Self-evolving LLM Agents

## Metadatos

- **Autores**: Shuai Shao, Qihan Ren, Chen Qian, Boyi Wei, Dadi Guo, Jingyi Yang, Xinhao Song, Linfeng Zhang, Weinan Zhang, Dongrui Liu, Jing Shao
- **Año**: 2026
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2509.26354](https://doi.org/10.48550/arXiv.2509.26354)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/UG2FQSEI)
- **Abstract**: Advances in LLMs have enabled self-evolving agents that autonomously improve. However, self-evolution introduces novel risks we call Misevolution. We evaluate misevolution along four key evolutionary pathways: model, memory, tool, and workflow.

---

## Resumen

Este paper introduce el concepto de **Misevolution** (misevolución): cuando la auto-evolución de un agente LLM **se desvía de formas no intencionadas**, produciendo resultados indeseables o dañinos. Se evalúan sistemáticamente 4 vías de misevolución: modelo (self-training), memoria (acumulación), herramientas (creación/reutilización), y workflow (optimización). Los hallazgos muestran que es un riesgo generalizado que afecta incluso a modelos top-tier (Gemini-2.5-Pro), y que las mitigaciones actuales son insuficientes.

---

## Problema / Motivación

Los agentes auto-evolutivos ganan capacidades autónomas, pero la investigación en seguridad actual se centra en LLMs estáticos (jailbreaking, misalignment en snapshots puntuales). La auto-evolución introduce riesgos cualitativamente distintos con cuatro características únicas:
1. **Emergencia temporal**: Los riesgos aparecen gradualmente durante la evolución, no existen en la "fotografía" estática
2. **Vulnerabilidad auto-generada**: El agente genera riesgos internamente sin adversario externo
3. **Control de datos limitado**: La naturaleza autónoma impide intervenciones directas de seguridad a nivel de datos
4. **Superficie de riesgo expandida**: Múltiples componentes evolucionan (modelo, memoria, herramientas, workflow), cada uno con vectores de ataque

---

## Metodología

Evaluación sistemática de misevolución en 4 vías evolutivas:

### 1. Misevolución vía Self-Training del Modelo
- Self-generated data (AbsoluteZero) y self-generated curriculum (SEAgent)
- **Hallazgo**: Degradación consistente del safety alignment después del self-training
- Incluso sin datos explícitamente inseguros, el modelo pierde alineamiento
- "Catastrophic forgetting" de consciencia de riesgos: pierde capacidad de rechazar instrucciones dañinas

### 2. Misevolución vía Acumulación de Memoria
- La mera acumulación de memorias puede degradar el safety alignment
- **Dos formas**: safety alignment decay (degradación gradual) y deployment-time reward hacking (atajos desde la memoria que desalinean con objetivos reales)

### 3. Misevolución vía Herramientas
- **Creación y reutilización**: Los agentes crean herramientas con vulnerabilidades (inyección, credenciales hardcoded, falta de privacidad) y las reutilizan en contextos sensibles. Overall Unsafe Rate: **65.5%**
- **Ingestión de herramientas externas**: Los agentes no detectan código malicioso embebido en repos de GitHub. Refusal Rate máxima: solo **7.28%** (incluso Qwen3-235B)

### 4. Misevolución vía Optimización de Workflow
- La optimización de workflows multi-agente enfocada en rendimiento puede degradar la seguridad
- Refusal Rate cae de 36.3% a **5.6%** (-84.6%), ASR sube de 54.4% a **83.1%** (+52.8%)

### Mitigaciones propuestas
- **Modelo**: Safety post-training tras auto-evolución (parcialmente efectivo)
- **Memoria**: Instruir al agente a tratar memorias como "referencias" no "reglas" (parcialmente efectivo)
- **Herramientas**: Verificación de seguridad automatizada en dos etapas
- **Workflow**: Prompt de seguridad en nodos vulnerables
- **Conclusión general**: Ninguna mitigación restaura completamente la seguridad original

---

## Resultados Clave

- La misevolución afecta a **todos los modelos top-tier** evaluados, incluyendo Gemini-2.5-Pro
- **65.5%** de herramientas auto-creadas contienen vulnerabilidades
- Solo **7.28%** de repos maliciosos son rechazados incluso por el mejor modelo
- La optimización de workflow puede reducir la tasa de rechazo en **84.6%**
- Las mitigaciones propuestas son **insuficientes** para restaurar completamente la seguridad pre-evolución

---

## Contribuciones Principales

1. **Concepto de Misevolution**: Primera conceptualización y taxonomía sistemática de riesgos emergentes en agentes auto-evolutivos
2. **Evaluación empírica**: Evidencia de misevolución en 4 vías (modelo, memoria, herramientas, workflow) afectando modelos top-tier
3. **Llamada urgente**: Demuestra la necesidad de nuevos paradigmas de seguridad específicos para agentes auto-evolutivos, más allá del safety alignment estático

---

## Limitaciones

- Las mitigaciones propuestas son preliminares y reconocidas como insuficientes
- La evaluación se centra en riesgos identificables; la misevolución puede manifestarse de formas no anticipadas
- No se exploran mitigaciones a nivel de arquitectura (ej. restricciones formales en la evolución)

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We study the case where an agent's self-evolution deviates in unintended ways, leading to undesirable or even harmful outcomes. We refer to this as Misevolution. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> Temporal emergence: risks can emerge over time during self-evolution. Self-generated vulnerability: agents may generate new risks internally without an external adversary. Limited data control: the autonomous nature constrains data-level safety interventions. Expanded risk surface: evolution across multiple components creates an expanded risk surface. [#ffd400]

---

> [!quote] Resaltado (p. 5)
> A consistent safety decay across all models after self-training, which suggests that inherent safety alignment can be compromised through self-training, even when self-generated data contains no explicitly unsafe content. [#ffd400]

---

> [!quote] Resaltado (p. 6)
> Catastrophic forgetting of risk awareness: the initial agent would explicitly refuse harmful instructions, whereas the agent after self-evolution lost this refusal ability. [#ffd400]

---

> [!quote] Resaltado (p. 6)
> Two primary forms from memory evolution: safety alignment decay and deployment-time reward hacking. [#ffd400]

---

> [!quote] Resaltado (p. 8)
> Even agents powered by leading LLMs frequently create and reuse tools with vulnerabilities. Overall Unsafe Rate reached 65.5%. [#ffd400]

---

> [!quote] Resaltado (p. 8)
> Even the best-performing model achieved a Refusal Rate of only 7.28% for detecting malicious code in GitHub repos. [#ffd400]

---

> [!quote] Resaltado (p. 8)
> After workflow optimization, the Refusal Rate dropped from 36.3% to 5.6%, while the ASR rose from 54.4% to 83.1%. [#ffd400]

---

> [!quote] Resaltado (p. 9)
> None of the mitigations fully restore the model to its initial safety level. [#ffd400]

---

## Ideas y Conexiones

- Este paper es la **contraparte crítica** directa de [[Self-Evolving Agentic Reasoning]]: el survey describe las capacidades de la auto-evolución, este paper expone sus riesgos inherentes
- La taxonomía de misevolución (modelo, memoria, herramientas, workflow) mapea exactamente a las tres capas de evolución del survey (verbal/procedimental/estructural) + la dimensión de [[Collective Multi-Agent Reasoning]] (workflow)
- La misevolución vía memoria conecta directamente con [[Agentic Memory]]: la acumulación sin reflective feedback puede ser peligrosa, reforzando la importancia de [[Reflective Feedback]] y [[Reflexion]] como mecanismos de protección
- El hallazgo de que herramientas auto-creadas tienen 65.5% de vulnerabilidades es un desafío directo para [[Tool Use]] auto-evolutivo y para [[MemSkill]] (cuyas operaciones auto-evolutivas podrían también "misevolucionar")
- Conecta con los 6 problemas abiertos del survey: governance y seguridad son identificados como desafíos clave
- La pregunta "quién vigila al vigilante" en agentes auto-evolutivos es un problema abierto fundamental que ni MemEvolve ni MemSkill abordan

---

## Notas Relacionadas

- [[Self-Evolving Agentic Reasoning]] — Paradigma que este paper cuestiona (riesgos)
- [[Agentic Memory]] — Misevolución vía acumulación de memoria
- [[Reflective Feedback]] — Posible mecanismo de protección
- [[Tool Use]] — Misevolución vía creación de herramientas vulnerables
- [[Collective Multi-Agent Reasoning]] — Misevolución vía optimización de workflow
- [[zhangMemEvolveMetaEvolutionAgent2025]] — MemEvolve: auto-evolución de arquitectura (capacidades)
- [[zhangMemSkillLearningEvolving2026]] — MemSkill: auto-evolución de operaciones (capacidades)
- [[weiSurveyAgenticReasoning2026]] — Survey que identifica governance como problema abierto
- [[Misevolution]] — Nota de concepto
