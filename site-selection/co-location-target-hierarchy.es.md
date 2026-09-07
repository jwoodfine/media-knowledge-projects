---
schema: foundry-doc-v1
title: "Jerarquía de Objetivos de Co-Ubicación"
slug: co-location-target-hierarchy
category: site-selection
index_group: anchors-and-tenants
type: topic
content_type: topic
quality: complete
short_description: "Las señales que busca el conjunto de datos de co-ubicación y el papel de cada una — un ancla de hipermercado, co-anclas dominantes de categoría e instituciones cívicas — y por qué el sistema actual de niveles exige cada una de forma independiente en lugar de sumarlas en una puntuación."
status: stable
audience: customer-woodfine
bcsc_class: current-fact
last_edited: 2026-09-04
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: co-location-target-hierarchy.md
cites: []
---

Ninguna señal aislada, por fuerte que sea, califica un sitio de desarrollo. Un hipermercado con ventas excepcionales no basta por sí solo; tampoco un hospital ni un club de almacén. La **Jerarquía de Objetivos de Co-Ubicación** nombra las señales comerciales e institucionales que busca el conjunto de datos de co-ubicación de Woodfine, y el papel que desempeña cada una en la validación de una geografía. Desde mayo de 2026 esas señales se comprueban como condiciones separadas que deben cumplirse todas. No se suman en una puntuación única en la que una lectura fuerte compense a una débil.

La jerarquía refleja la secuencia observada del desarrollo comercial en los [[about-regional-markets-system|Mercados Regionales]]. Un ancla de hipermercado establece el nodo. Las co-anclas dominantes de categoría lo siguen. Las instituciones cívicas confirman que existe una base de empleo institucional en la geografía circundante. Cada etapa aporta una evidencia distinta, y ninguna sustituye a otra.

## Los papeles de objetivo no son niveles de clúster

En este tema se cruzan dos vocabularios, y confundirlos es el error de lectura más frecuente.

Los **papeles de objetivo** — primario, secundario, terciario — describen qué busca la plataforma y por qué lo busca. Los **niveles de clúster** — Regional, Distrital, Local y Marginal — describen qué resultó ser un clúster una vez comprobadas todas las condiciones. Un clúster en el que están presentes los tres papeles puede quedar igualmente en el nivel más bajo si su alcance de captación es insuficiente.

Las etiquetas de nivel y su significado se establecen en la [[co-location-tier-nomenclature|nomenclatura de niveles]]. Las condiciones que un clúster debe superar para obtener cada nivel se establecen en la [[catchment-ranking-methodology|metodología de clasificación de captación]]. Este artículo trata las entradas de esas condiciones, no las condiciones en sí.

## Objetivo primario — el ancla de hipermercado

El objetivo primario es la tienda de gran formato que combina alimentación y mercancía general. No es simplemente el formato más grande que opera una cadena. Es el formato que un operador despliega únicamente donde ha validado una demanda de consumo suficiente para justificar una inversión combinada de alimentación y mercancía general a escala institucional plena.

### Secuenciación de la infraestructura

El hipermercado es el objetivo primario por lo que construye. Cuando un operador se compromete a levantar un hipermercado en una geografía, instala las mejoras de acceso vial, las conexiones de servicios públicos y la preparación del terreno que otros operadores comerciales necesitan para seguirle. Los operadores de ferretería y de club de almacén no suelen, por comportamiento observado de selección de emplazamientos, preceder al hipermercado en un mercado. Llegan después de que este haya validado y preparado el nodo comercial.

En el conjunto de datos el objetivo primario es además el registro semilla: un clúster candidato se identifica a partir de un ancla de clase hipermercado y se describe hacia afuera desde ella. Las cuatro clases de ancla que reconoce la condición de composición — hipermercado, estilo de vida, ferretería y almacén — se definen en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

### Las ventas por pie cuadrado clasifican; no califican

Las ventas por pie cuadrado de cada entrada de hipermercado son la métrica de clasificación principal de los registros individuales de objetivo primario. Son un indicador directo de la intensidad de la demanda: una tienda con ventas altas por pie cuadrado opera en una zona de influencia donde el volumen de compra está concentrado.

No tienen ningún peso en si un clúster supera una condición de nivel. Entran más tarde, en el [[co-location-ranking-system|paso de clasificación]] que ordena los clústeres ya calificados en una lista corta de sitios. Mantener ambas cosas separadas importa. Un hipermercado en los primeros puestos de la clasificación, situado en una geografía que incumple una condición de captación o cívica, sigue sin producir un clúster calificado.

## Objetivos secundarios — las co-anclas

Los objetivos secundarios son los operadores dominantes de categoría que siguen al hipermercado hasta el nodo. Cada uno valida un segmento distinto de la demanda de consumo y comercial.

Las anclas de **ferretería** — grandes superficies de mejora del hogar que atienden tanto a consumidores residenciales como a contratistas — confirman que una geografía sostiene una base de contratistas. Electricistas, fontaneros, contratistas generales y especialistas en reforma atienden tanto a la construcción residencial como a la comercial. Su presencia indica un Mercado Regional con una cadena de suministro de construcción activa, lo que se correlaciona con la disposición para el desarrollo inmobiliario comercial.

Las anclas de **almacén** — clubes de almacén por membresía — actúan como un filtro implícito de ingresos y de tamaño del hogar. La cuota de membresía es un umbral: los mercados donde un club opera con rentabilidad son mercados donde el ingreso disponible del consumidor sostiene la compra discrecional en almacén. Su presencia confirma un perfil de ingresos en la zona de influencia coherente con la base de inquilinos para la que se construyen los Centros Profesionales.

Las anclas de **estilo de vida** — el formato de gran superficie de hogar y decoración — se reconocen en ese mismo papel de co-ancla, y aparecen en la condición de composición del nivel más alto junto a un hipermercado.

### Proximidad significa nodo compartido, no mercado compartido

Una co-ancla cuenta para la composición solo cuando está lo bastante cerca del objetivo primario como para compartir el mismo nodo comercial: los mismos viales de acceso, la misma urbanización, la misma agrupación parcelaria. Una ferretería situada a varios kilómetros puede reflejar un desarrollo comercial independiente y no un [[power-centres|Power Centre]] co-anclado. La proximidad física es lo que distingue ambos casos.

Las convenciones de distancia que trazan esa línea son parámetros de ingeniería de la plataforma, reajustados entre reconstrucciones a medida que cambia la cobertura de cadenas ancla. No se publican aquí.

## Objetivos terciarios — instituciones cívicas

Los objetivos terciarios son empleadores institucionales que generan demanda sostenida de arrendamiento de servicios profesionales en la geografía circundante, con independencia del rendimiento comercial del propio nodo minorista.

Los **grandes centros médicos** — hospitales de gran tamaño y complejos sanitarios integrados — son de los empleadores institucionales más estables de cualquier Mercado Regional. Una sede hospitalaria atrae prácticas médicas afiliadas, clínicas especializadas, operadores de diagnóstico por imagen y minoristas farmacéuticos, todos ellos con necesidad de arrendamientos propios. Esa densidad de arrendamiento profesional sanitario convierte al centro médico en un predictor fiable de la demanda del tipo edificatorio de Centros Profesionales.

Los hospitales se clasifican por función: hospitales generales con servicio de urgencias, hospitales secundarios y centros especializados, y consultorios de atención primaria o clínicas sin cita. La condición cívica se estrecha al subir de nivel: el nivel más alto exige un hospital de clasificación regional, y las instalaciones de grado clínica no satisfacen las condiciones de los niveles superiores.

Las **universidades y los colegios superiores** emplean a personal administrativo, de investigación, clínico y de instalaciones que requiere servicios legales, contables, de asesoría financiera, médicos y dentales cerca de su lugar de trabajo diario. También producen las poblaciones de posgrado y profesionales que se incorporan a la economía de servicios profesionales del mercado circundante. Sus ubicaciones se recogen en la misma capa cívica que los hospitales e informan el argumento de demanda de arrendamiento profesional. En las definiciones actuales de nivel no satisfacen por sí solas una condición cívica: las compuertas cívicas comprueban la clasificación hospitalaria.

### El anillo cívico es más amplio que el nodo

Una institución cívica ancla una geografía, no una parcela. Un hospital atrae su captación profesional del Mercado Regional más amplio, no del solar del Power Centre. La condición cívica se comprueba, por tanto, sobre un anillo más amplio que la condición de composición, bajo el razonamiento de que un inquilino profesional puede trabajar en el centro médico y aun así buscar servicios dentales, legales o financieros a pocos minutos en coche. Ese anillo es un parámetro de la plataforma y no se publica aquí.

## Por qué son condiciones y no una puntuación

Cada papel aporta una evidencia que los demás no pueden aportar. Un hipermercado valida el volumen de consumo. Las co-anclas de ferretería y almacén validan la actividad de los oficios y la capacidad de compra del hogar. Un hospital de clasificación regional valida un empleo institucional que no depende en absoluto del rendimiento minorista.

Como las señales son independientes, no son intercambiables — y un sistema que las suma las trata implícitamente como si lo fueran. Ese es el razonamiento del cambio de mayo de 2026. Hasta entonces la plataforma asignaba niveles mediante una escala de puntos que sumaba composición, recuento, diversidad, profundidad cívica y una penalización por solapamiento en una única cifra. Un clúster podía alcanzar un nivel alto por una lectura fuerte en un término, careciendo del alcance de captación o de la infraestructura cívica que ese nivel debía señalar.

Bajo el sistema actual cada condición se comprueba por separado, y un clúster obtiene un nivel solo cuando se cumplen todas las condiciones de ese nivel. La fuerza parcial no se acumula. La escala retirada y sus etiquetas numéricas ya no describen ningún clúster actual.

## Qué no determina la jerarquía

La jerarquía de objetivos es una entrada entre varias. Dos condiciones más quedan enteramente fuera de ella: la posición de un clúster en la clasificación de captación frente a otros clústeres de su propio país, derivada de las zonas descritas en la [[od-catchment-methodology|metodología de bandas de distancia]], y su independencia espacial respecto de clústeres más fuertes cercanos.

Tampoco es un perfil demográfico. La salida de co-ubicación registra la comunidad, su población y el rendimiento y la clasificación de ventas del objetivo primario. La elaboración de perfiles demográficos es un paso analítico aparte, tratado en la [[optimum-mosaic-demographic-profiling|metodología Optimum Mosaic]].

## Véase también

- [[geographic-co-location-methodology]]
- [[catchment-ranking-methodology]]
- [[co-location-anchors]]
