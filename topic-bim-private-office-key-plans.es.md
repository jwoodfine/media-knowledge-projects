---
schema: foundry-doc-v1
title: "Oficina Privada — planos clave"
slug: topic-bim-private-office-key-plans
aliases:
  - topic-bim-private-office-key-plans
short_description: "Especificaciones de Private Office key plan — tres tamaños de suite (30, 43 y 64 m²) abriéndose directamente al corredor de edificio compartido sin corredor bilateral interno, dimensionados para inquilinos profesionales individuales en lugar de firmas."
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
paired_with: topic-bim-private-office-key-plans.md
---

Oficina Privada es un tipo de uso separado de la [[topic-bim-professional-office-key-plans|Oficina Profesional]]. Cada suite de Oficina Privada da directamente al corredor compartido del edificio — no hay corredor bilateral interno. El inquilino es típicamente un profesional individual, no una firma. La geometría de la suite se calcula mediante la [[topic-bim-building-width-method|Calculadora de Anchura del Edificio]] y los valores por tipo de uso catalogados en [[topic-bim-zone-depths-per-use-type|profundidades de zona por tipo de uso]]; las Plantas Clave alimentan el [[topic-bim-tile-system|sistema de teselas]] y la [[topic-bim-floor-plate-methodology|metodología de la planta]].

## Los tres tamaños

| Tamaño | Código | Área (m²) | Área (SF) | Frente de fachada |
|---|---|---:|---:|---|
| Pequeña | PO-1 | 30 | 325 | 13'-5" (4,09 m) |
| Mediana | PO-2 | 43 | 465 | 19'-3" (5,87 m) |
| Grande | PO-3 | 64 | 685 | 28'-6" (8,69 m) |

Total apiladas lado a lado: 137 m² / 1.475 SF.

## Vocabulario de zonas

| Zona | Profundidad | Nota |
|---|---|---|
| Zona 1 — Hábitat | 5,9944 m (19'-8") | Marcada para revisión en la firma final de la [[topic-bim-key-plans-index|Planta Clave]] — ligeramente inferior al estándar europeo de iluminación de 6,0 m |
| Zona 2 — Revista | 1,3716 m (4'-6") | Almacenamiento somero |
| Zona 3 — Corredor | 0 m | Ninguno — cada oficina da al corredor del edificio |

## PO-1 (Pequeña) — la muestra canónica

PO-1 es la demostración metodológica que ancla todo el sistema de Planos Clave. La derivación comienza posicionando el mobiliario alrededor de un punto central, luego ajustado para satisfacer la Ley Alemana de Circulación y el Estándar Europeo de Iluminación.

**Mobiliario:** un escritorio y silla (Steelcase), una mesa redonda para tres personas, un archivador, una credenza, una estantería y un perchero.

**Dimensiones:** frente de fachada 13'-5"; profundidad Hábitat 19'-8"; profundidad Revista 4'-6"; profundidad total excluyendo corredor 24'-2". Dos montantes cubren la fachada; la puerta se abre hacia dentro desde el lado del corredor.

**Ocupación:** 1 puesto de trabajo por 30 m² (325 SF); carga de ocupación para cálculo de evacuación: 6 personas por 5 m² (54 SF por persona).

## PO-2 (Mediana)

PO-2 añade un segundo escritorio y silla, y una segunda credenza a PO-1. La mesa redonda para tres personas, el archivador, la estantería y el perchero se mantienen en cantidad uno.

**Dimensiones:** frente de fachada 19'-3" (división 10'-0" + 9'-3"); profundidades de Hábitat y Revista sin cambios a 19'-8" y 4'-6".

**Ocupación:** 2 puestos de trabajo por 43 m²; 22 m² (233 SF) por puesto de trabajo.

PO-2 mide aproximadamente 100 SF más que PO-1, no el doble. El mobiliario compartido no se duplica — esta no-modularidad es fundacional al sistema de Planos Clave. El área arrendable por persona no es el impulsor del diseño; la calidad del espacio lo es.

## PO-3 (Grande)

PO-3 añade dos archivadores, dos estanterías y dos percheros a PO-2, reflejando un tercer ocupante.

**Dimensiones:** frente de fachada 28'-6" (división 10'-0" + 9'-3" + 9'-3"); profundidades de Hábitat y Revista sin cambios.

**Ocupación:** 3 puestos de trabajo por 64 m²; 21 m² (228 SF) por puesto de trabajo.

PO-3 representa tres profesionales que comparten una suite que mantiene la única mesa redonda para tres personas — típicamente una sociedad o una pequeña consulta con dos profesionales y un administrador.

## Distribución de mobiliario en una Baldosa de Oficina Privada

| Tamaño | Proporción en la baldosa |
|---|---:|
| Pequeña (PO-1) | 80% |
| Mediana (PO-2) | 10% |
| Grande (PO-3) | 10% |

La mayoría de las Baldosas de Oficina Privada son predominantemente celdas PO-1. Los inquilinos que necesitan espacio PO-2 o PO-3 lo arriendan explícitamente; el edificio optimiza el rendimiento de PO-1.

## Licencia vs. arrendamiento

Los inquilinos de Oficina Privada probablemente operarán bajo un contrato de licencia en lugar de un arrendamiento tradicional. El alquiler tiene precio fijo en los tres tamaños. Los IDs de edificio se emiten por puesto de trabajo: uno para PO-1, dos para PO-2, tres para PO-3. Los costos de Áreas Comunes no se detallan por separado para los inquilinos de Oficina Privada.

## Ver también

- [[topic-bim-key-plans-index]]
- [[topic-bim-professional-office-key-plans]]
- [[topic-bim-leasing-plan-efficiencies]]
