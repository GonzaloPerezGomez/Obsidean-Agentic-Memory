---
titulo: "Evo-Memory"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - benchmarks
aliases: ["ReMem", "ExpRAG"]
fecha_creacion: "2026-10-09"
---

# Evo-Memory

## Definición

> Benchmark y framework unificado para evaluar las capacidades de **memoria auto-evolutiva (self-evolving memory)** y el **test-time learning** en agentes LLM que operan sobre secuencias continuas de tareas (task streams).

## Explicación

Antes de Evo-Memory, la investigación en memoria para LLMs se evaluaba mediante inyección de texto masivo en un prompt o recuperación estática (RAG), asumiendo un entorno conversacional inamovible (ej. "encontrar la aguja en el pajar"). Evo-Memory cambia el paradigma reestructurando datasets para imitar interacciones del mundo real: el agente recibe una tarea, genera una respuesta, recibe feedback, y debe **extraer y actualizar su base de memoria** antes de enfrentarse a la siguiente tarea. El benchmark compila y unifica más de 10 arquitecturas distintas. Adicionalmente, los autores introducen **ExpRAG**, un modelo base de recuperación de experiencias previas, y **ReMem**, una política de decisión superior que entrelaza la toma de acción y el razonamiento con la reestructuración deliberada de la memoria, tratando a la gestión de memoria como una deducción agéntica primaria de alto nivel.

---

## Contexto

Desarrollado por el mismo grupo (Tianxin Wei et al.) responsable de establecer la taxonomía fundacional del [[Self-Evolving Agentic Reasoning]]. Este benchmark actúa como la plataforma métrica estándar para probar si un modelo realmente se adapta *entre episodios*, revelando que incluso modelos lógicamente potentes son muy frágiles a la hora de discernir *qué* abstraer y recordar de sus interacciones.

---

## Relación con otros conceptos

- **Mide a**: [[Agentic Memory]], [[Self-Evolving Agentic Reasoning]]
- **Relacionado con**: [[ReAct]] (en el que se basa ReMem), [[Dynamic Cheatsheet]] (evalúa capacidades similares a lo largo de un stream)
- **Alternativa a**: Evaluaciones de memoria plana (LongBench, Needle-in-a-Haystack)

---

## Referencias

- [[weiEvoMemoryBenchmarkingLLM2026]] — Paper que introduce el benchmark
- [[weiSurveyAgenticReasoning2026]] — Marco teórico subyacente
