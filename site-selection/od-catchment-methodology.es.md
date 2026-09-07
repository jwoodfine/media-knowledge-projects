---
schema: foundry-doc-v1
title: "Metodología de bandas de distancia — zonas de demanda primaria y secundaria"
slug: od-catchment-methodology
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Cada clúster de co-ubicación recibe dos bandas de distancia en línea recta — una zona primaria de 35 km y una secundaria de 35 a 150 km — que determinan la población y el gasto que se le atribuyen."
paired_with: site-selection/od-catchment-methodology.md
---

La plataforma de [[co-location-methodology|co-ubicación]] de Woodfine asigna a cada clúster dos zonas de demanda que determinan qué datos de población y gasto se le atribuyen: una zona primaria dentro de 35 km del clúster y una zona secundaria de 35 a 150 km. Ambas son bandas de distancia en línea recta, y se etiquetan como tales: una banda de distancia aproxima de dónde provienen los clientes; no es un área de captación medida, y la plataforma no la etiqueta como tal. La regla de etiquetado, y el paso previsto hacia orígenes observados y límites por tiempo de conducción, se establecen en [[trade-area-methodology]]. Las zonas alimentan el [[co-location-ranking-system|sistema de clasificación determinista]] y la [[catchment-ranking-methodology|metodología de clasificación de captación]]; las capas de población y gasto se documentan en [[trade-area-data-sources|fuentes de datos de áreas comerciales]].

## Definición de las zonas

**Zona primaria (0–35 km):** el área dentro de 35 km en línea recta del centroide del clúster. Esta zona representa el área de influencia inmediata de la que procede la mayoría de los desplazamientos habituales de compra.

**Zona secundaria (35–150 km):** el área entre 35 km y 150 km en línea recta del centroide del clúster. Esta zona captura la atracción regional más amplia, incluyendo compradores ocasionales y desplazamientos interregionales.

El límite primario es un parámetro provisional basado en convenciones establecidas de geografía minorista. Está sujeto a refinamiento cuando se disponga de datos empíricos de origen-destino. El límite exterior se alinea con el alcance de recopilación de datos de la propia plataforma, de modo que toda ubicación que contribuye a las zonas de un clúster ya ha sido ingestada y verificada.

La pertenencia a una zona se resuelve igual en todos los mercados, de modo que las cifras de zona son directamente comparables entre clústeres de cualquier país.

## Método de distancia

Todas las distancias son distancias terrestres en línea recta; no se utiliza enrutamiento por tiempo de conducción en esta etapa. Una banda de 35 km significa por tanto lo mismo en todos los mercados — urbanos o rurales, de América del Norte o de Europa — lo que hace posible la comparación entre clústeres antes de que lleguen datos de origen observado. La accesibilidad por la red vial es una mejora prevista, descrita en [[trade-area-methodology]].

## Perspectivas HOME y AWAY

La plataforma distingue dos perspectivas sobre la población de cada zona.

**HOME:** recuentos de población derivados de datos publicados de población residencial. Representa dónde vive la gente dentro de cada zona. Esta es la vista predeterminada y está completamente implementada.

**AWAY:** recuentos de población que representan la población diurna o laboral. La distribución del lugar de trabajo difiere de la residencial — concentrada en distritos comerciales y centros de empleo en lugar de dispersa en áreas residenciales. Esta perspectiva está prevista; la fuente de datos está pendiente.

## Un lugar, múltiples clústeres

Una sola ubicación puede pertenecer a las zonas de múltiples clústeres de co-ubicación. Esto es intencional: las áreas de influencia no son territorios exclusivos. Un hogar a menos de 35 km de dos clústeres competidores contribuye a la población de la zona primaria de ambos. Esto refleja el panorama minorista competitivo y es la base de la metodología de comparación entre clústeres; el manejo de límites de clúster en el mismo estacionamiento se documenta en [[cluster-deduplication-threshold|umbral de deduplicación de clústeres]].

## Aplicación

La pertenencia a una zona es la base para:

- Agregación de población (datos publicados de población por zona)
- Agregación de gasto (gasto en alimentación, bricolaje y mayorista por zona)
- Clasificación competitiva entre clústeres (véase [[catchment-ranking-methodology]])

Los polígonos de zona que aparecen en el mapa se generan a partir de los mismos radios de 35 km / 150 km en línea recta, visualizados en dos colores distintos para diferenciar la zona primaria de la secundaria.

## Véase también

- [[catchment-ranking-methodology]]
- [[trade-area-data-sources]]
- [[co-location-methodology]]

## Referencias

- [Área de captación](https://en.wikipedia.org/wiki/Catchment_area_(human_geography)) — Wikipedia, acceso 2026-06-14
- [Área comercial](https://en.wikipedia.org/wiki/Trade_area) — Wikipedia, acceso 2026-06-14
- [Conjunto de datos de población Kontur](https://data.humdata.org/dataset/kontur-population-dataset) — Kontur, acceso 2026-09-07

*Contenido de Wikipedia reproducido bajo [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*

*Los centroides de los clústeres a partir de los cuales se calculan las distancias de zona se derivan de registros de puntos de interés de OpenStreetMap. Datos de OpenStreetMap © colaboradores de OpenStreetMap, bajo licencia ODbL.*
