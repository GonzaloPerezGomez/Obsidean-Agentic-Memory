
# Tareas

1. Buscar papers de agentic memory en medicina
2. Revisar metodos de evaluación 
	1. Propuesta en [[0_evaluacion_arbol_decision.svg]]
3. Proponer arquitectura de memoria
	1. Empezar con una memoria simple en texto plano para pruebas
	2. Mas tarde poner alomejor un KG con timestamps
	3. Memoria a corto y largo plazo (?)
4. Definir un baseline para la evaluacion
	1. LLM in-context zero-shot
	2. LLM in-context few-shot
	3. Agente con memoria simple (texto plano)
	4. Agente con KG


Si tengo tiempo de sobra

1. Mirar maneras de preprocesar el dataset
2. Probar alguna implementación sencilla para hacer pruebas


Papers de importancia

[[geClinicalAgentsMultiAgentOrchestration2026]]
[[schmidgallAgentClinicMultimodalAgent2025]]
[[mcduffAccurateDifferentialDiagnosis2025]]


# Metodos de evaluacion usados en la literatura

### **3. Síntesis y Tendencias Clave**

De este análisis conjunto surgen **cuatro conclusiones metodológicas esenciales**:

1. **El agotamiento del QA médico estático:** Datasets como MedQA han quedado obsoletos para discriminar modelos de frontera. O bien se eleva la dificultad técnica a nivel de subespecialidad médica ([[MedXpertQA]]), o se evalúa la consulta como un proceso de recolección activa de datos con información oculta ([[AgentClinic]]).
2. **La métrica del IoU para toma de decisiones agénticas:** En tareas de solicitud de pruebas o prescripción de tratamientos ([[geClinicalAgentsMultiAgentOrchestration2026]]), la precisión simple no basta. El **IoU (_Intersection over Union_)** se consolida como el estándar para penalizar tanto la omisión de pruebas críticas como el sobrediagnóstico innecesario.
3. **El valor real de la memoria externa y el razonamiento en tiempo de inferencia:** [[schmidgallAgentClinicMultimodalAgent2025]] demostró empíricamente que un cuaderno persistente inter-casos eleva el rendimiento de modelos abiertos hasta en un 92% (conectando directamente con [[Dynamic Cheatsheet]] y [[Agentic Memory]]), mientras que [[zuoMedXpertQABenchmarkingExpertLevel2025]] y [[geClinicalAgentsMultiAgentOrchestration2026]] ratifican que los modelos de razonamiento profundo (MCTS o _test-time compute_) dominan cuando la medicina deja de ser lineal.
4. **Human-in-the-Loop como árbitro definitivo:** Aunque LLM-as-a-Judge es indispensable para escalar la evaluación en miles de casos sintéticos, el estudio de [[mcduffAccurateDifferentialDiagnosis2025]] en _Nature_ fija el patrón oro: la métrica de éxito de un agente médico debe ser el **beneficio neto que aporta al clínico humano** (ampliar el diagnóstico diferencial y evitar el cierre prematuro) frente al uso de herramientas tradicionales.
