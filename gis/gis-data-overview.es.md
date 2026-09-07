---
schema: foundry-doc-v1
title: "Descripción general de los datos — capas de inteligencia de ubicación y SIG"
slug: gis-data-overview
category: gis
index_group: data-overview-and-sources
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Orientación a las capas de datos espaciales que sustentan el mapa de selección de emplazamientos: las entradas de puntos de interés, población y gasto, la clasificación de cuatro niveles por compuertas de predicado que alimentan, y dónde se documenta cada una en detalle."
paired_with: gis/gis-data-overview.md
cites:
  - osm-odbl
---

Cada Emplazamiento de Desarrollo que Woodfine preselecciona procede de un mapa puntuado, no de un relato de mercado. **Las capas de datos de inteligencia de ubicación** son aquello de lo que está hecho ese mapa. Tres capas se superponen: los registros de puntos de interés que localizan cada ancla minorista, una capa de población en rejilla, y una capa de gasto minorista modelada sobre ella. Juntas producen un conjunto de datos de clústeres de co-ubicación que abarca mercados norteamericanos y europeos, en el que cada clúster lleva uno de cuatro niveles — Regional, Distrital, Local o Marginal — asignado por compuertas binarias de predicado y no por una puntuación acumulada. Este artículo es la orientación a esas capas: qué contiene cada una, cómo se combinan hasta producir un nivel, y qué artículo documenta cada una en detalle. Woodfine es titular del marco y del conjunto de datos resultante; MCorp mantiene los datos y ejecuta el análisis.

## Las tres capas de datos

### Registros de puntos de interés

La capa base localiza las tiendas. Las ubicaciones de anclas minoristas y de operadores secundarios proceden de los colaboradores de OpenStreetMap, bajo la Open Database Licence. Cuatro clases de ancla tienen peso en la puntuación: Hipermercado, las cadenas de mercancía general como Walmart, Target, Mercadona y Tesco; Lifestyle, gran formato de hogar y equipamiento, clase en la que IKEA es la única cadena; Bricolaje, las cadenas de mejora del hogar como Home Depot, Lowe's y Leroy Merlin; y Mayorista, los clubes de membresía como Costco, Sam's Club y Makro. La correspondencia entre cadena y familia se documenta en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]], y la definición de las anclas en [[co-location-anchors|anclas de co-ubicación]].

No todas las cadenas del mapa alteran una calificación. Los minoristas de alimentación aparecen como contexto de apoyo sin entrar en las compuertas de puntuación, y los formatos de proximidad quedan excluidos deliberadamente, porque su densidad generaría clústeres sin señal alguna de desarrollo. [osm-odbl]

### Población

La población procede de estimaciones de población en rejilla publicadas, que modelan residentes a partir de microdatos censales e imágenes satelitales en lugar de declararlos por límite administrativo. Las estimaciones se agregan sobre una única rejilla mundial, de modo que una cifra de un clúster en Noruega se calcula exactamente igual que una de México. El proceso de ingesta y agregación se documenta en [[trade-area-data-sources|fuentes de datos de áreas de influencia]]. Las debilidades reconocidas de la estimación — el supuesto de gasto per cápita uniforme, el riesgo de falsa precisión y el problema de la unidad de área modificable — se exponen en [[spend-population-provenance|procedencia del gasto y la población]], que además indica con claridad qué partes de la cadena están operativas y cuáles están previstas.

### Gasto minorista

El gasto es modelado, no observado. Se aplican a la rejilla de población multiplicadores anuales de gasto per cápita, repartidos entre las categorías de alimentación, bricolaje y mayorista. Los multiplicadores son proxies derivados de encuestas nacionales de gasto de los hogares, expresados en moneda local sin normalización cambiaria, por lo que una clasificación de gasto resulta más defendible dentro de un mismo país.

## De los puntos a los clústeres puntuados

Los registros de puntos de interés co-ubicados se agrupan en un clúster, el nodo contra el que se mide todo lo que viene después. La regla de formación se documenta en [[co-location-cluster-formation|formación de clústeres]], y el tratamiento de dos anclas que comparten un mismo aparcamiento en el [[cluster-deduplication-threshold|umbral de deduplicación de clústeres]].

A cada clúster se le asignan después dos zonas de demanda: una zona primaria próxima al ancla y una zona secundaria más amplia más allá de ella. Ambas son bandas de distancia en línea recta, no tiempos de recorrido por red viaria, y la plataforma las etiqueta como tales: una banda de distancia aproxima de dónde procede la clientela, y no es un área de influencia medida. Las definiciones de las bandas, su fundamento y el paso previsto a datos de origen observados se exponen en la [[od-catchment-methodology|metodología de bandas de distancia]]. La población y el gasto de cada celda de la rejilla situada dentro de cada zona se suman para producir las cifras de área de influencia del clúster.

Esas cifras se convierten a continuación en un rango dentro del propio país del clúster, expresado como percentil. Esto es lo que permite comparar un clúster de un país con unos cientos de nodos puntuados con otro de un país con varios miles.

La asignación de nivel aplica cuatro familias de compuerta binaria: **composición**, qué clases de ancla están presentes; **rango de captación**, el percentil nacional del clúster en población y gasto; **cívica**, si hay un hospital de la clasificación exigida dentro del anillo circundante; y **no solapamiento**, si un clúster más fuerte próximo ya domina el mismo nodo. Un clúster debe superar todas las compuertas que su nivel exige. Los resultados parciales no se acumulan, y un buen desempeño en una compuerta no compensa el fallo en otra: esa es precisamente la disciplina que las compuertas de predicado se introdujeron para imponer.

Las tablas de compuertas no se reproducen aquí. Se mantienen en la [[catchment-ranking-methodology|metodología de clasificación de captación]], con el vocabulario definido en el [[gis-cluster-scoring-glossary|glosario de puntuación de clústeres]] y la lectura orientada al desarrollo en la [[geographic-co-location-methodology|metodología geográfica de co-ubicación]].

## Los cuatro niveles y el vocabulario al que sustituyen

Los niveles son **Regional**, **Distrital**, **Local** y **Marginal**, de mayor a menor. Los nombres se inspiran en la jerarquía de propiedad minorista del International Council of Shopping Centres, aunque solo "Regional" es un término propiamente del ICSC; Distrital, Local y Marginal son denominaciones propias de la plataforma. En inglés las etiquetas son Regional, District, Local y Fringe. La historia completa de la denominación consta en la [[co-location-tier-nomenclature|nomenclatura de niveles]].

Este sistema de niveles sustituyó a una escala compuesta por puntos el 2026-05-16. La escala retirada empleaba las etiquetas numéricas T1, T2 y T3, y esas etiquetas no describen ningún clúster actual del conjunto de datos. Cuando un artículo relata un hecho anterior a esa fecha — [[nordic-uk-coverage|la ampliación de cobertura nórdica y del Reino Unido]] de mayo de 2026 es el caso más claro — conserva el vocabulario vigente en la fecha del hecho y lleva una nota fechada que así lo advierte. Los recuentos de tiendas, los recuentos de clústeres y las fechas de esos artículos no se ven afectados por el cambio de nombre; solo es histórico el vocabulario de niveles que los describe. Una etiqueta T1, T2 o T3 encontrada en cualquier punto de este wiki debe leerse como registro histórico, nunca como calificación vigente.

## Los tres arquetipos de co-ubicación

Las mismas capas de puntos, población y gasto sustentan tres arquetipos, cada uno de los cuales describe un patrón distinto de agrupación comercial. **PRO — Centros Minoristas** es el producto cartográfico base y el fundamento del conjunto de datos de selección de emplazamientos: co-ubicaciones ancladas en alimentación, puntuadas mediante el sistema de compuertas de cuatro niveles descrito arriba. **VWH — Periferia Urbana** identifica concentraciones de minoristas de bricolaje y de suministro industrial donde no hay hipermercado de alimentación, normalmente junto a enlaces de autopista con uso de suelo industrial adyacente. **PKS — Cercanías** identifica concentraciones comerciales en aeropuertos regionales y estaciones interurbanas más allá del núcleo metropolitano, donde el patrón de demanda determinante es aparcar y volar, o aparcar y tomar el tren, más que el tránsito peatonal minorista.

Los códigos de tres letras se ratificaron el 1 de junio de 2026. VWH y PKS se representan como capas superpuestas junto a la vista base PRO, de modo que el analista ve las estructuras de mercado adyacentes junto al mapa minorista principal. Las señales cualificadoras, los descalificadores y el estado de producción de cada arquetipo se documentan en los [[location-intelligence-archetypes|arquetipos de inteligencia de ubicación]].

## Cobertura y publicación

La cobertura crece por ingesta, y cada ampliación se registra como un artículo fechado en lugar de incorporarse en silencio al conjunto de datos. [[nordic-uk-coverage|La ampliación nórdica y del Reino Unido]] documenta la entrada de Noruega, Suecia y el Reino Unido; [[uk-eu-food-retail-coverage|la ampliación de alimentación del Reino Unido y la Unión Europea]] documenta qué cadenas de alimentación pasaron a ser visibles en el mapa, y declara sus propias lagunas pendientes en lugar de dar a entender exhaustividad. La cobertura por país se resume en la [[co-location-intelligence-overview|visión general de inteligencia de co-ubicación]].

Los clústeres puntuados se representan en el mapa publicado en `gis.woodfinegroup.com`, donde también se publican las tablas completas de compuertas.

Aguas abajo, el conjunto de datos puntuado alimenta dos cosas que un analista de desarrollo utiliza directamente: el conjunto cualificado de cuatrocientos mercados que mantiene el [[about-regional-markets-system|sistema de inteligencia de mercados regionales]], y la lista corta ordenada de emplazamientos a partir de la cual Woodfine contrata a profesionales inmobiliarios en cada mercado identificado para evaluar la disponibilidad de suelo y el plazo de desarrollo.

## Lo que este artículo no es

Este artículo es una orientación, no una especificación: nombra las familias de compuertas pero no enuncia ningún umbral de aprobación o rechazo, y describe las zonas de demanda sin reproducir sus distancias. Eso corresponde a los artículos metodológicos canónicos.

Tampoco las capas son más sólidas que sus fuentes. Las zonas de demanda son aproximaciones en línea recta, no áreas de influencia observadas; el paso previsto a la accesibilidad por red viaria se describe en la [[trade-area-methodology|metodología de áreas de influencia]]. La capa de gasto se modela a partir de promedios de encuesta, no de datos de transacción. Y el conjunto de datos se reconstruye con una cadencia de procesamiento, no se sirve como flujo en tiempo real.

## Véase también

- [[geographic-co-location-methodology]]
- [[catchment-ranking-methodology]]
- [[od-catchment-methodology]]
- [[trade-area-data-sources]]
- [[spend-population-provenance]]
- [[location-intelligence-archetypes]]
- [[gis-cluster-scoring-glossary]]
