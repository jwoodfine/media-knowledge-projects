---
schema: foundry-doc-v1
title: "Glosario de Puntuación de Clústeres GIS"
slug: gis-cluster-scoring-glossary
category: reference
type: topic
content_type: topic
quality: complete
short_description: "Definiciones para la terminología de grado de clúster (Primer al Quinto Grado), etiquetas de nivel (T3 Apex, T2 Hub, T1 Valid) y convenciones de umbral de radio utilizadas en el sistema de puntuación de co-ubicación geográfica de Woodfine — el vocabulario para interpretar los resultados del conjunto de datos de co-ubicación y los informes de cobertura GIS."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
  - "42cddb0e1bbd6516c578dbfe4a48f5ff2fd084529ef9adeaf09612c3bd36a5e1"
paired_with: gis-cluster-scoring-glossary.md
cites: []
---

Este glosario define la terminología utilizada en el sistema de puntuación de co-ubicación geográfica de Woodfine Management Corp. El vocabulario cubre las designaciones de grado de clúster, las etiquetas de puntuación de nivel, las convenciones de umbral de radio y las métricas de salida del conjunto de datos. Estos términos aparecen en los informes del conjunto de datos de co-ubicación, las comunicaciones de cobertura GIS y los materiales de selección de sitios preparados para revisión por los Directores Independientes del Socio General.

## Términos de Grado de Clúster

**Clúster de Primer Grado** — Un nodo de co-ubicación puntuado en el que un Objetivo Primario (Walmart Supercentre) y al menos un Objetivo Secundario (Home Depot o Costco Wholesale) están ubicados dentro de 1,0 km entre sí. El indicador de base de un nodo comercial co-anclado.

**Clúster de Segundo Grado** — Un Clúster de Primer Grado en el que al menos un Objetivo Terciario (institución de educación superior o centro médico importante) está ubicado dentro de 5,0 km. Indica presencia de co-ancla más demanda de empleo institucional dentro del radio de desplazamiento.

**Clúster de Tercer Grado** — Un nodo puntuado en el que un Objetivo Primario y ambos Objetivos Secundarios (Home Depot y Costco Wholesale) están ubicados dentro de 1,0 km entre sí. Requiere confirmación doble de secundarios al radio de 1,0 km.

**Clúster de Cuarto Grado** — Un Clúster de Tercer Grado con al menos un Objetivo Terciario dentro de 5,0 km. Confirmación doble de secundarios más demanda de empleo institucional.

**Clúster de Quinto Grado** — Un Clúster de Tercer Grado con ambos Objetivos Terciarios (institución de educación superior y centro médico importante) dentro de 5,0 km. La designación de clúster de mayor convicción en el sistema de puntuación: cinco categorías independientes de inversión institucional confirmadas dentro de los umbrales de radio aplicables.

## Etiquetas de Puntuación de Nivel

La metodología de puntuación V2 asigna los clústeres puntuados a tres niveles según la puntuación agregada:

**T3 Apex** — Puntuación ≥ 700. La designación de nivel superior. Los clústeres T3 Apex representan los candidatos a Sitio de Desarrollo de mayor prioridad en el conjunto de datos.

**T2 Hub** — Puntuación ≥ 450. La designación de nivel medio. Un clúster T2 Hub tiene co-ocurrencia Primario-Secundario confirmada y contribuciones de puntuación de factores adicionales. Los clústeres T2 Hub son candidatos calificados que requieren evaluación adicional de disponibilidad del sitio.

**T1 Valid** — Puntuación ≥ 150. La designación de nivel de entrada. Un clúster T1 Valid tiene presencia de Objetivo Primario con confirmación de co-ubicación parcial. Los clústeres T1 Valid pueden calificar si los factores de disponibilidad del sitio y proximidad terciaria se confirman en el proceso de Informe de Resumen de Transacción.

## Convenciones de Umbral de Radio

**Umbral de 1,0 km** — Aplicado a la co-ocurrencia de Objetivo Primario y Secundario. Corresponde a la zona de infraestructura de sitio compartida de un centro comercial co-anclado.

**Umbral de 3,0 km** — Un radio recalibrado aplicado cuando los Clústeres de Quinto Grado superan el 10% de todas las entradas de Objetivo Primario en el conjunto de datos. Cuando el nivel de clúster superior contiene más del 10% de todas las entradas, el umbral de proximidad terciaria se reduce de 5,0 km a 3,0 km.

**Umbral de 5,0 km** — Aplicado a la co-ocurrencia de Objetivo Terciario bajo la calibración estándar. Captura el área de captación geográfica de un empleador institucional que influye en la demanda de arrendamiento profesional en el área circundante.

## Métricas de Salida del Conjunto de Datos

**Objetivo Primario** — En el conjunto de datos de co-ubicación de Woodfine, un Walmart Supercentre que opera en una geografía dada. Cada entrada de Objetivo Primario está asociada con el nombre de una ciudad o municipio, cifra de población, ventas por pie cuadrado y una posición de ranking global.

**Ventas por Pie Cuadrado** — La métrica de productividad minorista utilizada para clasificar los Objetivos Primarios dentro del conjunto de datos. Refleja la intensidad de compra de los consumidores dentro de la zona de influencia y sirve como criterio de ordenación principal.

**Posición Global** — El rango de un Objetivo Primario por ventas por pie cuadrado en relación con todas las entradas de Objetivo Primario en los tres conjuntos de datos (Canadá, Estados Unidos, México).

**Clúster Puntuado** — Un nodo geo-localizado que ha cumplido los criterios de Objetivo Primario y al que se le ha asignado un grado de clúster y puntuación de nivel basados en la co-ocurrencia de Objetivos Secundarios y Terciarios a los umbrales de radio aplicables.
