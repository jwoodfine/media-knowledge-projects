---
schema: foundry-doc-v1
slug: topic-regional-markets-system.es
aliases:
  - topic-regional-markets-system.es
title: "Sistema de Inteligencia de Mercados Regionales"
language: es
language_protocol: TRANSLATE-ES
category: governance
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "Artículo de referencia sobre el sistema de análisis de co-localización que identifica y clasifica mercados minoristas suburbanos en América del Norte y Europa."
paired_with: topic-regional-markets-system.md
last_edited: 2026-05-30
editor: editorial
---

# Sistema de Inteligencia de Mercados Regionales

El Sistema de Inteligencia de Mercados Regionales es un marco de análisis geográfico de escala continental que identifica mercados minoristas suburbanos — municipios y suburbios con nombre propio situados a distancia de desplazamiento diario de los principales centros metropolitanos — definidos por la convergencia de grandes anclas minoristas, infraestructura cívica y captación demográfica.

La investigación aborda una brecha en el análisis institucional de bienes raíces comerciales. Las principales organizaciones de investigación, incluidas Oxford Economics, CBRE y Colliers International, producen cobertura extensa de los mercados metropolitanos primarios: Londres, París, Nueva York, Chicago, Dallas, Toronto y sus núcleos urbanos inmediatos. El anillo suburbano — el cinturón de municipios con nombre propio situados de 15 a 80 kilómetros de un centro metropolitano importante — está sistemáticamente subanali­zado por la investigación institucional. Es precisamente aquí donde los grandes formatos minoristas, los sistemas hospitalarios y los campus universitarios se co-localizan en patrones que funcionan como indicadores anticipados de actividad demográfica y económica a escala sub-metropolitana. El conjunto de datos de Mercados Regionales es la superficie analítica para ese anillo suburbano.

El conjunto de datos actual abarca 6.493 clústeres de co-localización en dieciocho países de América del Norte y Europa, clasificados en tres niveles de composición (T1, T2, T3) y agregados en 4.436 Mercados Regionales con nombre propio.

## Alcance del Conjunto de Datos

La construcción actual cubre 6.493 clústeres de co-localización en dieciocho países de dos continentes.

| Región | Países |
|---|---|
| América del Norte | Estados Unidos, Canadá, México |
| Europa — oeste y sur | España, Italia, Grecia, Francia, Alemania, Portugal, Países Bajos, Austria |
| Europa — Nórdica | Suecia, Noruega, Dinamarca, Finlandia, Islandia |
| Europa — central / este | Polonia, Reino Unido |

Recuentos de clústeres por nivel: **T1 = 1.746** (Anclas regionales), **T2 = 2.726** (Anclas de distrito), **T3 = 2.021** (Anclas locales). El proceso de construcción utiliza cuatro fuentes de datos primarias.

**OpenStreetMap (licencia ODbL).** Ubicaciones de cadenas minoristas filtradas por QID de Wikidata mediante la API de Overpass. La ingestión actual cubre más de sesenta cadenas que abarcan hipermercados, grandes almacenes de ferretería, clubes de precio, tiendas de electrónica, artículos deportivos y farmacias.

**Overture Maps Foundation (CDLA Permissive 2.0).** Ubicaciones de anclas cívicas extraídas del conjunto de datos de Lugares usando el campo `taxonomy.primary`. La cobertura actual incluye 27.833 registros médicos y 28.846 de educación superior en los dieciocho países.

**Kontur Population 2023 (CC BY 4.0).** Una cuadrícula global de población H3 de resolución 8 que cubre los dieciocho países; agregada a resolución H3-7 (≈1,22 km² por celda) para los cálculos de captación.

**WorldPop a 100 metros (edición 2026, CC BY 4.0).** Se utiliza en combinación con multiplicadores de gasto por país de BLS (Estados Unidos), Statistics Canada y encuestas de presupuesto familiar de Eurostat para modelar el potencial de gasto en alimentación, ferretería y mayoristas a nivel de captación.

La metodología de clusterización es un DBSCAN de dos pasadas: una primera pasada identifica los núcleos de hipermercados y anclas completas; una segunda pasada añade las anclas periféricas de ferretería y club de precio dentro de una restricción de extensión.

## Sistema de Niveles de Co-localización

Cada clúster se asigna a uno de tres niveles según la composición de anclas minoristas presentes dentro del límite del clúster.

| Nivel | Etiqueta | Regla de composición |
|---|---|---|
| **T1** | Regional | Hipermercado + ferretería + club de precio (o equivalente completo en tres categorías de ancla independientes) |
| **T2** | Distrito | Hipermercado + ferretería (dos categorías de ancla independientes) |
| **T3** | Local | Cualquier categoría de ancla calificada única |

La regla de nivel es composicional, no basada en conteo. Un sitio con cuatro hipermercados co-localizados y ninguna ferretería ni club de precio sigue siendo T3, porque la señal composicional que distingue el atractivo regional de la conveniencia local es la presencia de categorías de ancla *independientes*, no el recuento de tiendas dentro de una sola categoría.

**Clasificación por extensión geométrica dentro de los niveles.** Dentro de cada nivel, los clústeres se ordenan por `span_km` — el diámetro del círculo envolvente mínimo que contiene todas las anclas miembro. Los clústeres compactos (`span_km` inferior a 2,5) se clasifican antes que los dispersos.

**Categorías de anclas.** Se reconocen seis categorías de anclas en la construcción actual: `hipermercado`, `ferretería`, `club de precio`, `electrónica`, `artículos deportivos` y `farmacia`. Hipermercado, ferretería y club de precio tienen peso determinante para el nivel; electrónica, artículos deportivos y farmacia se reconocen como anclas de apoyo.

## Mercados Regionales

Un Mercado Regional es un municipio o unidad administrativa equivalente con nombre propio que contiene uno o más clústeres de co-localización y se encuentra a distancia de desplazamiento diario de un centro metropolitano importante. Se distinguen tres tipos de asentamiento:

| Tipo | Distancia del metro principal | Clasificación |
|---|---|---|
| **Núcleo metropolitano** | < 15 km | Excluido del Top 400 (cubierto por la investigación institucional de mercados metropolitanos) |
| **Suburbano-regional** | 15–80 km | Clasificado en el Top 400 (la brecha de investigación) |
| **Secundario independiente** | > 80 km | Excluido del Top 400 (categoría de análisis separada) |

El tipo suburbano-regional es el grupo del Top 400. Los mercados a menos de 15 km del centroide de un metro principal se tratan como extensiones del núcleo metropolitano. Los mercados a más de 80 km de cualquier centroide de metro principal son ciudades secundarias que funcionan de forma independiente.

**Recuento total: 4.436 Mercados Regionales** (los tres tipos combinados). De estos, **2.327 están en América del Norte** y **2.109 en Europa**.

## Clasificación Compuesta Top 400

La lista del Top 400 Mercados Regionales es una clasificación compuesta de asentamientos suburbano-regionales. La lista se produce por separado para América del Norte y Europa, generando dos superficies de 400 mercados cada una.

**Fórmula de puntuación compuesta.**

```
puntuación = puntuación_nivel × multiplicador_cívico × factor_confianza

donde:
  puntuación_nivel = (T1 × 4) + (T2 × 2) + (T3 × 1)
  multiplicador_cívico = 1,5  si hay ancla médica o de educación superior, si no 1,0
  factor_confianza = 1,0  para cobertura de cadena de alta confianza
                    0,7  para cobertura de cadena de baja confianza
```

**Resultados actuales más destacados.** América del Norte: posición 1 Plano, TX (suburbio de Dallas, 28 km, puntuación 25,5); posición 2 Mesa, AZ (suburbio de Phoenix, 31 km, puntuación 22,5); posición 3 Frisco, TX (suburbio de Dallas, 44 km, puntuación 21,0). Europa: posición 1 Chemnitz (suburbio de Dresden, 64 km, puntuación 18,0); posición 5 Krefeld (suburbio de Düsseldorf, 19 km, puntuación 12,0).

Las listas clasificadas completas se publican por separado: véase [Top 400 Mercados Regionales — América del Norte](topic-top-400-regional-markets-na) y [Top 400 Mercados Regionales — Europa](topic-top-400-regional-markets-eu).

## Capa de Infraestructura Cívica

La capa de infraestructura cívica añade la presencia de anclas médicas y de educación superior a los datos de los miembros del clúster. La fuente es el conjunto de datos de Lugares de la Overture Maps Foundation, consultado para las categorías primarias de `salud` y `educación superior`.

**Cobertura.** 27.833 registros médicos y 28.846 de educación superior en los dieciocho países.

**Codificación.** La presencia cívica se codifica como un indicador binario por clúster. El Mercado Regional hereda el indicador cívico de cualquier clúster constituyente.

## Capas de Datos AEC

Las capas de datos AEC (arquitectura, ingeniería y construcción) añaden contexto climático, normativo y ecológico a cada Mercado Regional.

**Capas entregadas.**

| Capa | Fuente | Cobertura |
|---|---|---|
| Zonas climáticas ASHRAE 169-2013 | Norma ASHRAE, extensión EE. UU. | 94,4% de los Mercados Regionales de EE. UU. |
| Zonas climáticas energéticas regulatorias de la UE | Normativas de eficiencia energética por país | Variable |
| Clase climática Köppen-Geiger | Beck et al. 2018 (CC BY 4.0) | 100% de todos los Mercados Regionales |
| Ecorregiones WWF 2017 | World Wildlife Fund (CC BY 4.0) | 99,5% de todos los Mercados Regionales |

**Capas en preparación.**

| Capa | Fuente | Estado |
|---|---|---|
| Aceleración pico del suelo sísmica | USGS (EE. UU.) y EFEHR (Europa) | Reprocesado previsto para el 1 de junio de 2026 |
| Riesgo de inundación | FEMA (EE. UU.) y JRC de la UE | Construcción prevista para el 31 de mayo de 2026 |

## Esquema de datos POI

La plataforma opera con dos clases de registros dentro de su capa de datos de localización: registros de negocios de servicios (cadenas minoristas) y registros de lugares de servicios (anclas cívicas).

**Registros de negocios de servicios.** Cada registro representa una única ubicación de cadena minorista e identificada por un `chain_id` que enlaza con un archivo de configuración de cadena y por un campo `brand_wikidata` que contiene el QID de Wikidata de la marca. El QID de Wikidata es el identificador canónico de cadena entre fuentes porque opera a nivel de marca y no de nombre; dos establecimientos con diferentes denominaciones en distintos idiomas pero con el mismo QID pertenecen a la misma cadena.

**Registros de lugares de servicios.** Anclas cívicas — hospitales, universidades, aeropuertos — incorporadas desde Overture Maps usando `taxonomy.primary` como filtro de categoría.

**Campos comunes compartidos.**

| Campo | Tipo | Notas |
|---|---|---|
| `location_name` | cadena | Nombre de presentación con fallback de categoría |
| `brand_wikidata` | cadena o nulo | QID de Wikidata; nulo para lugares cívicos sin identidad de marca |
| `street_address` | cadena o nulo | Dirección en formato libre |
| `city` | cadena o nulo | Localidad |
| `region` | cadena o nulo | Provincia, estado o región NUTS-3 |
| `iso_country_code` | cadena | Código de país ISO 3166-1 alfa-2 |
| `latitude`, `longitude` | flotante | WGS 84, 7 decimales |
| `naics_code` | cadena | Clasificación NAICS |
| `source` | cadena | `osm` u `overture` |
| `confidence` | flotante | OSM fijo en 0,85; Overture según el conjunto de datos |

**Deduplicación espacial.** Los registros dentro de un radio de 100 metros por cadena se dedupliccan, conservando el registro con los campos de dirección más completos. Un segundo paso a 25 metros entre diferentes valores de `chain_id` que comparten el mismo QID `brand_wikidata` identifica tiendas de subformatos o co-marcados.

## Modelo de Captación

El modelo de captación asigna a cada clúster un área de influencia primaria y secundaria definida por el radio en línea recta desde el centroide del clúster.

| Anillo | Radio | Función |
|---|---|---|
| Primario | 35 km | Área de influencia de residencia local |
| Secundario | 150 km | Atractivo regional |

---

*Datos de referencia actualizados al 30 de mayo de 2026. Fuentes: Colaboradores de OpenStreetMap (ODbL); Overture Maps Foundation (CDLA Permissive 2.0); Kontur Population 2023 (CC BY 4.0); WorldPop 2026 (CC BY 4.0); Beck et al. 2018 Köppen-Geiger (CC BY 4.0); WWF Ecorregiones 2017 (CC BY 4.0); US LODES (dominio público); MITMA España (datos abiertos).*

## Trabajo en preparación

Trabajo planificado o previsto para las próximas iteraciones del sistema.

**Finalización de la capa climática y de riesgos.** La capa de aceleración pico del suelo sísmica y la capa de riesgo de inundación están previstas para su construcción en mayo–junio de 2026. Una vez entregadas, cada Mercado Regional contará con un registro de envolvente completo que cubrirá zona climática, ecorregión, categoría de diseño sísmico y designación de zona de inundación.

**Regresión OLS sobre span_km.** Una regresión por mínimos cuadrados ordinarios a nivel de clúster de `span_km` frente a la densidad de población de captación, el gasto modelado y la actividad derivada de la movilidad está en preparación. Se contemplan efectos fijos por país y un término de interacción entre núcleo urbano y área peri-urbana.

**Artículos por mercado.** Artículos wiki dedicados a cada uno de los 400 Mercados Regionales de la lista Top-400 están previstos. Los artículos tienen como objetivo combinar los campos de datos aquí descritos con narrativa de resolución local basada en fuentes públicas.

**Normalización de divisas para el gasto transfronterizo.** Un paso de normalización de divisas sobre la capa de gasto modelado está previsto, lo que permitirá la clasificación de captación en múltiples monedas y la comparación directa del gasto en alimentación, ferretería y venta mayorista entre países.

## Véase también

- [[topic-regional-market-matrix|Matriz de Mercado Regional]]
- [[topic-co-location-methodology|Metodología de Co-ubicación]]
- [[topic-top-400-regional-markets-na|Top 400 Mercados Regionales — América del Norte]]
- [[topic-top-400-regional-markets-eu|Top 400 Mercados Regionales — Europa]]
