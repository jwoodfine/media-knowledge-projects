---
schema: foundry-doc-v1
title: "Oficina Profesional — línea base de planos clave"
slug: topic-bim-professional-office-key-plans
aliases:
  - topic-bim-professional-office-key-plans
short_description: "La categoría supraordinada Oficina Profesional cubriendo cinco subtipos — Business, Medical, Laboratory, Academic y Civic — con las dimensiones de zona del diseño inicial de línea de base que precedieron la especialización de subtipo."
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
paired_with: topic-bim-professional-office-key-plans.md
---

Oficina Profesional es la categoría superordinada para cinco sub-tipos: [[topic-bim-business-key-plans|Empresarial]], [[topic-bim-medical-key-plans|Médico]], Laboratorio, Académico y Cívico. Conserva una línea base de "Diseño Inicial" que precede a la especialización por sub-tipos y se preserva como linaje de diseño. La geometría de la suite se calcula mediante la [[topic-bim-building-width-method|Calculadora de Anchura del Edificio]] y los valores por tipo de uso catalogados en [[topic-bim-zone-depths-per-use-type|profundidades de zona por tipo de uso]]; las Plantas Clave alimentan el [[topic-bim-tile-system|sistema de teselas]] y la [[topic-bim-floor-plate-methodology|metodología de la planta]].

## La línea base de Diseño Inicial

| Campo | Valor |
|---|---|
| Pequeña | 130 m² / 1.400 SF |
| Mediana | No muestreada |
| Grande | No muestreada |
| Zona 1 — Hábitat | 6,0 m / 19'-8" |
| Zona 2 — Revista | 3,8 m / 12'-5" |
| Zona 3 — Corredor | 2,0 m / 6'-6" |

Ancho de edificio calculado = 2 × (6,0 + 3,8) + 2,0 = **21,6 m** (70'-10").

## Categorías de inquilinos

El sistema de [[topic-bim-key-plans-index|Planos Clave]] reconoce once categorías de inquilinos: Oficina Privada, cinco sub-tipos de Oficina Profesional ([[topic-bim-business-key-plans|Empresarial]], [[topic-bim-medical-key-plans|Médico]], Laboratorio, Académico, Cívico) y cinco tamaños de Oficina Corporativa (1/8, 1/4, 1/2, 3/4 y Planta Completa).

## Por qué importan las combinaciones Pequeña + Pequeña

Combinar dos Pequeñas de Oficina Profesional cubre el vacío entre la Oficina Profesional Grande y la Oficina Corporativa de 1/8 de planta. La tabla de combinaciones entre sub-tipos:

| Combinación | Lab | Académico | Empresarial | Médico | Cívico |
|---|---|---|---|---|---|
| Pequeña + Pequeña | 390 m² / 4.198 SF | 210 / 2.262 | 622 / 6.700 | 446 / 2.402 | 540 / 5.824 |
| Pequeña + Mediana | 511 / 5.500 | 345 / 3.714 | 711 / 7.652 | 554 / 5.969 | 847 / 9.127 |
| Pequeña + Grande | 596 / 6.412 | 483 / 5.201 | 980 / 10.874 | 709 / 7.633 | 1.092 / 11.762 |
| Mediana + Grande | 717 / 7.714 | 618 / 6.653 | 1.069 / 11.826 | 817 / 8.799 | 1.399 / 15.065 |

Las combinaciones permiten rellenar una planta de un Centro Profesional sin espacios vacíos. Dos suites Pequeñas de Laboratorio (390 m²) más una suite Mediana de Médico (331 m²) más una suite Grande de Cívico (822 m²) dan 1.543 m², cabiendo dentro de una planta típica de un Centro Profesional de 19.000–23.000 SF junto con el núcleo del edificio, servicios y hall de ascensores.

## Diseño Inicial frente a anchos de zona por sub-tipo

La Zona 2 del Diseño Inicial (3,8 m) es más estrecha que cuatro de los cinco sub-tipos:

| Sub-tipo | Z2 Revista | Delta frente al Diseño Inicial |
|---|---:|---:|
| Diseño Inicial | 3,8 m | (línea base) |
| Académico | 3,0 m | −0,8 m |
| Médico | 4,9 m | +1,1 m |
| Laboratorio | 4,8 m | +1,0 m |
| Empresarial | 7,3 m | +3,5 m |
| Cívico | 7,2 m | +3,4 m |

El Diseño Inicial no puede satisfacer ninguna de las cinco especializaciones sin expansión dimensional. Sirve como huella de "Oficina Profesional sin especialización" — en cuanto un inquilino declara una especialización, se aplica la Calculadora de Anchura del Edificio del sub-tipo correspondiente.

## La discrepancia entre 21 m y 21,6 m

La metodología presenta el ancho total de la planta de Oficina Profesional como 21 m (eje a eje) y 21,6 m cuando se incluyen las paredes de separación y estructurales. La aritmética 2 × (6,0 + 3,8) + 2,0 = 21,6 m confirma que la cifra de "21 m" es la distancia de eje a eje y 21,6 m incluye una sobrecarga de 0,6 m por separaciones y estructura. Esta sobrecarga debería codificarse como un token DTCG independiente para hacer la aritmética autodocumentada.

## Por qué no existen muestras de Mediana / Grande de Oficina Profesional

Los roles de Mediana y Grande están cubiertos por las propias muestras de los cinco sub-tipos. Un inquilino que necesita más espacio genérico arrienda, en la práctica, dos Pequeñas (≈ 260 m² / 2.800 SF).

## Ver también

- [[topic-bim-key-plans-index]]
- [[topic-bim-business-key-plans]]
- [[topic-bim-medical-key-plans]]
- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
