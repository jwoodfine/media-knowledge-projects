---
schema: foundry-doc-v1
title: "Centros Comerciales de Barrio (PRO)"
slug: retail-centres
category: site-selection
index_group: anchors-and-tenants
type: concept
content_type: topic
quality: complete
status: active
audience: vendor-public
bcsc_class: public-disclosure-safe
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-09-04
editor: pointsav-engineering
paired_with: site-selection/retail-centres.md
short_description: "Los Centros Comerciales de Barrio (PRO) son centros comerciales de proximidad anclados por supermercado, farmacia, banca y restauración informal — uno de los tres arquetipos de co-localización de Inteligencia de Localización y el producto cartográfico base del conjunto de datos de selección de sitios."
cites: []
---

Los **Centros Comerciales de Barrio** (PRO) son centros comerciales de proximidad anclados por el comercio minorista de necesidades cotidianas: un hipermercado de alimentación, una farmacia, una sucursal bancaria y restauración informal. El arquetipo captura la gravedad comercial anclada en alimentación que organiza la actividad de consumo local — el grupo de tiendas que los residentes visitan semanalmente para sus compras rutinarias, banca y comidas.

Código de tres letras: **PRO**. Uno de los tres arquetipos de Inteligencia de Localización junto al [[urban-fringe|Periferia Urbana (VWH)]] y al [[commuter|Viajero Habitual (PKS)]]. PRO es el producto cartográfico base — la base del conjunto de datos de [[site-selection-terminology|selección de sitios]] sobre el cual se superponen los otros dos arquetipos.

## Qué es un Centro Comercial de Barrio

Un Centro Comercial de Barrio es el corazón comercial de una zona residencial. Su ancla es un hipermercado de alimentación, alrededor del cual se acumula una mezcla de inquilinos predecible:

- **Hipermercado de alimentación** — el ancla principal; genera el tráfico peatonal semanal que sostiene el resto del centro
- **Farmacia** — comercio de salud y conveniencia co-localizado con el tráfico de alimentación
- **Sucursal bancaria** — servicios financieros minoristas situados donde los residentes ya compran
- **Restauración informal** — restaurantes de servicio rápido y de mesa que atienden la misma zona de captación
- **Comercio secundario** — ferretería, electrónica, tiendas club y comercio de estilo de vida que profundizan el atractivo del centro

El tráfico de consumidores en un Centro Comercial de Barrio es constante y se distribuye ampliamente a lo largo de la semana, con picos de fin de semana impulsados por las compras de alimentación del hogar. La señal definitoria es la [[co-location-strategy|co-localización]] anclada en alimentación: donde un hipermercado de alimentación y una ferretería se agrupan dentro de una distancia definida, hay un Centro Comercial de Barrio.

## Clasificación por niveles

Los clústeres PRO se clasifican en cuatro escalas — **T1 Regional**, **T2 Distrital**, **T3 Local** y **T4 Marginal**.

El nivel de un clúster se asigna por compuerta predicativa, no por una puntuación acumulada. Todas las condiciones de un nivel deben cumplirse, y una lectura fuerte en una condición no compensa el incumplimiento de otra. Se aplican en conjunto cuatro familias de condiciones:

- **Composición** — cuáles de las cuatro clases de ancla están presentes: hipermercado, estilo de vida, ferretería y almacén
- **Clasificación de captación** — la posición de la población y el gasto del área comercial del clúster frente a otros clústeres del mismo país, a partir de las zonas descritas en la [[od-catchment-methodology|metodología de bandas de distancia]]
- **Presencia cívica** — si hay un hospital de la clasificación requerida dentro del anillo cívico del clúster
- **Independencia espacial** — en los niveles superiores, si el clúster está sustancialmente solapado por un clúster más fuerte del mismo país

**T1 — Regional:** los centros más grandes, que atraen desde una zona de captación regional. Un ancla de hipermercado se combina con un ancla de almacén o de estilo de vida; el clúster figura entre los más altos de su país por población de captación; hay un hospital de clasificación regional; y el clúster es espacialmente independiente de vecinos más fuertes. Es el listón más exigente en todas las condiciones.

**T2 — Distrital:** un centro de distrito que sirve a un barrio definido con una mezcla completa de necesidades cotidianas. Un ancla de hipermercado se combina con un ancla de ferretería o de almacén; las clasificaciones de captación y de gasto del clúster se sitúan muy por encima de la mediana de su país; y hay acceso hospitalario dentro del anillo cívico. Todos los listones son más laxos que en Regional, pero siguen siendo listones.

**T3 — Local:** un centro local más pequeño con composición parcial de anclas. Hay un ancla de ferretería o de almacén, la clasificación de captación alcanza al menos la mediana del país, y cualquier clasificación hospitalaria satisface la condición cívica.

**T4 — Marginal:** clústeres que no superan ninguna de las compuertas superiores. Un clúster Marginal puede presentar co-tenencia minorista real; lo que le falta es alcance de captación, composición de anclas o apoyo cívico al nivel que exige un nivel superior.

La distancia del clúster sigue importando, pero como entrada de agrupamiento y no como prueba de calificación. Las ubicaciones minoristas de categoría ancla se agrupan en un mismo clúster candidato solo cuando caen dentro de una distancia definida entre sí, de modo que esa distancia determina qué cuenta como un único clúster antes de comprobar ninguna compuerta. Por sí sola no fija el nivel. Las convenciones de distancia son parámetros de la plataforma, reajustados entre reconstrucciones a medida que cambia la cobertura de cadenas ancla, y no se publican aquí.

Las definiciones completas de las compuertas se mantienen en la [[catchment-ranking-methodology|metodología de clasificación de captación]]; las propias etiquetas de nivel se definen en la [[co-location-tier-nomenclature|nomenclatura de niveles]]. Las etiquetas T1–T4 utilizadas aquí son compartidas con los otros arquetipos de Inteligencia de Localización.

## Cobertura

Los Centros Comerciales de Barrio (PRO) constituyen la capa fundamental del conjunto de datos de selección de sitios, cubriendo 17 países de visualización en Norteamérica y Europa. Los códigos de arquetipo de tres letras se ratificaron el 1 de junio de 2026.

Los recuentos de clústeres por nivel son una cifra móvil. Cambian con cada reconstrucción a medida que cambian la cobertura de cadenas ancla y la huella minorista subyacente, y los límites de nivel se reajustan periódicamente en consecuencia. Por ello no se reproducen aquí los recuentos actuales.

## Por qué PRO es el mapa base

Los Centros Comerciales de Barrio anclan todo el conjunto de datos de Inteligencia de Localización porque la co-localización anclada en alimentación es el patrón comercial más estable y ampliamente distribuido. Casi toda zona de captación poblada tiene un ancla de alimentación; el centro que se forma a su alrededor es un indicador fiable de la gravedad comercial residencial. Los arquetipos Periferia Urbana y Viajero Habitual se definen en parte en relación con los clústeres PRO — los sitios de Periferia Urbana se identifican por la *ausencia* de anclas de alimentación, y los sitios de Viajero Habitual hacen referencia al Centro Comercial de Barrio T1 o T2 más cercano como el [[about-regional-markets-system|mercado regional]] que genera su demanda de aparcamiento.

## Véase también

- [[location-intelligence-archetypes]] — la visión completa de los arquetipos de co-localización PRO/VWH/PKS
- [[catchment-ranking-methodology]] — las definiciones completas de las compuertas de nivel

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
