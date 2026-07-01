---
schema: foundry-doc-v1
title: "Jerarquía de Objetivos de Co-Ubicación"
slug: co-location-target-hierarchy
category: gis
type: topic
content_type: topic
quality: complete
short_description: "La clasificación de tres niveles que Woodfine utiliza en su conjunto de datos de co-ubicación geográfica — Primario (Walmart Supercentre), Secundario (Home Depot, Costco), Terciario (universidades, centros médicos) — definiendo qué minoristas e instituciones califican en cada nivel y por qué la presencia de cada nivel valida un Sitio de Desarrollo potencial."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: co-location-target-hierarchy.md
cites: []
---

La **Jerarquía de Objetivos de Co-Ubicación** es el sistema de clasificación de tres niveles que estructura el conjunto de datos de co-ubicación geográfica de Woodfine Management Corp. Cada nivel asigna una categoría de operador minorista o empleador institucional al papel que desempeña en la validación de un Sitio de Desarrollo potencial. La jerarquía refleja la secuencia observada de desarrollo comercial en Mercados Regionales: los Objetivos Primarios anclan el nodo minorista, los Secundarios siguen al Primario, y los Terciarios confirman que existe una base de demanda institucional para el arrendamiento de servicios profesionales en la geografía.

## Objetivo Primario: Walmart Supercentre

El Objetivo Primario en el conjunto de datos de Woodfine es el formato Walmart Supercentre — una tienda de gran formato combinada de comestibles y mercancía general. El Walmart Supercentre sirve como Objetivo Primario por su papel en el establecimiento de infraestructura comercial para un Mercado Regional. Cuando Walmart se compromete a construir un Supercentre en una geografía, simultáneamente instala las mejoras de acceso vial, conexiones de servicios públicos y preparación del sitio que otros operadores comerciales necesitan para seguirle.

Las ventas por pie cuadrado de cada Walmart Supercentre en el conjunto de datos son la métrica de clasificación principal para las entradas individuales de Objetivo Primario: un Supercentre con altas ventas por pie cuadrado opera en una zona de influencia donde el volumen de compras de los consumidores está concentrado.

## Objetivos Secundarios: Home Depot y Costco Wholesale

Los dos Objetivos Secundarios son The Home Depot y Costco Wholesale. Ambos validan segmentos específicos de la demanda de consumidores y comercial.

**Home Depot** valida una base de contratistas en la zona de influencia que genera actividad de construcción y renovación comercial y residencial. Para Woodfine, la presencia de Home Depot indica un Mercado Regional con cadena de suministro de construcción activa.

**Costco Wholesale** opera almacenes de membresía que apuntan a consumidores con capacidad de compra y escala del hogar suficiente para justificar cuotas de membresía anuales. El umbral de membresía actúa como un filtro implícito de ingresos: los mercados donde Costco opera rentablemente son mercados donde el ingreso disponible de los consumidores cumple el umbral para la compra discrecional en almacén.

Los Objetivos Secundarios reciben un umbral de co-ocurrencia de 1,0 km porque su presencia a esta distancia del Objetivo Primario indica infraestructura de sitio compartida, no proximidad geográfica coincidental.

## Objetivos Terciarios: Universidades y Centros Médicos

Las dos categorías de Objetivos Terciarios son las instituciones educativas de nivel superior (universidades y colegios) y los centros médicos importantes. Ambos generan demanda sostenida e institucionalmente anclada para el arrendamiento de servicios profesionales en la geografía circundante.

**Universidades y colegios** son empleadores de personal administrativo, investigación, clínico y de instalaciones que requieren servicios profesionales — legal, contable, asesoría financiera, médico y dental — en la zona cercana a su lugar de trabajo diario. Una institución de educación superior dentro de 5,0 km de un nodo de Centro Comercial es una fuente confirmada de demanda de arrendamiento profesional que no depende del rendimiento comercial del ancla minorista.

**Los centros médicos importantes** son algunos de los empleadores institucionales más estables en cualquier Mercado Regional. Las sedes de centros médicos atraen prácticas médicas afiliadas, clínicas especializadas, operadores de diagnóstico y minoristas farmacéuticos que requieren arrendamientos dedicados.

El umbral de 5,0 km para la co-ocurrencia terciaria refleja que los Objetivos Terciarios anclan una geografía, no un nodo comercial único. Una universidad o hospital atrae una captación profesional del Mercado Regional más amplio.

## Secuenciación de la Jerarquía y Validación del Mercado

La jerarquía está diseñada para capturar la lógica de validación secuencial que los operadores comerciales institucionales aplican en los Mercados Regionales. Cada nivel añade una señal de validación independiente: Walmart valida el volumen del consumidor; Home Depot y Costco validan la capacidad de compra y la actividad comercial; universidades y centros médicos validan la demanda de arrendamiento de servicios profesionales. El sistema de Clústeres de Cinco Grados agrega estas señales independientes en una puntuación compuesta.
