---
schema: foundry-doc-v1
title: "Arquetipos de Co-localización en Inteligencia de Ubicación"
slug: location-intelligence-archetypes
category: site-selection
index_group: strategy-and-investment-thesis
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Tres arquetipos de co-localización — Centros Comerciales (PRO), Franja Urbana (VWH) y Área de Acceso (PKS) — que identifican patrones de agrupación comercial diferenciados en 17 países de Norteamérica y Europa."
paired_with: site-selection/location-intelligence-archetypes.md
---

La plataforma de Inteligencia de Ubicación identifica la gravedad comercial y
minorista mediante tres arquetipos de co-localización: Centros Comerciales
(PRO), Franja Urbana (VWH) y Área de Acceso (PKS). Cada arquetipo describe un
patrón de agrupación distinto que refleja un tipo diferente de actividad
comercial y una relación diferente con la geografía urbana circundante.

Los códigos de tres letras fueron ratificados el 1 de junio de 2026.

## Los tres arquetipos

| Código | Nombre | Tipo de ancla | Estado |
|--------|--------|---------------|--------|
| **PRO** | Centros Comerciales | Prueba de predicados de composición — hipermercado de alimentación más combinaciones de anclas de ferretería/mayorista/estilo de vida | Activo — canal de niveles Regional/Distrito/Local/Marginal |
| **VWH** | Franja Urbana | Ferretería + ecosistema de suministro industrial (MRO, alquiler de herramientas, distribuidores de construcción, recambios de auto) | Activo — canal de co-localización productivo en tres niveles |
| **PKS** | Área de Acceso | Ancla de tránsito regional (aeropuerto, tren, bus) + aparcamiento disuasorio + alquiler de vehículos/hotel | Activo — canal de co-localización productivo en tres niveles |

PRO es el producto de mapa base — la base del conjunto de datos de selección
de ubicaciones. VWH y PKS son arquetipos superpuestos que identifican
estructuras de mercado adyacentes no capturadas por la agrupación anclada en
alimentación.

---

## PRO — Centros Comerciales

Los clústeres PRO representan co-localizaciones comerciales ancladas en
alimentación, asignadas a uno de cuatro niveles mediante una prueba de
predicados: cada nivel exige que se cumplan todas las condiciones listadas,
no una puntuación aditiva frente a un umbral. Las definiciones de las
compuertas se exponen íntegramente en la
[[catchment-ranking-methodology|metodología de clasificación de captación]],
que es el enunciado canónico de la lógica de niveles; lo que sigue resume
qué distingue a cada nivel.

### Definiciones de nivel

**Nivel 1 — Regional:** Un ancla de tipo Hipermercado combinada con un ancla
Mayorista o de Estilo de Vida; población de captación entre las más altas de
su país tanto en la zona primaria como en la secundaria; un hospital que
atiende a una captación regional dentro del anillo cívico; y ausencia de
superposición sustancial de área comercial con un clúster más fuerte.

**Nivel 2 — Distrito:** Un ancla de tipo Hipermercado más un ancla de
Ferretería o Mayorista; población de captación alta pero inferior a la
Regional, acompañada de un alcance comparable en al menos una categoría de
gasto; un hospital que atiende al menos a una captación de nivel distrital
dentro del anillo cívico.

**Nivel 3 — Local:** Un ancla de Ferretería o Mayorista; población de
captación en la mediana de su país o por encima de ella; un hospital de
cualquier tipo dentro del anillo cívico.

**Nivel 4 — Marginal:** Todos los clústeres que no superan las pruebas de
Nivel 1, 2 o 3.

Las clases de ancla — Hipermercado (alimentación de gran formato), Estilo de
Vida, Ferretería y Mayorista — se definen en la
[[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].
Los formatos de alimentación de proximidad se excluyen deliberadamente: su
densidad generaría clústeres falsos positivos en lugar de una convergencia
real de anclas.

### Forma y cobertura del conjunto de datos

El conjunto de datos de producción está fuertemente sesgado hacia los niveles
inferiores. Los clústeres Marginales superan en número a los tres niveles
calificados combinados, cada nivel sucesivo hacia abajo es sensiblemente
mayor que el anterior, y los clústeres Regionales son una fracción pequeña
del total. La cobertura abarca siete países principales — Estados Unidos,
México, España, Alemania, Canadá, Francia y Gran Bretaña — más otros mercados
aún no desglosados individualmente. Los límites de nivel se reajustan
periódicamente a medida que cambia la cobertura de cadenas ancla y la huella
minorista subyacente.

---

## VWH — Franja Urbana

Los clústeres VWH identifican concentraciones de minoristas de ferretería y
suministros industriales en ausencia de anclas de alimentación. Estos
emplazamientos ocupan la franja urbana — una banda de distancia más allá del
núcleo metropolitano inmediato pero por debajo del territorio de mercado
independiente — y tienden a agruparse cerca de intercambiadores de autopista
en zonas con uso del suelo industrial adyacente.

### Definición

Un candidato VWH es una ubicación donde hay uno o más establecimientos de
ferretería, no existe ningún hipermercado de alimentación dentro del radio
del clúster, y el emplazamiento se encuentra dentro de la banda de distancia
metropolitana de la Franja Urbana. La forma construida típica es un edificio
de almacén o fabricación ligera de varias plantas, distinto del formato de
caja grande de una planta del parque comercial.

Las ubicaciones VWH prestan servicio a contratistas del sector de la
construcción, operadores de fabricación ligera y arrendatarios de logística
de aprovisionamiento inmediato — no a consumidores minoristas generales.

### Señales de co-localización

**Esenciales:**

| Señal | Justificación |
|-------|--------------|
| Intercambiador de autopista cercano | Acceso de camiones y salida de mercancías |
| Población suficiente en un radio de desplazamiento corto | Mano de obra para fabricación y logística |
| Uso del suelo industrial adyacente | Compatibilidad de zonificación |

**Significativas:**

| Señal | Justificación |
|-------|--------------|
| Aeropuerto de carga al alcance | Electrónica y componentes, reposición rápida |
| Ferrocarril de mercancías cercano | Entrega de componentes justo a tiempo |
| Corredor de transporte público cercano | Acceso de la mano de obra |

**Descalificadoras:** Zona residencial densa inmediatamente adyacente; llanura
de inundación; zona de conservación del patrimonio; ubicación dentro de un
clúster PRO.

### Estado de producción

La clasificación de Franja Urbana es de calidad productiva. Los
establecimientos de ferretería sirven como ancla proxy perfilada, y la
agrupación de suministro industrial se validó antes de que la clasificación
pasara a producción.

El conjunto de datos abarca miles de clústeres en los 17 países cubiertos,
con la concentración más alta en Estados Unidos y una cobertura significativa
en varios otros mercados de Norteamérica y Europa.

Los clústeres se distribuyen entre los tres niveles con la forma esperada:
una minoría reducida alcanza el nivel de Hub comercial completo, una
proporción mayor alcanza el nivel Establecido, y la mayoría se sitúa en el
nivel Emergente/Reducido. Esa distribución con predominio de T3 es esperada
— un hub de suministro completo que combine MRO, alquiler de herramientas,
distribuidor de construcción y recambios es una combinación legítimamente
poco frecuente.

Algunos clústeres de Franja Urbana se encuentran lo bastante cerca de un
hipermercado de alimentación como para funcionar como parques comerciales de
uso mixto — co-localizaciones VWH válidas que también incluyen comercio de
alimentación.

---

## PKS — Área de Acceso

Los clústeres PKS identifican concentraciones comerciales cerca de aeropuertos
regionales y estaciones de tren interurbano situados en una corona de acceso
más allá del núcleo metropolitano inmediato pero por debajo de la distancia de
mercado independiente. El patrón de demanda definitorio es el desplazamiento
de estacionamiento y vuelo, o estacionamiento y tren: los residentes de un
Mercado Regional conducen hasta un nodo de transporte, estacionan y viajan al
Mercado Metropolitano.

### Definición

Un candidato PKS es un nodo de transporte regional — aeropuerto o estación de
tren interurbano — dentro de la banda de distancia metropolitana del Área de
Acceso. Los nodos más cercanos que esa banda se clasifican como suburbanos en
lugar de regionales; los nodos más allá de ella se consideran mercados
independientes con una relación metropolitana propia.

La señal comercial definitoria en una ubicación PKS es el alquiler de
vehículos. Los recambios de automoción, las gasolineras, los restaurantes de
servicio rápido y las tiendas de conveniencia son señales secundarias.

### Señales de co-localización

**Esenciales:**

| Señal | Justificación |
|-------|--------------|
| Ancla de transporte regional cercana | Aeropuerto o estación con servicio directo al área metropolitana |
| Aislamiento metropolitano dentro de la banda del Área de Acceso | Define la relación regional |
| Clúster T1 o T2 de PRO cercano | La misma población genera demanda de estacionamiento |
| Población regional suficiente | Demanda mínima para estacionamiento de varios pisos |

**Significativas:**

| Señal | Justificación |
|-------|--------------|
| Alquiler de vehículos cercano | Los viajeros que llegan requieren transporte |
| Concentración hotelera cercana | Viajes de negocios y estacionamiento de varios días |
| Segundo modo de transporte cercano | Integración multimodal |

**Descalificadoras:** Gran hub dentro del núcleo metropolitano inmediato;
población por debajo de un umbral mínimo viable; sin servicio directo al
área metropolitana.

### Estado de producción

La clasificación de Área de Acceso es de calidad productiva. Los registros de
aparcamiento disuasorio son el ancla geográfica principal — puntos de
transición coche→tránsito distribuidos de forma independiente de la geometría
de la red ferroviaria. Los modos de transporte son señales de
enriquecimiento; la presencia de alquiler de vehículos y hoteles define la
madurez comercial. Las categorías de modo de transporte relacionadas se
agrupan antes de asignar el nivel, para evitar que modos relacionados inflen
artificialmente una señal aparente de multimodalidad.

Los clústeres se distribuyen entre tres niveles. Un nivel de Hub regional
combina acceso multimodal con un ecosistema comercial completo. Un nivel de
Intercambiador de tránsito combina tránsito con al menos una señal comercial.
Un nivel más amplio de Nodo de tránsito es aquel donde el tránsito está
presente pero la oportunidad comercial aún está por confirmarse.

El enriquecimiento comercial se apoya en las principales cadenas de alquiler
de vehículos y hoteles activas en cada mercado, reflejadas en el conjunto de
datos actual.

### Filtro de grandes hubs

Los aeropuertos adyacentes a un gran clúster minorista PRO se excluyen como
probables grandes hubs comerciales. Los grandes aeropuertos internacionales
generan su propia gravedad minorista y no exhiben el patrón de estacionamiento
y tránsito que el arquetipo busca identificar; el filtro de adyacencia los
excluye.

### Mejoras previstas

Lo siguiente está previsto, no es capacidad actual:

- Datos de pasajeros aeroportuarios, destinados a sustituir el proxy de
  adyacencia actual por un clasificador basado directamente en el tráfico
- Un directorio de operadores de estacionamiento que cubra a los principales
  operadores activos en cada mercado

---

## Integración en el mapa

VWH y PKS están disponibles como capas superpuestas junto con la vista
principal de Centros Comerciales (PRO), de modo que un revisor puede ver los
candidatos de Franja Urbana y Área de Acceso junto con el mapa base de
clústeres minoristas. Los candidatos PKS se distinguen además como
integrados — cerca de un clúster PRO de Nivel 1 o Nivel 2 — o independientes,
conforme a la definición de Área de Acceso anterior.

## Véase también

- [[catchment-ranking-methodology|Metodología de clasificación de captación]] — el enunciado canónico de las compuertas de nivel PRO
- [[co-location-methodology|Metodología de co-ubicación]] — la prueba de composición de anclas que impulsa la asignación de niveles PRO
- [[co-location-ranking-system|Sistema de clasificación de co-ubicación]] — el índice de densidad comercial de cinco rangos que clasifica los clústeres PRO
- [[retail-brand-family-taxonomy|Taxonomía de familias de marcas minoristas]] — las clases de ancla referenciadas en todo el artículo
- [[about-regional-markets-system|Sistema de Inteligencia de Mercados Regionales]] — el conjunto de 400 mercados construido sobre datos de clústeres PRO
- [[atlas-top-400-north-america|Top 400 Mercados Regionales — Norteamérica]] — conjunto calificado de mercados PRO suburbano-regionales en NA
- [[atlas-top-400-europe|Top 400 Mercados Regionales — Europa]] — conjunto calificado de mercados PRO suburbano-regionales en EU
- [[od-catchment-methodology|Metodología de Bandas de Distancia]] — cómo se miden las zonas de demanda alrededor de cada centroide de clúster

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
