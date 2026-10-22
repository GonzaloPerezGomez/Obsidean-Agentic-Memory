---
titulo: "Evo-Memory Benchmark"
tags:
  - dataset
  - recurso
  - memory
  - benchmark
  - streaming
fuente: "https://github.com/Evo-Memory/Evo-Memory"
fecha_creacion: "2026-10-22"
---

# Evo-Memory Benchmark

## Descripción

> Primer benchmark comprensivo de secuencias continuas de tareas (*streaming task streams*) diseñado para evaluar sistemáticamente la capacidad de los agentes LLM para aprender, adaptar y evolucionar su memoria a lo largo del tiempo (*test-time evolution*).

A diferencia de las evaluaciones estáticas donde la memoria se recupera pasivamente de un diálogo fijo, Evo-Memory estructura tareas en flujos secuenciales donde el agente debe procesar la tarea $t$, interactuar, recibir retroalimentación, actualizar su memoria y aplicar ese aprendizaje a la tarea $t+1$.

## Características Principales

- **Unificación:** Estandariza la evaluación de más de 10 arquitecturas de memoria previas en la literatura.
- **Diversidad:** Transforma datasets heterogéneos de preguntas y respuestas, razonamiento algorítmico y tareas orientadas a objetivos en flujos continuos.
- **Baselines y Framework:** Propone **ExpRAG** (recuperación pasiva de experiencias) y **ReMem** (bucle unificado de acción, pensamiento y razonamiento sobre memoria).

## Papers que lo utilizan en la bóveda

- [[weiEvoMemoryBenchmarkingLLM2026]] — Paper fundacional que introduce el benchmark.
- [[weiSurveyAgenticReasoning2026]] — Marco teórico del razonamiento agéntico auto-evolutivo.
