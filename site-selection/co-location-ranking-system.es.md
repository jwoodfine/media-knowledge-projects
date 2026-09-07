---
schema: foundry-doc-v1
title: "Sistema de clasificación de co-ubicación minorista"
slug: co-location-ranking-system
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
editor: editorial
es_status: complete
short_description: "La mecánica determinista detrás de la clasificación de clústeres en la plataforma de co-ubicación — ejes de percentil relativos al país, la prueba de superposición entre clústeres vecinos y el orden de desempate aplicado dentro de un nivel."
paired_with: site-selection/co-location-ranking-system.md
---

La [[co-location-methodology|metodología de co-ubicación]] de Woodfine asigna el nivel de cada clúster mediante compuertas predicativas binarias, no mediante una puntuación compuesta — ningún clúster obtiene un nivel acumulando puntos hacia un umbral. Este artículo cubre la mecánica detrás de esas compuertas: cómo se mide la posición de captación de un clúster frente a sus pares nacionales, cómo se comparan los clústeres competidores por superposición, y cómo se ordenan los clústeres una vez clasificados. Las definiciones de las compuertas — qué combinación de pruebas requiere cada nivel — se detallan en la [[catchment-ranking-methodology|metodología de clasificación de captación]]; las etiquetas de nivel se describen en la [[co-location-tier-nomenclature|nomenclatura de niveles]].

## Clasificación relativa al país

El nivel de un clúster depende de su posición frente a todos los demás clústeres de su propio país, no frente a un umbral global fijo. Cada clúster se clasifica frente a sus pares nacionales según medidas de población de captación y de gasto de los consumidores. Clasificar dentro de cada país, en lugar de contra un único umbral global, preserva la estructura de un mercado más pequeño: un clúster de importancia nacional en un país pequeño se evalúa frente a su propio campo nacional, sin quedar eclipsado por la escala de uno más grande. Los ejes de percentil y el cálculo que los sustenta están previstos para publicarse en gis.woodfinegroup.com.

La captación se mide en dos bandas de distancia — una zona primaria dentro de 35 km del clúster y una zona secundaria entre 35 km y 150 km —, según la [[od-catchment-methodology|metodología de bandas de distancia]]. Las estimaciones de gasto se basan en encuestas nacionales de gasto de los hogares.

Estos umbrales son intencionalmente amplios. El sistema está diseñado para separar los clústeres de importancia nacional de los nodos locales, no para clasificar con precisión los clústeres entre sí dentro de un mismo nivel.

## La prueba de superposición

Un clúster solo se acredita para su nivel cuando no está dominado por un vecino más fuerte cercano. La superposición entre clústeres vecinos se mide mediante una prueba geométrica sobre un radio fijo alrededor de cada clúster: cuanto más cerca están dos clústeres, mayor es la superposición medida, y los clústeres suficientemente separados se consideran espacialmente independientes. Un clúster que se superpone sustancialmente con uno más fuerte se mantiene por debajo del nivel que su composición y captación alcanzarían por sí solas. Regional lleva el límite de superposición más estricto de todos los niveles, según las [[catchment-ranking-methodology|definiciones de compuertas]]. La medida de superposición y su radio están previstos para publicarse en gis.woodfinegroup.com.

## Orden dentro de un nivel

Los clústeres que comparten nivel y país se ordenan por una secuencia fija de criterios, que termina en un desempate que no puede producir un empate. El orden es, por tanto, plenamente determinista: los mismos datos devuelven siempre el mismo orden, de modo que una clasificación citada en una revisión puede reproducirse en la siguiente. Los criterios de orden y la secuencia de desempate están previstos para publicarse en gis.woodfinegroup.com.

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

## Ver también

- [[co-location-methodology]]
- [[co-location-intelligence-overview]]
- [[catchment-ranking-methodology]]

## Referencias

- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Atribución-SinDerivadas 4.0 Internacional](https://creativecommons.org/licenses/by-nd/4.0/).*
