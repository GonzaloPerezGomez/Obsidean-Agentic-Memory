---
titulo: "AgentClinic Benchmark"
tags:
  - dataset
  - recurso
  - clinical
  - multimodal
  - interactive
  - simulation
fuente: "https://github.com/SamuelSchmidgall/AgentClinic"
fecha_creacion: "2026-10-22"
---

# AgentClinic Benchmark

## Descripción

> Entorno de simulación clínica interactiva diseñado para evaluar agentes médicos en procesos de toma de decisiones secuenciales bajo información incompleta, donde deben dialogar activamente con pacientes simulados, ordenar analíticas y utilizar herramientas.

A diferencia de los cuestionarios estáticos, los casos en AgentClinic se despliegan en un entorno interactivo con 4 roles de agentes (Doctor, Paciente, Medición y Moderador).

## Características Principales

- **Cobertura de Casos:**
  - 260 pacientes en 9 especialidades médicas.
  - 120 agentes multimodales (con imágenes diagnósticas reales).
  - 215 agentes de texto basados en viñetas USMLE.
  - 749 casos clínicos multilingües en 7 idiomas.
- **Datos Reales:** Integración con Historias Clínicas Electrónicas (EHR).
- **Herramientas evaluadas:** Acceso a manuales médicos, navegación web, ciclos de reflexión y cuaderno de notas persistente (*notebook tool*).
- **Métricas:** Exactitud en decisiones secuenciales, eficiencia en pruebas ordenadas, empatía comunicativa y resistencia a sesgos cognitivos clínicos.

## Papers que lo utilizan en la bóveda

- [[schmidgallAgentClinicMultimodalAgent2025]] — Paper fundacional que introduce AgentClinic.
