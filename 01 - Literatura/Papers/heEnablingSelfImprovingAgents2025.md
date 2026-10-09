---
titulo: "Enabling Self-Improving Agents to Learn at Test Time With Human-In-The-Loop Guidance"
autores: "Yufei He, Ruoyu Li, Alex Chen, Yue Liu, Yulin Chen, Yuan Sui, Cheng Chen, Yi Zhu, Luca Luo, Frank Yang, Bryan Hooi, Saloni Potdar, Lina Rojas-Barahona, Sebastien Montella"
año: "2025"
fuente: ""
DOI: "10.18653/v1/2025.emnlp-industry.115"
citekey: "heEnablingSelfImprovingAgents2025"
zotero: "zotero://select/library/items/FVK7BX9Y"
tags:
  - paper
  - agentic-reasoning
  - human-in-the-loop
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-09"
valoracion: ⭐⭐⭐⭐
---

# Enabling Self-Improving Agents to Learn at Test Time With Human-In-The-Loop Guidance

## Metadatos

- **Autores**: Yufei He, Ruoyu Li, Alex Chen, Yue Liu, Yulin Chen, Yuan Sui, Cheng Chen, Yi Zhu, Luca Luo, Frank Yang, Bryan Hooi, Saloni Potdar, Lina Rojas-Barahona, Sebastien Montella
- **Año**: 2025
- **Publicación**: EMNLP Industry Track
- **DOI**: [10.18653/v1/2025.emnlp-industry.115](https://doi.org/10.18653/v1/2025.emnlp-industry.115)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/FVK7BX9Y)
- **Abstract**: LLM agents struggle in environments where rules and required domain knowledge frequently change. We propose the Adaptive Reflective Interactive Agent (ARIA), an LLM framework designed to continuously learn updated domain knowledge at test time. ARIA assesses its own uncertainty through structured self-dialogue, proactively identifying knowledge gaps and requesting targeted explanations from human experts.

---

## Resumen

ARIA (Adaptive Reflective Interactive Agent) es un agente diseñado para entornos industriales donde el conocimiento de dominio cambia rápidamente (ej. cumplimiento regulatorio). Mediante un diálogo interno estructurado, evalúa su propia incertidumbre; si detecta huecos de conocimiento o baja confianza, interrumpe la ejecución para solicitar proactivamente guía a un humano experto. Esta corrección se integra en un repositorio de conocimiento interno estructurado con marcas de tiempo, actualizando sus reglas y adaptándose al instante (test-time learning).

---

## Problema / Motivación

En dominios del mundo real como cumplimiento regulatorio y screening de riesgos (ej. control de usuarios en plataformas de pago), las reglas de negocio, regulaciones y definiciones cambian constantemente. Los modelos estáticos (incluso con RAG) se vuelven obsoletos rápidamente. El fine-tuning continuo es costoso e impráctico. Se necesita un agente que pueda: 1) saber cuándo no sabe, 2) pedir ayuda a humanos solo cuando es estrictamente necesario, y 3) asimilar esa nueva regla al instante para casos futuros, sin requerir re-entrenamiento.

---

## Metodología

El framework ARIA opera en un flujo interactivo:

1. **Structured Self-Dialogue (Evaluación de Incertidumbre)**:
   - Ante una tarea, ARIA genera un juicio preliminar.
   - Aplica preguntas reflexivas para interrogar su propia base de conocimiento y el nivel de confianza de su razonamiento.
2. **Intelligent Guidance Solicitation (Petición de Ayuda Proactiva)**:
   - Si la incertidumbre es alta, el agente redacta preguntas dirigidas a un experto humano para aclarar ambigüedades.
3. **Human-Guided Knowledge Adaptation (Actualización)**:
   - Recibe la corrección, explicación detallada o actualización de la regla del humano.
   - Incorpora la información en un Repositorio de Conocimiento estructurado, marcando la entrada con *timestamps*.
   - Si encuentra entradas contradictorias (ej. la regla vieja vs la nueva), utiliza el matching semántico y la marca de tiempo para resolver el conflicto y descartar la obsoleta.

---

## Resultados Clave

- Rendimiento superior a baselines que utilizan fine-tuning offline estándar o agentes auto-evolutivos puramente autónomos.
- Capacidad demostrada para adaptarse a reglas dinámicas en el dataset realista Customer Due Diligence (CDD).
- **Despliegue Industrial**: ARIA ha sido desplegado exitosamente en el sistema de screening de nombres de *TikTok Pay*, plataforma con más de 150 millones de usuarios activos mensuales.

---

## Contribuciones Principales

1. **Self-Dialogue Estructurado**: Un método confiable para la estimación de incertidumbre que reduce peticiones innecesarias al experto.
2. **Mecanismo Test-time Learning HIL**: Cierre del ciclo entre descubrimiento de incertidumbre, corrección humana e integración en memoria.
3. **Validación a escala industrial**: Prueba empírica en un sistema real de cumplimiento de pagos masivo.

---

## Limitaciones

- Requiere disponibilidad asíncrona o síncrona de expertos humanos en el bucle (Human-in-the-Loop), lo cual tiene costo asociado.
- La fiabilidad a largo plazo del repositorio de conocimiento frente a miles de reglas contradictorias podría ser un cuello de botella si no se introducen mecanismos de poda complejos.

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> ARIA assesses its own uncertainty through structured selfdialogue, proactively identifying knowledge gaps and requesting targeted explanations or corrections from human experts. It then systematically updates an internal, timestamped knowledge repository with provided human guidance, detecting and resolving conflicting or outdated knowledge through comparisons and clarification queries. [#ffd400]

---

> [!quote] Resaltado (p. 2)
> It incorporates these human-provided knowledge inputs into a structured knowledge repository that marks each knowledge item with timestamps. Whenever a new knowledge update occurs, ARIA retrieves related entries by semantic matching in its repository and compares them against the new information. [#ffd400]

---

## Ideas y Conexiones

- ARIA aborda directamente la dimensión **Human-In-The-Loop** en la memoria agéntica. Todo el marco del survey [[weiSurveyAgenticReasoning2026]] asume evolución *autónoma* (self-evolving), pero ARIA demuestra que la co-evolución agente-humano es mucho más viable para compliance empresarial.
- La resolución de conflictos de memoria mediante *timestamps* es un mecanismo elegante para manejar entornos no estacionarios, lo que conecta con el problema abierto número 3 del survey: "Cómo entrenar en entornos no estacionarios".
- Se alinea con enfoques de memoria estructurada ([[Agentic Memory]]) al formalizar un knowledge repository donde se audita el origen y la fecha de cada regla.

---

## Notas Relacionadas

- [[Agentic Memory]] — Memoria actualizada y versionada
- [[Metacognición en Agentes]] — Capacidad de estimar incertidumbre propia
- [[weiSurveyAgenticReasoning2026]] — Entornos no estacionarios
