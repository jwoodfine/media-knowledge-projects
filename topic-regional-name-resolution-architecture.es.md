---
schema: foundry-doc-v1
title: "Arquitectura de Resolución de Nombres Regionales"
slug: topic-regional-name-resolution-architecture.es
aliases:
  - topic-regional-name-resolution-architecture.es
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "Cada clúster de co-localización se etiqueta con un nombre regional legible por humanos — un Área Metropolitana de América del Norte, una región NUTS-3 europea, un municipio mexicano, una Subdivisión Censal canadiense. Ese nombre es la salida de un proceso de geocodificación inversa por capas que opera sin llamadas a servicios externos."
paired_with: topic-regional-name-resolution-architecture.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

El mapa de [[topic-co-location-methodology|co-localización]] etiqueta cada clúster con un nombre regional legible por humanos — un Área Metropolitana de América del Norte, una región NUTS-3 europea, un municipio mexicano, una Subdivisión Censal canadiense. El nombre no es un campo único en los datos de origen; es el resultado de un proceso de geocodificación inversa por capas. Este artículo documenta las fuentes de datos, el orden de consulta y el post-procesamiento que produce los nombres visibles en la plataforma; el clúster en sí se produce mediante el [[topic-co-location-ranking-system|sistema de clasificación determinista]] tras la [[topic-cluster-deduplication-threshold|deduplicación]].

## Las cinco capas de límites

Las coordenadas del ancla de cada clúster se contrastan con cinco conjuntos de datos de límites en un orden específico por país:

| Capa | Fuente | Cobertura | Granularidad |
|---|---|---|---|
| `us_cbsa.geojson` | US Census Bureau TIGER GENZ2023 | Estados Unidos | Áreas Estadísticas Centrales (Metro + Micropolitano) |
| `ca_cma.geojson` | Statistics Canada, Censo 2021 | Canadá | Áreas Metropolitanas Censales |
| `ca_csd.geojson` | GADM 4.1 admin-3 (UC Davis Open Data) | Canadá | Subdivisiones Censales (municipios) |
| `mx_municipio.geojson` | GADM 4.1 admin-2 (UC Davis Open Data) | México | Municipios |
| `eu_nuts3.geojson` | Eurostat GISCO 2021 | UE + RU + AELC + Balcanes Occidentales | Regiones NUTS-3 |
| `fallback_ne_admin1.geojson` | Natural Earth 10m | Global | Admin-1 (estados / provincias) |

Todos los archivos se cargan una vez durante la inicialización del motor. Los índices espaciales aceleran las consultas de punto en polígono.

## Enrutamiento por país

El motor dirige las coordenadas del ancla de cada clúster según el código de país ISO:

- **Estados Unidos**: Consulta CBSA. Si hay coincidencia, el nombre del CBSA se formatea apropiadamente.
- **Canadá**: Primero se realiza la consulta de Subdivisión Censal (admin-3). Cuando tanto la Subdivisión Censal como el Área Metropolitana Censal circundante coinciden y difieren, el resultado se compone: "Strathcona County, Edmonton". Cuando sólo coincide uno, se devuelve ese nombre.
- **México**: Consulta de municipio (admin-2). En caso de coincidencia, se devuelve el nombre del municipio con el post-procesamiento de texto en español aplicado. En caso de no coincidencia, se utiliza el nivel provincial de Natural Earth.
- **Unión Europea, Reino Unido, AELC, Balcanes Occidentales**: Consulta NUTS-3.
- **Reserva**: Natural Earth admin-1 para cualquier país no cubierto por los archivos anteriores. Devuelve nombres de estados o provincias.

## Post-procesamiento de los nombres originales

Los archivos de límites contienen nombres en el idioma de origen con afijos concatenados que no son legibles por humanos. Tres transformaciones los corrigen.

**Separador CamelCase.** Los nombres de GADM 4.1 admin-2 y admin-3 se almacenan sin separadores de palabras. "StrathconaCounty" se convierte en "Strathcona County".

**Separador de preposiciones en español.** Los nombres de municipios mexicanos ocasionalmente contienen preposiciones concatenadas: "Bocadel Río", "Apetatitlánde Antonio Carvajal". Una expresión regular detecta las preposiciones *de*, *del*, *la*, *las*, *el*, *los* pegadas a un carácter en minúscula precedente e inserta un espacio antes de la preposición.

**Normalizador de puntuación.** "Gustavo A.Madero" se normaliza a "Gustavo A. Madero".

Un diccionario de anulaciones explícitas gestiona los casos fuera del alcance de las expresiones regulares: nombres griegos transliterados al inglés, simplificaciones de sufijos finlandeses, eliminación de prefijos polacos, normalización de nombres bilingües belgas.

## Escala

Tras el enrutamiento por capas y el post-procesamiento, el motor produce aproximadamente 1.200 nombres regionales únicos en todo el alcance operativo a mayo de 2026. Por país: 671 Áreas Metropolitanas de Estados Unidos distintas, 245 regiones canadienses, 104 Municipios mexicanos y varios cientos de regiones NUTS-3 europeas.

## Véase también

- [[topic-co-location-methodology]]
- [[topic-cluster-deduplication-threshold]]
