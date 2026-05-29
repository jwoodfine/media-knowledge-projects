---
schema: foundry-doc-v1
title: "Fuentes de datos de áreas de influencia — población y gasto"
slug: topic-trade-area-data-sources
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Las estimaciones de población de WorldPop 2026 y los proxies de gasto per cápita anuales de encuestas nacionales de hogares sustentan las estadísticas de área de influencia para cada cluster de co-ubicación."
paired_with: topic-trade-area-data-sources.md
---

Las estimaciones de población y de gasto minorista son las dos capas de entrada que impulsan las estadísticas de áreas de influencia para cada cluster de [[topic-co-location-methodology|co-ubicación]]. Ambas se derivan de fuentes de datos públicas y se aplican al nivel de la rejilla hexagonal H3 de resolución 7, según la [[topic-od-catchment-methodology|metodología de captación O-D]]. Juntas suministran los ejes de población y gasto utilizados por el [[topic-co-location-ranking-system|sistema de clasificación determinista]] y por la [[topic-catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]].

## Datos de población

Las estimaciones de población se obtienen de la **rejilla de población de 100 metros de WorldPop 2026** (worldpop.org). WorldPop produce estimaciones de población modeladas a partir de microdatos censales, imágenes satelitales y redistribución dasimétrica. La resolución de 100 m sitúa la población a nivel de sub-manzana, permitiendo una delimitación precisa del área de influencia.

### Proceso de tratamiento

1. **Filtro espacial:** Solo se conservan las celdas de la rejilla situadas a menos de 150 km de al menos un centroide de cluster de co-ubicación, reduciendo el volumen de datos en aproximadamente un 80%.
2. **Agregación H3:** Las celdas conservadas se asignan a su hexágono H3 de resolución 7 correspondiente y se suman los valores de población.
3. **Salida:** `census-h3-res7.jsonl` — un registro por celda H3 con campos `{h3, lat, lon, pop, iso}`.

### Países cubiertos

Estados Unidos, Canadá, México, Gran Bretaña, Alemania, Francia, Países Bajos, Austria, Portugal, Grecia, Dinamarca, Islandia y Polonia — 13 países según la versión actual del proceso.

## Datos de gasto

Las estimaciones de gasto se sintetizan aplicando **multiplicadores de gasto per cápita anual** por categoría minorista a la rejilla de población. Los multiplicadores son proxies derivados de encuestas nacionales de gastos de los hogares.

| País | Alimentación (anual) | Bricolaje (anual) | Mayorista (anual) | Moneda |
|------|---------------------|-------------------|-------------------|--------|
| Estados Unidos | $3.500 | $1.200 | $1.500 | USD |
| Canadá | C$3.200 | C$1.100 | C$1.300 | CAD |
| México | MX$18.000 | MX$3.500 | MX$2.500 | MXN |
| Gran Bretaña | £2.800 | £850 | £900 | GBP |
| Alemania | €2.900 | €950 | €1.000 | EUR |
| Francia | €3.100 | €900 | €1.000 | EUR |
| Países Bajos | €2.700 | €1.000 | €1.100 | EUR |
| Austria | €3.000 | €950 | €1.000 | EUR |
| Portugal | €2.400 | €600 | €700 | EUR |
| Grecia | €2.200 | €500 | €600 | EUR |
| Dinamarca | €3.500 | €1.200 | €1.100 | EUR |
| Islandia | €4.000 | €1.500 | €1.500 | EUR |
| Polonia | PLN 8.000 | PLN 2.000 | PLN 2.500 | PLN |

Los multiplicadores se expresan en moneda local. Las comparaciones de gasto entre países requieren normalización cambiaria, que no se aplica en la versión actual del proceso. Las clasificaciones son más significativas dentro de un mismo país o dentro de la eurozona.

## Agregación por área de influencia

Para cada cluster de co-ubicación, las zonas de captación primaria y secundaria se definen mediante anillos de distancia en línea recta (véase: Metodología de captación O-D). La población y el gasto de todas las celdas H3 dentro de cada zona se suman para producir las estadísticas del área de influencia del cluster. Estos valores agregados son la base de la clasificación competitiva entre clusters.

## Véase también

- [[topic-od-catchment-methodology]]
- [[topic-catchment-ranking-methodology-v3]]
- [[topic-co-location-methodology]]
