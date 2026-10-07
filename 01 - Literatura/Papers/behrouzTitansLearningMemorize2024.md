---
titulo: "Titans: Learning to Memorize at Test Time"
autores: "Ali Behrouz, Peilin Zhong, Vahab Mirrokni"
año: "2024"
fuente: ""
DOI: "10.48550/arXiv.2501.00663"
citekey: "behrouzTitansLearningMemorize2024"
zotero: "zotero://select/library/items/EBSYJQLK"
tags:
  - paper
  - agentic-reasoning
  - memoria
  - arquitectura
estado: "#estado/en-progreso"
fecha_lectura: "2026-10-02"
valoracion: ⭐⭐⭐⭐
---

# Titans: Learning to Memorize at Test Time

## Metadatos

- **Autores**: Ali Behrouz, Peilin Zhong, Vahab Mirrokni
- **Año**: 2024
- **Publicación**: arXiv preprint (Google Research)
- **DOI**: [10.48550/arXiv.2501.00663](https://doi.org/10.48550/arXiv.2501.00663)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/EBSYJQLK)
- **Abstract**: Over more than a decade there has been an extensive research effort on how to effectively utilize recurrent models and attention. While recurrent models aim to compress the data into a fixed-size memory (called hidden state), attention allows attending to the entire context window, capturing the direct dependencies of all tokens. This more accurate modeling of dependencies, however, comes with a quadratic cost, limiting the model to a fixed-length context. We present a new neural long-term memory module that learns to memorize historical context and helps attention to attend to the current context while utilizing long past information. We show that this neural memory has the advantage of fast parallelizable training while maintaining a fast inference. From a memory perspective, we argue that attention due to its limited context but accurate dependency modeling performs as a short-term memory, while neural memory due to its ability to memorize the data, acts as a long-term, more persistent, memory. Based on these two modules, we introduce a new family of architectures, called Titans, and present three variants to address how one can effectively incorporate memory into this architecture.

---

## Resumen

Titans propone una **nueva familia de arquitecturas** que combina atención (como memoria a corto plazo) con un módulo de **memoria neural a largo plazo** que aprende a memorizar en tiempo de test. El módulo de memoria comprime el contexto histórico de forma persistente, mientras la atención se centra en el contexto inmediato. Esto permite escalar a ventanas de más de 2M tokens con entrenamiento paralelizable e inferencia rápida, superando tanto a Transformers como a modelos lineales recurrentes.

---

## Problema / Motivación

Existe una tensión fundamental entre dos paradigmas de procesamiento secuencial: los **modelos recurrentes** comprimen datos en un estado oculto de tamaño fijo (memoria eficiente pero pierde información), mientras que la **atención** captura dependencias exactas de todos los tokens (precisa pero con coste cuadrático que limita el contexto). Ninguno de los dos resuelve el problema de combinar modelado preciso de dependencias locales con retención de información a largo plazo de forma eficiente. Los Transformers están limitados a ventanas de contexto fijas, lo que impide el procesamiento de secuencias extremadamente largas.

---

## Metodología

La arquitectura Titans se basa en dos módulos complementarios, conceptualizados desde la perspectiva de la memoria:

### Módulo de Atención (Memoria a Corto Plazo)
- Atención estándar que opera sobre la **ventana de contexto actual**
- Modelado preciso de dependencias pero limitado en alcance temporal
- Análogo a la memoria de trabajo (working memory) en humanos

### Módulo de Memoria Neural (Memoria a Largo Plazo)
- Red neural que **aprende a memorizar** el contexto histórico en tiempo de test (test-time training)
- Los datos "sorprendentes" (alta pérdida) reciben más atención en la memorización
- Entrenamiento paralelizable gracias a la formulación como operación sobre bloques
- Compresión persistente del pasado sin coste cuadrático
- Análogo a la memoria a largo plazo en humanos

### Tres variantes de integración
Los autores proponen tres formas de combinar memoria y atención:
1. **Memory as Context (MAC)**: La memoria proporciona contexto adicional a la atención
2. **Memory as Gate (MAG)**: La memoria modula las representaciones de la atención mediante gating
3. **Memory as Layer (MAL)**: Memoria y atención operan como capas secuenciales

---

## Resultados Clave

- Supera a **Transformers y modelos lineales recurrentes modernos** (Mamba, RWKV, etc.) en language modeling, razonamiento de sentido común, genómica y series temporales
- Escala a ventanas de contexto de **>2M tokens** con mayor precisión en needle-in-haystack que los baselines
- El módulo de memoria neural logra entrenamiento **rápido y paralelizable** manteniendo inferencia eficiente
- La memorización en test-time (sin actualizar pesos del modelo base) es el mecanismo clave de escalabilidad

---

## Contribuciones Principales

1. **Marco conceptual memoria dual**: Formalización de atención como short-term memory y un nuevo módulo neural como long-term memory, inspirado en la distinción cognitiva de sistemas de memoria humanos
2. **Módulo de memoria neural**: Arquitectura que aprende a memorizar en test-time con entrenamiento paralelizable, resolviendo la tensión recurrencia vs. atención
3. **Familia de arquitecturas Titans**: Tres variantes (MAC, MAG, MAL) que demuestran diferentes estrategias de integración memoria-atención con rendimiento superior a Transformers

---

## Limitaciones

- La metáfora cognitiva (short-term vs. long-term memory) es inspiracional pero no está validada neurobiológicamente
- El overhead del módulo de memoria neural no se analiza exhaustivamente para despliegue en producción
- Evaluado principalmente en tareas de procesamiento de secuencias; la transferibilidad a razonamiento agéntico multi-paso no se explora directamente

---

## Resaltados y Anotaciones

> [!quote] Resaltado
> We present a new neural long-term memory module that learns to memorize historical context and helps attention to attend to the current context while utilizing long past information. We show that this neural memory has the advantage of fast parallelizable training while maintaining a fast inference. From a memory perspective, we argue that attention due to its limited context but accurate dependency modeling performs as a short-term memory, while neural memory due to its ability to memorize the data, acts as a long-term, more persistent, memory. [#ffd400]

---

## Ideas y Conexiones

- La distinción **atención = short-term memory / módulo neural = long-term memory** mapea directamente con la jerarquía de [[Agentic Memory]] del survey de Wei et al.: la atención es análoga a la memoria de trabajo (contexto inmediato), mientras que el módulo neural es análogo a la memoria persistente que acumula experiencia
- Titans opera a nivel de **arquitectura del modelo** (memoria paramétrica interna), mientras que [[MemOS]], [[HippoRAG]] y Mem0 operan a nivel de **sistema externo**. La distinción de MemOS entre "activation memory" y "parameter memory" captura exactamente esta diferencia
- El concepto de **test-time memorization** (aprender a memorizar sin actualizar pesos del modelo base) conecta con [[In-Context Reasoning]]: es una forma de escalar cómputo en inferencia, pero a nivel de arquitectura en vez de a nivel de prompt
- La idea de priorizar datos "sorprendentes" en la memorización recuerda a los mecanismos de [[Reflective Feedback]]: solo lo inesperado merece atención y almacenamiento
- Si se combinara Titans (memoria interna a largo plazo) con un framework agéntico como [[ReAct]] o el framework de Wu et al., se podría tener un agente con memoria persistente tanto interna (Titans) como externa ([[Mind-Map Agent]]), un sistema dual más completo

---

## Notas Relacionadas

- [[Agentic Memory]] — Marco conceptual de memoria que Titans implementa a nivel arquitectónico
- [[MemOS]] — Enfoque complementario: memoria como recurso de sistema operativo
- [[HippoRAG]] — Otro enfoque bio-inspirado pero a nivel de sistema externo
- [[In-Context Reasoning]] — Test-time memorization como escalado de inferencia
- [[Reflective Feedback]] — Memorización selectiva basada en "sorpresa"
- [[weiSurveyAgenticReasoning2026]] — Survey que contextualiza tipos de memoria
- [[Titans (Arquitectura)]] — Nota de concepto
