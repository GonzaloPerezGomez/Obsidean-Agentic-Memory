---
titulo: "AgentClinic"
tags:
  - concepto
  - agentic-reasoning
  - benchmarks
  - multimodal
  - clinical
aliases: ["AgentClinic Benchmark"]
fecha_creacion: "2026-10-22"
---

# AgentClinic

## Definición

> Benchmark y entorno de simulación clínica interactiva diseñado para evaluar **agentes LLM y multimodales en procesos de decisión secuencial**, donde deben interrogar a pacientes simulados, ordenar pruebas médicas bajo información incompleta y emplear herramientas externas en múltiples especialidades e idiomas.

## Explicación

Tradicionalmente, los modelos de lenguaje médico se evaluaban mediante exámenes tipo test de opción múltiple (como MedQA), donde el modelo recibe de antemano toda la historia clínica procesada y resumida en el enunciado. AgentClinic revoluciona esta metodología al plantear la evaluación como una consulta médica real interactiva. El entorno se estructura mediante cuatro agentes especializados: un **Doctor Agent** (el LLM a prueba), un **Patient Agent** (que responde al interrogatorio revelando datos sólo si se le pregunta), un **Measurement Agent** (que actúa como laboratorio o servicio de radiología) y un **Moderator**.

Bajo este esquema, el agente evaluado debe decidir activamente qué preguntas formular, qué pruebas diagnósticas solicitar y cómo interpretar imágenes clínicas reales mientras gestiona recursos e interactúa con herramientas agénticas (navegación, reflexión y cuadernos de notas persistentes). La dificultad añadida del entorno secuencial revela que modelos con puntuaciones superiores al 80% en tests estáticos sufren caídas drásticas de precisión diagnóstica cuando deben recopilar la evidencia por sí mismos. Además, AgentClinic permite medir dimensiones inéditas como la empatía, el coste de las pruebas ordenadas innecesariamente y la resistencia a sesgos cognitivos médicos.

---

## Contexto

Desarrollado por investigadores de Stanford y Johns Hopkins, AgentClinic es el benchmark de referencia para la evaluación de agentes clínicos en entornos interactivos dinámicos, complementando a benchmarks de memoria auto-evolutiva como [[Evo-Memory]] y a benchmarks médicos estáticos de nivel subespecialista como [[MedXpertQA]].

---

## Relación con otros conceptos

- **Mide a**: Agentes clínicos, toma de decisiones secuencial, uso de herramientas
- **Estructura**: Entorno multi-agente (Doctor, Paciente, Medición, Moderador)
- **Relacionado con**: [[ClinicalAgents]], [[Evo-Memory]], [[MedXpertQA]], [[Agentic Memory]]

---

## Referencias

- [[schmidgallAgentClinicMultimodalAgent2025]] — Paper original de AgentClinic
