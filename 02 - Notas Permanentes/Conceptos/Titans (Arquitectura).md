---
titulo: "Titans (Arquitectura)"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - arquitectura
aliases: ["Titans", "Neural Long-Term Memory", "Memoria Neural a Largo Plazo"]
fecha_creacion: "2026-10-02"
---

# Titans (Arquitectura)

## Definición

> Familia de arquitecturas neurales que combina **atención como memoria a corto plazo** con un **módulo de memoria neural a largo plazo** que aprende a memorizar contexto histórico en tiempo de test, permitiendo escalar a ventanas de más de 2 millones de tokens sin coste cuadrático.

## Explicación

Titans resuelve una tensión fundamental en el procesamiento de secuencias: la atención modela dependencias exactas pero tiene coste cuadrático (limitando el contexto), mientras que los modelos recurrentes comprimen eficientemente el pasado pero pierden información. La innovación clave es un módulo de **memoria neural** que funciona como red que aprende a memorizar durante la inferencia (test-time training): procesa bloques de tokens, actualiza su estado interno priorizando datos "sorprendentes" (alta pérdida), y proporciona una representación comprimida y persistente del contexto pasado. La atención se encarga del contexto inmediato (short-term memory) mientras que el módulo neural gestiona el largo plazo (long-term memory). Esta dualidad se inspira en la distinción cognitiva entre memoria de trabajo y memoria a largo plazo en humanos. Los autores proponen tres variantes de integración: memoria como contexto (MAC), como gate (MAG) y como capa (MAL).

---

## Contexto

Titans opera a nivel de **arquitectura interna del modelo** — es decir, la memoria es parte de los cómputos del propio LLM, no un sistema externo. Esto lo diferencia fundamentalmente de los enfoques de [[Agentic Memory]] externos como [[HippoRAG]] (knowledge graphs), Mem0 (hechos extraídos), [[Mind-Map Agent]] (grafos de razonamiento) o [[MemOS]] (sistema operativo de memoria). En la taxonomía de MemOS, Titans se situaría en la capa de **activation memory** — estados intermedios que persisten y evolucionan durante la inferencia. La capacidad de memorizar en test-time sin actualizar los pesos del modelo base lo alinea con el paradigma de [[In-Context Reasoning]]: escalar cómputo en inferencia para mejorar capacidades.

---

## Relación con otros conceptos

- **Requiere**: Mecanismo de atención, módulos recurrentes
- **Relacionado con**: [[Agentic Memory]], [[In-Context Reasoning]], [[MemOS]] (activation memory)
- **Complementario a**: [[HippoRAG]] (memoria externa documental), [[Mind-Map Agent]] (memoria externa de razonamiento)
- **Se inspira en**: Psicología cognitiva (working memory vs. long-term memory)

---

## Referencias

- [[behrouzTitansLearningMemorize2024]] — Paper que introduce Titans
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza tipos de memoria
