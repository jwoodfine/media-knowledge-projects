---
schema: foundry-doc-v1
title: "Inteligencia de co-ubicación minorista — Resumen"
slug: co-location-intelligence-overview
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
index_type: thematic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-04
editor: editorial
es_status: complete
short_description: "Análisis geográfico sistemático que identifica y clasifica sitios minoristas donde las categorías de gran formato convergen dentro de radios de captación definidos."
paired_with: site-selection/co-location-intelligence-overview.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

La plataforma de inteligencia de co-ubicación de Woodfine clasifica nodos comerciales en mercados minoristas transfronterizos de Norteamérica y Europa por convergencia de anclas — la co-ubicación independiente de hipermercados, clubs de almacén y tiendas de mejoras del hogar en la misma zona comercial. Cada nodo está validado no por previsiones de analistas, sino por los compromisos de capital independientes de los minoristas que se instalaron allí. La convergencia se mide según la [[co-location-methodology|metodología de co-ubicación]] y se clasifica mediante el [[co-location-ranking-system|sistema de clasificación determinista]]; los insumos de población y gasto se documentan en [[trade-area-data-sources|fuentes de datos de áreas comerciales]] y la política geográfica en la [[about-regional-markets-system|matriz de mercados regionales]].

La plataforma opera en [gis.woodfinegroup.com](https://gis.woodfinegroup.com).

## Objetivo estratégico

Los minoristas de gran formato no se ubican de forma arbitraria. Los operadores de supercentros, clubs de almacén y tiendas de mejoras del hogar aplican cada uno de forma independiente criterios de selección de sitios que requieren una inversión de capital intensiva — conteos de tráfico, densidad de ingresos de los hogares, accesibilidad a la red vial y posicionamiento competitivo. Cuando dos o tres de estos operadores convergen en el mismo nodo dentro de un corredor determinado, esa convergencia señala una ubicación comercial validada: una en la que múltiples partes independientes han comprometido capital de forma independiente para atender la misma zona comercial. El requisito de adyacencia de [[co-location-anchors|anclas]] calificadas es binario, no una cuestión de grado.

El sistema de inteligencia de co-ubicación identifica y clasifica esos nodos mediante un modelo determinista de compuertas predicativas. El resultado es un índice de sitios por niveles — Regional, Distrital, Local, Marginal — que puede filtrarse por región, país y radio secundario.

## Cobertura geográfica y escala

La plataforma evalúa clústeres de co-ubicación en mercados minoristas de Norteamérica y Europa, ofreciendo una visión transfronteriza de la densidad minorista y la defensibilidad comercial. La cobertura se amplía a medida que se incorporan nuevos datos de cadenas, de modo que la plataforma SIG en vivo — y no este artículo — es la declaración autorizada de qué países y qué operadores ancla están actualmente en alcance. Una instantánea de wiki sobre la cobertura queda desactualizada entre ciclos de actualización de datos; la plataforma no.

Los operadores ancla se asignan a cuatro clases canónicas — hipermercado, lifestyle, ferretería y club de almacén — de modo que una cadena regional de cualquier mercado cubierto se evalúa en las mismas condiciones que su equivalente norteamericana. Esa correspondencia es lo que hace que la comparación transfronteriza sea significativa y no meramente nominal, y las asignaciones de cadena a clase se documentan en [[retail-brand-family-taxonomy|la taxonomía de familias de marcas minoristas]].

## Fundamentos de datos

La plataforma integra tres fuentes de datos primarias para garantizar un análisis espacial de alta fidelidad:

1.  **Datos de ubicación de negocios (operadores minoristas):** Procedentes de los colaboradores de OpenStreetMap, filtrados por identificadores canónicos de marcas en Wikidata para garantizar una correspondencia coherente de familias de marcas entre fronteras. El conjunto de datos abarca decenas de miles de ubicaciones minoristas individuales de decenas de cadenas, y se actualiza de forma continua a medida que se incorporan nuevos datos de cadenas.
2.  **Datos de lugares (infraestructura cívica):** Registros de hospitales y centros médicos procedentes del conjunto de datos Places de la Overture Maps Foundation. Esta capa terciaria proporciona el contexto cívico requerido para las compuertas de los niveles Regional y Distrital.
3.  **Datos de transporte (apoyo logístico):** Registros de instalaciones de aviación de la Overture Maps Foundation, conservados para dimensiones de puntuación terciaria que la plataforma podría incorporar en el futuro.

*Los supuestos materiales para el conjunto de datos incluyen la disponibilidad continua de los datos de OpenStreetMap y de la Overture Maps Foundation bajo sus respectivas licencias (ODbL y CDLA Permissive 2.0). [osm-odbl] [overture-maps-cdla-2-0]*

## Índice de sitios y clasificación por niveles

Cada nodo puntuado se clasifica en uno de cuatro niveles — **Regional**, **Distrital**, **Local**, **Marginal** — cubiertos por el [[co-location-tier-system|sistema de niveles de co-ubicación]]. Un clúster obtiene su nivel al superar compuertas predicativas de composición de anclas, rango de captación nacional, infraestructura cívica e independencia espacial, descritas en su totalidad en la [[catchment-ranking-methodology|metodología de clasificación de captación]].

Los recuentos de sitios actuales por nivel y país se publican en vivo en la plataforma SIG en lugar de repetirse aquí; una instantánea de wiki queda desactualizada entre ciclos de actualización de datos, mientras que la plataforma se actualiza en cada ejecución de procesamiento.

## Superficie interactiva

La plataforma del Sistema de Información Geográfica (SIG) representa el índice de sitios por niveles como un mapa interactivo en [gis.woodfinegroup.com](https://gis.woodfinegroup.com). La interfaz admite el filtrado en tiempo real por nivel de clúster y por radio de captación.

La plataforma se actualiza cuando se incorporan nuevos datos de cadenas o cuando se recalibra la asignación de niveles. Todos los recuentos del conjunto de datos y los identificadores de versión se muestran en la cabecera de la plataforma, de modo que las cifras actuales están siempre disponibles en la fuente.

## Procedencia
- **Verificación:** La cobertura por país y el alcance de operadores ancla se verifican contra el conjunto de datos de clústeres en vivo de la plataforma SIG, en lugar de repetirse aquí.
- **Declaración prospectiva:** Los objetivos de expansión de datos terciarios europeos son resultados previstos, etiquetados conforme a [ni-51-102].

## Ver también

- [[co-location-methodology]]
- [[co-location-ranking-system]]
- [[co-location-tier-system]]

## Referencias

- [Parque comercial](https://es.wikipedia.org/wiki/Parque_comercial) — Wikipedia, consultado 2026-06-14
- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Atribución-SinDerivadas 4.0 Internacional](https://creativecommons.org/licenses/by-nd/4.0/).*
