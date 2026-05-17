---
schema: foundry-doc-v1
title: "Sistema de baldosas — pequeña, mediana, grande y especial"
slug: topic-bim-tile-system
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-tile-system.md
---

Una Baldosa es una unidad rectangular componible de la planta. Cada Baldosa es exactamente una zona climática HVAC. Las Baldosas se componen para cubrir el Área Neta Arrendable sin resto.

Existen tres familias de baldosas regulares (Pequeña, Mediana, Grande) y una familia residual (Baldosas Especiales).

## Las tres familias regulares

### Baldosas Pequeñas — 2.700 SF (250,84 m²)

| Código | Nombre | Composición | Zonas climáticas | Función |
|---|---|---|---|---|
| Baldosa A | Oficina Corporativa | Unidad única de 2.700 SF | 1 | Ancla corporativa de planta media |
| Baldosa B-1 | Oficina Privada | 5 OP (300 + 500 + 450 + 300 + 300) + Profesional Pequeña 800 ≈ 2.700 SF | 6 | Interior con predominio de despachos privados |
| Baldosa C-1 | Oficina Profesional (Med + Med + Pequeña) | OP-M 2.000 + OP-M 450 + OP-P 300 = 2.750 | 3 | Ancla profesional (Médica, Empresarial) |
| Baldosa C-2 | Oficina Profesional (Grande + Pequeña) | OP-G 2.400 + OP-P 300 = 2.700 | 2 | Profesional con ancla mayor |
| Baldosa C-3 | (Alternativas) | Composición variante | 2 | Véase PDF de Alternativas |
| Baldosa C-4 | (Alternativas) | Composición variante | 1 | Ancla Cívica / Académica |
| Baldosa E-1 | End Cap Mixto (Izquierda) | OP mixta + Profesional Pequeña + corredor | 3 | Lado corto izquierdo |
| Baldosa E-2 | End Cap Mixto (Derecha) | Espejo de E-1 | 3 | Lado corto derecho |

**Nota.** La Metodología V12 (p. 2) también documenta una "Baldosa B" Pequeña con composición 300 + 500 + 300 + 450 + 450 + 300 = 2.300 SF de OP + 400 SF residual. El PDF de Alternativas amplía la Baldosa B en Baldosa B-1 con una unidad Profesional Pequeña añadida. Convención: Baldosa B-1 es el token vigente; Baldosa B es la abreviatura de la metodología para la misma función.

### Baldosas Medianas — 3.500 SF (325,16 m²)

Esta familia está documentada en la Metodología V12 pero actualmente no aparece en `tile-system.dtcg.json` — señalado para incorporación pendiente.

| Código | Nombre | Composición | Zonas climáticas |
|---|---|---|---|
| Baldosa D | Oficina Corporativa Media | Unidad Corporativa única de 3.500 SF | 1 |
| Baldosa E | Oficina Privada Media | 8 OP (≈ 2.900) + corredor | 8 |
| Baldosa F (Mediana) | Oficina Profesional Media | OP Pequeña 800 + OP Pequeña 800 + OP Media 1.100 + OP Pequeña 800 = 3.500 | 4 |
| Baldosa E-1 (Mediana) | End Cap Izquierdo (Privada) | OP mixta con corredor de extremo; ≈ 3.500–5.500 SF | 8 |
| Baldosa E-2 (Mediana) | End Cap Derecho (Profesional) | Espejo de E-1 Mediana con plantas clave de Oficina Profesional | 4–6 |

**Colisión de nombres.** "Baldosa F" aparece tanto a 3.500 SF (Profesional Mediana) como a 4.900 SF (Corporativa Grande) en la Metodología V12. El diferenciador es la etiqueta de familia. Las herramientas deben normalizar a `tile-f-medium` y `tile-f-large` para evitar ambigüedad en el almacén de tokens.

### Baldosas Grandes — 4.900 SF (455,22 m²)

| Código | Nombre | Composición | Zonas climáticas |
|---|---|---|---|
| Baldosa F | Oficina Corporativa Grande | Unidad Corporativa única de 4.900 SF | 1 |
| Baldosa G | Mezcla de Oficina Privada Grande | 10 OP (300–500 SF cada una) + corredor | 10 |
| Baldosa H | Oficina Profesional Grande | 5 unidades OP (800 + 800 + 1.100 + 800 + 1.400 = 4.900) | 5 |

Las baldosas grandes se aproximan a la baldosa de 1/4 de planta (5.000 SF) en escala. Son útiles para anclas Corporativas, plantas de Oficina Privada de alta densidad y Centros Profesionales que necesitan subtipos de Oficina Profesional contiguos.

### End Caps Pareados de 6.000 SF

Existe una segunda serie de End Caps para edificios en los que el lado corto abarca dos Baldosas Pequeñas pareadas más una Escalera de Emergencia:

| Código | Nombre | Uso |
|---|---|---|
| Baldosa A-1 | End Cap de Oficina Corporativa | Par de unidades de Oficina Corporativa + Escalera de Emergencia + Corredor Interno |
| Baldosa B-2 | End Cap de Oficina Privada | Par de grupos de Oficina Privada + Escalera de Emergencia |
| Baldosa C-3 | End Cap de Oficina Profesional Media | Dos unidades OP-Media + Escalera de Emergencia |
| Baldosa C-4 | End Cap de Oficina Profesional Grande | OP-Grande 2.400 + mezcla OP + Escalera de Emergencia |

Fuente: PDF de Alternativas p. 2 (variantes de mayo 2025 y enero 2026).

## Baldosas Especiales

Las Baldosas Especiales rellenan el área residual alrededor del Núcleo del Edificio y del Vestíbulo de Ascensores. Sus tamaños son variables y se ajustan a la anchura de la Planta Clave de Oficina Profesional más próxima.

| Código | Tamaños aproximados | Función |
|---|---|---|
| SP-A | 400 / 1.350 / 2.000 / 2.100 SF | Relleno adyacente al núcleo (izquierda y derecha del Núcleo) |
| SP-B | 300 / 800 / 900 SF | Relleno adyacente al núcleo secundario |
| SP-C | 4.700 SF | Frente del Vestíbulo de Ascensores; restricción: sin alineación directa de puerta con ascensor |

Fuente: Metodología V12 pp. 3–5.

El álgebra de Baldosas (del PDF de Combinaciones V1) trata las Baldosas Especiales como una clase de composición diferenciada:

```
T_Básica    = n × P_Privada_Pequeña + p × P_Privada_Media + q × P_Privada_Grande
T_Compuesta = T_Básica + r × P_(Académico | Laboratorio | Médico | Negocio | Cívico)
T_Especial  = n × OP_Pequeña + p × OP_Media + q × OP_Grande
              + r × P_(Académico | Laboratorio | Médico | Negocio | Cívico)
Planta      = T_Básica + T_Compuesta + T_Especial + Núcleo del Edificio
```

## Dimensiones de la Planta Clave

De la Ficha Técnica "Plantas Clave y Baldosas" (V12 enero 2026):

| Clase | Pequeña | Media | Grande |
|---|---|---|---|
| Oficina Privada | 300 SF (OP-1) | 450 SF (OP-2) | 500 SF (OP-3) |
| Oficina Profesional — Médica | 1.100 SF (M-1) | 1.400 SF (M-2) | 800 SF (M-3) |
| Oficina Profesional — Empresarial | 1.100 SF (B-1) | 1.400 SF (B-2) | 800 SF (B-3) |
| Oficina Profesional — Laboratorio | 1.100 SF (L-1) | 1.400 SF (L-2) | 800 SF (L-3) |
| Oficina Profesional — Académica | 1.100 SF (A-1) | 1.400 SF (A-2) | 800 SF (A-3) |
| Oficina Profesional — Cívica | 1.100 SF (C-1) | 1.400 SF (C-2) | 800 SF (C-3) |

**Distribución de disponibilidad** (Ficha Técnica enero 2026):

- Oficina Privada: Pequeña 80 % / Media 10 % / Grande 10 %
- Subtipos de Oficina Profesional: Pequeña 40 % / Media 30 % / Grande 20 % (10 % otro / mixto)

## Investigación abierta

- **P1.** La Ficha Técnica "% de disponibilidad" para Médico/Empresarial/Laboratorio/Académico/Cívico suma el 90 %, no el 100 %. Confirmar la categoría que representa el 10 % faltante.
- **P2.** Los subtipos Médico / Empresarial tienen una mezcla de 1.100/1.100/1.400/800/800 que totaliza 5.200 SF, no 5.000. Reconciliar con la referencia a la baldosa de 1/4 de planta de exactamente 5.000 SF.
- **P3.** La Baldosa B-1 en el archivo de tokens registra "5 oficinas privadas + 900 SF de corredor", pero el PDF de Alternativas muestra 5 OP + una Oficina Profesional Pequeña (800 SF). Seleccionar la versión canónica.
- **P4.** ¿Los End Caps Pareados de 6.000 SF (A-1, B-2, C-3, C-4) se usan únicamente cuando la longitud de la planta supera un umbral específico? Ningún documento fuente establece la condición desencadenante.

## Véase también

- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-floor-plate-tile-combinations]]
- [[topic-bim-key-plans-index]]
- [[topic-bim-zone-depths-per-use-type]]
