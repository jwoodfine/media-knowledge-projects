---
schema: foundry-doc-v1
title: "Niveles y puntuación de co-ubicación"
slug: co-location-tiering-scoring
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: archived
archived: 2026-09-05
archived_reason: "Reconciled 2026-09-05: this article documented the points-based T1/T2/T3 compositional tier scale retired platform-wide on 2026-05-16, which describes no current cluster in the dataset. Its two passages with no equivalent elsewhere -- the cluster-count sensitivity finding and the planned per-cluster strength score -- were merged into catchment-ranking-methodology, the canonical four-tier predicate-gate article; the remaining T1/T2/T3 material is superseded vocabulary and is retained here as historical record only."
superseded_by: catchment-ranking-methodology
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Puntuación por niveles de clústeres de co-localización — qué miden los niveles T1–T3 de composición, qué no afirman explícitamente, y por qué un conteo total de clústeres es una salida del modelo y no una medición."
paired_with: site-selection/co-location-tiering-scoring.md
cites: []
---

Este artículo describe una metodología de niveles composicionales que asigna a cada clúster de co-ubicación uno de tres niveles — T1, T2 o T3 — sobre la base de la composición de categorías de minoristas. Representados como puntos de colores, los niveles se gradúan de T1 (co-ubicación más profunda) a T3 (co-ubicación calificada más superficial). Comprender con precisión qué miden estos niveles — y qué no — es necesario para leer correctamente un resultado de clúster composicional.

Las etiquetas de nivel que se muestran actualmente en el mapa de inteligencia de ubicación de Woodfine son el sistema de cuatro niveles — Regional, Distrital, Local, Marginal — descrito en [[co-location-tier-nomenclature]]. El modelo composicional T1/T2/T3 documentado en este artículo es un enfoque de clasificación distinto y relacionado; los dos no deben leerse como intercambiables.

## Qué miden los niveles

La variable que impulsa el nivel es la **composición de categorías de minoristas**: el conteo y la combinación de categorías de ancla distintas co-presentes dentro de un solo clúster espacial. El nivel es, por tanto, una clasificación composicional ordinal.

Los niveles miden la composición. No miden la fortaleza del área de atracción, el potencial de ventas, la población alcanzada ni el gasto capturado. La composición no implica demanda: un clúster T1 tiene más diversidad de anclas que un clúster T3, pero no se sigue que tenga más personas, más gasto o mejor accesibilidad en su área de atracción.

El etiquetado en el mapa dice "profundidad de co-ubicación (conteo de anclas)" en lugar de "niveles de calidad", y la definición en lenguaje sencillo de cada nivel está vinculada a la composición:

- **T1** — mayor profundidad de co-ubicación (más categorías de ancla co-presentes)
- **T2** — profundidad de co-ubicación intermedia
- **T3** — co-ubicación calificada más superficial

## Cómo se forman los clústeres

Los clústeres se producen mediante agrupación espacial basada en densidad de ubicaciones de minoristas ancla, seguida de un pase de deduplicación para que la misma aglomeración física nunca se cuente dos veces. Tres ajustes publicados rigen el resultado: la escala espacial a la que tiendas separadas se leen como un solo clúster, la presencia mínima de tiendas que califica como co-ubicación en lugar de una tienda aislada, y el umbral de superposición utilizado en la deduplicación. Un límite duro en el alcance del clúster se aplica uniformemente, porque un ajuste más amplio fusiona aglomeraciones que operan como destinos minoristas distintos. Cada ajuste se publica junto con cada resultado de clúster. La especificación completa de agrupación y los valores de parámetro vigentes están previstos para publicarse en gis.woodfinegroup.com.

### Sensibilidad: el conteo de clústeres es una salida del modelo, no una medición

La agrupación es un procedimiento descriptivo. Divide las ubicaciones minoristas observadas bajo un modelo de densidad elegido; no recupera un número verdadero e independiente del ajuste que exista en el mundo. El número devuelto se mueve materialmente cuando los ajustes se mueven dentro de un rango defendible.

Los barridos de parámetros realizados durante el desarrollo demuestran esto directamente: en el rango razonable probado, el conteo de clústeres norteamericanos varía en más del doble, sin ningún cambio en los datos minoristas subyacentes. Un conteo titular de clústeres es, por tanto, una cifra producida bajo una parametrización elegida. Toda presentación de un conteo de clústeres indica los parámetros que lo produjeron — un conteo sin cualificar invita al lector a tratar una elección de modelado como un hecho observado.

## El puntaje de fortaleza planeado

El nivel de composición responde "¿qué combinación de minoristas hay aquí?" Un **puntaje de fortaleza** por clúster separado está destinado a responder "¿cuánto mercado comanda esta ubicación?" Las dos dimensiones se informan una al lado de la otra una vez que estén disponibles; nunca se colapsan en un solo color o un solo número.

### Principios de diseño

El puntaje de fortaleza previsto es explicable, no opaco. Es una combinación transparente de factores nombrados, cada uno de los cuales puede mostrarse en el cuadro de mando del clúster con su propio valor y su contribución al total. Sin ponderaciones de aprendizaje automático ni términos de interacción ocultos. Un revisor debe poder reconstruir el puntaje a partir de los factores mostrados.

### Conjunto de variables propuesto

Tres cantidades del lado de la demanda que las capas de datos ya admiten:

1. **Población alcanzada** — población de la cuenca e hogares, de las estimaciones de población WorldPop 2026. Este es el tamaño del mercado direccionable.
2. **Gasto capturado** — gasto minorista anual estimado en la cuenca, derivado de la población y proxies de gasto per cápita publicados por agencias estadísticas nacionales. Lleva las advertencias de estimación documentadas en [[spend-population-provenance]].
3. **Accesibilidad** — qué tan accesible es la cuenca, expresada mediante demanda de origen-destino observada donde los datos de movilidad de un país lo permiten, y una aproximación por banda de distancia en los demás casos. Cuál de las dos sustenta cada clúster se divulga en el propio clúster, de modo que un sitio con movilidad observada y uno aproximado nunca se clasifican en el mismo grupo sin que el lector lo sepa.

### Ponderaciones: una cuestión abierta

Cómo se combinan estos tres factores en un solo número es una cuestión abierta que este artículo deliberadamente no resuelve. Hasta que se ratifique la ponderación, el cuadro de mando muestra los valores de los factores individualmente para que cualquier compuesto mostrado siempre sea descomponible.

### Qué está destinado a mostrar el cuadro de mando

Para cada clúster seleccionado, el panel de detalle planeado presenta, como mínimo:

- El nivel de composición y su definición en lenguaje sencillo.
- La población e informe de hogares de la cuenca, con la vigencia indicada.
- El gasto anual estimado, explícitamente enmarcado como una estimación modelada.
- La lista de cadenas co-ubicadas que impulsan la composición.
- El puntaje de fortaleza (cuando esté construido) con sus principales factores, la contribución de cada uno, y si su cifra de accesibilidad es observada o aproximada.

## Véase también

- [[trade-area-methodology]] — derivación de la cuenca y la migración desde bandas de distancia hacia áreas de atracción observadas
- [[spend-population-provenance]] — la cadena de estimación para el factor de gasto en el puntaje de fortaleza
- el resumen a nivel de asentamiento y el criterio de selección Top-400
- el proceso que produce los clústeres por niveles
- la agrupación minorista ascendente que alimenta el índice de co-ubicación
