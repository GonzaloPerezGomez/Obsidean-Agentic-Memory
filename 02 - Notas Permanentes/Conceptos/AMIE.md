---
titulo: "AMIE"
tags:
  - concepto
  - agentic-reasoning
  - clinical
  - human-in-the-loop
aliases: ["Articulate Medical Intelligence Explorer"]
fecha_creacion: "2026-10-22"
---

# AMIE

## Definición

> Sistema de inteligencia artificial conversacional (Articulate Medical Intelligence Explorer) basado en LLM optimizado para el **razonamiento diagnóstico diferencial (DDx)** clínico interactivo, diseñado tanto para operar de forma autónoma como para actuar como herramienta asistencial para facultativos médicos.

## Explicación

El diagnóstico diferencial es el proceso cognitivo mediante el cual un médico analiza los síntomas, antecedentes y pruebas de un paciente para generar una lista priorizada de posibles enfermedades causantes. AMIE fue desarrollado por Google Research y DeepMind con una arquitectura entrenada específicamente para estructurar este diálogo médico: interroga proactivamente, solicita aclaraciones sobre síntomas atípicos y formula listas diferenciales graduadas. 

En su validación clínica publicada en *Nature*, AMIE demostró no solo superar a médicos generalistas cuando opera en solitario, sino que al integrarse en la consulta humana eleva de forma estadísticamente significativa la precisión y exhaustividad diagnóstica de los facultativos frente a herramientas convencionales (como motores de búsqueda o manuales médicos). Esto establece un precedente metodológico para el paradigma *Human-in-the-Loop* en medicina, demostrando que el mayor valor de los agentes no reside necesariamente en sustituir al clínico, sino en mitigar sesgos cognitivos humanos (como el cierre prematuro del diagnóstico) y ampliar la cobertura diagnóstica de casos complejos.

---

## Contexto

AMIE constituye el estándar metodológico en la literatura médica reciente para la evaluación controlada de agentes en diagnóstico. Se relaciona estrechamente con el enfoque de colaboración humano-máquina y con arquitecturas de deliberación clínica como [[ClinicalAgents]], así como con bancos de pruebas interactivos como [[AgentClinic]].

---

## Relación con otros conceptos

- **Requiere**: Modelos de lenguaje ajustados al dominio biomédico y diálogo clínico
- **Relacionado con**: [[ClinicalAgents]], [[AgentClinic]], Human-in-the-Loop
- **Se evalúa en**: Diagnóstico diferencial (DDx), estudios aleatorizados con clínicos

---

## Referencias

- [[mcduffAccurateDifferentialDiagnosis2025]] — Paper de validación clínica de AMIE en Nature (2025)
