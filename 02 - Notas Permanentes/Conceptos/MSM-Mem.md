---
titulo: "MSM-Mem"
tags:
  - concepto
  - agentic-reasoning
  - memoria
  - multimodal
  - clinical
aliases: ["Medical Structured Multimodal Memory"]
fecha_creacion: "2026-10-20"
---

# MSM-Mem

## Definición

> Framework de **memoria agéntica multimodal estructurada** para agentes médicos de inteligencia artificial que organiza las experiencias clínicas en tres almacenes complementarios —**memoria semántica ($M_S$), episódica ($M_E$) y visual ($M_V$)**— y se actualiza de forma incremental durante la inferencia para posibilitar el aprendizaje continuo a partir de la práctica.

## Explicación

La mayoría de los agentes médicos basados en modelos de lenguaje multimodal (MLLM) operan como sistemas sin estado (*stateless*): atienden cada consulta como si fuera la primera, sin acumular intuición diagnóstica ni recordar el historial previo de un paciente a través de visitas sucesivas. En contraste, un médico humano perfecciona continuamente su pericia contrastando la evolución histórica del enfermo con recuerdos de casos previos y patrones visuales reconocibles.

MSM-Mem cierra esta brecha modelando tres tipos de evidencia clínica estructurada:
1. **Memoria Semántica ($M_S$)**: Sintetiza resúmenes longitudinales del estado del paciente agregando deterministamente hallazgos pasados.
2. **Memoria Episódica ($M_E$)**: Registra trayectorias completas de razonamiento (evidencia observada $\rightarrow$ deliberación $\rightarrow$ decisión tomada) en encuentros previos.
3. **Memoria Visual ($M_V$)**: Retiene representaciones vectoriales compactas y prototipos de imágenes clínicas (como radiografías), permitiendo comparar de forma análoga nuevos estudios por imágenes con patologías encontradas con anterioridad.

Al actualizar estos tres componentes durante la propia inferencia, el agente no requiere re-entrenar sus parámetros para volverse progresivamente más preciso con el uso continuado.

---

## Contexto

Introducido por Jabin et al., MSM-Mem sitúa la memoria multimodal en el centro del desarrollo de agentes en salud. Conecta la noción de memoria médica con la arquitectura de [[Agentic Memory]] y los principios de aprendizaje continuo no paramétrico durante el tiempo de despliegue (*test-time adaptation*).

---

## Relación con otros conceptos

- **Requiere**: Modelos de lenguaje multimodal (MLLM) y encoders visuales
- **Relacionado con**: [[Agentic Memory]], [[MIRIX]], [[ClinicalAgents]]
- **Componentes**: Memoria semántica ($M_S$), episódica ($M_E$) y visual ($M_V$)
- **Se enmarca en**: [[Self-Evolving Agentic Reasoning]]

---

## Referencias

- [[jabinMSMMemUniversalMedical2019]] — Paper original de MSM-Mem
- [[weiSurveyAgenticReasoning2026]] — Survey de razonamiento agéntico y memoria
