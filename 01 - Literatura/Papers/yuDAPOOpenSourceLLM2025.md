---
titulo: "DAPO: An Open-Source LLM Reinforcement Learning System at Scale"
autores: "Qiying Yu, Zheng Zhang, Ruofei Zhu, Yufeng Yuan, Xiaochen Zuo, Yu Yue, Weinan Dai, Tiantian Fan, Gaohong Liu, Lingjun Liu, Xin Liu, Haibin Lin, Zhiqi Lin, Bole Ma, Guangming Sheng, Yuxuan Tong, Chi Zhang, Mofan Zhang, Wang Zhang, Hang Zhu, Jinhua Zhu, Jiaze Chen, Jiangjie Chen, Chengyi Wang, Hongli Yu, Yuxuan Song, Xiangpeng Wei, Hao Zhou, Jingjing Liu, Wei-Ying Ma, Ya-Qin Zhang, Lin Yan, Mu Qiao, Yonghui Wu, Mingxuan Wang"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2503.14476"
citekey: "yuDAPOOpenSourceLLM2025"
zotero: "zotero://select/library/items/FWB5MNEZ"
tags:
  - paper
  - agentic-reasoning
  - RL
  - reasoning
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-05"
valoracion: ⭐⭐⭐⭐⭐
---

# DAPO: An Open-Source LLM Reinforcement Learning System at Scale

## Metadatos

- **Autores**: Qiying Yu et al. (35 autores; ByteDance / Tsinghua University)
- **Año**: 2025
- **Publicación**: arXiv preprint
- **DOI**: [10.48550/arXiv.2503.14476](https://doi.org/10.48550/arXiv.2503.14476)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/FWB5MNEZ)
- **Abstract**: Inference scaling empowers LLMs with unprecedented reasoning ability, with reinforcement learning as the core technique to elicit complex reasoning. However, key technical details of state-of-the-art reasoning LLMs are concealed (such as in OpenAI o1 blog and DeepSeek R1 technical report), thus the community still struggles to reproduce their RL training results. We propose the Decoupled Clip and Dynamic sAmpling Policy Optimization (DAPO) algorithm, and fully open-source a state-of-the-art large-scale RL system that achieves 50 points on AIME 2024 using Qwen2.5-32B base model.

---

## Resumen

DAPO (**Decoupled Clip and Dynamic sAmpling Policy Optimization**) es un algoritmo y sistema abierto de aprendizaje por refuerzo a gran escala para entrenar modelos de razonamiento (reasoning LLMs). Resuelve la falta de transparencia y los problemas de reproducibilidad de sistemas como OpenAI o1 y DeepSeek-R1, introduciendo cuatro técnicas clave de optimización sobre el framework `verl`. Con un modelo base Qwen2.5-32B, alcanza 50 puntos en AIME 2024, liberando completamente el código de entrenamiento, datasets curados y recetas técnicas.

---

## Problema / Motivación

Aunque el escalado en inferencia (test-time compute) mediante RL ha demostrado desencadenar capacidades avanzadas de razonamiento en LLMs (o1, DeepSeek-R1), la comunidad carece de los **detalles técnicos críticos** para reproducir estos resultados de forma estable a gran escala. Muchos intentos abiertos sufren de inestabilidad en el entrenamiento RL (colapso de políticas, sobre-optimización de longitud, ineficiencia muestral). Se requiere un marco reproducible, transparente y de código abierto para democratizar el entrenamiento post-training de reasoning models.

---

## Metodología

DAPO se basa en cuatro innovaciones técnicas centrales orientadas a estabilizar el RL a gran escala:

1. **Decoupled Clipping**: Desacopla el clipping de la política respecto a la ventaja y probabilidades relativas, evitando gradientes destructivos comunes en PPO tradicional sobre secuencias ultra-largas.
2. **Dynamic Sampling Policy Optimization**: Adapta la distribución del muestreo durante el entrenamiento para focalizar el cómputo en trayectorias con señales de recompensa informativas, evitando el estancamiento en ejemplos triviales o irresolubles.
3. **Optimización sobre framework verl**: Sistema de entrenamiento distribuido optimizado para soportar rollouts de cadenas de pensamiento extensas (long CoT) con baja latencia y alto rendimiento computacional.
4. **Curación de datasets y verifiabilidad**: Filtrado riguroso de problemas de matemáticas y razonamiento con verificación determinista de respuestas para funciones de recompensa exactas (outcome-based rewards).

---

## Resultados Clave

- **50 puntos en AIME 2024** partiendo de Qwen2.5-32B, situándose en la frontera de modelos abiertos de razonamiento matemático.
- Alta estabilidad durante el entrenamiento con ventanas de razonamiento extensas (sin el colapso común en PPO convencional).
- Liberación completa de código, pesos, datasets procesados y configuraciones reproducibles.

---

## Contribuciones Principales

1. **Algoritmo DAPO**: Innovación algorítmica con decoupled clipping y muestreo dinámico que estabiliza el RL para razonamiento complejo en LLMs.
2. **Sistema abierto a escala**: Infraestructura completa construida sobre `verl` que permite a la comunidad entrenar reasoning models a nivel SOTA.
3. **Transparencia y reproducibilidad**: Exposición detallada de hiperparámetros, dinámicas de entrenamiento y recetas de curación de datos ausentes en reportes propietarios.

---

## Limitaciones

- Alta demanda de infraestructura computacional (clusters de GPUs) para replicar el pipeline a escala completa de 32B.
- Diseñado principalmente para problemas con recompensas verificables (matemáticas y código), siendo menos directo de aplicar en tareas abiertas sin evaluador determinista.

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We propose the Decoupled Clip and Dynamic sAmpling Policy Optimization (DAPO) algorithm, and fully open-source a state-of-the-art large-scale RL system that achieves 50 points on AIME 2024 using Qwen2.5-32B base model. Unlike previous works that withhold training details, we introduce four key techniques of our algorithm that make large-scale LLM RL a success. [#ffd400]

---

## Ideas y Conexiones

- DAPO es el fundamento algorítmico utilizado por trabajos como [[yuMemAgentReshapingLongContext2026]] (MemAgent), donde se adaptó para optimizar agentes de memoria en contextos multi-conversación independientes.
- Comparte objetivo con [[GRPO]] (utilizado en DeepSeek-R1): ambos buscan alternativas eficientes a PPO para el entrenamiento de reasoning models, pero DAPO introduce clipping desacoplado y muestreo dinámico adaptativo.
- Encaja directamente en la dimensión transversal de [[Post-Training Reasoning]]: muestra cómo internalizar patrones de pensamiento paso a paso en los pesos del modelo mediante refuerzo guiado por recompensas objetivas.
- Es una pieza técnica indispensable para habilitar el andamiaje del [[Foundational Agentic Reasoning]] y [[Self-Evolving Agentic Reasoning]].

---

## Notas Relacionadas

- [[GRPO]] — Algoritmo de RL para razonamiento competidor/análogo
- [[Post-Training Reasoning]] — Paradigma de entrenamiento en el que opera DAPO
- [[yuMemAgentReshapingLongContext2026]] — Aplica y extiende DAPO para optimización de memoria
- [[weiSurveyAgenticReasoning2026]] — Survey que discute algoritmos de RL para razonamiento
- [[Chain of Thought]] — Patrón de razonamiento estimulado durante el RL
- [[DAPO]] — Nota de concepto
