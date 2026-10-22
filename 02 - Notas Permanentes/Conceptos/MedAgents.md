---
titulo: "MedAgents"
tags:
  - concepto
  - agentic-reasoning
  - multi-agent
  - clinical
aliases: ["MedAgents Framework"]
fecha_creacion: "2026-10-22"
---

# MedAgents

## Definición

> Framework *training-free* de **colaboración multidisciplinar multi-agente** para el razonamiento médico en zero-shot, que simula comités clínicos colegiados donde múltiples agentes asumen roles de especialistas para deliberar y alcanzar consensos diagnósticos iterativos.

## Explicación

El conocimiento médico se encuentra compartimentado en múltiples subdisciplinas interdependientes (farmacología, patología, medicina interna, cirugía). Cuando un modelo monolítico se enfrenta a un problema clínico complejo, suele sufrir de sesgos de focalización o cometer errores al pasar por alto interacciones biológicas o contraindicaciones farmacológicas sutiles.

MedAgents supera esta barrera trasladando a la inteligencia artificial el funcionamiento de las comisiones clínicas de expertos de los hospitales. El framework opera en 5 etapas secuenciales: 1) selecciona automáticamente las especialidades relevantes según la consulta; 2) cada agente especialista elabora un análisis inicial independiente desde su prisma disciplinar; 3) se sintetizan las aportaciones en un informe global; 4) los especialistas participan en un debate multi-ronda estructurado donde critican argumentos contrarios, corrigen premisas erróneas de sus colegas y negocian discrepancias; y 5) el comité emite una decisión diagnóstica consensuada. Este enfoque permite extraer pericia médica latente en los pesos del LLM sin requerir fine-tuning ni bases de datos externas adicionales.

---

## Contexto

Desarrollado en la Universidad de Yale por Tang et al. (2024), MedAgents es un exponente representativo de la Capa 3 ([[Collective Multi-Agent Reasoning]]) en dominios científicos especializados. Demuestra que la discusión multi-agente deliberativa supera tanto al razonamiento directo como al prompting estándar con [[Chain of Thought]] y Self-Consistency.

---

## Relación con otros conceptos

- **Requiere**: [[Multi-Agent Systems]], role-playing especializado
- **Se enmarca en**: [[Collective Multi-Agent Reasoning]]
- **Relacionado con**: [[ClinicalAgents]], Multi-Agent Debate
- **Opuesto a**: Razonamiento monomodelo unidisciplinar estático

---

## Referencias

- [[tangMedAgentsLargeLanguage2024]] — Paper que presenta MedAgents
- [[weiSurveyAgenticReasoning2026]] — Survey que sistematiza la colaboración multi-agente
