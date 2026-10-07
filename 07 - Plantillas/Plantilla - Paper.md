---
titulo: "{{title}}"
autores: "{% for creator in creators %}{{creator.firstName}} {{creator.lastName}}{% if not loop.last %}, {% endif %}{% endfor %}"
año: "{{date | format('YYYY')}}"
fuente: "{{publicationTitle}}"
DOI: "{{DOI}}"
citekey: "{{citekey}}"
zotero: "{{desktopURI}}"
tags:
  - paper
  - agentic-reasoning
estado: "#estado/borrador"
fecha_lectura: "{{importDate | format('YYYY-MM-DD')}}"
valoracion: 
---

# {{title}}

## Metadatos

- **Autores**: {% for creator in creators %}{{creator.firstName}} {{creator.lastName}}{% if not loop.last %}, {% endif %}{% endfor %}
- **Año**: {{date | format("YYYY")}}
- **Publicación**: {{publicationTitle}}
- **DOI**: [{{DOI}}](https://doi.org/{{DOI}})
- **Zotero**: [Abrir en Zotero]({{desktopURI}})
- **Abstract**: {{abstractNote}}

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

{% if annotations.length > 0 %}
{% for annotation in annotations %}
{% if annotation.imageRelativePath %}
![[{{annotation.imageRelativePath}}]]
{% endif %}
{% if annotation.annotatedText %}
> [!quote] Resaltado (p. {{annotation.page}})
> {{annotation.annotatedText}} {% if annotation.color %}[{{annotation.color}}]{% endif %}
{% endif %}
{% if annotation.comment %}
**Nota:** {{annotation.comment}}
{% endif %}

---
{% endfor %}
{% else %}
> Sin anotaciones todavía. Resalta en Zotero y reimporta.
{% endif %}

## Ideas y Conexiones

> Reflexiones propias, conexiones con otros papers/ideas, posibles extensiones.

- 

---

## Notas Relacionadas

- [[]]
