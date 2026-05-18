---
schema: foundry-doc-v1
title: "Combinaciones de baldosas en la planta — composiciones de muestra y compromisos"
slug: topic-bim-floor-plate-tile-combinations
short_description: "Las composiciones de Tile de muestra nombradas de la Metodología V12 — cuatro configuraciones documentando los intercambios que cada una realiza entre mezcla de inquilinos, autonomía de zona climática, posiciones de brecha de arrendamiento y tolerancia de demarcación."
category: bim
type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-floor-plate-tile-combinations.md
---

La Metodología de la Planta es intencionalmente no determinista: el catálogo tiene el tamaño necesario para que existan múltiples composiciones válidas para cualquier combinación de inquilinos. Este artículo documenta las composiciones de muestra con nombre de la Metodología V12, los compromisos que implica cada una y las consecuencias para el arrendamiento.

## Las cuatro composiciones de muestra de la Metodología V12

### Muestra Baldosa Pequeña (Metodología p. 3, p. 4)

```
Baldosa A | Baldosa A | SP-A | Núcleo | SP-B | Baldosa A | Baldosa A×2
2.700     | 2.700     | 400  | —      | 300  | 2.700     | 5.400
```

Baldosas Básicas: 18.900 SF. Baldosas Especiales: 1.100 SF. Total: 20.000 SF.

**Compromiso.** Cuando todas las baldosas son Pequeñas, la autonomía climática por metro cuadrado es máxima, pero el salto entre Oficina Profesional (2.700 SF por baldosa) y Oficina Corporativa (2.700 SF por baldosa) desaparece — la metodología señala esto como el vacío "Oficina Corporativa (2.700) − Oficina Profesional Media (1.100) = 1.600", que deja una gama intermedia difícil entre 1.600 y 2.700 SF.

### Muestra Baldosa Mediana (Metodología p. 3, p. 8)

```
Baldosa D | SP-A  | Núcleo | SP-A  | Baldosa D | Baldosa D×2
3.500     | 2.100 | —      | 2.000 | 3.500     | 7.000
```

Baldosas Básicas: 17.500 SF. Baldosas Especiales: 2.500 SF. Total: 20.000 SF.

**Compromiso.** Las baldosas medianas producen una proporción núcleo-extremo más equilibrada y reducen la carga de Baldosas Especiales, pero introducen un salto mayor desde la Oficina Profesional Media (1.100) hasta la Oficina Corporativa (3.500) = 2.400 SF.

### Muestra Baldosa Grande (Metodología p. 4, p. 8)

```
Corredor Interno | SP-B | Núcleo | SP-A | Baldosa F
Corporativa ×2 (9.800) | SP-B (800) | — | SP-A (2.000) | Baldosa F (4.900)
```

Baldosas Básicas: 14.700 SF. Baldosas Especiales: 5.300 SF. Total: 20.000 SF.

**Compromiso.** Las baldosas grandes hacen el edificio más corto (mayor longitud de planta) pero cada baldosa ocupa más del lado corto, reduciendo el número de zonas climáticas independientes disponibles para los inquilinos. La metodología señala que con baldosas grandes "la propia Baldosa se vuelve demasiado grande en el sentido de que impide que ambos extremos del edificio puedan desglosarse en Zonas Climáticas inclusivas."

### Muestra Salón del Inquilino de 2 Plantas (Metodología p. 5, p. 8)

La segunda planta de todos los edificios de Centro Profesional y Oficina Suburbana se reserva para un Salón del Inquilino. El Salón ocupa media planta (referencia de 10.000 SF) en el lado largo opuesto al núcleo; la otra media planta lleva baldosas de Oficina Privada. Una Escalera Decorativa conecta el vestíbulo de la Planta Principal con el atrio del Salón del Inquilino.

**Compromiso.** La mitad de la segunda planta es un elemento sin superficie arrendable. El Salón está posicionado para atraer tráfico a través de la fachada pública del edificio; este espacio reclamo es la expresión de la metodología de "la Oficina como Minorista" (Libro Blanco §3).

## Tipologías de composición

Las muestras con nombre anteriores se generalizan en cuatro tipologías de composición. Son etiquetas orientadas al operador; los documentos fuente no las emplean, pero los compromisos sí son explícitos en la metodología.

### De predominio corporativo

Mayoritariamente Baldosa A / Baldosa F / fracciones Corporativas. Pocas zonas climáticas por planta (4–6). Mayor espacio contiguo. Mayor idoneidad para un único inquilino. Se utiliza para inquilinos ancla Corporativos que ocupan una planta completa o fracciones mayores.

### De predominio de Oficina Privada (Mixta)

Mayoritariamente Baldosa B-1 / Baldosa G / End Caps mixtos E-1/E-2. De 30 a 40 zonas climáticas por planta. Autonomía máxima del termostato. Mayor coste de ingeniería HVAC; mayor rentabilidad del arrendamiento porque cada termostato es una línea de factura independiente.

### Centro Profesional (Mixta)

Mayoritariamente Baldosa C-1/C-2/C-3/C-4 / Baldosa H. Adecuada para inquilinos de rango medio de usos médico, empresarial, de laboratorio, académico y cívico. El número de zonas climáticas es moderado (8–15 por planta). La metodología denomina a esta la configuración de planta media canónica.

### Planta mixta

Una composición que combina varios tipos de baldosas Básicas, Compuestas y Especiales en una misma planta. Oficina Corporativa a la izquierda, Oficina Privada en el centro, Oficina Profesional inmediatamente a la derecha del Núcleo, End Cap en ambos lados cortos.

## Combinaciones de baldosas y tolerancia de tabiquería

Los inquilinos pueden ocupar espacio cruzando los límites de las Baldosas siempre que los tabiques divisorios se alineen con uno de los bordes de la Baldosa. La metodología establece:

> "Los inquilinos tienen la capacidad de tomar cualquier tamaño de espacio siempre que los tabiques divisorios se alineen con cualquiera de las Baldosas. Los inquilinos que toman espacio más allá de los límites de las Baldosas ya no mantienen el control de la Zona Climática."
> — Metodología V12 p. 10 (Arrendamiento).

El diagrama de la página de Arrendamiento muestra tres Inquilinos (A, B, C) que se superponen en múltiples límites de Baldosas. El instrumento de arrendamiento valora explícitamente la pérdida del control de la zona climática: un Inquilino cuyo tabique divisorio divide una Zona Climática comparte el termostato con el inquilino vecino de esa zona.

## Muestras de luz natural en End Caps

La Metodología V12 (pp. 7–8) muestra cuatro muestras de End Cap: dos aceptables (Muestra n.º 1 y n.º 2 — luz natural en ambos ejes perpendiculares) y dos inaceptables (Muestra n.º 3 y n.º 4 — sin luz natural en los End Caps, "No es 100 % eficiente en el arrendamiento"). Los operadores deben consultar estas muestras al revisar la disposición de ventanas de los End Caps en nuevos diseños de edificios.

## Investigación abierta

- **P1.** La composición de la Muestra Baldosa Grande lista "Oficina Corporativa ×2 = 9.800 SF", pero dos instancias de Baldosa F suman 9.800. ¿Se trata de una Oficina Corporativa arrendable única de 9.800 SF o de dos baldosas de Oficina Corporativa contiguas de 4.900 cada una? El diagrama es ambiguo.
- **P2.** El diagrama de la Muestra de 2 Plantas muestra "Baldosa Especial x 2 = 11.200 SF" combinada con "Oficina Corporativa x 2 = 7.000 SF" en la mitad del Salón del Inquilino. Las cifras (11.200 + 7.000 = 18.200) son inconsistentes con la referencia de 20.000 SF. Confirmar la composición del salón.
- **P3.** La Metodología Muestra Baldosa Mediana reporta un total de 22.900 SF en la p. 11, mayor que la referencia de 20.000 SF. Confirmar si 22.900 SF está previsto como ejemplo de trabajo del "límite superior de Centros Profesionales".
- **P4.** Ningún documento fuente especifica qué ocurre cuando un inquilino toma una Baldosa parcial que no se alinea con ningún borde de Baldosa. ¿Puede el instrumento de arrendamiento rechazar dicha solicitud, o se recompone la Baldosa?

## Véase también

- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-tile-system]]
- [[topic-bim-zone-depths-per-use-type]]
