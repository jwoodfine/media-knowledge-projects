---
schema: foundry-doc-v1
title: "Taxonomía de Familias de Marcas Minoristas"
slug: topic-retail-brand-family-taxonomy.es
aliases:
  - topic-retail-brand-family-taxonomy.es
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
short_description: "Cada ubicación minorista en el mapa de co-localización lleva una clasificación de familia de marca que determina cómo se muestra la ubicación y, para algunas familias, si contribuye a la puntuación del clúster. La taxonomía fue diseñada en torno a los tipos de ancla utilizados en la metodología de co-localización, y es extensible a la gama completa de operadores ingestados."
paired_with: topic-retail-brand-family-taxonomy.md
cites:
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

Cada ubicación minorista en el mapa de [[topic-co-location-methodology|co-localización]] lleva una clasificación de familia de marca — una etiqueta categórica que determina cómo se muestra la ubicación y, para algunas familias, si contribuye a la puntuación del clúster. La taxonomía fue diseñada en torno a los tipos de [[topic-co-location-anchors|ancla]] específicos utilizados por el [[topic-co-location-ranking-system|sistema de clasificación determinista]], siendo extensible a la gama completa de operadores ingestados como datos de soporte.

## Las seis familias primarias

### Hipermercado

Minoristas de gran formato de mercancía general y víveres que operan instalaciones de 80.000 pies cuadrados o más. Incluye Walmart Supercenter, Target, Carrefour Hypermarket, IKEA y equivalentes en los mercados de [[topic-tier-index-north-america|América del Norte]] y [[topic-tier-index-europe|Europa]]. Las tiendas de tipo Hipermercado son el tipo de ancla principal en la metodología de co-localización — la formación de clústeres requiere un ancla Hipermercado. Se muestra con una insignia azul marino.

### Ferretería

Minoristas de mejoras para el hogar y materiales de construcción. Incluye Home Depot, Lowe's, Leroy Merlin, Canadian Tire, Hagebaumarkt, Praktiker y equivalentes regionales. La presencia de Ferretería dentro del radio secundario definido del ancla principal es el primer criterio de puntuación en el índice de co-localización. Se muestra con una insignia naranja.

### Almacén

Minoristas de membresía y al por mayor que operan bajo un formato de club o autoservicio mayorista. Incluye Costco, Sam's Club, BJ's Wholesale, Makro y Metro. La presencia de Almacén dentro del radio secundario del ancla principal es el segundo criterio de puntuación. Se muestra con una insignia turquesa.

### Alimentación

Operadores de supermercados convencionales y especializados. Incluye Save-On-Foods, Safeway, Whole Foods, Lidl, Mercadona, Biedronka y cadenas regionales de alimentación en todos los mercados cubiertos. Las tiendas de la familia Alimentación se ingestan y muestran en la capa de Todas las Ubicaciones como contexto de apoyo — son visibles en el mapa — pero no afectan las puntuaciones de los clústeres ni las asignaciones de niveles. Esto preserva el índice de co-localización como una medida de la convergencia de anclas de gran formato, no de la densidad minorista general. Se muestra con una insignia verde.

### Mobiliario

Especialistas en decoración y mobiliario del hogar a escala. Actualmente poblada por Conforama en el mercado español; se prevé la expansión a otros minoristas europeos de mobiliario. Se muestra con una insignia morada.

### Farmacia

Venta minorista de salud y farmacia con una combinación significativa de productos no farmacéuticos. Actualmente poblada por London Drugs en el mercado canadiense. Se muestra con una insignia violeta.

## Familias complementarias

### Gran Almacén

Operadores de grandes almacenes tradicionales no clasificados como hipermercados de gran formato. Actualmente poblada por Macy's en los Estados Unidos. Los grandes almacenes típicamente comparten zonas comerciales con minoristas de categoría ancla, pero representan un formato distinto que no corresponde a ninguna de las categorías de nivel de la metodología de co-localización. Se muestra con una insignia gris neutro.

## Médico y Académico

Los hospitales y universidades, ingestados como infraestructura cívica, se clasifican fuera del sistema de familias de marca mediante un identificador de categoría en lugar de un identificador de familia. Las ubicaciones Médico (hospital) y Académico (universidad) se muestran con insignias distintas y contribuyen a la puntuación terciaria en la metodología de co-localización.

## Alcance de la clasificación

Todas las ubicaciones ingestadas llevan una de estas clasificaciones en su campo de familia de marca. Las ubicaciones sin un identificador de cadena reconocido no reciben familia de marca y se muestran sin insignia de categoría. Las ubicaciones no clasificadas permanecen visibles en el mapa como puntos grises y no afectan la puntuación.

## Véase también

- [[topic-co-location-methodology]]
- [[topic-uk-eu-food-retail-coverage]]
