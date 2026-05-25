---
schema: foundry-doc-v1
title: "Cobertura de Retail Alimentario en el Reino Unido y Europa"
slug: topic-uk-eu-food-retail-coverage.es
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "El índice de co-localización distingue entre cadenas que participan en la puntuación de clústeres — anclas, ferreterías, almacenes — y cadenas que aparecen en el mapa como contexto de apoyo sin afectar las calificaciones. La familia Alimentación pertenece a este segundo grupo. Este artículo documenta la cobertura de retail alimentario en el Reino Unido y la Unión Europea tras la expansión de mayo de 2026."
paired_with: topic-uk-eu-food-retail-coverage.md
cites:
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

El índice de co-localización distingue entre las cadenas minoristas que participan en el algoritmo de puntuación de clústeres — anclas, ferreterías, clubes de almacén — y las cadenas que aparecen en el mapa como contexto de apoyo pero no afectan las calificaciones de los clústeres. La familia Alimentación pertenece a este segundo grupo. Este artículo documenta la cobertura de retail alimentario en el Reino Unido y la Unión Europea tras la expansión de mayo de 2026.

## Por qué la Alimentación es sólo datos de contexto

La metodología de co-localización mide la convergencia de tiendas ancla de gran formato: hipermercados, ferreterías, clubes de almacén. Añadir una cadena de supermercados al algoritmo de puntuación diluiría la señal — la mayoría de las áreas urbanas tienen muchos operadores de alimentación, por lo que una "co-localización" de un ancla y un supermercado aportaría información limitada sobre la densidad comercial. Mantener la familia Alimentación exclusivamente como capa de datos preserva el índice como medida de la convergencia de anclas de gran formato, mientras muestra a los operadores de campo el contexto minorista más amplio alrededor de un ancla.

Una tienda Tesco aparece en el mapa como un punto verde. No contribuye a ninguna calificación de clúster. Aparece en el panel inspector del clúster circundante como parte de la capa de Todas las Ubicaciones.

## Cobertura del Reino Unido

Tres cadenas conforman la capa alimentaria del Reino Unido a partir de mayo de 2026:

| Cadena | Wikidata | Aprox. tiendas | Notas |
|---|---|---|---|
| Tesco | Q487494 | 3.300 | El mayor supermercado del Reino Unido. Los subformatos Extra, Superstore, Metro, Express se gestionan mediante el pase de sub-entidades post-ingestión. |
| Sainsbury's | Q152096 | 1.400 | Subformatos Local + Superstore. |
| Lidl GB | Q151954 | 960 | Segmento de descuento. El cuadro delimitador del país confina los resultados a Gran Bretaña. |

Estas cadenas se suman a la cobertura minorista previa del Reino Unido de B&Q (ferretería), IKEA (ancla) y Costco (ancla + almacén). La capa Alimentación aproximadamente triplica la densidad de puntos en el mapa en todo el Reino Unido, sin modificar las calificaciones de los clústeres.

## Cobertura de la Unión Europea

En mayo de 2026 se añadieron cinco instancias nacionales de Lidl y cuatro instancias de Aldi:

| Lidl | Wikidata | Aprox. tiendas | | Aldi | Wikidata | Aprox. tiendas |
|---|---|---|---|---|---|---|
| Lidl Alemania | Q151954 | 3.250 | | Aldi Alemania | Q41171 + búsqueda por nombre | 4.200 |
| Lidl Francia | Q151954 | 1.600 | | Aldi Reino Unido | Q41171 + búsqueda por nombre | 1.000 |
| Lidl Países Bajos | Q151954 | 440 | | Aldi Países Bajos | Q125054 + búsqueda por nombre | ~480 |
| Lidl Austria | Q151954 | 260 | | Aldi Polonia | Q41171 + búsqueda por nombre | 280 |
| Lidl Portugal | Q151954 | 270 | | | | |

Aldi opera como dos entidades corporativas — Aldi Süd (Wikidata Q41171) y Aldi Nord (Wikidata Q125054) — que dividen la geografía europea en un eje norte-sur. En los Países Bajos y los mercados adyacentes a los países nórdicos, sólo opera Aldi Nord. En el Reino Unido y Polonia, sólo opera Aldi Süd. La etiqueta de identificador de marca en OpenStreetMap en los registros individuales de tiendas es inconsistente en algunos mercados. Para lograr una cobertura aceptable donde la etiqueta de identificador es escasa, la configuración de ingestión recurre a una consulta basada en el nombre de la marca, limitada al cuadro delimitador del país.

## Observaciones sobre la cobertura

Tres notas de cobertura surgidas durante la expansión de mayo de 2026:

**Baja cobertura de Aldi en los Países Bajos.** El primer pase de ingestión devolvió tres registros mediante la consulta de identificador Wikidata, muy por debajo de las aproximadamente 480 tiendas esperadas. Cambiar la configuración para forzar la consulta de reserva basada en el nombre restauró la cobertura a varios cientos de registros.

**Filtración de subformatos de Tesco.** Tesco opera tiendas Express en formatos de hub de transporte. Un pequeño número de estas puede estar etiquetado con tipos no comerciales en OpenStreetMap y ser descartado durante el filtro de gasolineras y farmacias.

**La expansión de la familia Alimentación no es exhaustiva.** Carrefour Francia, Auchan, Mercadona España y otros grandes distribuidores europeos de alimentación aún no han sido ingestados en sus países de origen. Añadir cada uno es una única configuración de cadena; estas cadenas no formaban parte del alcance del sprint de mayo de 2026.

## Relevancia para el análisis

Para una evaluación de Woodfine sobre una oportunidad de desarrollo en el Reino Unido o la Europa continental, la calificación de co-localización cuenta una historia: cuántas anclas de gran formato convergen en ese sitio. La capa Alimentación añade una segunda historia: cuál es la densidad de retail de compra diaria en los alrededores. Un clúster con una calificación fuerte y alta densidad de Alimentación local tiene un comportamiento diferente en el mercado al de un clúster con la misma calificación en un mercado de baja densidad alimentaria.

## Véase también

- [[topic-retail-brand-family-taxonomy]]
- [[topic-co-location-methodology]]
