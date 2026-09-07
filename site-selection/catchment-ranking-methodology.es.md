---
schema: foundry-doc-v1
title: "Metodología de clasificación de captación por composición"
slug: catchment-ranking-methodology
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
editor: pointsav-engineering
short_description: "El sistema vigente de compuertas predicativas que asigna cada clúster de co-ubicación a uno de cuatro niveles — Regional, Distrital, Local, Marginal — mediante composición de anclas, posición nacional de captación, infraestructura cívica e independencia espacial, introducido en mayo de 2026 para reemplazar un modelo anterior de puntuación compuesta."
paired_with: site-selection/catchment-ranking-methodology.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

El sistema de niveles de [[co-location-methodology|co-localización]] asigna cada clúster a uno de cuatro niveles — Regional, Distrital, Local o Marginal (etiquetados según la [[co-location-tier-nomenclature|nomenclatura de niveles]]) — mediante compuertas de predicado binarias en lugar de una puntuación compuesta. Un clúster debe superar todas las compuertas del conjunto correspondiente a un nivel para calificar para ese nivel; los resultados parciales no se acumulan. Esta metodología describe la implementación actual, introducida en mayo de 2026. Complementa el [[co-location-ranking-system|sistema de clasificación determinista]] y toma sus insumos de área comercial de la [[od-catchment-methodology|metodología de bandas de distancia]] y de las [[trade-area-data-sources|fuentes de datos de áreas comerciales]].

## Por qué las compuertas de predicado reemplazan las puntuaciones compuestas

El sistema anterior asignaba niveles combinando varias señales ponderadas en una única puntuación compuesta. El resultado era internamente coherente, pero difícil de explicar: un clúster podía alcanzar un nivel superior gracias a una sola señal favorable, aun cuando le faltara la captación de población y la infraestructura cívica que el nivel pretendía señalar.

Las compuertas binarias hacen que los criterios de calificación sean explícitos e individualmente verificables. Un clúster Regional debe tener alcance poblacional a escala nacional, una composición de ancla específica, acceso hospitalario regional e independencia espacial respecto a clústeres más fuertes. Ninguno de estos requisitos se satisface mediante un indicador sustituto.

## Rangos de captación de población

La captación de población se calcula mediante una cuadrícula geográfica de resolución fija sobre distancia en línea recta, según la [[od-catchment-methodology|metodología de bandas de distancia]]. Se definen dos zonas para cada clúster:

- **Zona primaria**: todas las celdas de la cuadrícula dentro de 35 km del ancla del clúster
- **Zona secundaria**: todas las celdas de la cuadrícula entre 35 km y 150 km del ancla del clúster

Los totales de población provienen de un conjunto de datos de población en cuadrícula publicado bajo licencia abierta, agregado a la misma cuadrícula usada para el análisis de captación (véase [[trade-area-data-sources|fuentes de datos de áreas comerciales]]). Cada clúster se clasifica después frente a los demás clústeres de su propio país ISO en dos familias de medidas — alcance poblacional y gasto de consumo por categoría —, cada una tomada sobre ambas zonas.

El rango se expresa como una fracción percentil dentro del país del clúster: un valor más bajo indica un mayor alcance relativo. Esto permite comparar países con recuentos totales de clústeres muy distintos en una escala común.

Las medidas de gasto son estimaciones modeladas, no transacciones observadas: se derivan aplicando patrones publicados de gasto de los hogares per cápita a la cuadrícula de población y estratificando el resultado por categoría minorista.

## Definición de las compuertas de nivel

Las clases de ancla mencionadas a continuación — Hipermercado, Almacén, Ferretería y Estilo de Vida — se definen en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

### Nivel 1 — Regional

Un clúster califica como Regional si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster combina un ancla de tipo Hipermercado con un ancla de tipo Almacén o de tipo Estilo de Vida.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe estar entre los más altos del país — la barra de captación primaria más exigente de todos los niveles.
3. **Captación secundaria**: El rango de población secundaria del clúster dentro de su país también debe situarse muy por encima de la mediana del país, aunque esta barra es más laxa que la de captación primaria.
4. **Cívico — hospital regional**: Hay un hospital que atiende a una captación regional dentro de un anillo cívico de proximidad definido alrededor del ancla del clúster.
5. **Independencia espacial**: El área comercial de este clúster no debe superponerse de forma sustancial con la de ningún clúster del mismo país con mayor rango de población primaria — Regional exige la barra de independencia más estricta de todos los niveles.

### Nivel 2 — Distrital

Un clúster califica como Distrital si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Hipermercado junto con un ancla de tipo Ferretería o de tipo Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe superar una barra sustancialmente más baja que la de Regional, aunque sigue estando muy por encima de la mediana del país.
3. **Alcance de gasto**: El rango del clúster dentro de su país en al menos una categoría de gasto también debe superar esa misma barra.
4. **Cívico — hospital presente**: Hay un hospital que atiende al menos a una captación de nivel distrital dentro del anillo cívico de proximidad.
5. **Independencia espacial**: Se permite que la superposición entre el área comercial de este clúster y la de cualquier clúster Regional del mismo país sea mayor que el límite del nivel Regional, aunque sigue estando acotada.

### Nivel 3 — Local

Un clúster califica como Local si se cumplen las tres condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Ferretería o de tipo Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe estar en la mediana del país o por encima de ella.
3. **Cívico — cualquier hospital**: Hay un hospital de cualquier tipo dentro del anillo cívico de proximidad.

### Nivel 4 — Marginal

Un clúster que no califica para los niveles Regional, Distrital o Local se clasifica como Marginal. Un clúster Marginal puede contener co-tenencia comercial significativa; la clasificación indica que uno o más requisitos necesarios para Local o superior no se cumplieron.

## Medición de la superposición

La compuerta de independencia espacial compara las áreas comerciales de dos clústeres, cada una representada como un disco de radio fijo constante en todos los niveles, y mide en qué grado ambas se superponen. Los clústeres lo bastante separados como para que sus áreas comerciales no se crucen se consideran totalmente independientes. A medida que la superposición crece, el nivel del clúster más débil se limita en consecuencia.

## Clasificación cívica

La presencia hospitalaria se deriva de datos cartográficos abiertos y se gradúa según la escala de captación que atiende cada instalación. Las instalaciones que atienden a una población regional amplia satisfacen las compuertas cívicas superiores; las instalaciones locales pequeñas satisfacen únicamente la compuerta de nivel Local. La graduación funciona como un indicador de la profundidad de la infraestructura pública que respalda a un clúster, no como una medida clínica o de capacidad.

## Resumen de umbrales

Las barras de captación y de gasto se vuelven más exigentes al pasar de Local a Regional, y el margen de independencia espacial se estrecha en consecuencia — los clústeres Regional enfrentan tanto la barra de captación más alta como el límite de superposición más estricto, mientras que los clústeres Local enfrentan la barra de captación más baja y ninguna compuerta explícita de superposición. El radio del anillo cívico y el radio del disco de independencia espacial se mantienen cada uno constante en todos los niveles.

Los umbrales son deliberadamente gruesos — están diseñados para distinguir clústeres de relevancia nacional de nodos locales, no para clasificar con finura dentro de un mismo nivel. Se prevé un refinamiento en una actualización futura, a medida que se disponga de datos de captación adicionales.

## Sensibilidad: el conteo de clústeres es una salida del modelo, no una medición

La agrupación es un procedimiento descriptivo. Divide las ubicaciones minoristas observadas bajo un modelo de densidad elegido; no recupera un número verdadero e independiente del ajuste que exista en el mundo. El número devuelto se mueve materialmente cuando los ajustes se mueven dentro de un rango defendible.

Los barridos de parámetros realizados durante el desarrollo demuestran esto directamente: en el rango razonable probado, el conteo de clústeres norteamericanos varía en más del doble, sin ningún cambio en los datos minoristas subyacentes. Un conteo titular de clústeres es, por tanto, una cifra producida bajo una parametrización elegida. Toda presentación de un conteo de clústeres indica los parámetros que lo produjeron — un conteo sin cualificar invita al lector a tratar una elección de modelado como un hecho observado.

## El puntaje de fortaleza planeado

Las compuertas de nivel clasifican un clúster; no miden cuánto mercado comanda. Un **puntaje de fortaleza** por clúster separado está destinado a responder esa segunda pregunta. Las dos dimensiones se informan una al lado de la otra una vez que estén disponibles; nunca se colapsan en un solo color o un solo número.

### Principios de diseño

El puntaje de fortaleza previsto es explicable, no opaco. Es una combinación transparente de factores nombrados, cada uno de los cuales puede mostrarse en el cuadro de mando del clúster con su propio valor y su contribución al total. Sin ponderaciones de aprendizaje automático ni términos de interacción ocultos. Un revisor debe poder reconstruir el puntaje a partir de los factores mostrados.

### Conjunto de variables propuesto

Tres cantidades del lado de la demanda que las capas de datos ya admiten:

1. **Población alcanzada** — población de la cuenca e hogares, de las estimaciones de población de Kontur. Este es el tamaño del mercado direccionable.
2. **Gasto capturado** — gasto minorista anual estimado en la cuenca, derivado de la población y proxies de gasto per cápita publicados por agencias estadísticas nacionales. Lleva las advertencias de estimación documentadas en [[spend-population-provenance]].
3. **Accesibilidad** — qué tan accesible es la cuenca, expresada mediante demanda de origen-destino observada donde los datos de movilidad de un país lo permiten, y una aproximación por banda de distancia en los demás casos. Cuál de las dos sustenta cada clúster se divulga en el propio clúster, de modo que un sitio con movilidad observada y uno aproximado nunca se clasifican en el mismo grupo sin que el lector lo sepa.

### Ponderaciones: una cuestión abierta

Cómo se combinan estos tres factores en un solo número es una cuestión abierta que este artículo deliberadamente no resuelve. Tres formas candidatas están sobre la mesa: una suma normalizada de peso igual, una clasificación lexicográfica y ponderaciones ajustables por el operador. Hasta que se ratifique la ponderación, el cuadro de mando muestra los valores de los factores individualmente para que cualquier compuesto mostrado siempre sea descomponible.

### Qué está destinado a mostrar el cuadro de mando

Para cada clúster seleccionado, el panel de detalle planeado presenta, como mínimo:

- El nivel del clúster y su definición en lenguaje sencillo.
- La población e informe de hogares de la cuenca, con la vigencia indicada.
- El gasto anual estimado, explícitamente enmarcado como una estimación modelada.
- La lista de cadenas co-ubicadas que impulsan la composición.
- El puntaje de fortaleza (cuando esté construido) con sus principales factores, la contribución de cada uno, y si su cifra de accesibilidad es observada o aproximada.

## Referencias

*Los datos de ubicación de hospitales, universidades y minoristas usados para derivar los radios de captación de clústeres provienen de colaboradores de OpenStreetMap y están licenciados bajo la Licencia de Base de Datos Abierta (ODbL). Datos de OpenStreetMap © colaboradores de OpenStreetMap.*

## Véase también

- [[co-location-tier-nomenclature]]
- [[co-location-methodology]]
- [[co-location-ranking-system]]
- [[retail-brand-family-taxonomy]]
- [[trade-area-methodology]] — derivación de la cuenca y la migración desde bandas de distancia hacia áreas de atracción observadas
- [[spend-population-provenance]] — la cadena de estimación para el factor de gasto en el puntaje de fortaleza
