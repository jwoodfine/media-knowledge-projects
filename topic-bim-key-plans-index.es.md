---
schema: foundry-doc-v1
title: "Índice de plantas clave — referencia maestra"
slug: topic-bim-key-plans-index
short_description: "Directorio maestro de 72 key plans en nueve Development Classes, pareando Development Class con Typology y Eco Region para producir los slugs de nombre de archivo referenciados en artefactos BIM posteriores, tokens DTCG, clasificaciones de entidad IFC y superposiciones reglamentarias."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
paired_with: topic-bim-key-plans-index.md
---

El Directorio de Plantas Clave inventaría cada sub-área diferenciada de la planta que el Modelo de Información del Edificio (BIM, por sus siglas en inglés) reconoce. Cada entrada combina una Clase de Desarrollo con una Tipología y (donde corresponde) una Eco Región, generando un identificador de nombre de archivo que se referencia desde todos los artefactos BIM posteriores — tokens del Design Token Community Group (DTCG), clasificaciones de entidades de las Clases de Fundaciones de la Industria (IFC), solvers en Rust, presentaciones y superposiciones de normativa.

El Directorio actual (V2, con fechas tanto del 2025-01-07 como redatado al 2026-01-06 — contenido idéntico) contiene **72 plantas clave en nueve Clases de Desarrollo**.

## Clases de Desarrollo y número de plantas clave

| # | Clase de Desarrollo | Número de plantas clave | Rango del índice |
|---|---|---:|---|
| 1 | General | 25 | 1–25 |
| 2 | Centro Profesional | 13 | 26–38 |
| 3 | Comercio Selecto | 3 | 39–41 |
| 4 | Oficina Suburbana | 14 | 42–55 |
| 5 | Industrial Tecnológico | 3 | 56–58 |
| 6 | Paisajismo | 4 | 59–62 |
| 7 | Aparcamiento | 10 | 63–72 |
| | **Total** | **72** | |

## Clase General — Índice 1–25 (arrendable + núcleo de circulación)

| Índice | Tipología | ID | Notas |
|---:|---|---|---|
| 1 | Oficina Privada | Pequeña | Muestra PO-1; 325 SF |
| 2 | Oficina Privada | Media | Muestra PO-2; 465 SF |
| 3 | Oficina Privada | Grande | Muestra PO-3; 685 SF |
| 4 | Oficina Corporativa | Planta completa | una baldosa por planta |
| 5 | Oficina Corporativa | 1/2 Planta | |
| 6 | Oficina Corporativa | 1/3 Planta | |
| 7 | Oficina Corporativa | 1/4 Planta | un cuarto de baldosa |
| 8 | Oficina Corporativa | 1/8 Planta | incremento Corporativo mínimo |
| 9 | Médico | Quiropráctico | especialización; sin muestra completada |
| 10 | Médico | Dentista | Muestra M3; 2.402 SF |
| 11 | Médico | Médico de Familia | especialización |
| 12 | Negocio | B-1 | muestra pequeña de negocio; 3.350 SF |
| 13 | Negocio | B-2 | media; 4.302 SF |
| 14 | Negocio | B-3 | grande; 7.524 SF |
| 15 | Laboratorio | Médico | especialización de Lab |
| 16 | Laboratorio | Investigación | especialización de Lab |
| 17 | Laboratorio | L-3 | planta clave de laboratorio grande |
| 18 | Académico | A-1 | pequeño; 1.131 SF |
| 19 | Académico | A-2 | medio; 2.583 SF |
| 20 | Académico | A-3 | grande; 4.070 SF |
| 21 | Cívico | C-1 | pequeño; 2.912 SF |
| 22 | Cívico | C-2 | medio; 6.215 SF |
| 23 | Cívico | C-3 | grande; 8.850 SF |
| 24 | Expansores de Corredor | R-1 | baldosa especial |
| 25 | Sala de Contadores | V-1 | baldosa especial |

## Centro Profesional — Índice 26–38

Salón del Inquilino (N-1), Atrio del Vestíbulo (EE-1), Director del Edificio (O-1), Sala de Correo (P-1), Vestíbulo de Ascensores (S-1), Aseos del Inquilino (U-1), Carga (X-1), Reciclaje (Y-1), Sala de Bicicletas (Z-1), Banco de Trabajo (AA-1), Taquillas del Personal del Edificio (BB-1), Cafetería/Panadería (CC-1), Aseos Públicos (DD-1).

## Oficina Suburbana — Índice 42–55

El mismo vocabulario de equipamiento que el Centro Profesional con sufijo "-2", más la Sala de Limpieza (W-2), exclusiva de la Oficina Suburbana.

## Comercio Selecto — Índice 39–41

Tres variantes de Arrendamiento Comercial: RA-1, RB-2, RC-3.

## Industrial Tecnológico — Índice 56–58

Tres tamaños de Arrendamiento Tecnológico Industrial: TI-1, TI-2, TI-3.

## Paisajismo — Índice 59–62

Las Biocunetas (LL-1) aparecen tres veces — una por Eco Región (llanuras boreales, pradera fescue, parque natural) — y una Galería de Riego (LL-2).

## Aparcamiento — Índice 63–72

Plazas de Aparcamiento (PP-1, tres variantes de Eco Región), Accesibles (PP-2, tres variantes de Eco Región), Aceras (PP-3), Nieve (PP-4), Señalización (PP-5), Iluminación (PP-6).

## Reconciliación del Resumen Maestro V3

La tabla del Resumen Maestro V3 (enero 2026) reemplaza las versiones anteriores para las tipologías arrendables de la Clase General. Cifras autorizadas:

| Tipo de uso | Z1 Hábitat | Z2 Almacén | Z3 Corredor | PK-P (m² / SF) | PK-M | PK-G |
|---|---:|---:|---:|---|---|---|
| Oficina Privada | 6,0 m / 19'8" | 1,4 m / 4'6" | — | 30 / 325 | 43 / 465 | 64 / 685 |
| Laboratorio | 6,8 m / 22'3" | 4,8 m / 15'9" | 3,0 m / 10' | 195 / 2.099 | 316 / 3.401 | 401 / 4.313 |
| Académico | 4,7 m / 15'5" | 3,0 m / 3'7" | — | **105 / 1.131** | 240 / 2.583 | 378 / 4.070 |
| Negocio | 6,0 m / 19'8" | 7,3 m / 23'11" | 2,7 m | 311 / 3.350 | 400 / 4.302 | 669 / 7.524 |
| Médico | 7,2 m / 23'10" | 4,9 m / 16" | 2,9 m / 9'5" | 223 / 2.402 | 331 / 3.568 | 486 / 5.231 |
| Cívico | 6,0 m / 19'8" | 7,2 m / 23'8" | 3,6 m / 12' | 270 / 2.912 | 577 / 6.215 | 822 / 8.850 |
| Oficina Profesional (referencia de diseño inicial) | 6,0 m / 19'8" | 3,8 m / 12'5" | 2,0 m / 6'6" | 130 / 1.400 | — | — |

### Académico Pequeño — reconciliación

El área de la planta clave Académico Pequeño aparece con tres valores diferentes:

- **87,7 m² / 944 SF** — opción "más pequeña" de Muestras V2
- **110,5 m² / 1.189 SF** — Resumen V2 (febrero 2025)
- **105 m² / 1.131 SF** — Resumen Maestro V3 (enero 2026) — **autoritativo**

El token DTCG en `building-width-calculator.dtcg.json` registra correctamente 105 m² / 1.131 SF. El token en `professional-office-subtypes.dtcg.json` debe actualizarse para coincidir con V3.

## Convención de nomenclatura

Las plantas clave usan la convención:

```
planta clave-{clase-de-desarrollo}-{tipología}-{id}[-{eco-región}]
```

Ejemplos:
- `planta clave-general-oficina privada-pequeña`
- `planta clave-general-negocio-media`
- `planta clave-paisajismo-biocunetas-LL-1-llanuras boreales` (sufijo de Eco Región)

El Directorio mezcla dos registros de nomenclatura — identificadores cortos (B-2, M-3, PP-1) y etiquetas de tamaño (pequeña / media / grande). El código posterior debe aceptar ambos; el identificador canónico utiliza etiquetas de tamaño.

## Códigos de baldosa FFE frente a huellas de plantas clave

Cada subtipo de Oficina Profesional también lleva códigos de baldosa FFE (Mobiliario, Instalaciones y Equipamiento) que representan sub-asignaciones de 1/4 de planta:

- `-1` = 1.100 SF
- `-2` = 1.400 SF
- `-3` = 800 SF

Estos **no** son las huellas de las plantas clave. Un código de baldosa FFE Medical M2 (1.400 SF) es distinto de la planta clave Medical Media (3.568 SF), que es el área de suite completa de la muestra.

## Preguntas abiertas

1. **Áreas de las plantas clave de Oficina Corporativa (Índice 4–8)** siguen siendo por determinar en todos los documentos fuente examinados. ¿Cuándo estarán disponibles las muestras de Oficina Corporativa?
2. **Las especializaciones médicas Quiropráctico y Médico de Familia** (Índice 9, 11) aparecen en el Directorio pero no tienen muestras completadas. ¿Se prevén como variantes de disposición de las huellas M1/M2/M3, o como ejercicios de muestra separados?
3. **Las variantes de Eco Región para Biocunetas y Aparcamiento** (Índice 59–68) requieren contenido de plantas clave adaptado al clima — actualmente las filas del Directorio existen pero no han surgido bocetos de muestra por región.

## Véase también

- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-building-width-method]]
- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-tile-system]]
