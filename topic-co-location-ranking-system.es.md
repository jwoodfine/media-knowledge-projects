---
schema: foundry-doc-v1
title: "Sistema de Clasificación de Co-ubicación Minorista"
slug: topic-co-location-ranking-system
aliases:
  - topic-co-location-ranking-system
category: governance
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-06-19
editor: editorial
es_status: complete
short_description: "Algoritmo de puntuación de 12 rangos determinista que evalúa sitios de co-ubicación minorista por convergencia de ancla nombrada en radios de captación definidos."
paired_with: topic-co-location-ranking-system.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

La [[topic-co-location-methodology|metodología de co-ubicación]] de Woodfine se operacionaliza como una **matriz de combinación de anclas nominadas** — un algoritmo determinista que califica cada ubicación de hipermercado [[topic-co-location-anchors|ancla]] basándose en la convergencia de categorías secundarias y terciarias (comerciales y cívicas) dentro de radios de captación definidos.

El sistema genera un índice de 12 rangos agrupados en cinco niveles de calidad, visualizados en la plataforma del Sistema de Información Geográfica (SIG) en [gis.woodfinegroup.com](https://gis.woodfinegroup.com) mediante una escala de colores que va desde el ámbar intenso (★★★★★ Rango 1, el más alto) hasta el azul pálido (★ Rango 5, el más bajo). Las etiquetas orientadas al mapa — Regional, Distrital, Local, Marginal — siguen la jerarquía ICSC descrita en [[topic-co-location-tier-nomenclature|nomenclatura de niveles]], y las compuertas de calificación se detallan en la [[topic-catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]]. Este enfoque proporciona un marco objetivo y validado por capital para evaluar la defendibilidad comercial de un sitio.

## El modelo de anclas nominadas

Cada sitio en el índice está anclado por un único operador de hipermercado o mercancía general de gran formato — Walmart, IKEA, Carrefour y sus equivalentes regionales. El ancla es el requisito fundamental: ningún sitio sin un ancla calificada se admite en el índice. El mapeo completo de cadenas a familias se documenta en la [[topic-retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

Los operadores secundarios y terciarios se clasifican en cuatro categorías deterministas:

| Categoría | Función | Fundamento comercial |
|-----------|---------|----------------------|
| **Hardware** | Secundario-1 | Grandes superficies de bricolaje y materiales de alta frecuencia orientadas al destino (Home Depot, Lowe's, Leroy Merlin). |
| **Club de precio** | Secundario-2 | Comercio mayorista por membresía y alto volumen (Costco, Sam's Club, Makro). |
| **Salud** | Terciario-A | Infraestructura cívica crítica (hospitales, centros médicos) que proporciona bases demográficas estables. |
| **Educación superior** | Terciario-B | Anclas institucionales (universidades, colegios) que generan densidad de tráfico no cíclica. |

Un operador secundario se considera co-ubicado cuando se encuentra dentro del radio secundario (por defecto: 3 km desde el ancla). Los operadores terciarios se puntúan dentro de un radio de 5 km.

## La matriz de 12 rangos

La combinación de categorías presentes determina el rango del sitio. La matriz contiene doce combinaciones nombradas, ordenadas por complejidad estructural y validación comercial:

| Rango | Nivel | Hardware | Club de precio | Salud | Ed. superior |
|-------|-------|:--------:|:--------------:|:-----:|:------------:|
| 1  | ★★★★★ | ✓ | ✓ | ✓ | ✓ |
| 2  | ★★★★ | ✓ | ✓ |   | ✓ |
| 3  | ★★★★ | ✓ | ✓ | ✓ |   |
| 4  | ★★★  | ✓ | ✓ |   |   |
| 5  | ★★★  | ✓ |   |   | ✓ |
| 6  | ★★★  | ✓ |   | ✓ |   |
| 7  | ★★★  |   | ✓ | ✓ | ✓ |
| 8  | ★★   | ✓ |   |   |   |
| 9  | ★★   |   | ✓ |   | ✓ |
| 10 | ★★   |   | ✓ | ✓ |   |
| 11 | ★    |   |   | ✓ | ✓ |
| 12 | ★    |   | ✓ |   |   |

*Las anclas presentes sin operadores secundarios o terciarios calificados quedan excluidas del índice clasificado.*

## Niveles de calidad y distribución

Los doce rangos se agrupan en cinco niveles para ofrecer una visión de alto nivel de la calidad del mercado.

**Nota sobre la escala de rangos de calidad.** La escala de cinco rangos de este artículo (Rango 1 = más alto, Rango 5 = más bajo) describe el índice de calidad visualizado en el mapa. Los sitios individuales de co-ubicación dentro de un Mercado Regional se describen por separado mediante una clasificación espacial de tres niveles de clústeres (T1, T2, T3), en la que T1 designa el clúster con el mayor número de categorías de tipo ancla presentes — el tipo de clúster de mayor composición en un mercado determinado. La escala de cinco rangos de calidad y los niveles espaciales T1/T2/T3 son distintos: el rango de calidad mide la densidad comercial en todo el índice; el nivel espacial clasifica la composición de anclas dentro de un único mercado. Para el vocabulario de niveles T1/T2/T3, consulte [[topic-co-location-tier-nomenclature|Nomenclatura de Niveles de Co-ubicación]].

### ★★★★★ Rango 1 — Co-ubicación completa
*Solo Rango 1. Las cuatro categorías presentes.*
La designación más alta. El ancla opera dentro de 3 km tanto de una gran superficie de hardware como de un club de precio, y dentro de 5 km de una instalación sanitaria y una universidad. Esto indica que cuatro procesos independientes de selección de sitios han convergido en el mismo nodo. A 2 de mayo de 2026: **102 sitios** (Norteamérica).

### ★★★★ Rango 2 — Co-ubicación fuerte
*Rangos 2–3. Tres categorías presentes.*
El ancla está emparejada con una gran superficie de hardware y un club de precio, más una de las dos categorías terciarias. La co-ubicación comercial es estructuralmente completa; falta una dimensión institucional. A 2 de mayo de 2026: **268 sitios** (NA: 259, UE: 9).

### ★★★ Rango 3 — Co-ubicación parcial
*Rangos 4–7. Dos categorías presentes.*
La base comercial del índice. Incluye la combinación de Rango 4 (ancla + hardware + club de precio) así como combinaciones de secundario único apoyadas por presencia institucional terciaria. A 2 de mayo de 2026: **1,571 sitios** (NA: 1,396, UE: 175).

### ★★ Rango 4 — Co-ubicación limitada
*Rangos 8–10. Una categoría presente.*
El ancla tiene un secundario o soporte terciario co-ubicado importante. La calidad del sitio en este nivel depende en gran medida del mercado. A 2 de mayo de 2026: **356 sitios** (NA: 333, UE: 23).

### ★ Rango 5 — Solo ancla
*Rangos 11–12. Solo terciario o solo club de precio.*
El ancla hipermercado está presente, pero los secundarios principales de co-ubicación comercial (hardware y/o club de precio) están mayormente ausentes. Estos sitios representan el mínimo del índice. A 2 de mayo de 2026: **441 sitios** (NA: 398, UE: 43).

## Calibración y escasez

El radio secundario (1 km, 2 km o 3 km) determina la densidad del índice. La plataforma aplica una **regla de calibración** automática para mantener la escasez del índice: si los sitios de Rango 1 superan el 10% del total de ubicaciones de anclas, el sistema reduce el radio por defecto.

A 2 de mayo de 2026, los sitios de Rango 1 representan el 3,7% del total de anclas — muy por debajo del umbral. El valor por defecto actual de 3 km sigue siendo la configuración de calibración activa.

## Adaptación al mercado

Cada uno de los ocho mercados minoristas utiliza una configuración de región dedicada que mapea los operadores locales a los roles canónicos de ancla y secundario. Esto asegura que el algoritmo aplique una lógica estructural consistente en las distintas jurisdicciones donde diferentes marcas desempeñan funciones comerciales equivalentes (por ejemplo, Costco en Canadá, Makro en Europa).

La integración del conjunto de datos de instalaciones de aviación (29.020 registros) en la puntuación terciaria es un objetivo previsto para futuras iteraciones de la matriz de clasificación. [ni-51-102] [osc-sn-51-721]

## Procedencia
- **Verificación:** La distribución de rangos y la lógica de la matriz han sido verificadas contra la configuración de la plataforma SIG al 2 de mayo de 2026.
- **Declaración prospectiva:** La integración del conjunto de datos de aviación en la puntuación terciaria es un objetivo previsto, etiquetado conforme a [ni-51-102].

## Ver también
*   [[topic-co-location-methodology]]
*   [[topic-co-location-intelligence-overview]]
*   [[topic-co-location-anchors]]

## Referencias

- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14
- [DBSCAN](https://es.wikipedia.org/wiki/DBSCAN) — Wikipedia, consultado 2026-06-14

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
