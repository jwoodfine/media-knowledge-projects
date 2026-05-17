---
schema: foundry-doc-v1
title: "Profundidades de zona por tipo de uso — fuentes, valores y justificación"
slug: topic-bim-zone-depths-per-use-type
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-zone-depths-per-use-type.md
---

> **Complemento:** [[topic-bim-building-width-method]] para la fórmula y la sección transversal especular.

## Tabla resumen — valores canónicos

Los valores de Z1/Z2/Z3 indicados a continuación son las profundidades **por lado** (Z1 y Z2 son especulares; Z3 es única en la línea central). Todos los valores se remontan a la fuente citada.

| Tipo de Uso | Z1 Hábitat | Z2 Almacén | Z3 Corredor | Anchura del Edificio | Fuente |
|---|---|---|---|---|---|
| Oficina Privada | 5,9944 m / 19'8" | 1,3716 m / 4'6" | — | **14,73 m / 48'4"** | Bocetos PO-1/PO-2/PO-3 |
| Académico | 4,7 m / 15'5" | 3,0 m / 9'10" | — | **15,40 m / 50'6"** | Resumen V2, 2025-05-13 |
| Oficina Profesional (referencia V12) | 6,0 m / 19'8" | 3,0 m / 9'10" | 3,0 m / 9'10" | **21,00 m / 68'11"** | V12, 2025-01-07 (Z2/Z3 marcados como por definir) |
| Laboratorio | 6,7818 m / 22'3" | 4,8006 m / 15'9" | 3,048 m / 10'0" | **26,21 m / 86'0"** | Resumen V2; egreso de alta peligrosidad IBC |
| Médico | 7,2819 m / 23'10" | 4,877 m / 16'0" | 2,892 m / 9'5" | **27,20 m / 89'3"** | Bocetos M3/M1/M2 (286 5/8" + 192" + 113 7/8") |
| Negocio | 5,51 m / 18'1" | 9,26 m / 30'5" | 2,75 m / 9'0" | **29,30 m / 96'2"** | Notas V3 Opción A/A (la más ancha enumerada) |
| Cívico | 6,0 m / 19'8" | 7,23 m / 23'9" | 3,6 m / 11'10" | **30,06 m / 98'8"** | Valores sintetizados; sin boceto completado |

Fórmula: `Anchura = 2 × (Z1 + Z2) + Z3`. Consulte [[topic-bim-building-width-method]] para la derivación.

## Por tipo de uso

### Oficina Privada (PO-1 / PO-2 / PO-3)

| Zona | Valor | Evidencia de boceto |
|---|---|---|
| Z1 Hábitat | **5,9944 m / 19'8"** | "19'-8"" en cada uno de PO-1, PO-2, PO-3 |
| Z2 Almacén | **1,3716 m / 4'6"** | "4'-6"" en cada boceto (zona de almacenamiento reducido, por debajo de la línea central discontinua) |
| Z3 Corredor | **— (ninguno)** | Cada despacho se abre al corredor compartido del edificio (fuera del arrendamiento) |
| Área de planta clave SF | PO-1 = 325, PO-2 = 465, PO-3 = 685 | Etiquetas del boceto |
| Área de planta clave m² | 30,19, 43,20, 63,64 | Calculado a partir de SF |
| Anchura del edificio | **14,73 m / 48'4"** | 2 × (5,9944 + 1,3716) |

La Oficina Privada es el tipo de uso más estrecho. Los 5,9944 m de Hábitat quedan marginalmente por debajo del umbral de 6,0 m de la Norma Europea de Iluminación — marcado para revisión en la aprobación de la Planta Clave.

Combinaciones: PO-1 + PO-1 = 60,4 m² (650 SF); PO-1 + PO-2 = 73,4 m² (790 SF); PO-1 + PO-3 = 93,8 m² (1.010 SF); PO-2 + PO-3 = 106,8 m² (1.150 SF). Estas cubren la brecha entre Oficina Privada Grande y Oficina Profesional Pequeña.

### Académico (A1 / A2 / A3)

| Zona | Valor | Fuente |
|---|---|---|
| Z1 Hábitat | **4,7 m / 15'5"** | Resumen V2 |
| Z2 Almacén | **3,0 m / 9'10"** | Resumen V2 (la fuente muestra "3'7"" en pies, que es una transposición; 3,0 m = 9'10" es correcto) |
| Z3 Corredor | **— (ninguno)** | Los locales se abren al corredor del edificio |
| Área m² planta clave | Pequeña 87,7 / Media 240,3 / Grande 376,3 | Muestras de Plantas Clave V2 |
| Área SF planta clave | Pequeña 944 / Media 2.586 / Grande 4.050 | |
| Anchura del edificio | **15,40 m / 50'6"** | 2 × (4,7 + 3,0) |

El Académico comprime el Hábitat por debajo de 6 m porque **el asiento mira hacia adelante** (hacia un podio o pizarra) en lugar de hacia la fachada. La Norma Europea de Iluminación se aplica a puestos de trabajo; el asiento en estilo auditorio no es uso de puesto de trabajo.

**Inconsistencia:** `building-width-calculator.dtcg.json` registra el Académico Pequeño como **105 m² / 1.131 SF**, mientras que `professional-office-subtypes.dtcg.json` lo registra como **87,7 m² / 944 SF**. Pendiente de decisión del operador sobre cuál es canónico.

### Oficina Profesional (referencia)

| Zona | Valor | Fuente |
|---|---|---|
| Z1 Hábitat | **6,0 m / 19'8"** | V12 (enero 2025) |
| Z2 Almacén | **3,0 m / 9'10"** | V12 — *marcado "por definir"; valor provisional* |
| Z3 Corredor | **3,0 m / 9'10"** | V12 — *marcado "por definir"; valor provisional* |
| Área m² planta clave | Solo pequeña: 130,06 | Token DTCG; Media/Grande pendientes |
| Área SF planta clave | Solo pequeña: 1.400 | Token DTCG |
| Anchura del edificio | **21,00 m / 68'11"** | Total declarado en V12 |

La Oficina Profesional es el tipo de uso **de referencia** — el tipo del que derivan los demás subtipos del Centro Profesional (Médico, Negocio, Laboratorio, Académico, Cívico) variando Z1, Z2 y Z3.

V12 marca explícitamente Z2 y Z3 como **"por definir"** con valores provisionales de 3 m. Cuando se complete la Planta Clave de Oficina Profesional, el operador fijará Z2 y Z3 para que coincidan con la disposición amueblada.

### Laboratorio (L1 / L2 / L3)

| Zona | Valor | Fuente |
|---|---|---|
| Z1 Hábitat | **6,7818 m / 22'3"** | Resumen V2 |
| Z2 Almacén | **4,8006 m / 15'9"** | Resumen V2 |
| Z3 Corredor | **3,048 m / 10'0"** | Resumen V2 (mínimo de egreso de alta peligrosidad IBC) |
| Área m² planta clave | Pequeña 195,0 / Media 316,0 / Grande 400,7 | Muestras V2 |
| Área SF planta clave | Pequeña 2.099 / Media 3.401 / Grande 4.313 | Muestras V2 |
| Anchura del edificio | **26,21 m / 86'0"** | 2 × (6,7818 + 4,8006) + 3,048 |

El Z1 más ancho del Laboratorio acomoda la profundidad de la mesa de trabajo (Treston TP-915 ≈ 900 mm) y el espacio libre de la campana de extracción (≈ 940 mm + 1.500 mm de egreso frente a la campana). El corredor de 10'0" es el mínimo de egreso para ocupación de alta peligrosidad según el IBC.

Especializaciones: Laboratorio Médico, Laboratorio de Investigación.

### Médico (M1 / M2 / M3)

| Zona | Valor | Evidencia de boceto |
|---|---|---|
| Z1 Hábitat | **7,2819 m / 23'10"** | "286 5/8"" en M1/M2/M3 (= 7,282 m) |
| Z2 Almacén | **4,877 m / 16'0"** | "192"" en M1/M2/M3 (= 4,877 m) |
| Z3 Corredor | **2,892 m / 9'5"** | "113 7/8"" en M1/M2/M3 (= 2,892 m) |
| M3 (Pequeño, 2 sillones dentales) | **2.401,5 SF** / 223 m² | Etiqueta del boceto |
| M1 (Medio, 4 sillones dentales) | **3.567,7 SF** / 331 m² | Etiqueta del boceto |
| M2 (Grande, 6 sillones dentales) | **5.231,4 SF** / 486 m² | Etiqueta del boceto |
| Anchura del edificio | **27,20 m / 89'3"** | 2 × (7,2819 + 4,877) + 2,892 |

El uso Médico tiene el Hábitat más ancho de todos los tipos de uso. La profundidad acomoda la camilla de exploración (Midmark 626 ≈ 790 mm) más asiento del paciente, circulación del personal sanitario y una ventanilla de recepción con vista a la fachada. El corredor de 2,892 m cumple el espacio libre para camilla y silla de ruedas según ADA/CSA-B651.

Las notas del operador en el boceto M3 señalan: "Añadir segunda puerta para emergencias", "Línea de visión — seguridad — la recepción necesita ver la puerta" y "Mover los asientos hacia abajo fuera de la Zona n.º 1".

Especializaciones: Dentista, Médico de Familia.

### Negocio (B1 / B2 / B3)

El tipo de uso Negocio tiene **21 opciones de anchura enumeradas** según las Notas V3. El almacén de tokens registra la opción simétrica más ancha como valor por defecto:

| Zona | Valor | Fuente |
|---|---|---|
| Z1 Hábitat | **5,51 m / 18'1"** | Notas V3 Opción A |
| Z2 Almacén | **9,26 m / 30'5"** | Notas V3 Opción A (la más ancha enumerada) |
| Z3 Corredor | **2,75 m / 9'0"** | Notas V3 (fijo en las 21 opciones) |
| Área SF planta clave | Pequeña 3.350 / Media 4.302 / Grande 7.524 | Bocetos 2-4 |
| Anchura del edificio | **32,29 m / 105'11"** | 2 × (5,51 + 9,26) + 2,75 (Opción A/A) |

**Advertencia importante:** las Notas V3 enumeran 21 combinaciones (Opción A/A hasta D/D), donde las dos letras indican la elección de Z1/Z2 en el lado izquierdo y en el lado derecho. La opción de Negocio más estrecha es **25,29 m (D/D)** y la más ancha es **32,29 m (A/A)**. Las opciones asimétricas son generalmente desfavorables para la composición de baldosas porque los tabiques divisorios deben absorber la asimetría.

Del comentario del operador en las Notas V3 sobre la Opción D: "El área total de las Plantas Fijas [es] para Centros Profesionales de aproximadamente **19.000 SF a 23.000 SF** y para Oficina Suburbana de aproximadamente **17.000 SF a 21.000 SF**."

### Cívico (C1 / C2 / C3)

| Zona | Valor | Fuente |
|---|---|---|
| Z1 Hábitat | **6,0 m / 19'8"** | Sintetizado (sin boceto completado) |
| Z2 Almacén | **7,23 m / 23'9"** | Sintetizado (valor del almacén de tokens) |
| Z3 Corredor | **3,6 m / 11'10"** | Sintetizado — egreso de asamblea pública |
| Área m² planta clave | Pequeña 270 / Media 577 / Grande 822 | Almacén de tokens (derivado de muestras) |
| Área SF planta clave | Pequeña 2.912 / Media 6.215 / Grande 8.850 | Almacén de tokens |
| Anchura del edificio | **30,06 m / 98'8"** | 2 × (6,0 + 7,23) + 3,6 |

**El uso Cívico no tiene aún un boceto completado.** Los valores de Z1/Z2/Z3 en el almacén de tokens son sintetizados a partir de la intención de diseño (archivo de registros públicos; corredor más ancho para circulación ceremonial y egreso de asamblea pública). Especializaciones: Sala de Vistas, Oficina Municipal, Espacio Cultural, Asamblea Cívica.

## La adición perpendicular de escritorios de 0,7 m

Se aplica a **cualquier Z1 Hábitat** que disponga los escritorios de forma perpendicular a la fachada. Token: `bim.circulation-addition.perpendicular-desk = 0,7 m`. Z1 efectivo = 6,0 + 0,7 = **6,7 m** cuando se requieren escritorios perpendiculares para sentar tres escritorios en serie.

## Rangos objetivo de la planta

| Clase | Rango |
|---|---|
| Centros Profesionales | 19.000 – 23.000 SF |
| Oficina Suburbana | 17.000 – 21.000 SF |

El almacén de tokens actual codifica de forma fija 20.000 SF como `floorPlate.netLeasableSF`. Convertir a rango con variantes PC y SU.

## Investigación futura

- [ ] Confirmar el área de la planta clave Académico Pequeño: **87,7 m² (944 SF)** según Muestras V2 frente a **105 m² (1.131 SF)** según el almacén de tokens DTCG
- [ ] Completar el boceto Cívico para anclar los valores de Z1/Z2/Z3 en una disposición de mobiliario real
- [ ] Confirmar la preferencia del operador para Negocio: Opción A/A (más ancha, 32,29 m) frente a una opción equilibrada como C/C (~27 m)
- [ ] Capturar las dimensiones del número de referencia del fabricante en un archivo `furniture.dtcg.json`
- [ ] Completar los valores Z2/Z3 de Oficina Profesional (actualmente valores provisionales de V12 a 3 m / 3 m por definir)
- [ ] Documentar el suplemento de 0,7 m por escritorios perpendiculares como modificador de Hábitat efectivo
- [ ] Verificar si los 6,0 m de Hábitat siguen una cláusula específica de EN 12464-1

## Inconsistencias en los documentos fuente (abiertas)

| # | Problema | Acción |
|---|---|---|
| 1 | Área Académico Pequeño: 105 m² (DTCG) frente a 87,7 m² (subtipos DTCG / Muestras V2) | Decisión del operador necesaria |
| 2 | Token Médico Z1 = 7,2 m, boceto = 286 5/8" = 7,28 m | Actualización del archivo de tokens a 7,2819 m pendiente |
| 3 | Valores provisionales Z2/Z3 de Oficina Profesional (V12: 3 m / 3 m por definir) | Valores a confirmar desde la Planta Clave |
| 4 | Planta codificada de forma fija en 20.000 SF; las Notas V3 establecen rangos | Convertir a token de rango |
| 5 | Total de 21 m del PDF frente a aritmética anterior de 21,6 m del token | Reconciliado el 2026-05-17 restaurando los valores de V12 |

## Véase también

- [[topic-bim-building-width-method]]
- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-key-plans-index]]
