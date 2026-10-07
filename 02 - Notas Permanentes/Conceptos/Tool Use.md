---
titulo: "Tool Use"
tags:
  - concepto
  - agentic-reasoning
aliases: ["Uso de Herramientas", "Tool-Use Optimization"]
fecha_creacion: "2026-09-29"
---

# Tool Use

## Definición

> Capacidad de un agente para **aumentar sus habilidades intrínsecas invocando inteligentemente módulos externos** (APIs, buscadores, intérpretes de código), razonando sobre cuándo usar una herramienta, cuál seleccionar y cómo generar la llamada correcta.

## Explicación

El uso de herramientas permite a los agentes superar limitaciones como conocimiento desactualizado, imprecisión en cálculos y falta de acceso a información privada. Se organiza en tres estilos: **in-context integration** (métodos training-free como ReAct que intercalan razonamiento y acción mediante prompting), **post-training integration** (primero SFT para bootstrapping de competencia básica, luego RL para dominio adaptativo y generalizable), y **orchestration-based integration** (coordinación de múltiples herramientas mediante planificación, secuenciación y gestión de dependencias, como en HuggingGPT y TaskMatrix.AI). El nivel más avanzado incluye la capacidad emergente de los agentes para *crear* nuevas herramientas cuando las existentes son insuficientes.

---

## Contexto

Es uno de los tres componentes fundamentales del [[Foundational Agentic Reasoning]]. Su evolución (self-evolving tool use) incluye la síntesis autónoma de herramientas, donde el agente actúa como programador creando nuevas herramientas ante problemas no resueltos por el toolset existente.

---

## Relación con otros conceptos

- **Requiere**: [[Planning]], [[In-Context Reasoning]] o [[Post-Training Reasoning]]
- **Relacionado con**: [[ReAct]], [[Foundational Agentic Reasoning]]
- **Se evoluciona en**: [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[weiSurveyAgenticReasoning2026]] — Sección 3.2: Tool-Use Optimization
