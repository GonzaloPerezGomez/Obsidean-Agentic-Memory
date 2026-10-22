---
titulo: "MIMIC-CXR"
tags:
  - dataset
  - recurso
  - clinical
  - multimodal
  - radiology
aliases: ["MIMIC-CXR-JPG"]
fuente: "https://physionet.org/content/mimic-cxr-jpg/2.1.0/"
fecha_creacion: "2026-10-22"
---

# MIMIC-CXR / MIMIC-CXR-JPG

## Descripción

> Colección masiva de acceso abierto de radiografías de tórax digitales desidentificadas emparejadas con sus correspondientes informes de radiología de texto libre e impresiones diagnósticas, procedente del Beth Israel Deaconess Medical Center (MIT PhysioNet).

Es la base de datos de referencia mundial para la investigación en visión artificial médica, modelos multimodales (MLLM) y memorias perceptivas para agentes clínicos.

## Características Principales

- **Tamaño:** 377.110 imágenes de radiografías de tórax correspondientes a 227.835 estudios radiológicos de 65.379 pacientes únicos.
- **Modalidad:** Imagen médica (DICOM / JPG) + Texto (informes radiológicos semiestructurados con secciones de hallazgos e impresión diagnóstica).
- **Anotaciones:** 14 etiquetas de patologías clínicas extraídas de los informes (neumonía, cardiomegalia, edema, derrame pleural, neumotórax, atelectasia, etc.).

## Papers que lo utilizan en la bóveda

- [[jabinMSMMemUniversalMedical2019]] — Evaluación del framework MSM-Mem, utilizando radiografías de tórax emparejadas con informes para poblar y actualizar la memoria visual ($M_V$) y semántica ($M_S$).
