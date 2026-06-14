---
schema: foundry-doc-v1
title: "Médico — planos clave"
slug: topic-bim-medical-key-plans
aliases:
  - topic-bim-medical-key-plans
short_description: "Especificaciones de key plan de oficina médica dentro de la clasificación Oficina Profesional, distinguidas por la profundidad más amplia de Zone 1 Habitat en 7,28 m para acomodar el espacio libre de mesa de examen y circulación dual de paciente-clínico, en tres tamaños de 223 a 486 m²."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-medical-key-plans.md
---

La Oficina Médica es uno de los cinco sub-tipos de [[topic-bim-professional-office-key-plans|Oficina Profesional]]. Su característica distintiva es la Zona 1 Hábitat a 7,2 m — la más ancha de cualquier sub-tipo — determinada por la profundidad de la camilla de exploración más la circulación requerida para paciente y clínico. La profundidad se calcula mediante la [[topic-bim-building-width-method|Calculadora de Anchura del Edificio]] y alimenta el [[topic-bim-tile-system|sistema de teselas]] que compone la [[topic-bim-floor-plate-methodology|planta]].

## Los tres tamaños

| Tamaño | Sillones dentales | Código | Área (m²) | Área (SF) |
|---|---:|---|---:|---:|
| Pequeña | 2 | M3 | 223 | 2.401,5 |
| Mediana | 4 | M1 | 331 | 3.567,7 |
| Grande | 6 | M2 | 486 | 5.231,4 |

Los códigos FFE se numeran por orden de autoría histórica, no por tamaño. Para documentos externos se prefieren las etiquetas de tamaño (Pequeña / Mediana / Grande).

## Vocabulario de zonas

| Zona | Profundidad | Nota |
|---|---|---|
| Zona 1 — Hábitat | 7,2 m (23'-10") | La más ancha de todos los sub-tipos |
| Zona 2 — Revista | 4,9 m (16') | Almacén médico, esterilización, equipamiento |
| Zona 3 — Corredor | 2,9 m (9'-5") | Bilateral; ancho ADA/CSA-B651 para camillas y sillas de ruedas |

Ancho de edificio calculado = 2 × (7,2 + 4,9) + 2,9 = **27,1 m** (88'-11").

## Anclaje de mobiliario — sillón dental KaVo uniQa

Cada boceto Médico utiliza el sillón dental KaVo uniQa como SKU de referencia. El envolvente del sillón es 2.451 mm × 2.898 mm; cada sala de exploración mide aproximadamente 7.280 mm × 4.877 mm. El SKU es una dependencia rastreada: cualquier cambio de línea dental repercute en las dimensiones de la sala.

## Composición de las suites

M3 (Pequeña) incluye dos salas de exploración, una oficina médica, área de recepción con ventana de línea de visión, sala de espera (6 pacientes) y equipamiento de esterilización. M1 (Mediana) añade dos salas más y reorganiza la Zona 2. M2 (Grande) añade dos sillas adicionales, una segunda oficina médica y un equipamiento completo de Zona 2, con los aseos agrupados en un único bloque.

## Requisito de línea de visión en recepción

En los tres bocetos Médicos aparece el mismo requisito: Recepción debe mantener línea de visión directa a la puerta de entrada. La solución canónica es la "ventana" de recepción — una oficina administrativa adyacente con apertura acristalada.

## Optimización de la profundidad de la Zona 2

La profundidad de 4,9 m está determinada por la mesa de la sala de personal más la circulación. Reducir la mesa de personal es la palanca para reducir el ancho del edificio, siempre que la mesa sea un producto Steelcase real, accesible y asequible.

## Ver también

- [[topic-bim-key-plans-index]]
- [[topic-bim-professional-office-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
