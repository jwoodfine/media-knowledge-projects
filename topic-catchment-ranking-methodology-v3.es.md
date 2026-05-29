---
schema: foundry-doc-v1
title: "Metodología de Clasificación de Captación por Predicados Puros (V3)"
slug: topic-catchment-ranking-methodology-v3.es
category: governance
type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "La metodología V3 asigna cada clúster de co-localización a uno de cuatro niveles mediante compuertas de predicado binarias — composición, rango de captación nacional, clasificación cívica e independencia espacial — sustituyendo el sistema previo de puntuación compuesta introducido en Sprint 17 (mayo de 2026)."
paired_with: topic-catchment-ranking-methodology-v3.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

El sistema de niveles de [[topic-co-location-methodology|co-localización]] asigna cada clúster a uno de cuatro niveles — Regional, Distrital, Local o Marginal (etiquetados según la [[topic-co-location-tier-nomenclature|nomenclatura de niveles]]) — mediante compuertas de predicado binarias en lugar de una puntuación compuesta. Un clúster debe superar todas las compuertas del conjunto correspondiente a un nivel para calificar para ese nivel; los resultados parciales no se acumulan. Esta metodología describe la implementación V3 introducida en el Sprint 17 (mayo de 2026). Complementa el [[topic-co-location-ranking-system|sistema de clasificación determinista]] y toma sus insumos de área comercial de la [[topic-od-catchment-methodology|metodología de captación O-D]] y de las [[topic-trade-area-data-sources|fuentes de datos de áreas comerciales]].

## Por qué las compuertas de predicado reemplazan las puntuaciones compuestas

El sistema V2 anterior asignaba niveles sumando una puntuación base, un bono por recuento, un bono por diversidad, un término de profundidad cívica y una penalización por superposición. La puntuación resultante era internamente coherente, pero difícil de explicar: un clúster podía alcanzar el Nivel 2 mediante un bono por diversidad elevado, aun cuando le faltara la captación de población y la infraestructura cívica que el nivel pretendía señalar.

Las compuertas binarias hacen que los criterios de calificación sean explícitos e individualmente verificables. Un clúster Regional debe tener alcance poblacional a escala nacional, una composición de ancla específica, acceso hospitalario regional e independencia espacial respecto a clústeres más fuertes. Ninguno de estos requisitos se satisface mediante un indicador sustituto.

## Rangos de captación de población

La captación de población se calcula mediante una cuadrícula H3 en línea recta a resolución 7 (ancho de celda aproximado de 2,1 km), según la [[topic-od-catchment-methodology|metodología de captación O-D]]. Se definen dos zonas para cada clúster:

- **Zona primaria**: todas las celdas H3 dentro de 35 km del ancla del clúster
- **Zona secundaria**: todas las celdas H3 entre 35 km y 150 km del ancla del clúster

Los totales de población provienen de los rásteres WorldPop 2026 a 100 m, agregados a la resolución 7 de H3 (véase [[topic-trade-area-data-sources|fuentes de datos de áreas comerciales]]). Los clústeres se clasifican dentro de su país ISO en ocho ejes: población primaria, población secundaria, gasto primario en víveres, gasto secundario en víveres, gasto primario en ferretería, gasto secundario en ferretería, gasto primario en mayoreo y gasto secundario en mayoreo.

El rango se expresa como fracción: el rango 1 en un país con 500 clústeres produce un valor de 0,002; el rango 50, de 0,100. Los valores más bajos indican mayor alcance relativo dentro del país.

## Definición de las compuertas de nivel

### Nivel 1 — Regional

Un clúster califica como Regional si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Almacén (Costco, Sam's Club, Makro o equivalente) y un ancla de tipo Hipermercado (Walmart, Target, Mercadona, Tesco, Sainsbury's o equivalente); o contiene un ancla de tipo Estilo de Vida (IKEA) y un ancla de tipo Hipermercado.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país está en el 10% superior (valor de rango ≤ 0,10).
3. **Captación secundaria**: El rango de población secundaria del clúster dentro de su país está en el 20% superior (valor de rango ≤ 0,20).
4. **Cívico — hospital regional**: Al menos un hospital clasificado como "regional" está presente dentro del anillo cívico de 5 km alrededor del ancla del clúster.
5. **Independencia espacial**: La intersección sobre la unión (IoU) entre el disco de 3 km de este clúster y el disco de 3 km de cualquier clúster del mismo país con mayor rango de población primaria no supera 0,10.

### Nivel 2 — Distrital

Un clúster califica como Distrital si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Hipermercado y un ancla de tipo Ferretería (Home Depot, Lowe's, Leroy Merlin o equivalente) o un ancla de tipo Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país está en el 25% superior (valor de rango ≤ 0,25).
3. **Alcance de gasto**: El rango del clúster dentro de su país en al menos uno de los ejes — gasto en víveres, ferretería o mayoreo — está en el 25% superior (valor de rango ≤ 0,25).
4. **Cívico — hospital presente**: Al menos un hospital clasificado como "regional" o "distrital" está presente dentro del anillo cívico de 5 km.
5. **Independencia espacial**: La IoU entre el disco de 3 km de este clúster y el disco de 3 km de cualquier clúster Regional del mismo país no supera 0,25.

### Nivel 3 — Local

Un clúster califica como Local si se cumplen las tres condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Ferretería o Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país está en el 50% superior (valor de rango ≤ 0,50).
3. **Cívico — cualquier hospital**: Al menos un hospital de cualquier clasificación está presente dentro del anillo cívico de 5 km.

### Nivel 4 — Marginal

Un clúster que no califica para los niveles Regional, Distrital o Local se clasifica como Marginal. Un clúster Marginal puede contener co-tenencia comercial significativa; la clasificación indica que uno o más requisitos necesarios para Local o superior no se cumplieron.

## Medición de la superposición

La compuerta de independencia espacial utiliza la fórmula de forma cerrada de intersección sobre unión para dos círculos de radio igual:

```
área_lente = 2r² · arccos(d/2r) − (d/2) · √(4r² − d²)
IoU = área_lente / (2·π·r² − área_lente)
```

donde d es la distancia haversine entre centroides de clúster y r = 3,0 km.

## Resumen de umbrales

| Umbral | Símbolo | Valor |
|---|---|---|
| Captación primaria T1 | P10 | 10% superior dentro del país |
| Captación secundaria T1 | P20 | 20% superior dentro del país |
| Captación primaria / gasto T2 | P25 | 25% superior dentro del país |
| Captación primaria T3 | P50 | 50% superior dentro del país |
| Límite IoU T1 | — | ≤ 0,10 |
| Límite IoU T2 | — | ≤ 0,25 |
| Radio del anillo cívico | — | 5 km |
| Radio del disco IoU | — | 3 km |

## Véase también

- [[topic-co-location-tier-nomenclature]]
- [[topic-co-location-methodology]]
- [[topic-co-location-ranking-system]]
