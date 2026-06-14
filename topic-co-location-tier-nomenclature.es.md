---
schema: foundry-doc-v1
title: "Nomenclatura de Niveles de Co-localización"
slug: topic-co-location-tier-nomenclature.es
aliases:
  - topic-co-location-tier-nomenclature.es
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
short_description: "Las cuatro etiquetas de nivel — Regional, Distrital, Local, Marginal — visibles en el mapa de co-localización siguen la jerarquía de propiedades comerciales del Consejo Internacional de Centros Comerciales (ICSC), una nomenclatura internacionalmente reconocida que lleva significado propio sin necesidad de contexto específico de la plataforma."
paired_with: topic-co-location-tier-nomenclature.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El [[topic-co-location-methodology|índice de co-localización]] asigna cada clúster a uno de cuatro niveles en función de la composición categórica de sus [[topic-co-location-anchors|anclas]] y tiendas secundarias, y de la posición del clúster dentro de la captación nacional de población. Las etiquetas visibles en el mapa y en el panel inspector — **Regional**, **Distrital**, **Local**, **Marginal** — siguen la jerarquía de propiedades del Consejo Internacional de Centros Comerciales (ICSC), utilizada por promotores inmobiliarios, planificadores y analistas de retail en [[topic-tier-index-north-america|América del Norte]] y [[topic-tier-index-europe|Europa]]. Las compuertas de calificación se definen en la [[topic-catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]] y la lógica de puntuación subyacente en el [[topic-co-location-ranking-system|sistema de clasificación de co-ubicación]].

## Qué significa cada nivel

| Nivel | Nombre | Descripción |
|---|---|---|
| 1 | **Regional** | Un nodo de co-localización de importancia nacional. Contiene tanto un ancla de tipo hipermercado como un club de almacén o ancla de estilo de vida, se encuentra en el decil superior de su país por captación de población primaria y tiene un hospital clasificado como regional dentro del anillo cívico. El nivel más alto. |
| 2 | **Distrital** | Un nodo de área comercial subregional. Contiene un hipermercado y un ancla de ferretería o almacén, está en el cuartil superior de su país por captación de población primaria y tiene acceso hospitalario dentro del anillo cívico. |
| 3 | **Local** | Un hub de ferretería o mayoreo con apoyo cívico a nivel comunitario. Contiene al menos un ancla de tipo ferretería o almacén, está en la mitad superior de su país por captación de población primaria y tiene algún hospital dentro del anillo cívico. |
| 4 | **Marginal** | Por debajo del umbral en una o más compuertas requeridas. Un clúster comercial con co-tenencia minorista pero con captación insuficiente, composición inadecuada o apoyo cívico insuficiente para calificar para Local o superior. |

## Descriptores de composición

Cada clúster lleva un descriptor de composición que se muestra debajo de la insignia de nivel en el inspector. El descriptor nombra las clases de ancla presentes, separadas por "+": por ejemplo, "Hipermercado + Ferretería + Almacén" o "Estilo de Vida + Hipermercado". Las cuatro clases de ancla son: Hipermercado (tiendas de mercancías generales: Walmart, Target, Mercadona, Tesco, Sainsbury's), Estilo de Vida (hogar y decoración a gran escala: IKEA), Ferretería (mejoras para el hogar: Home Depot, Lowe's, Leroy Merlin) y Almacén (clubes de almacén por membresía: Costco, Sam's Club, Makro). El mapeo completo de cadenas a familias se documenta en la [[topic-retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

## Historia de la nomenclatura

Las etiquetas de nivel han sido renombradas dos veces desde el lanzamiento de la plataforma.

**Sprint 9 (mayo de 2026):** Las etiquetas numéricas originales (T3 Complemento Total, T2 Ancla Minorista, T0 Nodo Comercial, entre otras) fueron reemplazadas por sustantivos en lenguaje sencillo: Prime, Strong (Retail), Strong (Bulk), Strong (Hub), Core (Hyper), Core (Hardware), Core (Wholesale), Emerging. Esto resolvió dos problemas de legibilidad: la ambigüedad del "+" en los descriptores compuestos y el esfuerzo cognitivo de mapear un número de nivel a un rango de calidad.

**Sprint 17 (mayo de 2026):** Las etiquetas del Sprint 9 fueron reemplazadas por la jerarquía ICSC: Regional, Distrital, Local, Marginal. La motivación fue la alineación con una nomenclatura internacionalmente reconocida que lleva significado sin requerir contexto específico de la plataforma.

## Lectura del panel inspector

Cuando un usuario selecciona un clúster en el mapa, el panel inspector muestra el nombre del nivel como una insignia de gran tamaño. Debajo de la insignia, un descriptor de composición en tono apagado nombra las clases de ancla presentes.

El color de la insignia codifica la jerarquía: azul marino oscuro para Regional, índigo para Distrital, pizarra para Local, gris claro para Marginal.

## Véase también

- [[topic-co-location-methodology]]
- [[topic-catchment-ranking-methodology-v3]]
- [[topic-retail-brand-family-taxonomy]]
