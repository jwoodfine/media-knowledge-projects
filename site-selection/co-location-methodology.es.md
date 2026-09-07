---
schema: foundry-doc-v1
title: "Metodología de co-ubicación minorista"
slug: co-location-methodology
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-25
editor: pointsav-engineering
es_status: complete
short_description: "Un marco de análisis espacial determinista que clasifica los nodos de bienes raíces comerciales por la convergencia objetiva de operadores minoristas independientes con capital intensivo — corroboración independiente en lugar de estimación de mercado."
paired_with: site-selection/co-location-methodology.md
cites:
  - ni-51-102
  - osc-sn-51-721
  - planetizen-retail-clusters
  - osm-odbl
---

El capital de desarrollo minorista suele comprometerse sobre comparables y estimaciones de analistas. Si la demanda independiente realmente converge en un sitio — la razón por la que debería tener éxito — se supone en lugar de medirse.

La metodología de co-ubicación de Woodfine la mide. Clasifica los sitios de desarrollo por la convergencia objetiva de operadores minoristas independientes con capital intensivo, no por estimaciones de mercado ni pronósticos de analistas. El marco se operacionaliza mediante el [[co-location-ranking-system|sistema de clasificación determinista]] y se expone a los usuarios de la plataforma a través del [[co-location-intelligence-overview|resumen de inteligencia de co-ubicación]].

Un nodo califica cuando un hipermercado, un club de almacén y una tienda de mejoras del hogar han comprometido capital independientemente dentro de un radio de captación definido entre sí. Cada operador ejecuta su propio proceso de selección de sitio; la convergencia es corroboración independiente, no un pronóstico único. La lógica de calificación, la formación de clústeres y el requisito de adyacencia de [[co-location-anchors|anclas]] son los tres insumos estructurales del índice.

Para un asignador de capital el índice es un filtro defensivo: prioriza los sitios donde varias partes han validado de forma independiente el área de comercio. Este artículo cubre la taxonomía de anclas y las compuertas predicativas del sistema de niveles; los artículos relacionados describen la [[od-catchment-methodology|metodología de bandas de distancia]], las [[trade-area-data-sources|fuentes de datos de áreas comerciales]] y la [[catchment-ranking-methodology|metodología de clasificación de captación]].

## Taxonomía de anclas

Los grandes minoristas aplican criterios de selección de sitio rigurosos y basados en datos antes de comprometer capital en un mercado. Cuando varios operadores independientes convergen en el mismo nodo geográfico, esa convergencia señala un corredor comercial validado — una ubicación donde múltiples partes han confirmado de forma independiente la fortaleza del área de comercio.

Cada clúster se forma alrededor de un ancla principal de una de cuatro clases. Las anclas **Hipermercado** son cadenas de mercancía general — Walmart, Target, Mercadona, Tesco. Las anclas **Estilo de Vida** son minoristas de gran formato para el hogar; IKEA es la única cadena de esta clase. Las anclas **Ferretería** son cadenas de mejoras para el hogar — Home Depot, Lowe's, Leroy Merlin. Las anclas **Almacén** son clubes de membresía — Costco, Sam's Club, Makro. El mapeo completo de cadenas a familias se documenta en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

## Clasificación por niveles

Cada clúster recibe uno de cuatro niveles — **Regional**, **Distrital**, **Local**, **Marginal** — al superar un conjunto de compuertas predicativas en lugar de acumular una puntuación. Las etiquetas orientadas al mapa siguen la jerarquía de propiedad minorista del ICSC; el historial completo de nomenclatura está en [[co-location-tier-nomenclature|nomenclatura de niveles]].

| Nivel | Qué requiere |
|---|---|
| **Regional** | Un hipermercado combinado con un ancla de almacén o de estilo de vida, población de captación en el decil superior nacional, y un hospital regional dentro del anillo cívico. El nivel más alto. |
| **Distrital** | Un hipermercado combinado con ferretería o almacén, población de captación en el cuartil superior, y acceso hospitalario dentro del anillo cívico. |
| **Local** | Un ancla de ferretería o almacén, población de captación en la mitad superior, y cualquier hospital dentro del anillo cívico. |
| **Marginal** | Existe co-ubicación comercial, pero el alcance de captación, la composición o el respaldo cívico no alcanzan el nivel Local. |

Las definiciones completas de las compuertas — composición, rango de captación, presencia cívica e independencia espacial — se detallan en la [[catchment-ranking-methodology|metodología de clasificación de captación]].

## Estrategia y aplicación

El sistema de niveles actúa como un filtro defensivo para el despliegue de capital. Al priorizar los nodos Regional y Distrital, un inversor selecciona los sitios con la validación de capital multi-operador más sólida y el mayor respaldo de población de captación.

La metodología se aplica de forma consistente en los mercados globales asignando operadores regionales a estas clases canónicas de ancla. La ampliación del conjunto de datos cívicos terciarios — para llevar la cobertura de universidades y hospitales en México y Canadá a la misma madurez que en Estados Unidos — es un objetivo previsto para futuras iteraciones. [ni-51-102] [osc-sn-51-721]

## Fuentes de datos

Las ubicaciones de anclas y operadores secundarios se obtienen de **colaboradores de OpenStreetMap** bajo la [Licencia de Base de Datos Abierta (ODbL)](https://opendatacommons.org/licenses/odbl/). Los registros se filtran por identificadores canónicos de marca en Wikidata para garantizar una correspondencia coherente de familias de cadenas entre fronteras. El mapeo completo de cadenas a familias se documenta en [[retail-brand-family-taxonomy]]. [osm-odbl]

## Véase también

- [[co-location-ranking-system]]
- [[co-location-intelligence-overview]]
- [[co-location-anchors]]

## Referencias

- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14
- [Parque comercial](https://es.wikipedia.org/wiki/Parque_comercial) — Wikipedia, consultado 2026-06-14
- [DBSCAN](https://es.wikipedia.org/wiki/DBSCAN) — Wikipedia, consultado 2026-06-14

*Datos de OpenStreetMap © colaboradores de OpenStreetMap, licenciados bajo ODbL.*

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Atribución-SinDerivadas 4.0 Internacional](https://creativecommons.org/licenses/by-nd/4.0/).*
