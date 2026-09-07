---
schema: foundry-doc-v1
title: "Metodología de Co-Ubicación Geográfica"
slug: geographic-co-location-methodology
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
short_description: "Sistema de niveles por compuertas de calificación que puntúa clústeres de co-ubicación minorista por composición de anclas, rango de captación y presencia cívica para clasificar sitios de desarrollo."
status: stable
bcsc_class: current-fact
last_edited: 2026-08-26
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: geographic-co-location-methodology.md
cites: []
---

La **Metodología de Co-Ubicación Geográfica** es la disciplina de análisis espacial que Woodfine aplica para identificar y clasificar Sitios de Desarrollo potenciales en sus cuatro jurisdicciones calificadas: Canadá, Estados Unidos, España y México. La metodología puntúa los nodos minoristas según la proximidad y la combinación de minoristas ancla que operan en la geografía, produciendo un conjunto de datos clasificados de sitios en los que la inversión de desarrollo está validada por los compromisos comerciales demostrables de minoristas institucionales, en lugar de proyecciones demográficas especulativas.

La metodología asigna cada clúster a uno de cuatro niveles mediante compuertas de calificación, no mediante una puntuación acumulada. Un clúster obtiene un nivel solo cuando supera todas las compuertas requeridas para ese nivel — composición de anclas, rango de captación y presencia cívica en conjunto, no un solo factor por sí solo. Esta estructura de compuertas reemplazó una escala anterior basada en puntos el 16 de mayo de 2026; la escala retirada, y sus etiquetas numéricas, ya no describen ningún clúster actual.

## El Sistema de Niveles

Cada clúster está anclado por una tienda de una de cuatro clases de ancla — Hipermercado, Estilo de Vida, Ferretería o Almacén — y se asigna a un nivel al superar las compuertas requeridas de ese nivel. Los nombres de nivel siguen la jerarquía de propiedades comerciales del Consejo Internacional de Centros Comerciales: **Regional**, **Distrital**, **Local** y **Marginal**, de mayor a menor. Las definiciones completas de nivel y las tablas de compuertas se mantienen en el [[gis-cluster-scoring-glossary|glosario de puntuación de clústeres]] y la [[co-location-tier-nomenclature|nomenclatura de niveles]]; el resumen a continuación indica lo que un analista de desarrollo necesita para leer el mapa.

### Regional y Distrital — los niveles calificantes para selección de sitios

Los clústeres **Regionales** combinan un ancla de Almacén o Estilo de Vida con un ancla de Hipermercado, se ubican en el decil superior de su país por captación de población primaria y tienen un hospital clasificado como regional cerca. Este es el nivel de mayor convicción: la presencia simultánea de múltiples categorías de ancla independientes, a escala de captación nacionalmente significativa, confirma que varios operadores institucionales llegaron a la misma conclusión sobre la geografía.

Los clústeres **Distritales** combinan un ancla de Hipermercado con un ancla de Ferretería o Almacén, se ubican en el cuartil superior de su país por captación de población primaria y tienen acceso hospitalario dentro del anillo cívico. Los clústeres Distritales son candidatos calificados: se cumplen las condiciones de co-ubicación y captación, pero a escala subregional en lugar de nacionalmente significativa.

### Local y Marginal

Los clústeres **Locales** contienen un ancla de Ferretería o Almacén, se ubican en la mitad superior de su país por captación de población primaria y tienen algún hospital dentro del anillo cívico. Los clústeres Locales confirman co-ubicación y apoyo de captación a nivel comunitario sin calificar a escala Distrital o Regional.

**Marginal** se asigna a cualquier clúster que no supere las compuertas de Regional, Distrital o Local. Un clúster Marginal puede aún mostrar co-tenencia minorista; le falta el alcance de captación, la composición o el apoyo cívico que requieren los niveles superiores.

## Radio de No-Superposición

Dos clústeres cercanos se comparan por superposición usando un disco de radio fijo de 3,0 km centrado en cada uno. Cuando la superposición entre los discos de dos clústeres supera el límite de la compuerta de no-superposición, el clúster más débil queda por debajo del nivel que su composición habría obtenido de otro modo — evitando que un solo nodo fuerte se cuente como varios clústeres separados. Esta convención de radio única se aplica de manera uniforme; no se ajusta al alza o a la baja según cuántos clústeres califiquen actualmente en un nivel dado.

## Métricas de Salida del Conjunto de Datos

Para cada entrada de Objetivo Primario, la salida de co-ubicación geográfica registra: la ciudad, pueblo o municipio del Objetivo Primario; la población de la comunidad circundante; las ventas por pie cuadrado del Objetivo Primario; y el ranking global de ese Objetivo Primario por ventas por pie cuadrado en todas las entradas del conjunto de datos.

## Clasificación y producción de shortlist

La salida se clasifica luego para equilibrar el nivel del clúster, la proximidad de anclas y las ventas por pie cuadrado absolutas del Objetivo Primario. La clasificación produce la shortlist de sitios a partir de la cual Woodfine contrata profesionales inmobiliarios en cada mercado identificado para evaluar la disponibilidad de terreno y el cronograma de desarrollo.

## Cantidad de Sitios Requerida por Jurisdicción

Los requisitos de shortlist de sitios están calibrados a las captaciones de capital planificadas y calendarios de construcción de cada Direct-Hold Solution. Cada jurisdicción — Canadá, Estados Unidos, España y México — tiene su propia cantidad de desarrollo requerida, a lo largo de los financiamientos de capital y deuda planificados durante el período de construcción plurianual.

### Proporción de shortlist y disponibilidad de suelo

Dado que no siempre habrá terrenos de desarrollo disponibles adyacentes a los mejores Objetivos Primarios, y algunos sitios disponibles conllevarán calendarios de recalificación o permisos que se extienden por varios años, la shortlist de sitios debe superar el número requerido de desarrollo en un margen sustancial. Se preseleccionan suficientes candidatos por sitio requerido para absorber el desgaste por disponibilidad de suelo y trámites de permisos. Se mantienen cuatro conjuntos de datos separados, uno por jurisdicción.
