---
schema: foundry-doc-v1
title: "Inteligencia de Co-ubicación Minorista — Resumen"
slug: topic-co-location-intelligence-overview
aliases:
  - topic-co-location-intelligence-overview
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
short_description: "Análisis geográfico sistemático que identifica y clasifica sitios minoristas donde las categorías de gran formato convergen dentro de radios de captación definidos."
paired_with: topic-co-location-intelligence-overview.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

La plataforma de inteligencia de co-ubicación de Woodfine Management Corp. clasifica 2.738 nodos comerciales en 8 mercados minoristas por convergencia de anclas — la co-ubicación independiente de hipermercados, clubs de almacén y tiendas de mejoras del hogar en el mismo área comercial. Cada nodo está validado por los compromisos de capital independientes de los minoristas que se instalaron allí. La convergencia se mide según la [[topic-co-location-methodology|metodología de co-ubicación]] y se puntúa mediante el [[topic-co-location-ranking-system|sistema de clasificación determinista]]; los insumos de población y gasto se documentan en [[topic-trade-area-data-sources|fuentes de datos de áreas comerciales]] y la política geográfica en la [[topic-regional-market-matrix|matriz de mercados regionales]].

La plataforma opera en [gis.woodfinegroup.com](https://gis.woodfinegroup.com), mantenida por PointSav Digital Systems.

## Objetivo Estratégico

La ubicación de los minoristas de gran formato no es arbitraria; responde a criterios de selección de sitios que requieren una inversión de capital intensiva. Cuando dos o tres de estos operadores convergen en un mismo nodo, dicha convergencia valida la ubicación como un corredor comercial de alta calidad. El requisito de adyacencia de [[topic-co-location-anchors|anclas]] calificadas es binario, no una cuestión de grado.

El sistema de Woodfine identifica estos nodos mediante una matriz de combinación de "anclas nominadas". El resultado es un índice clasificado de sitios en cinco niveles de calidad (Tiers), permitiendo filtrar por región, país y radio de proximidad.

## Alcance y Cobertura

La plataforma evalúa actualmente 8 mercados minoristas en 13 países, proporcionando una visión transfronteriza de la densidad comercial. En [[topic-tier-index-north-america|América del Norte]], el análisis cubre Estados Unidos, Canadá y México (incluyendo los formatos de Walmart, IKEA y operadores locales). En [[topic-tier-index-europe|Europa]], el enfoque inicial se centra en España, Italia, Grecia, Polonia y los países nórdicos.

## Tiers de Calidad

El índice identifica **2,738 sitios de co-ubicación** clasificados globalmente. Los sitios se agrupan en cinco niveles según la convergencia de operadores:

*   **★★★★★ Tier 5:** Convergencia total (Ancla + Hardware + Warehouse + Tertiaries).
*   **★★★★ Tier 4:** Co-ubicación comercial fuerte.
*   **★★★ Tier 3:** Base comercial (Ancla + ambos secundarios).
*   **★★ Tier 2:** Co-ubicación limitada.
*   **★ Tier 1:** Presencia de ancla únicamente.

La expansión de las fuentes de datos para los indicadores terciarios (salud y educación) en los mercados europeos es un objetivo previsto para futuras iteraciones de la plataforma. [ni-51-102] [osc-sn-51-721]

## Ver También
*   [[topic-co-location-methodology]]
*   [[topic-co-location-ranking-system]]
*   [[topic-tier-index-north-america]]

---
## Procedencia
- **Verificación:** Los recuentos de sitios y la cobertura por país han sido verificados contra la configuración de la plataforma GIS al 2 de mayo de 2026. Los objetivos de expansión de datos europeos son resultados previstos, etiquetados conforme a [ni-51-102].

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
