---
schema: foundry-doc-v1
slug: about-regional-markets-system
title: "Sistema de Inteligencia de Mercados Regionales"
language: es
language_protocol: TRANSLATE-ES
category: markets
index_group: coverage-methodology
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "Artículo de referencia sobre el sistema de análisis de co-localización que identifica mercados minoristas suburbanos en América del Norte y Europa."
paired_with: markets/about-regional-markets-system.md
last_edited: 2026-08-26
editor: editorial
---

El Sistema de Inteligencia de Mercados Regionales es un marco de análisis geográfico de escala continental que identifica mercados minoristas suburbanos — municipios y suburbios con nombre propio situados a distancia de desplazamiento diario de los principales centros metropolitanos — definidos por la convergencia de grandes anclas minoristas, infraestructura cívica y captación demográfica.

La investigación aborda una brecha en el análisis institucional de bienes raíces comerciales. La cobertura de investigación establecida se concentra en los mercados metropolitanos primarios: Londres, París, Nueva York, Chicago, Dallas, Toronto y sus núcleos urbanos inmediatos. El cinturón de municipios con nombre propio situados más allá de esos núcleos se analiza con mucha menos constancia. Es precisamente aquí donde los grandes formatos minoristas, los sistemas hospitalarios y los campus universitarios se co-localizan en patrones que funcionan como indicadores anticipados de actividad demográfica y económica a escala sub-metropolitana. El conjunto de datos de Mercados Regionales es la superficie analítica para ese cinturón.

El conjunto de datos actual abarca varios miles de clústeres de co-localización en 24 países de América del Norte y Europa, clasificados en cuatro niveles (Regional, Distrital, Local, Marginal) y agregados en Mercados Regionales con nombre propio. El Top 400 es el producto publicado insignia de este sistema: un subconjunto curado y seleccionado editorialmente de aproximadamente 400 mercados por continente. Método de selección más abajo.

## Alcance del Conjunto de Datos

La construcción actual cubre varios miles de clústeres de co-localización en 24 países de dos continentes.

| Región | Países |
|---|---|
| América del Norte | Estados Unidos, Canadá, México |
| Europa — oeste y sur | España, Italia, Grecia, Francia, Alemania, Portugal, Países Bajos, Austria |
| Europa — Nórdica | Suecia, Noruega, Dinamarca, Finlandia, Islandia |
| Europa — central | Polonia, Reino Unido, Chequia, Hungría, Eslovaquia |
| Europa — sureste | Bulgaria, Croacia, Rumanía |

Los recuentos de clústeres por nivel — anclas regionales, de distrito y locales — se publican en la plataforma GIS y no se reproducen aquí, porque una instantánea en el wiki queda obsoleta entre ejecuciones de procesamiento. El proceso de construcción utiliza cuatro fuentes de datos primarias.

### Fuentes de datos primarias

**OpenStreetMap (licencia ODbL).** Ubicaciones de cadenas minoristas filtradas por QID de Wikidata mediante la API de Overpass. La ingestión actual cubre más de sesenta cadenas que abarcan hipermercados, grandes almacenes de ferretería, clubes de precio, tiendas de electrónica, artículos deportivos y farmacias.

**Overture Maps Foundation (CDLA Permissive 2.0).** Ubicaciones de anclas cívicas extraídas del conjunto de datos de Lugares, que cubre sitios médicos y de educación superior en los 24 países.

**Kontur Population 2023 (CC BY 4.0).** Una cuadrícula global de población H3 de resolución 8 que cubre los 24 países; agregada a resolución H3-7 (≈1,22 km² por celda) para los cálculos de captación.

**Multiplicadores de gasto por país** de BLS (Estados Unidos), Statistics Canada y encuestas de presupuesto familiar de Eurostat se aplican a esa misma cifra de población de Kontur para modelar el potencial de gasto en alimentación, ferretería y mayoristas a nivel de captación — el gasto no procede de una fuente de población separada.

Los clústeres se forman en dos pasadas: la primera identifica los núcleos de hipermercados y anclas completas; la segunda añade las anclas periféricas de ferretería y club de precio que caen dentro de la extensión del clúster.

## Sistema de Niveles de Co-localización

Cada clúster se asigna a uno de cuatro niveles al superar un conjunto de compuertas predicativas que abarcan la composición de anclas, la posición de la población de captación, la infraestructura cívica y la no superposición con clústeres vecinos. Metodología completa: [[co-location-tier-system]].

| Nivel | Etiqueta | Regla de composición |
|---|---|---|
| **T1** | Regional | Hipermercado + ferretería + club de precio (o equivalente completo en tres categorías de ancla independientes), más población de captación en la banda nacional más alta y un hospital regional dentro del anillo cívico |
| **T2** | Distrito | Hipermercado + ferretería (dos categorías de ancla independientes), más población de captación en una banda nacional alta y acceso hospitalario dentro del anillo cívico |
| **T3** | Local | Cualquier categoría de ancla calificada única, más población de captación por encima del punto medio nacional y cualquier hospital dentro del anillo cívico |
| **T4** | Marginal | Existe co-ubicación comercial, pero el alcance de captación, la composición o el respaldo cívico no alcanzan el nivel Local |

La regla de nivel es composicional, no basada en conteo. Un sitio con cuatro hipermercados co-localizados y ninguna ferretería ni club de precio sigue siendo T3, porque la señal composicional que distingue el atractivo regional de la conveniencia local es la presencia de categorías de ancla *independientes*, no el recuento de tiendas dentro de una sola categoría.

### Clasificación por extensión y categorías de anclas

**Clasificación por extensión geométrica dentro de los niveles.** Dentro de cada nivel, los clústeres se ordenan por extensión — el diámetro del círculo mínimo que contiene todas las anclas miembro. Los clústeres compactos se clasifican antes que los dispersos, porque unas anclas situadas a corta distancia entre sí ocupan una posición comercial genuinamente compartida. Un límite superior impide que un corredor arterial largo se trate como un solo clúster.

**Categorías de anclas.** Se reconocen seis categorías de anclas en la construcción actual: `hipermercado`, `ferretería`, `club de precio`, `electrónica`, `artículos deportivos` y `farmacia`. Hipermercado, ferretería y club de precio tienen peso determinante para el nivel; electrónica, artículos deportivos y farmacia se reconocen como anclas de apoyo.

## Mercados Regionales

Un Mercado Regional es un municipio o unidad administrativa equivalente con nombre propio que contiene uno o más clústeres de co-localización. Cada mercado registra el centro metropolitano frente al cual se mide y su distancia en línea recta desde ese centro.

**La distancia se registra, no condiciona.** Describe dónde se sitúa un mercado; no decide si califica. En el conjunto publicado, las distancias registradas van de unos 12 a casi 700 kilómetros, con una mediana cercana a los 80. Tanto los mercados lo bastante próximos como para leerse como extensiones de un núcleo metropolitano como los situados a varios cientos de kilómetros de cualquier centro importante figuran en el conjunto publicado, porque ambos pueden presentar la composición de anclas sobre la que selecciona el marco.

Se distinguen dos relaciones de asentamiento, con carácter descriptivo. La mayoría de los mercados son satélites, registrados frente al centro metropolitano con el que se relacionan. Un grupo menor son centros regionales independientes — lugares que funcionan por sí mismos en lugar de como satélites, y que se publican en los mismos términos que cualquier otro mercado calificado.

Una regla de coherencia geográfica excluye las agregaciones por coincidencia de nombre: un asentamiento cuyos clústeres constituyentes están demasiado dispersos para formar una sola localización comercial se trata como un artefacto administrativo y no como un mercado en funcionamiento.

## Método de calificación para el Top 400

Lo que sitúa a un mercado en el Top 400 es la composición de anclas minoristas que ya han convergido en él. La lista se produce por separado para América del Norte y Europa, generando dos listas de 400 mercados cada una, ordenadas alfabéticamente y no por puntuación. Ningún campo de posición o puntuación se publica para ningún mercado.

### Calificación

Un mercado califica por la mezcla de categorías de ancla independientes presentes en sus clústeres de co-localización — la misma lógica de composición que sustenta el sistema de niveles, aplicada a escala de mercado y no de clúster. Un mercado aislado de otros mercados calificados se evalúa sobre la misma base de composición, de modo que un centro regional genuino no quede excluido por no tener vecinos calificados. Los criterios concretos son lógica de la plataforma y no se reproducen aquí.

Los 400 de cada continente se extraen de un grupo calificado mayor: 650 mercados en quince países en Europa y 1.121 en tres países en América del Norte. Cuando el grupo calificado supera los 400, se publican los mercados con la composición de anclas más sólida. Los recuentos por país son un resultado de ese corte, no una cuota fijada de antemano.

Existe una puntuación compuesta de uso interno para apoyar la selección, pero no se publica y no constituye una clasificación de cara al público. No influye en cómo se describe un mercado en esta wiki.

**Ningún término de distancia al metro participa en la selección.** Bajo una iteración anterior de la metodología, una bonificación por distancia hacía que ciudades secundarias independientes superaran a suburbios genuinos de metros principales. Ese término se eliminó. La distancia se registra ahora en cada mercado como contexto descriptivo, y solo la composición de anclas determina si un mercado califica. Las cifras de población y de gasto de consumo son igualmente descriptivas y no participan en la selección.

Las listas completas se publican por separado: véase [[atlas-top-400-north-america|Top 400 Mercados Regionales — América del Norte]] y [[atlas-top-400-europe|Top 400 Mercados Regionales — Europa]].

## Capa de Infraestructura Cívica

La capa de infraestructura cívica añade la presencia de anclas médicas y de educación superior a los datos de los miembros del clúster. La fuente es el conjunto de datos de Lugares de la Overture Maps Foundation.

**Cobertura.** Decenas de miles de registros médicos y de educación superior en los 24 países. Los recuentos actuales se publican en la plataforma GIS.

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

## Modelo de Captación

El modelo de captación asigna a cada clúster un área de influencia primaria y secundaria definida por el radio en línea recta desde el centroide del clúster.

| Anillo | Radio | Función |
|---|---|---|
| Primario | 35 km | Área de influencia de residencia local |
| Secundario | 150 km | Atractivo regional |

---

*Datos de referencia actualizados al 30 de mayo de 2026. Fuentes: Colaboradores de OpenStreetMap (ODbL); Overture Maps Foundation (CDLA Permissive 2.0); Kontur Population 2023 (CC BY 4.0); Beck et al. 2018 Köppen-Geiger (CC BY 4.0); WWF Ecorregiones 2017 (CC BY 4.0); US LODES (dominio público); MITMA España (datos abiertos).*

## Trabajo en preparación

Trabajo planificado o previsto para las próximas iteraciones del sistema.

**Finalización de la capa climática y de riesgos.** La capa de aceleración pico del suelo sísmica y la capa de riesgo de inundación están previstas para su construcción en mayo–junio de 2026. Una vez entregadas, cada Mercado Regional contará con un registro de envolvente completo que cubrirá zona climática, ecorregión, categoría de diseño sísmico y designación de zona de inundación.

**Regresión sobre la extensión del clúster.** Una regresión a nivel de clúster de la extensión geométrica frente a la densidad de población de captación, el gasto modelado y la actividad derivada de la movilidad está en preparación, destinada a comprobar hasta qué punto la concentración de anclas sigue a la demanda subyacente.

**Artículos por mercado.** Artículos wiki dedicados a cada uno de los 400 Mercados Regionales de la lista Top-400 están previstos. Los artículos tienen como objetivo combinar los campos de datos aquí descritos con narrativa de resolución local basada en fuentes públicas.

**Normalización de divisas para el gasto transfronterizo.** Un paso de normalización de divisas sobre la capa de gasto modelado está previsto, lo que permitirá la comparación directa del gasto en alimentación, ferretería y venta mayorista entre países.

## Véase también

- [[regional-market-definition|Definición de mercado regional]]
- [[co-location-methodology|Metodología de Co-ubicación]]
- [[atlas-top-400-north-america|Top 400 Mercados Regionales — América del Norte]]
- [[atlas-top-400-europe|Top 400 Mercados Regionales — Europa]]
- [[development-regions|Regiones de Desarrollo]]
