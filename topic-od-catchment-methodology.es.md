---
schema: foundry-doc-v1
title: "Metodología de captación O-D — áreas de influencia primaria y secundaria"
slug: topic-od-catchment-methodology
aliases:
  - topic-od-catchment-methodology
category: governance
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Las áreas de influencia para cada cluster de co-ubicación se definen usando anillos de distancia en línea recta sobre una rejilla hexagonal H3: una zona primaria de 35 km y una secundaria de 35–150 km, ambas calculadas a partir de datos de población WorldPop 2026."
paired_with: topic-od-catchment-methodology.md
---

La plataforma de [[topic-co-location-methodology|co-ubicación]] de Woodfine define las áreas de influencia para cada cluster usando un modelo de Origen-Destino (O-D) basado en anillos de distancia en línea recta sobre una rejilla espacial hexagonal. Cada cluster recibe dos zonas de captación que determinan qué datos de población y gasto se le atribuyen. Los insumos de área comercial al [[topic-co-location-ranking-system|sistema de clasificación determinista]] y a la [[topic-catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]] provienen de este modelo; las capas de población y gasto se documentan en [[topic-trade-area-data-sources|fuentes de datos de áreas comerciales]].

## Marco espacial

Las áreas de influencia se calculan usando la rejilla hexagonal global H3 a resolución 7. Cada celda H3 de resolución 7 cubre aproximadamente 5,16 km² con un espaciado entre centros de aproximadamente 2,11 km. La rejilla es continua y coherente en todo el mundo, lo que permite la comparación directa entre clusters en todos los países del dataset actual.

## Definición de las zonas de captación

**Captación primaria:** todas las celdas H3 de resolución 7 cuyo punto central se encuentra a menos de 35 km (en línea recta) del centroide del cluster. Esta zona representa el área de influencia inmediata de la que procede la mayoría de los desplazamientos habituales de compra.

**Captación secundaria:** todas las celdas H3 de resolución 7 cuyo punto central se encuentra entre 35 km y 150 km (en línea recta) del centroide del cluster. Esta zona captura la atracción regional más amplia, incluyendo compradores ocasionales y desplazamientos interregionales.

El límite primario de 35 km es un parámetro provisional basado en convenciones establecidas de geografía minorista. Está sujeto a refinamiento cuando se disponga de datos empíricos de origen-destino.

El límite exterior de 150 km se alinea con el radio de recopilación de datos de la plataforma, garantizando que cada celda que contribuye a la captación de un cluster haya sido ingestada y verificada.

## Método de distancia

Todas las distancias se calculan como distancia en línea recta (gran círculo) usando la fórmula del haversine. No se utiliza enrutamiento por tiempo de conducción. Este enfoque es reproducible sin infraestructura de enrutamiento de mapas, consistente entre geografías urbanas y rurales, y eficiente computacionalmente sobre millones de celdas H3.

## Perspectivas HOME y AWAY

La plataforma distingue dos perspectivas sobre la población de captación.

**HOME:** recuentos de población derivados de datos residenciales (WorldPop 2026). Representa dónde vive la gente dentro de cada zona de captación. Esta es la vista predeterminada y está completamente implementada.

**AWAY:** recuentos de población que representan la población diurna o laboral. La distribución del lugar de trabajo difiere de la residencial — concentrada en distritos comerciales y centros de empleo. Esta perspectiva está prevista; la fuente de datos está pendiente.

## Una celda, múltiples clusters

Una sola celda H3 puede pertenecer al área de captación de múltiples clusters de co-ubicación. Esto es intencional: las áreas de influencia no son territorios exclusivos. Un hogar a menos de 35 km de dos clusters competidores contribuye a la población de captación primaria de ambos; el manejo de límites de clúster en el mismo estacionamiento se documenta en [[topic-cluster-deduplication-threshold|umbral de deduplicación de clústeres]].

## Aplicación

La pertenencia a la zona de captación es la base para:

- Agregación de población (datos censales por zona)
- Agregación de gasto (gasto en alimentación, bricolaje y mayorista por zona)
- Clasificación competitiva entre clusters (véase: Metodología de clasificación de captación V3)

## Véase también

- [[topic-catchment-ranking-methodology-v3]]
- [[topic-trade-area-data-sources]]
- [[topic-co-location-methodology]]

## Referencias

- [Área de captación](https://en.wikipedia.org/wiki/Catchment_area_(human_geography)) — Wikipedia, acceso 2026-06-14
- [Área comercial](https://en.wikipedia.org/wiki/Trade_area) — Wikipedia, acceso 2026-06-14
- [H3: Índice espacial hexagonal jerárquico de Uber](https://h3geo.org/) — H3 Geo, acceso 2026-06-14
- [WorldPop: Proyecto Global de Denominadores de Población de Alta Resolución](https://www.worldpop.org/) — WorldPop, Universidad de Southampton, acceso 2026-06-14

*Contenido de Wikipedia reproducido bajo [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*

*Los centroides de los clusters a partir de los cuales se calculan las distancias de captación se derivan de registros de puntos de interés de OpenStreetMap. Datos de OpenStreetMap © colaboradores de OpenStreetMap, bajo licencia ODbL.*
