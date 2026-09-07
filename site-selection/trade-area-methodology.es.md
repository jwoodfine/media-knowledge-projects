---
schema: foundry-doc-v1
title: "Metodología de área de atracción"
slug: trade-area-methodology
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Etiquetado honesto de la geografía de demanda — por qué las bandas de distancia rectilínea nunca se llaman áreas de captación, y el paso previsto a isócronas."
paired_with: site-selection/trade-area-methodology.md
cites: []
---

La metodología de área de atracción establece cómo el mapa de inteligencia de ubicación de Woodfine (gis.woodfinegroup.com) define, representa y etiqueta el área alrededor de cada clúster de co-ubicación desde la cual se estima que viajan los clientes. Un área de atracción no es simplemente la extensión geográfica de las tiendas en un clúster; es una representación de dónde se origina la demanda. La metodología especifica, con claridad y con sus limitaciones declaradas, cómo se construye esa representación en cada etapa del desarrollo del producto.

## Lo que muestra el mapa hoy

El mapa en vivo muestra una banda de distancia alrededor del centroide de cada clúster. **Hasta que la canalización de áreas de atracción observadas esté integrada, esa banda es un radio de línea recta, no una cuenca hidrográfica medida.** La regla de etiquetado es inequívoca: cualquier geometría derivada de una fórmula de línea recta se lee como "banda de distancia (línea recta)" en la cara del mapa y en el panel de detalles — nunca "cuenca hidrográfica" y nunca "área de atracción."

El mapa declara con claridad: *"Las bandas de distancia son radios de línea recta alrededor del centroide del clúster; aproximan, pero no miden, de dónde provienen los clientes."*

Una banda etiquetada como 35 km representa 35 km de distancia real sobre el terreno a cualquier latitud. Las distancias se miden sobre la superficie curva de la tierra, no sobre la imagen aplanada del mapa, de modo que una cifra declarada significa lo mismo en cada mercado. El propio mapa, como todo mapa web, se estira con la latitud en pantalla — las cifras subyacentes no se mueven. El tratamiento de distancia y proyección que respalda esta garantía está previsto para publicarse en gis.woodfinegroup.com.

## El modelo previsto: orígenes observados y tiempo de conducción

Dos métodos — isócronas de tiempo de conducción y polígonos de origen-destino empíricos — están planeados como mejoras sucesivas a las bandas de distancia actuales.

### Isócronas de tiempo de conducción

Una isócrona reemplaza el radio de línea recta con el área accesible dentro de un tiempo de conducción declarado (por ejemplo, 10, 20 o 30 minutos) a lo largo de la red vial. Las isócronas respetan barreras que los círculos ignoran — ríos, acceso a autopistas, puertos de montaña, rutas costeras de un solo sentido — por lo que dos clústeres con radios de línea recta idénticos pueden tener áreas de alcance sustancialmente diferentes. Las isócronas de tiempo de conducción son el estándar de la geografía minorista que esperan los revisores de selección de sitios.

La implementación prevista utiliza enrutamiento auto-alojado sobre datos de mapas abiertos que la plataforma ya posee, en lugar de un servicio de isócronas de terceros con tarificación por uso — coherente con un producto construido sobre infraestructura de datos soberana y autocontenida.

### Polígonos de origen-destino observados

En lugar de modelar de dónde podrían venir los clientes, un polígono de O-D dibuja de dónde vienen realmente, utilizando datos de movilidad observados. La cobertura actual abarca dos países: los flujos de origen-destino de trabajadores publicados para Estados Unidos, y las matrices de movilidad publicadas por el Ministerio de Transporte de España — cada uno proporciona una distribución de origen observada en lugar de un anillo modelado. Los datos necesarios para representar polígonos de origen observados para clústeres de EE. UU. y España ya están disponibles; convertir un clic en un clúster en un polígono de origen observado, en lugar de un anillo, está planeado pero aún no disponible. Las fuentes de datos y el detalle de su cobertura están previstos para publicarse en gis.woodfinegroup.com.

La cobertura es desigual (EE. UU. y España hoy; Reino Unido, Francia y Alemania investigados como fuentes viables siguientes), por lo que el despliegue planeado es por país. Los clústeres sin cobertura de O-D mantienen la banda de distancia claramente etiquetada como medida provisional explícita.

### Por qué ambos métodos son complementarios

Las isócronas de tiempo de conducción responden a la pregunta "quién puede llegar a este sitio." Los polígonos de O-D observados responden "quién realmente compra o trabaja aquí." El mapa previsto expone la mejor representación disponible por clúster, indicando en pantalla qué modelo produjo el polígono y sobre qué período de datos. Un polígono medido y un círculo dibujado nunca se combinan bajo una sola etiqueta.

## La fórmula de radio anterior

La banda de distancia utilizada en la versión inicial del producto se calculaba a partir de la extensión geográfica del clúster — qué tan dispersas están sus tiendas miembro —, inflada por un factor de ajuste no documentado y sin derivación publicada, y acotada por un piso mínimo para que ningún clúster reciba una banda irrealmente pequeña.

Esto es un artefacto geométrico, no una cantidad de demanda. Describe qué tan dispersas están las tiendas, no qué tan lejos viajan realmente los clientes. De ahí se derivan directamente dos modos de fallo: un clúster urbano denso obtiene un anillo pequeño porque sus tiendas están cerca entre sí, aunque su área de atracción real pueda ser grande; un clúster exurbano disperso obtiene un anillo grande porque sus tiendas están alejadas entre sí, no porque atraiga clientes de lejos.

Ni el factor de inflación ni el piso tienen una derivación publicada. Son constantes de ajuste que hacen que la imagen se vea razonable. Hasta que se adopten los límites de O-D observado o de tiempo de conducción, cualquier banda de distancia provisional divulga que se apoya en esta fórmula no publicada, basada solo en geometría, en lugar de aplicarla en silencio.

El estado final previsto elimina por completo esta fórmula basada en la extensión geográfica de la canalización en vivo, reemplazándola por un límite cuyo parámetro es una cantidad que un experto en la materia puede evaluar por sus propios méritos — un tiempo de conducción declarado, un percentil declarado de demanda modelada, o un umbral de población declarado.

## Las distancias se miden sobre el terreno, no en la pantalla

Cada cifra de distancia y área en la plataforma es una medición real sobre el terreno, calculada de forma consistente en toda la huella de 24 países del sistema de co-ubicación y en los marcos norteamericano y europeo. La proyección del mapa se estira con la latitud, como ocurre en todo mapa web — un anillo dibujado con el mismo tamaño en pantalla cubre menos terreno cerca de los polos que cerca del ecuador — de modo que ninguna cifra se deriva jamás de la imagen misma. El mapa declara esto en su propia cara: la forma representada puede estirarse; las cifras subyacentes no. El detalle de proyección y cálculo que respalda esto está previsto para publicarse en gis.woodfinegroup.com.

## Marco espacial

La población y el gasto se agregan en una única cuadrícula hexagonal continua y consistente en todo el mundo. Debido a que cada mercado se mide sobre la misma cuadrícula, las cifras de población y gasto de un clúster son directamente comparables entre los 13 países con multiplicadores de gasto per cápita publicados (véase [[spend-population-provenance]] para la cobertura completa). Esta revisión no cambia la cuadrícula de agregación; cambia cómo se define el polígono de área de atracción sobre esa cuadrícula — por origen observado o tiempo de conducción donde los datos lo permiten, y por una banda de distancia claramente etiquetada donde aún no. La especificación de la cuadrícula está prevista para publicarse en gis.woodfinegroup.com.

Una sola celda de la cuadrícula puede caer dentro de las áreas de atracción de varios clústeres. Esto es intencional: las áreas de atracción se superponen porque el panorama minorista es competitivo, y un hogar cercano a dos clústeres en competencia contribuye a ambos. Esto se cumple ya sea que el límite sea una banda de distancia, una isócrona o un polígono de O-D, y es la base de la comparación entre clústeres.

## Qué cambia a continuación

El paso desde los anillos de línea recta está previsto como una migración por fases, país por país: primero el etiquetado honesto de cada banda provisional; luego los polígonos de origen observado donde los datos de movilidad ya lo permiten, con los clústeres sin cobertura manteniendo la banda etiquetada; después las isócronas de tiempo de conducción como vista predeterminada de área alcanzable, retirando la fórmula provisional basada en la extensión geográfica; y finalmente límites calibrados de decaimiento de distancia que extienden polígonos defendibles a más países a medida que se confirman fuentes viables. Cada paso reduce la brecha entre lo que el polígono afirma y lo que respaldan los datos. La secuencia de ingeniería y su estado actual están previstos para publicarse en gis.woodfinegroup.com.

## Aplicación

La pertenencia al área de atracción es la base para la agregación de población (Kontur Population), la agregación de gasto (multiplicadores per cápita modelados) y la clasificación competitiva entre clústeres. Las cifras atribuidas a un clúster son solo tan defendibles como el polígono sobre el que se suman — por lo que la definición del polígono, sus parámetros y el tratamiento de proyección se declaran aquí en lugar de darse por sentados en un círculo dibujado sobre un mapa.

## Véase también

- [[catchment-ranking-methodology]] — cómo se asignan los niveles a los clústeres y el puntaje de fortaleza planeado
- [[spend-population-provenance]] — la cadena de estimación para población y gasto dentro del área de atracción
- el resumen a nivel de asentamiento construido sobre clústeres de co-ubicación
- el proceso que ejecuta el análisis espacial
