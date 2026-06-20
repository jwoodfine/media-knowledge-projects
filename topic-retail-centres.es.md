---
schema: foundry-doc-v1
title: "Centros Comerciales de Barrio (PRO)"
slug: topic-retail-centres
category: governance
type: concept
content_type: topic
quality: complete
status: active
audience: vendor-public
bcsc_class: public-disclosure-safe
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-06-20
editor: pointsav-engineering
paired_with: topic-retail-centres.md
short_description: "Los Centros Comerciales de Barrio (PRO) son centros comerciales de proximidad anclados por supermercado, farmacia, banca y restauración informal — uno de los tres arquetipos de co-localización de Inteligencia de Localización y el producto cartográfico base del conjunto de datos de selección de sitios."
cites: []
---

Los **Centros Comerciales de Barrio** (PRO) son centros comerciales de proximidad anclados por el comercio minorista de necesidades cotidianas: un hipermercado de alimentación, una farmacia, una sucursal bancaria y restauración informal. El arquetipo captura la gravedad comercial anclada en alimentación que organiza la actividad de consumo local — el grupo de tiendas que los residentes visitan semanalmente para sus compras rutinarias, banca y comidas.

Código de tres letras: **PRO**. Uno de los tres arquetipos de Inteligencia de Localización junto al [[topic-urban-fringe|Periferia Urbana (VWH)]] y al [[topic-commuter|Viajero Habitual (PKS)]]. PRO es el producto cartográfico base — la base del conjunto de datos de selección de sitios sobre el cual se superponen los otros dos arquetipos.

## Qué es un Centro Comercial de Barrio

Un Centro Comercial de Barrio es el corazón comercial de una zona residencial. Su ancla es un hipermercado de alimentación, alrededor del cual se acumula una mezcla de inquilinos predecible:

- **Hipermercado de alimentación** — el ancla principal; genera el tráfico peatonal semanal que sostiene el resto del centro
- **Farmacia** — comercio de salud y conveniencia co-localizado con el tráfico de alimentación
- **Sucursal bancaria** — servicios financieros minoristas situados donde los residentes ya compran
- **Restauración informal** — restaurantes de servicio rápido y de mesa que atienden la misma zona de captación
- **Comercio secundario** — ferretería, electrónica, tiendas club y comercio de estilo de vida que profundizan el atractivo del centro

El tráfico de consumidores en un Centro Comercial de Barrio es constante y se distribuye ampliamente a lo largo de la semana, con picos de fin de semana impulsados por las compras de alimentación del hogar. La señal definitoria es la co-localización anclada en alimentación: donde un hipermercado de alimentación y una ferretería se agrupan dentro de una distancia definida, hay un Centro Comercial de Barrio.

## Clasificación por niveles

Los clústeres PRO se clasifican en tres escalas. El sistema agrupa las ubicaciones de comercio minorista de categoría ancla que caen dentro de una distancia definida y asigna cada grupo a un nivel según su composición de anclas.

**T1 — Regional:** Un clúster que contiene un hipermercado de alimentación y una ferretería, más al menos uno de: tienda club, comercio de estilo de vida o tienda de electrónica. Alternativamente: cuatro o más comercios de categoría ancla en un clúster compacto (distancia ≤ 1 km), o tres o más anclas en cualquier clúster compacto. Son los centros más grandes, que atraen desde una zona de captación regional.

**T2 — Distrito:** Un clúster que contiene un hipermercado de alimentación y una ferretería, con una distancia no superior a 2,5 km. El centro de distrito sirve a un barrio definido con una mezcla completa de necesidades cotidianas.

**T3 — Local:** Todos los pares de anclas restantes que no califican para T1 o T2. Centros locales más pequeños con composición parcial de anclas.

Las etiquetas de nivel T1/T2/T3 utilizadas aquí son compartidas con los otros arquetipos de Inteligencia de Localización.

## Conjunto de datos de producción

El sistema PRO es la capa fundamental del conjunto de datos de selección de sitios, cubriendo 17 países de visualización en Norteamérica y Europa.

| Nivel | Clústeres | Países |
|------|----------|--------|
| T1 | 1.746 | 17 |
| T2 | 2.726 | 17 |
| T3 | 2.021 | 17 |
| **Total** | **6.493** | |

El límite de distancia de T2 se fijó en 2,5 km en la reconstrucción más reciente, ajustando el límite de escala de distrito respecto a fases anteriores. Los códigos de arquetipo de tres letras se ratificaron el 1 de junio de 2026.

## Por qué PRO es el mapa base

Los Centros Comerciales de Barrio anclan todo el conjunto de datos de Inteligencia de Localización porque la co-localización anclada en alimentación es el patrón comercial más estable y ampliamente distribuido. Casi toda zona de captación poblada tiene un ancla de alimentación; el centro que se forma a su alrededor es un indicador fiable de la gravedad comercial residencial. Los arquetipos Periferia Urbana y Viajero Habitual se definen en parte en relación con los clústeres PRO — los sitios de Periferia Urbana se identifican por la *ausencia* de anclas de alimentación, y los sitios de Viajero Habitual hacen referencia al Centro Comercial de Barrio T1/T2 más cercano como el mercado regional que genera su demanda de aparcamiento.

## Véase también

- [[topic-location-intelligence-archetypes]] — la visión completa de los arquetipos de co-localización PRO/VWH/PKS

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
