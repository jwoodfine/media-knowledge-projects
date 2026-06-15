---
schema: foundry-doc-v1
title: "Sistema de Clasificación de Co-ubicación Minorista"
slug: topic-co-location-ranking-system
aliases:
  - topic-co-location-ranking-system
category: governance
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-06-15
editor: pointsav-engineering
es_status: stub
short_description: "Algoritmo de puntuación de 12 rangos determinista que evalúa sitios de co-ubicación minorista por convergencia de ancla nombrada en radios de captación definidos."
paired_with: topic-co-location-ranking-system.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

La [[topic-co-location-methodology|metodología de co-ubicación]] de Woodfine se operacionaliza como una **matriz de combinación de anclas nominadas**. Este algoritmo determinista califica cada ubicación de hipermercado [[topic-co-location-anchors|ancla]] basándose en la convergencia de categorías secundarias y terciarias (comerciales y cívicas) dentro de radios de captación definidos.

El sistema genera un índice de 12 rangos agrupados en cinco niveles de calidad (Tiers), visualizados en la plataforma GIS mediante una escala de colores que va desde el ámbar intenso (★★★★★ Rango 1, el más alto) hasta el azul pálido (★ Rango 5, el más bajo). Las etiquetas orientadas al mapa — Regional, Distrital, Local, Marginal — siguen la jerarquía ICSC descrita en [[topic-co-location-tier-nomenclature|nomenclatura de niveles]], y las compuertas de calificación se detallan en la [[topic-catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]].

## El Modelo de Anclas Nominadas

Cada sitio en el índice está anclado por un único operador de hipermercado o mercancía general de gran formato (como Walmart o IKEA). El mapeo completo de cadenas a familias se documenta en la [[topic-retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]]. El sistema clasifica a los operadores secundarios en cuatro categorías deterministas:

1.  **Hardware (Secundario-1):** Tiendas de mejoras para el hogar (Home Depot, Leroy Merlin).
2.  **Warehouse Club (Secundario-2):** Clubes de precios (Costco, Sam's Club, Makro).
3.  **Healthcare (Terciario-A):** Hospitales y centros médicos.
4.  **Higher Education (Terciario-B):** Universidades y colegios.

## Matriz de 12 Rangos

La combinación de categorías presentes determina el rango del sitio. El Rango 1 (★★★★★) representa la convergencia absoluta de las cuatro categorías con el ancla principal. Este nivel de validación indica que cuatro procesos independientes de selección de sitios han coincidido en el mismo nodo geográfico.

## Niveles de Calidad y Distribución

Los doce rangos se agrupan en cinco niveles para ofrecer una visión de alto nivel de la calidad del mercado.

**Nota sobre la escala de rangos de calidad.** La escala de cinco rangos de este artículo (Rango 1 = más alto, Rango 5 = más bajo) describe el índice de calidad visualizado en el mapa. Los sitios individuales de co-ubicación dentro de un Mercado Regional se describen por separado mediante una clasificación espacial de tres niveles de clústeres (T1, T2, T3), en la que T1 designa el clúster con el mayor número de categorías de tipo ancla presentes — el tipo de clúster de mayor composición en un mercado determinado. La escala de cinco rangos de calidad y los niveles espaciales T1/T2/T3 son distintos: el rango de calidad mide la densidad comercial en todo el índice; el nivel espacial clasifica la composición de anclas dentro de un único mercado. Para el vocabulario de niveles T1/T2/T3, consulte [Nomenclatura de Niveles de Co-ubicación](https://documentation.pointsav.com/reference/colocation-tier-nomenclature).

## Calibración y Escasez

Para mantener la relevancia del índice, el sistema aplica una **regla de calibración** automática: si los sitios de nivel superior exceden el 10% del total de anclas, el radio de proximidad se ajusta para mantener la escasez y la calidad del índice. Actualmente, los sitios de Rango 1 representan el 3.7% del total, cumpliendo con los estándares de selectividad de la plataforma.

## Ver También
*   [[topic-co-location-methodology]]
*   [[topic-co-location-intelligence-overview]]
*   [[topic-co-location-anchors]]

---
## Procedencia
- **Verificación:** La distribución de rangos y la lógica de la matriz han sido verificadas contra la configuración de la plataforma GIS al 2 de mayo de 2026.

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
