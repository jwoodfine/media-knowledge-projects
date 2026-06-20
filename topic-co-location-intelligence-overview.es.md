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
last_edited: 2026-06-19
editor: editorial
es_status: complete
short_description: "Análisis geográfico sistemático que identifica y clasifica sitios minoristas donde las categorías de gran formato convergen dentro de radios de captación definidos."
paired_with: topic-co-location-intelligence-overview.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

La plataforma de inteligencia de co-ubicación de MCorp clasifica 2.738 nodos comerciales en 8 mercados minoristas por convergencia de anclas — la co-ubicación independiente de hipermercados, clubs de almacén y tiendas de mejoras del hogar en la misma zona comercial. Cada nodo está validado no por previsiones de analistas, sino por los compromisos de capital independientes de los minoristas que se instalaron allí. La convergencia se mide según la [[topic-co-location-methodology|metodología de co-ubicación]] y se puntúa mediante el [[topic-co-location-ranking-system|sistema de clasificación determinista]]; los insumos de población y gasto se documentan en [[topic-trade-area-data-sources|fuentes de datos de áreas comerciales]] y la política geográfica en la [[topic-regional-market-matrix|matriz de mercados regionales]].

La plataforma opera en [gis.woodfinegroup.com](https://gis.woodfinegroup.com), construida y mantenida por PointSav Digital Systems.

## Objetivo estratégico

Los minoristas de gran formato no se ubican de forma arbitraria. Los operadores de supercentros, clubs de almacén y tiendas de mejoras del hogar aplican cada uno de forma independiente criterios de selección de sitios que requieren una inversión de capital intensiva — conteos de tráfico, densidad de ingresos de los hogares, accesibilidad a la red vial y posicionamiento competitivo. Cuando dos o tres de estos operadores convergen en el mismo nodo dentro de un corredor determinado, esa convergencia señala una ubicación comercial validada: una en la que múltiples partes independientes han comprometido capital de forma independiente para atender la misma zona comercial. El requisito de adyacencia de [[topic-co-location-anchors|anclas]] calificadas es binario, no una cuestión de grado.

El sistema de inteligencia de co-ubicación identifica y clasifica esos nodos mediante una matriz de combinación de anclas nominadas de carácter determinista. El resultado es un índice clasificado de sitios, expresado en cinco niveles de calidad, que puede filtrarse por región, país y radio secundario.

## Cobertura geográfica y escala

La plataforma evalúa actualmente 8 mercados minoristas en 13 países, proporcionando una visión transfronteriza de la densidad minorista y la defensibilidad comercial.

| Región | Países | Operadores ancla |
|--------|--------|-----------------|
| Estados Unidos | US | Walmart, IKEA |
| Canadá | CA | Walmart, IKEA, Real Canadian Superstore |
| México | MX | Walmart, IKEA |
| España | ES | IKEA, Carrefour, Alcampo, Leclerc |
| Italia | IT | IKEA, Carrefour, Ipercoop, Iper La Grande, Bennet |
| Grecia | GR | IKEA |
| Polonia | PL | IKEA, Carrefour, Leclerc, Auchan |
| Países Nórdicos | SE · NO · DK · FI · IS | IKEA, Bilka, Prisma, K-Citymarket, Obs Coop |

## Fundamentos de datos

La plataforma integra tres fuentes de datos primarias para garantizar un análisis espacial de alta fidelidad:

1.  **Negocios de servicios (Operadores minoristas):** Procedentes de los colaboradores de OpenStreetMap, filtrados por identificadores canónicos de marcas en Wikidata para garantizar una correspondencia coherente de familias de marcas entre fronteras. A 2 de mayo de 2026, el conjunto de datos contiene más de 31.219 ubicaciones minoristas individuales de más de 60 cadenas.
2.  **Lugares de servicios (Infraestructura cívica):** Registros de hospitales y centros médicos procedentes del conjunto de datos Places de la Overture Maps Foundation (publicación del 15 de abril de 2026). Esta capa terciaria proporciona el contexto demográfico "estabilizador" requerido para la clasificación en niveles superiores.
3.  **Transporte de servicios (Apoyo logístico):** Registros de instalaciones de aviación de la Overture Maps Foundation, conservados para futuras dimensiones de puntuación terciaria.

*Los supuestos materiales para los recuentos del conjunto de datos actual incluyen la disponibilidad continua de los datos de OpenStreetMap y de la Overture Maps Foundation bajo sus respectivas licencias (ODbL y CDLA Permissive 2.0). [osm-odbl] [overture-maps-cdla-2-0]*

## Índice de sitios y niveles de calidad

El conjunto de datos actual identifica **2.738 sitios de co-ubicación clasificados** a nivel global: 2.488 en [[topic-tier-index-north-america|América del Norte]] y 250 en [[topic-tier-index-europe|Europa]]. Los sitios se clasifican mediante una matriz determinista que evalúa la proximidad y la categoría de los anclas secundarias en relación con el ancla principal de hipermercado.

| Nivel | Descripción | Recuento NA | Recuento UE |
|-------|-------------|-------------|-------------|
| ★★★★★ | Co-ubicación completa | 102 | 0 |
| ★★★★ | Co-ubicación fuerte | 259 | 9 |
| ★★★ | Co-ubicación parcial | 1.396 | 175 |
| ★★ | Co-ubicación limitada | 333 | 23 |
| ★ | Solo ancla | 398 | 43 |

La ausencia actual de sitios de Nivel 5 en Europa refleja hitos objetivos de cobertura de datos; la dimensión de puntuación terciaria (salud y educación superior) actualmente se basa en datos de Overture que tienen mayor madurez en los mercados norteamericanos. La expansión de las fuentes de datos terciarios europeos es un objetivo previsto para futuras iteraciones de la plataforma. [ni-51-102] [osc-sn-51-721]

## Superficie interactiva

La plataforma del Sistema de Información Geográfica (SIG) representa el índice clasificado de sitios como un mapa interactivo en [gis.woodfinegroup.com](https://gis.woodfinegroup.com). La interfaz admite el filtrado en tiempo real por grado de clúster y radio de captación (1 km, 2 km o 3 km).

La plataforma se actualiza cuando se incorporan nuevos datos de cadenas o cuando se recalibra la matriz de clasificación. Todos los recuentos del conjunto de datos y los identificadores de versión se muestran en la cabecera de la plataforma para garantizar la transparencia operativa.

## Procedencia
- **Verificación:** Los recuentos de sitios y la cobertura por país han sido verificados contra la configuración de la plataforma SIG al 2 de mayo de 2026.
- **Declaración prospectiva:** Los objetivos de expansión de datos terciarios europeos son resultados previstos, etiquetados conforme a [ni-51-102].

## Ver también
*   [[topic-co-location-methodology]]
*   [[topic-co-location-ranking-system]]
*   [[topic-tier-index-north-america]]

## Referencias

- [Parque comercial](https://es.wikipedia.org/wiki/Parque_comercial) — Wikipedia, consultado 2026-06-14
- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
