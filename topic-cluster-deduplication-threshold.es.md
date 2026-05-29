---
schema: foundry-doc-v1
title: "Umbral de Deduplicación de Clústeres"
slug: topic-cluster-deduplication-threshold.es
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "El proceso de deduplicación del índice de co-localización elimina los clústeres superpuestos que representan la misma zona comercial utilizando un umbral de 150 metros, conservando el clúster con mayor recuento de operadores secundarios. Un umbral previo de 500 metros suprimía nodos comerciales legítimamente distintos en corredores suburbanos de alta densidad."
paired_with: topic-cluster-deduplication-threshold.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El proceso de deduplicación del [[topic-co-location-methodology|índice de co-localización]] elimina los clústeres superpuestos que representan la misma zona comercial. Cuando dos [[topic-co-location-anchors|anclas]] ocupan la misma zona comercial, el resultado son dos clústeres superpuestos que representan la misma área de captación. El paso de deduplicación resuelve esa redundancia. Los insumos de área comercial al [[topic-co-location-ranking-system|sistema de clasificación]] se agregan después de la ejecución de la deduplicación.

## El problema del estacionamiento compartido

Las grandes zonas comerciales frecuentemente albergan dos o más tiendas de categoría ancla a pocos metros de distancia entre sí. Un Home Depot y un Costco que comparten un estacionamiento en los suburbios de Edmonton, por ejemplo, se ubican a aproximadamente 20 metros de distancia. Sin deduplicación, ambas tiendas generan clústeres con geometría de captación, co-inquilinos y puntuaciones casi idénticos. El mapa muestra dos anillos concéntricos que cubren la misma zona — ninguno incorrecto de forma aislada, pero juntos inducen a error sobre el número de nodos comerciales distintos en ese corredor.

## Selección del umbral: 0,15 km

El paso de deduplicación elimina cualquier clúster cuya tienda ancla se encuentre dentro de un radio fijo respecto a un ancla de mayor rango ya confirmada para su retención. El umbral se establece en **0,15 km (150 metros)**. A esta distancia, sólo se colapsan las tiendas que genuinamente comparten un único estacionamiento o complejo de edificios. Las anclas en centros comerciales adyacentes separados por una calle de servicio (generalmente entre 200 y 500 metros de distancia) se tratan como nodos distintos y se conservan.

Una implementación anterior utilizaba un umbral de 0,50 km. La revisión de campo del área metropolitana de Edmonton identificó casos en los que nodos comerciales legítimos y operados de forma independiente eran suprimidos sin notificación: un nodo anclado en Walmart y un nodo anclado en Home Depot en bloques comerciales vecinos, que atendían a captaciones residenciales diferentes, eran tratados como duplicados y uno era eliminado.

## Selección del superviviente

Cuando dos anclas se encuentran dentro de la distancia umbral, el clúster retenido es el que tiene el mayor recuento de co-inquilinos dentro del radio de captación de 3 km. Los empates se resuelven con el recuento a 1 km. Esto garantiza que el clúster que representa la zona comercial más completa — más tiendas, mayor atractivo multipropósito — sea el que sobrevive, independientemente de qué ancla fue procesada primero.

## Efecto en el proceso

Tras aplicar el umbral de 0,15 km, una ejecución representativa del proceso produjo 6.422 clústeres retenidos a partir de 7.594 candidatos — 1.172 duplicados de la misma zona eliminados. La reducción se concentra en los corredores comerciales de alta densidad donde múltiples formatos de ancla se co-localizan en proximidad estrecha.

## Véase también

- [[topic-co-location-methodology]]
- [[topic-tier-index-north-america]]
