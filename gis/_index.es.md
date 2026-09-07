---
schema: foundry-doc-v1
title: "Mapas y Datos"
slug: gis
category: gis
type: topic
content_type: topic
quality: complete
short_description: "Los mapas y datos detrás del análisis: de dónde provienen los datos espaciales, qué cubren, y los métodos utilizados para seleccionar mercados y evaluar sitios."
index_type: thematic
index_scope: gis
status: active
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
paired_with: gis/_index.md
---

Mapas y Datos abarca los datos espaciales detrás del análisis: de dónde provienen, qué cubren y los métodos utilizados para seleccionar mercados y evaluar sitios.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Comience aquí:** [[gis-data-overview|Resumen de Datos]]

<!-- END-START-HERE-HIGHLIGHT -->

## Resumen de Datos y Fuentes

[[gis-data-overview|Resumen de Datos]] es el punto de entrada — una orientación a los clústeres de inteligencia de localización, los niveles de co-ubicación y el canal de mosaicos que convierte los datos espaciales en bruto en un mapa puntuado. [[trade-area-data-sources|Las Fuentes de Datos de Área de Influencia]] y [[spend-population-provenance|la Procedencia de Población y Gasto]] documentan el origen de cada estimación de población y gasto detrás de un área de influencia.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: data-overview-and-sources -->
- [[gis-data-overview]] — Orientación a las capas de datos espaciales que sustentan el mapa de selección de emplazamientos: las entradas de puntos de interés, población y gasto, la clasificación de cuatro niveles por compuertas de predicado que alimentan, y dónde se documenta cada una en detalle.
- [[trade-area-data-sources]] — Las estimaciones de población de Kontur Population y los proxies de gasto per cápita anuales de encuestas nacionales de hogares sustentan las estadísticas de área de influencia para cada cluster de co-ubicación.
- [[spend-population-provenance]] — Cadena de procedencia de las estimaciones de población y gasto — Kontur Population, agregación H3 y multiplicadores per cápita, con sus debilidades declaradas.
<!-- END AUTO-GENERATED -->

## Expansión de Cobertura

[[nordic-uk-coverage|La Cobertura Nórdica y del Reino Unido]] y [[uk-eu-food-retail-coverage|la Cobertura Minorista de Alimentos del Reino Unido y la UE]] registran cuándo y cómo se incorporaron nuevos países y categorías de cadenas al conjunto de datos.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: coverage-expansion -->
- [[nordic-uk-coverage]] — Cómo Noruega, Suecia y el Reino Unido ingresaron al conjunto de datos de inteligencia de co-ubicación mediante tres promociones de cadenas al nivel Alfa en mayo de 2026.
- [[uk-eu-food-retail-coverage]] — El índice de co-localización distingue entre cadenas que participan en la puntuación de clústeres — anclas, ferreterías, almacenes — y cadenas que aparecen en el mapa como contexto de apoyo sin afectar las calificaciones. La familia Alimentación pertenece a este segundo grupo. Este artículo documenta la cobertura de retail alimentario en el Reino Unido y la Unión Europea tras la expansión de mayo de 2026.
<!-- END AUTO-GENERATED -->

## Registros de Sitio y Aprobaciones

[[site-ledger-integration|La Integración del Registro de Sitio]] vincula cada sitio de construcción físico con un contenedor de archivo digital aislado, manteniendo registros de auditoría inmutables desde el inicio de obra hasta la puesta en marcha. [[transaction-summary-report-protocol|El Protocolo de Reporte Resumen de Transacción]] avanza a los candidatos preseleccionados de Sitio de Desarrollo desde la puntuación geográfica hasta la revisión del Director Independiente.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: site-records-and-approvals -->
- [[site-ledger-integration]] — Vínculo operacional que conecta cada sitio de construcción físico con un contenedor de archivo digital aislado, manteniendo registros de auditoría inmutables desde el inicio hasta la puesta en servicio.
- [[transaction-summary-report-protocol]] — Protocolo que lleva los candidatos a Sitio de Desarrollo de la puntuación geográfica a la revisión del Director Independiente mediante el Informe de Resumen de Transacción.
<!-- END AUTO-GENERATED -->

## Véase también

- [[site-selection-index|Selección de Sitios]]
- [[markets|Mercados Regionales]]
