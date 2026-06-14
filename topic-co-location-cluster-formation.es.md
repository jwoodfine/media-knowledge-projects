---
schema: foundry-doc-v1
title: "Formación de Agrupaciones de Co-ubicación"
slug: topic-co-location-cluster-formation
aliases:
  - topic-co-location-cluster-formation
category: governance
type: topic
quality: stub
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-06-04
editor: pointsav-engineering
paired_with: topic-co-location-cluster-formation.md
---

# Formación de Agrupaciones de Co-ubicación

La formación de agrupaciones es el paso del flujo del [[topic-co-location-methodology|índice de co-ubicación]] que convierte las tiendas ancla calificadas en agrupaciones candidatas. Cada tienda [[topic-co-location-anchors|ancla]] calificada — cada hipermercado, superstore de mejoras para el hogar y club de almacén que ha comprometido capital de forma independiente dentro de 1,0 a 3,0 km de las demás — genera una agrupación candidata centrada en las coordenadas de esa tienda.

Dado que cada ancla produce su propia candidata, una sola zona comercial con varias anclas adyacentes produce varias agrupaciones superpuestas que describen la misma área de comercio. Esas superposiciones se resuelven más adelante mediante el paso de [[topic-cluster-deduplication-threshold|deduplicación]] antes de que las entradas del área de comercio se agreguen para el [[topic-co-location-ranking-system|sistema de clasificación]].

La formación de agrupaciones no puntúa ni clasifica. Solo enumera agrupaciones candidatas a partir de la lógica de calificación; la calificación, la formación y la adyacencia de anclas son las tres entradas estructurales del índice.

## Véase también

- [[topic-co-location-methodology|Metodología de Co-ubicación Minorista]]
- [[topic-co-location-anchors|Anclas de Co-ubicación]]
- [[topic-cluster-deduplication-threshold|Umbral de Deduplicación de Agrupaciones]]
