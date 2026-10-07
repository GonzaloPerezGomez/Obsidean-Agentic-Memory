---
titulo: "Least-to-Most Prompting"
tags:
  - concepto
  - agentic-reasoning
  - prompting
aliases: ["LtM Prompting", "Prompting de Menor a Mayor"]
fecha_creacion: "2026-09-30"
---

# Least-to-Most Prompting

## Definición

> Estrategia de prompting que permite a los LLMs resolver problemas más complejos que los ejemplos del prompt mediante una **descomposición top-down** del problema en subproblemas progresivamente más simples, seguida de una **resolución bottom-up** donde cada solución alimenta la siguiente.

## Explicación

Least-to-Most Prompting aborda una limitación fundamental de Chain-of-Thought: la incapacidad de generalizar de problemas fáciles a difíciles. El método opera en dos fases distintas. Primero, la fase de **descomposición** rompe el problema original en una serie ordenada de subproblemas, desde el más simple al más complejo. Luego, la fase de **resolución secuencial** resuelve cada subproblema incorporando como contexto las soluciones de todos los subproblemas previos, creando una cadena acumulativa de conocimiento. Este patrón de contexto incremental es lo que permite la generalización composicional: el modelo construye respuestas complejas a partir de piezas simples, de forma similar a como un programador resuelve un problema grande construyendo primero las funciones auxiliares. La limitación principal es que los prompts de descomposición son específicos del dominio.

---

## Contexto

Junto con [[Chain of Thought]], [[Plan-and-Solve Prompting]] y [[Tree of Thoughts]], forma parte de las estrategias de prompting que anticipan capacidades agénticas. Su idea central de descomposición + resolución incremental es un precursor directo de la [[Planning]] agéntica y de la [[Agentic Memory]] experiencial. Los propios autores señalan que el prompting es "comunicación unidireccional" y sugieren evolucionar hacia interacción bidireccional — exactamente el paradigma de [[Agentic Reasoning]].

---

## Relación con otros conceptos

- **Requiere**: [[Chain of Thought]]
- **Relacionado con**: [[Plan-and-Solve Prompting]], [[Planning]], [[In-Context Reasoning]]
- **Evoluciona hacia**: [[Agentic Reasoning]] (prompting → interacción bidireccional)

---

## Referencias

- [[zhouLeasttoMostPromptingEnables2023]] — Paper que introduce Least-to-Most Prompting
