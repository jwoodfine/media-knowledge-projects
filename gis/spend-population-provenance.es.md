---
schema: foundry-doc-v1
title: "Estimación de gasto y población: procedencia y supuestos"
slug: spend-population-provenance
category: gis
index_group: data-overview-and-sources
type: concept
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "Cadena de procedencia de las estimaciones de población y gasto — Kontur Population, agregación H3 y multiplicadores per cápita, con sus debilidades declaradas."
paired_with: gis/spend-population-provenance.md
cites: []
---

El mapa de inteligencia de ubicación de Woodfine presenta dos superficies demográficas sintetizadas para cada clúster de co-ubicación: una población de cuenca y un gasto minorista anual estimado. Ambas son entradas de grado decisional — un analista de selección de sitios o un asignador de capital las leerá como mediciones. No son mediciones. Son estimaciones de modelos en capas construidas sobre datos abiertos. Este artículo documenta exactamente cómo se producen esas dos superficies, qué asumen, dónde son más débiles y cómo se comunica — y aún no se comunica — su incertidumbre.

## La cadena de estimación

La cifra de gasto mostrada en un clúster es la salida de tres pasos de modelado secuenciales. Ningún error introducido en cada paso se propaga actualmente hacia adelante al valor mostrado.

### Paso 1 — Población: Kontur Population, nativa de H3

La población se origina de **Kontur Population** (CC BY 4.0), entregada por país en **resolución 8 de H3** — una rejilla más fina que el nivel de resolución 7 al que finalmente se agregan las cuencas. Dado que los valores de población de Kontur ya están vinculados a la geometría hexagonal desde el origen, no existe un paso de reproyección de ráster a hexágono ni un modelo de redistribución dasimétrica en esta etapa de la cadena; los supuestos de modelado que producen las propias cifras de resolución 8 de Kontur son de Kontur, no de esta canalización, y no están documentados de forma independiente aquí.

### Paso 2 — Agregación a la resolución 7 de H3

Cada celda de resolución 8 se resuelve a su **hexágono padre de resolución 7** (área promedio aproximadamente 5,16 km²), y los valores de población se suman entre todas las celdas hijas de resolución 8 que comparten ese padre. La población de la cuenca es la suma de las poblaciones de las celdas de resolución 7 cuyos centroides caen dentro de los anillos de distancia de un clúster.

### Paso 3 — Gasto: multiplicador per cápita

El gasto anual estimado es **población × un multiplicador de gasto per cápita**, aplicado por país y categoría minorista. Los multiplicadores son proxies derivados de encuestas nacionales de gastos de los hogares: BLS Consumer Expenditure Survey para EE. UU., Statistics Canada Household Expenditures para Canadá, Eurostat Household Budget Survey para los países miembros de la UE, e INEGI para México.

### El supuesto per cápita uniforme

La simplificación más consecuente es: **a cada residente de un país se le asigna el mismo gasto per cápita, independientemente de dónde viva.** Un hogar en el centro de Londres y un hogar en una ciudad de mercado galesa reciben el multiplicador de alimentos idéntico. El modelo no tiene variación de ingresos, edad, tamaño del hogar ni costo de vida por debajo del nivel nacional.

Este supuesto es defendible como línea base — es transparente, requiere solo una encuesta autorizada por país y no pretende una granularidad que los datos de entrada no pueden sostener. Pero falla de maneras predecibles:

- Las áreas metropolitanas de altos ingresos quedan sistemáticamente subestimadas. Un clúster en una cuenca pudiente lleva el multiplicador promedio nacional y por lo tanto reporta menos gasto del que el área realmente genera.
- Las regiones de menores ingresos quedan sistemáticamente sobreestimadas por el mismo mecanismo.
- El error está correlacionado espacialmente, no es aleatorio. Como sigue el gradiente de ingreso local, no se cancela dentro de una cuenca; sesga el total de toda el área comercial en una sola dirección.

Una futura versión de la canalización tiene previsto variar el multiplicador a nivel subnacional usando datos de ingreso local — ingreso medio del hogar por sección censal de la ACS de EE. UU., ingreso censal de Statistics Canada, ingreso regional de Eurostat a nivel NUTS-2/NUTS-3 — reemplazando la constante nacional plana. Hasta que eso se implemente, el supuesto uniforme se mantiene y se declara en el modal de Metodología.

### Riesgo de falsa precisión

Cada paso arriba tiene su propio error, y se acumulan. La canalización actual no lleva ningún término de error a través de ningún paso. El gasto se muestra redondeado a una banda que el modelo puede defender — por ejemplo "~$150M de gasto anual en alimentos" o un rango — y etiquetado como estimado.

### El problema de la unidad areal modificable

Ambas superficies se agregan a la cuadrícula de resolución 7 de H3 antes de que se tomen las sumas de la cuenca. El problema de la unidad areal modificable (MAUP) es el resultado bien establecido de que las estadísticas calculadas sobre unidades areales cambian cuando cambia el tamaño o el límite de la unidad. Dos consecuencias para este mapa:

- **Efecto de escala.** Consolidar las celdas de resolución 8 de Kontur en el hexágono de resolución 7, de aproximadamente 5,16 km², suaviza la superficie de población. Una resolución de destino diferente produciría totales de cuenca distintos para los mismos anillos, porque la retícula hexagonal intersecta los anillos de distancia de manera diferente en cada resolución.
- **Efecto de borde.** Un anillo de distancia corta los hexágonos en su límite. Una celda se cuenta como totalmente dentro o totalmente fuera según su centroide, de modo que el total de la cuenca es sensible a exactamente cómo cae la retícula de hexágonos respecto al anillo.

MAUP no es un defecto por corregir; es una propiedad inherente de cualquier agregación areal. La obligación es reconocerlo en el modal de Metodología y evitar sobreinterpretar pequeñas diferencias entre clústeres. La magnitud del efecto MAUP a la resolución 7 para los anillos de distancia en uso aún no se ha cuantificado; un barrido de sensibilidad entre las resoluciones 6, 7 y 8 es una brecha documentada.

## Confianza y cómo se muestra

La canalización ya calcula una **bandera de confianza** por mercado en `regional-markets.json`. Esta bandera es una función de la calidad de la resolución del nombre regional, no de la calidad de ingestión de datos POI o censales. Se degrada específicamente donde el proceso de resolución de nombres recurre a un nombre de límite administrativo en lugar de resolver un nombre de lugar coloquial a nivel de asentamiento. En la compilación del 2026-05-22, 2.942 de 2.986 objetos del Mercado Regional llevaban la bandera de alta confianza. La cobertura ha crecido sustancialmente desde entonces. Según la ejecución de procesamiento completa más reciente (2026-08-06), `regional-markets.json` en vivo lleva 12.689 objetos del Mercado Regional en 24 países. De ellos, 12.578 — cerca del 99% — llevan la bandera de alta confianza. La lógica de resolución no ha cambiado; el crecimiento refleja la expansión del conjunto de datos, no un cambio de regla. A pesar de esto, la bandera aún no se representa en ningún lugar — el mapa dibuja cada clúster con opacidad completa y un marcador idéntico.

La intención cartográfica es hacer de la confianza un canal visual en el punto del nivel:

- **Opacidad** — clústeres de menor confianza representados con opacidad de relleno reducida.
- **Marcadores huecos frente a rellenos** — un punto hueco para clústeres de menor confianza y un punto relleno para los de mayor confianza.

## Registro de fuentes

La línea de procedencia en el mapa y el modal de Datos / Metodología derivan ambos de este
registro.

### Línea de procedencia en el mapa

Una línea persistente en la superficie del mapa, con la forma:

> Datos: Kontur Population CC-BY, OSM — actualizado [mes de compilación] · Metodología ⓘ

La atribución de OpenStreetMap es una obligación de licencia bajo ODbL y permanece presente
por separado de la línea de procedencia.

### Fuentes de datos

| Fuente | Rol | Vigencia | Licencia |
|---|---|---|---|
| Kontur Population | Población cuadriculada nativa de H3, resolución 8 — Paso 1 de la cadena de gasto | Versión por país de 2023 | CC BY 4.0 |
| OpenStreetMap | Ubicaciones de puntos de interés minoristas y cívicos que definen los clústeres | Actualización continua; instantánea por compilación | ODbL 1.0 — © colaboradores de OpenStreetMap |
| Overture Maps — Places | Tema global de puntos de interés para la resolución de anclas | Versión 2026 | CDLA-Permissive-2.0 — © Overture Maps Foundation |
| Overture Maps — Addresses | Relleno de direcciones postales para registros de POI sin dirección | Versión 2026-04-15.0 | ODbL 1.0 — © colaboradores de Overture Maps Foundation |
| BLS Consumer Expenditure Survey | Proxy del multiplicador de gasto per cápita de EE. UU. | Última publicada | Datos públicos federales de EE. UU. |
| Statistics Canada — Household Expenditures | Proxy del multiplicador de gasto per cápita de Canadá | Última encuesta | Licencia Abierta de StatCan — adaptado de datos de Statistics Canada; no constituye un aval |
| Eurostat — Household Budget Survey | Proxy del multiplicador de gasto per cápita de la UE | Última HBS | CC BY 4.0 — © Unión Europea, 1995–2026 |
| INEGI | Proxy de gasto y registro empresarial de México | Última | Términos de Uso Libre de INEGI |

### Países cubiertos

La capa de población cubre Estados Unidos, Canadá, México, España, Francia, Alemania, Gran
Bretaña, Italia, Países Bajos, Austria, Polonia, Grecia y Portugal — 13 países en la versión
actual de la canalización. Es un subconjunto de la huella de co-ubicación más amplia de la
plataforma, que abarca 24 países según la ejecución de procesamiento completa más reciente
(2026-08-06). Véase [[co-location-intelligence-overview]] para la cobertura completa por país.

**Discrepancia abierta, no resuelta aquí:** la tabla de multiplicadores de gasto per cápita
más abajo lleva Dinamarca e Islandia en lugar de España e Italia — un conjunto de 13 países
distinto al de la propia cobertura de la capa de población anterior. Si los multiplicadores
de gasto realmente aplican a un conjunto de países diferente (por ejemplo, una fuente de
encuesta de hogares separada con su propia cobertura) o si la tabla simplemente está
desactualizada no lo establece este artículo; se señala para el responsable de la
canalización en lugar de reconciliarse silenciosamente.

### Multiplicadores de gasto per cápita anual

Los multiplicadores son proxies de gasto per cápita anual expresados en moneda local. Son
entradas del Paso 3 y no están normalizados por tipo de cambio.

| País | Alimentos | Ferretería | Mayorista | Moneda |
|---|---|---|---|---|
| EE. UU. | $3.500 | $1.200 | $1.500 | USD |
| Canadá | C$3.200 | C$1.100 | C$1.300 | CAD |
| México | MX$18.000 | MX$3.500 | MX$2.500 | MXN |
| Gran Bretaña | £2.800 | £850 | £900 | GBP |
| Alemania | €2.900 | €950 | €1.000 | EUR |
| Francia | €3.100 | €900 | €1.000 | EUR |
| Países Bajos | €2.700 | €1.000 | €1.100 | EUR |
| Austria | €3.000 | €950 | €1.000 | EUR |
| Portugal | €2.400 | €600 | €700 | EUR |
| Grecia | €2.200 | €500 | €600 | EUR |
| Dinamarca | €3.500\* | €1.200\* | €1.100\* | DKK\* |
| Islandia | €4.000\* | €1.500\* | €1.500\* | ISK\* |
| Polonia | PLN 8.000 | PLN 2.000 | PLN 2.500 | PLN |

**Nota de moneda.** Dado que los multiplicadores están en moneda local y no están normalizados por tipo de cambio, las comparaciones de gasto entre países no son directamente significativas.

\* Dinamarca e Islandia no son miembros de la eurozona; sus multiplicadores se muestran aquí todavía denominados en euros, pendientes de re-derivarse en DKK e ISK, y no son comparables aún con las cifras de la eurozona anteriores.

## Cómo leer una cifra de gasto o población

1. **La población y el gasto son estimaciones modeladas, no recuentos.**
2. **El gasto asume que todos en un país gastan lo mismo por persona.** Los tramos pudientes están subestimados; los de menores ingresos están sobreestimados.
3. **Las cifras se redondean a propósito.** Un número redondo señala una estimación.
4. **Un punto tenue o hueco significa menor confianza,** no un nivel inferior.
5. **Las pequeñas diferencias entre clústeres pueden ser artefactos de la cuadrícula** (MAUP), no diferencias reales.
6. **El gasto es comparable dentro de un país, no entre monedas** hasta que se implemente la normalización de tipos de cambio.

## Resumen de estado

| Elemento | Estado |
|---|---|
| Superficie de población Kontur → resolución 7 de H3 | Implementado |
| Multiplicadores de gasto per cápita (13 países) | Implementado |
| Bandera de confianza en `regional-markets.json` | Calculada; aún no representada |
| Línea de procedencia y vigencia en el mapa | Planeado |
| Modal de Datos / Metodología con registro de fuentes completo y advertencias | Planeado |
| Confianza representada en los puntos de nivel (opacidad o marcador hueco) | Planeado |
| Propagación de error por estimación y bandas ± | Planeado |
| Multiplicadores de gasto que varían por ingreso subnacional | Planeado |
| Barrido de sensibilidad MAUP (resoluciones 6, 7, 8) | Planeado — brecha, aún no cuantificada |
| Normalización de tipo de cambio para gasto entre países | Pregunta abierta |

Todos los elementos prospectivos anteriores se declaran como planeados o previstos; describen
la dirección prevista de la canalización, no capacidades actualmente activas en
gis.woodfinegroup.com.

## Véase también

- [[trade-area-methodology]] — cómo se define el polígono sobre el cual se suman la población y el gasto
- [[catchment-ranking-methodology]] — cómo la cifra de gasto alimenta el puntaje de fortaleza planeado
- [[trade-area-data-sources]] — las fuentes de datos de población y gasto y la tabla de multiplicadores per cápita
