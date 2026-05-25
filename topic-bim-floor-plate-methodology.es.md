---
schema: foundry-doc-v1
title: "Metodología de la planta — plantas clave y baldosas"
slug: topic-bim-floor-plate-methodology
short_description: "Un sistema de planificación de espacios geométricamente autosimilar y aperiódico que dimensiona floor plates a partir del inventario de mobiliario real mediante Key Plans, Tiles y ensamblajes de Building Core — todas las dimensiones rastreables a SKUs de mobiliario real, cada zona climática coincidiendo exactamente con un Tile."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-25
editor: pointsav-engineering
paired_with: topic-bim-floor-plate-methodology.md
---

La metodología de planta es un sistema de planificación espacial geométrico en el que cada pie cuadrado de un edificio se asigna a una Planta Clave con nombre que se rastrea directamente hasta dimensiones de mobiliario real. Una **Planta Clave** es la unidad mínima: un rectángulo etiquetado alrededor del inventario real de mobiliario de un inquilino, dimensionado para incluir escritorios, almacenamiento, circulación y holguras de accesibilidad. Una **Baldosa** es un grupo componible de Plantas Clave — cada Baldosa es exactamente una zona climática HVAC. Una **Planta** es el conjunto de Baldosas más un Núcleo del Edificio más Baldosas Especiales; nada de la planta queda sin representar.

El sistema se define en la Metodología V12 (mayo 2025) y la Ficha Técnica V12 (enero 2026) como "un sistema de planificación espacial geométrico, autosimilar y aperiódico basado en disposiciones de mobiliario y equipamiento, circulación y progresiones modulares de área por persona."

Tres propiedades cualifican el sistema:

- **Aperiódico** — las Baldosas no se repiten en una cuadrícula fija.
- **Autosimilar** — cada Baldosa es exactamente una zona climática HVAC, independientemente de su tamaño.
- **Geométrico** — todas las dimensiones se resuelven como medidas métricas reales impulsadas por referencias reales de mobiliario (Steelcase, Midmark, Treston, Agati).

## Las tres familias de baldosas

| Familia | Área | m² | Función |
|---|---|---|---|
| Pequeña | 2.700 SF | 250,84 | Más flexible; unidad mínima de autonomía climática |
| Mediana | 3.500 SF | 325,16 | Familia puente; absorbe la geometría del lado corto |
| Grande | 4.900 SF | 455,22 | Ancla corporativa; se aproxima a la baldosa de 1/4 de planta |

Fuente: Metodología V12 p. 2. La familia Mediana está documentada en el PDF de la Metodología V12 pero actualmente no aparece en `tile-system.dtcg.json` — señalado como vacío en el almacén de tokens.

## Reglas de composición de baldosas

Estas reglas rigen la forma en que las Baldosas se componen en una Planta válida. Se codifican como validadores `FP-*` en el crate Rust `tool-floorplates` previsto.

### FP-SUM — cada metro cuadrado está representado

El conjunto de Baldosas Básicas + Baldosas Compuestas + Baldosas Especiales + el Núcleo del Edificio suma el Área Neta Arrendable completa con una tolerancia de ±100 SF. No existe espacio libre sin una Planta Clave correspondiente.

### FP-ENDCAP — los lados cortos reciben luz natural

Los dos extremos del edificio utilizan baldosas de extremo (End Cap):

- End Caps de familia Pequeña: Baldosa B-1 (Privada 2.700 SF), Baldosa E-1 (Mixta izquierda 2.700 SF), Baldosa E-2 (Mixta derecha 2.700 SF).
- End Caps pareados de 6.000 SF: Baldosa A-1 (Corporativa), Baldosa B-2 (Privada), Baldosa C-3 (Profesional Media), Baldosa C-4 (Profesional Grande).
- End Caps de familia Mediana: Baldosa E-1 (variante Oficina Privada Media) y Baldosa E-2 (variante Oficina Profesional Media), cada una de aproximadamente 3.500–5.500 SF.

Los End Caps deben recibir luz natural en ambos ejes perpendiculares; un End Cap sin ventana en uno de los ejes requiere una revisión del módulo de ventanas (Metodología V12 p. 8, Muestra n.º 3/n.º 4).

### FP-CORE — Núcleo retranqueado desplazado

El Núcleo del Edificio (ascensores, escaleras de servicio, escaleras de emergencia, aseos, sala de contadores, sala de limpieza) se posiciona al menos 18 m desde el extremo corto del edificio. Esto deja suficiente longitud de planta para dos End Caps más al menos una Baldosa Básica a cada lado del núcleo.

### FP-SNAP — la anchura de la Baldosa Especial coincide con la anchura de la Planta Clave

Las Baldosas Especiales SP-A, SP-B y SP-C rellenan el área residual que rodea el Núcleo. Su anchura se ajusta a la anchura de la Planta Clave de Oficina Profesional más próxima. Esto preserva la continuidad de los tabiques divisorios. SP-C, frente al Núcleo, debe evitar la alineación directa de cualquier puerta con la apertura del ascensor (Metodología V12 p. 9).

### FP-CLIMATE — una baldosa, una zona HVAC

Cada Baldosa es una zona climática independiente. Los inquilinos que combinan Baldosas combinan el control climático; el contrato de arrendamiento valora explícitamente esta compensación. Las baldosas más pequeñas aumentan la autonomía del inquilino; las más grandes reducen el número de zonas a favor del espacio contiguo.

### FP-DOORS — número de puertas por baldosa y por planta

Cada baldosa puede tener hasta 10 puertas; cada planta puede tener hasta 80 puertas. El número de puertas es uno de los impulsores del coste en la economía del arrendamiento — cada puerta es también una conexión de servicio (eléctrica, datos, toma HVAC).

### FP-CORNER — las baldosas pequeñas en esquinas requieren revisión estructural

Cuando una baldosa de familia Pequeña se ubica en una esquina estructural, se revisa la cuadrícula de pilares antes de finalizar la baldosa. Las baldosas pequeñas pueden entrar en conflicto con el módulo estructural; la posición del núcleo se ajusta si las baldosas del lado corto presentan conflictos (Metodología V12 p. 2, nota sobre el inventario de Baldosas).

## Rango dimensional de la planta

| Clase | Área neta arrendable por planta | Número de plantas |
|---|---|---|
| Centros Profesionales | 19.000 – 23.000 SF | 3 – 5 plantas |
| Oficina Suburbana | 17.000 – 21.000 SF | 6 – 9 plantas |
| Comercio Selecto | 4.500 / 6.700 / 7.700 SF | variable |
| Industrial Tecnológico | 7.200 / 8.400 SF | variable |

Fuente: PDF de Combinaciones V1 p. 2 (álgebra formal).

## Por qué importa "geométrico autosimilar aperiódico"

- **Geométrico** — cada dimensión cita una referencia de mobiliario más un espacio libre reglamentario, no una regla empírica del promotor.
- **Autosimilar** — una Baldosa de 2.700 SF es el mismo tipo de objeto que una Baldosa de 4.900 SF: una zona climática, un instrumento de arrendamiento.
- **Aperiódico** — las baldosas no se repiten en una cuadrícula fija. Una planta puede llevar una secuencia de baldosas diferente en cada nivel.

## Ejemplo de composición de planta

De la Metodología V12 p. 4 (Muestra Baldosa Pequeña):

- Baldosa A (Oficina Corporativa 2.700) ×2 a la izquierda de las escaleras de emergencia izquierdas
- Baldosa A (Oficina Corporativa 2.700) ×2 entre las escaleras de emergencia
- Baldosa Especial A (400 SF) — adyacente al núcleo por la izquierda
- Núcleo del Edificio
- Baldosa Especial B (300 SF) — adyacente al núcleo por la derecha
- Baldosa A (Oficina Corporativa 2.700) — a la derecha del núcleo
- Baldosa A ×2 (5.400 SF combinado) en el extremo derecho

Baldosas Básicas: 18.900 SF. Baldosas Especiales: 1.100 SF. Total: 20.000 SF.

## Investigación abierta

- **P1.** El almacén de tokens registra E-1 y E-2 como End Caps Pequeños de 2.700 SF. La Metodología V12 los muestra como End Caps Medianos de aproximadamente 3.500–5.500 SF. ¿Cuál de las dos convenciones es autoritativa?
- **P2.** SP-C está documentada con 4.700 SF frente al Núcleo. ¿Cómo interactúa con el vestíbulo de ascensores en composiciones con baldosas medianas?
- **P3.** ¿Cuál es la derivación exacta de la distancia mínima de 18 m entre el núcleo y el extremo corto? Se infiere a partir de la anchura del End Cap y la primera baldosa, pero ningún PDF cita la cifra directamente.
- **P4.** El token Baldosa B-1 registra 1.800 SF de oficina + 900 SF de corredor. La Metodología de mayo muestra 5 módulos PO que suman 1.850 SF + 850 SF residual. ¿Cuál composición está vigente?
- **P5.** La tolerancia de 100 SF en FP-SUM es política del operador, no texto del documento fuente. Confirmar la banda de tolerancia antes de codificarla.

## Véase también

- [[topic-bim-tile-system]]
- [[topic-bim-floor-plate-tile-combinations]]
- [[topic-bim-building-width-method]]
- [[topic-bim-zone-depths-per-use-type]]
