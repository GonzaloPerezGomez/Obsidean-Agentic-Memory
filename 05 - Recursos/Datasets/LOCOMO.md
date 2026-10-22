---
titulo: "LOCOMO"
tags:
  - dataset
  - recurso
  - memory
  - conversational
  - long-term
aliases: ["LOCOMO Benchmark"]
fuente: "https://github.com/mem0ai/mem0"
fecha_creacion: "2026-10-22"
---

# LOCOMO

## Descripción

> Benchmark diseñado para evaluar la capacidad de retención, consolidación y recuperación de memoria a largo plazo en agentes conversacionales a lo largo de múltiples sesiones y diálogos prolongados (*long conversational memory*).

Pone a prueba si el sistema de memoria es capaz de recordar preferencias del usuario, resolver dependencias temporales y mantener coherencia factual sin procesar la totalidad del historial en bruto en la ventana de contexto.

## Características Principales

- **Evaluación en 4 tipos de preguntas:** Preguntas de un solo salto (*single-hop*), razonamiento de múltiples saltos (*multi-hop*), razonamiento temporal y consultas de dominio abierto.
- **Métrica:** Evaluación mediante LLM-as-a-Judge para calificar la factualidad, precisión y coherencia contextual.

## Papers que lo utilizan en la bóveda

- [[chhikaraMem0BuildingProductionReady2025]] — Evaluación de Mem0 y Mem0g, demostrando un 26% de mejora relativa frente a baselines comerciales con un 90% menos de coste en tokens.
