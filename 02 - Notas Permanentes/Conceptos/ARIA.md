---
titulo: "ARIA"
tags:
  - concepto
  - agentic-reasoning
  - human-in-the-loop
aliases: ["Adaptive Reflective Interactive Agent"]
fecha_creacion: "2026-10-09"
---

# ARIA

## Definición

> Framework de agente LLM (Adaptive Reflective Interactive Agent) que integra **test-time learning y human-in-the-loop (HIL)** mediante un diálogo interno para estimar su propia incertidumbre y solicitar proactivamente correcciones a humanos expertos, asimilando este nuevo conocimiento en un repositorio versionado temporalmente.

## Explicación

A diferencia de agentes completamente autónomos, ARIA reconoce que en entornos empresariales altamente volátiles (como el cumplimiento regulatorio o screening de riesgos), el agente inevitablemente se enfrentará a reglas cambiantes que no figuran en su entrenamiento. Mediante **Self-Dialogue**, ARIA examina su razonamiento para detectar lagunas. Si la confianza es baja, genera preguntas dirigidas al experto humano. Cuando recibe la respuesta, en lugar de aplicarla solo a la tarea actual, la consolida en una base de memoria agéntica con una marca de tiempo (*timestamp*). Si la nueva regla contradice una anterior recuperada semánticamente, la marca de tiempo dictamina su primacía. Esto permite al agente actualizar su política operativa instantáneamente, resolviendo contradicciones dinámicas sin requerir un re-entrenamiento del modelo.

---

## Contexto

ARIA demuestra la viabilidad industrial del test-time learning, estando desplegado en el servicio de screening de TikTok Pay. Representa una solución híbrida dentro del [[Self-Evolving Agentic Reasoning]]: mientras el agente automatiza la abstracción y gestión de memoria, confía en el humano como la fuente de verdad del entorno dinámico.

---

## Relación con otros conceptos

- **Requiere**: [[Metacognición en Agentes]] (para calibrar incertidumbre)
- **Relacionado con**: [[Agentic Memory]], Human-in-the-loop
- **Aplicación**: Manejo de entornos no estacionarios (Non-stationary environments)

---

## Referencias

- [[heEnablingSelfImprovingAgents2025]] — Paper original (EMNLP Industry)
