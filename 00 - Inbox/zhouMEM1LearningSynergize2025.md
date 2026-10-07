---
titulo: "MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents"
autores: "Zijian Zhou, Ao Qu, Zhaoxuan Wu, Sunghwan Kim, Alok Prakash, Daniela Rus, Jinhua Zhao, Bryan Kian Hsiang Low, Paul Pu Liang"
año: "2025"
fuente: ""
DOI: "10.48550/arXiv.2506.15841"
citekey: "zhouMEM1LearningSynergize2025"
zotero: "zotero://select/library/items/J4JJVPC7"
tags:
  - paper
  - agentic-reasoning
estado: "#estado/borrador"
fecha_lectura: "2026-10-05"
valoracion: 
---

# MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents

## Metadatos

- **Autores**: Zijian Zhou, Ao Qu, Zhaoxuan Wu, Sunghwan Kim, Alok Prakash, Daniela Rus, Jinhua Zhao, Bryan Kian Hsiang Low, Paul Pu Liang
- **Año**: 2025
- **Publicación**: 
- **DOI**: [10.48550/arXiv.2506.15841](https://doi.org/10.48550/arXiv.2506.15841)
- **Zotero**: [Abrir en Zotero](zotero://select/library/items/J4JJVPC7)
- **Abstract**: Modern language agents must operate over long-horizon, multi-turn interactions, where they retrieve external information, adapt to observations, and answer interdependent queries. Yet, most LLM systems rely on full-context prompting, appending all past turns regardless of their relevance. This leads to unbounded memory growth, increased computational costs, and degraded reasoning performance on out-of-distribution input lengths. We introduce MEM1, an end-to-end reinforcement learning framework that enables agents to operate with constant memory across long multi-turn tasks. At each turn, MEM1 updates a compact shared internal state that jointly supports memory consolidation and reasoning. This state integrates prior memory with new observations from the environment while strategically discarding irrelevant or redundant information. To support training in more realistic and compositional settings, we propose a simple yet effective and scalable approach to constructing multi-turn environments by composing existing datasets into arbitrarily complex task sequences. Experiments across three domains, including internal retrieval QA, open-domain web QA, and multi-turn web shopping, show that MEM1-7B improves performance by 3.5x while reducing memory usage by 3.7x compared to Qwen2.5-14B-Instruct on a 16-objective multi-hop QA task, and generalizes beyond the training horizon. Our results demonstrate the promise of reasoning-driven memory consolidation as a scalable alternative to existing solutions for training long-horizon interactive agents, where both efficiency and performance are optimized.

---

## Resumen

> Resumen breve del paper en tus propias palabras (2-3 frases).



---

## Problema / Motivación

¿Qué problema intenta resolver? ¿Por qué es importante?



---

## Metodología

¿Cómo lo resuelven? ¿Qué enfoque, arquitectura o técnica usan?



---

## Resultados Clave

- 
- 
- 

---

## Contribuciones Principales

1. 
2. 
3. 

---

## Limitaciones

- 
- 

---

## Resaltados y Anotaciones





> [!quote] Resaltado (p. )
> Modern language agents must operate over long-horizon, multi-turn interactions, where they retrieve external information, adapt to observations, and answer interdependent queries. Yet, most LLM systems rely on full-context prompting, appending all past turns regardless of their relevance. This leads to unbounded memory growth, increased computational costs, and degraded reasoning performance on out-of-distribution input lengths. We introduce MEM1, an end-to-end reinforcement learning framework that enables agents to operate with constant memory across long multi-turn tasks. At each turn, MEM1 updates a compact shared internal state that jointly supports memory consolidation and reasoning. This state integrates prior memory with new observations from the environment while strategically discarding irrelevant or redundant information. To support training in more realistic and compositional settings, we propose a simple yet effective and scalable approach to constructing multi-turn environments by composing existing datasets into arbitrarily complex task sequences. Experiments across three domains, including internal retrieval QA, open-domain web QA, and multi-turn web shopping, show that MEM1-7B improves performance by 3.5× while reducing memory usage by 3.7× compared to Qwen2.5-14B-Instruct on a 16-objective multi-hop QA task, and generalizes beyond the training horizon. Our results demonstrate the promise of reasoning-driven memory consolidation as a scalable alternative to existing solutions for training long-horizon interactive agents, where both efficiency and performance are optimized [#ffd400]



---



> [!quote] Resaltado (p. 10)
> 5 Conclusion, Limitations, and Future Work  We introduced MEM1, a reinforcement learning framework that enables language agents to perform long-horizon reasoning with consolidated memory. By integrating inference-time reasoning and memory consolidation into a unified internal state, MEM1 addresses the scalability challenges of prompt growth and achieves competitive performance across QA and web navigation benchmarks, with substantially reduced memory usage and inference latency. Despite these advantages, MEM1 assumes access to environments with well-defined and verifiable rewards. While this assumption holds in domains such as QA, math, and web navigation, many open-ended tasks present ambiguous or noisy reward structures. Fully realizing the potential of MEM1 therefore requires advances in modeling such tasks and designing suitable reward mechanisms—challenges that lie beyond the scope of this work. A promising future direction is to explore methods for training MEM1 agents in these open-ended settings where reward signals are sparse, delayed, or implicit. [#ffd400]



---



## Ideas y Conexiones

> Reflexiones propias, conexiones con otros papers/ideas, posibles extensiones.

- 

---

## Notas Relacionadas

- [[]]
