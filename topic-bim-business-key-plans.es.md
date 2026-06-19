---
schema: foundry-doc-v1
title: "Empresarial — planos clave"
slug: topic-bim-business-key-plans
aliases:
  - topic-bim-business-key-plans
short_description: "Especificaciones de key plan de oficina comercial dentro de la clasificación Oficina Profesional, distinguidas por la profundidad más amplia de Zone 2 Magazine de cualquier subtipo en 9,26 m, impulsada por paredes de almacenamiento abierto, salas de servidores y zonas de colaboración en equipo, en tres tamaños de 311 a 669 m²."
category: bim
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-05-17
editor: pointsav-engineering
es_status: complete
paired_with: topic-bim-business-key-plans.md
---

La Oficina Empresarial (Oficina Profesional — Empresarial) es uno de los cinco sub-tipos de [[topic-bim-professional-office-key-plans|Oficina Profesional]]. Su característica distintiva es la Zona 2 Revista a 7,3 m — la más ancha de cualquier sub-tipo — impulsada por paredes de almacenamiento abierto, salas de servidores, áreas de impresión y zonas de colaboración propias de firmas de servicios profesionales. La profundidad se calcula mediante la [[topic-bim-building-width-method|Calculadora de Anchura del Edificio]] y alimenta el [[topic-bim-tile-system|sistema de teselas]] que compone la [[topic-bim-floor-plate-methodology|planta]].

## Los tres tamaños

| Tamaño | Código | Área (m²) | Área (SF) |
|---|---|---:|---:|
| Pequeña | B-1 | 311 | 3.350 |
| Mediana | B-2 | 400 | 4.302 |
| Grande | B-3 | 669 | 7.524 |

## Vocabulario de zonas

| Zona | Profundidad | Nota |
|---|---|---|
| Zona 1 — Hábitat | 6,0 m (19'-8") | Mínimo de la Norma Europea de Iluminación |
| Zona 2 — Revista | 7,3 m (23'-11") | La más ancha entre todos los sub-tipos |
| Zona 3 — Corredor | 2,7 m (8'-10") | Corredor bilateral |

Ancho de edificio calculado = 2 × (6,0 + 7,3) + 2,7 = **29,3 m** (96'-1").

## Especializaciones

El sub-tipo Empresarial abarca firmas de servicios profesionales: despachos de abogados, firmas de contabilidad y empresas de ingeniería. No son Planos Clave separados, sino variantes de los mismos espacios B-1/B-2/B-3 con contenido de Revista ajustado (archivos legales, carpetas de auditoría, impresoras de gran formato).

## Opciones de ancho de edificio A/B/C/D

Los bocetos de la Pequeña Empresarial incluyen una exploración de cuatro opciones de ancho que captura el principio de ajuste bidireccional:

| Opción | Puestos de trabajo | Z1 Hábitat | Z2 Revista | Ancho total | Área (m²) |
|---|---:|---:|---:|---:|---:|
| A | 15 | 5,51 m | 9,26 m | 17,52 m | 450,7 |
| B | 21 | 7,39 m | 6,76 m | 16,90 m | 399,6 |
| C | 15 | 5,63 m | 6,63 m | 15,01 m | 345,5 |
| D | 15 | 5,51 m | 5,76 m | 14,02 m | 339,5 |

La Opción A maximiza la Revista. La Opción D comprime ambas zonas pero pierde la capacidad de Oficina Ejecutiva. La línea base V3 (Z2 = 7,3 m) es el resultado de la Calculadora de Anchura del Edificio que guía el conjunto de Planos Clave de tres tamaños.

## Principios de diseño del comentario MW3

- La norma de 6,0 m governa la iluminación natural, pero debe considerarse junto con los requisitos funcionales según los arreglos de mobiliario.
- La Zona 1 y la Zona 2 no son necesariamente fijas; los inquilinos pueden posicionar oficinas cerradas en la fachada o trasladarlas a la Zona 2 manteniendo el mobiliario y la circulación.
- Cualquier área de Zona 2 no asignada crea oportunidades para áreas informales y almacenamiento de apoyo a la ocupación.

## Aseo del inquilino en la Zona 2

El Aseo del Inquilino puede ubicarse dentro de la Zona 2 — Revista. Cinco configuraciones de aseo muestran distintas disposiciones de 2 cabinas + lavabos + vestíbulo, todas dentro de aproximadamente 7 m × 3 m. El ancho mínimo de la Zona 2 está co-determinado por la Sala de Personal o el Aseo, según cuál sea más ancho.

## Elemento ancla de la taxonomía espacial

Cada sub-tipo de Oficina Profesional lleva un elemento ancla en el extremo de la fachada cuyas dimensiones determinan la profundidad del Hábitat. Para el tipo Empresarial, este elemento es la Recepción — el mismo papel gramatical que la Sala Limpia desempeña en el Laboratorio, el Auditorio en el Académico, la Sala de Juicios en el Cívico y la sala de exploración en el [[topic-bim-medical-key-plans|Médico]].

## Ver también

- [[topic-bim-key-plans-index]]
- [[topic-bim-professional-office-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
