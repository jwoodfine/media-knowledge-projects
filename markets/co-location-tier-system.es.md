---
schema: foundry-doc-v1
title: "Sistema de niveles de co-ubicación"
slug: co-location-tier-system
category: markets
index_group: coverage-methodology
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: editorial
short_description: "La clasificación de cuatro niveles — Regional, Distrital, Local, Marginal — asignada a cada clúster de co-ubicación en la plataforma, las compuertas predicativas que la determinan, y cómo se aplica el sistema en los mercados de América del Norte y Europa."
paired_with: markets/co-location-tier-system.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

Cada clúster de co-ubicación que la plataforma clasifica lleva uno de cuatro niveles — **Regional**, **Distrital**, **Local** o **Marginal**. El nivel indica cuán fuertemente han convergido en ese nodo los compromisos de capital independientes, antes de que se adquiera cualquier terreno. Las anclas comerciales, la población de captación y la infraestructura cívica son las tres señales que convergen. Las etiquetas orientadas al mapa siguen la jerarquía de propiedades del Consejo Internacional de Centros Comerciales (ICSC); el historial completo de nomenclatura está en [[co-location-tier-nomenclature|nomenclatura de niveles]].

## Cómo se asigna un nivel

Un clúster obtiene su nivel al superar un conjunto de compuertas predicativas — pruebas de aprobado o reprobado, no una puntuación acumulada. Se aplican cuatro familias de compuertas.

**Composición.** Cada clúster se forma alrededor de un [[co-location-anchors|ancla principal]] de una de cuatro clases: Hipermercado (cadenas de mercancía general como Walmart, Target, Mercadona y Tesco), Estilo de Vida (minoristas de gran formato para el hogar — IKEA es la única cadena de esta clase), Ferretería (cadenas de mejoras para el hogar como Home Depot, Lowe's y Leroy Merlin) y Almacén (clubes de membresía como Costco, Sam's Club y Makro). Las clases presentes en un nodo determinan qué nivel puede alcanzar un clúster.

**Rango de captación.** La población de un clúster se clasifica frente a la de otros de su propio país, de modo que un nodo se juzga según las condiciones nacionales y no con un único criterio transfronterizo. Los niveles superiores exigen una posición nacional más alta.

**Presencia cívica.** Un hospital calificado debe encontrarse dentro del anillo cívico del clúster. Regional y Distrital requieren un hospital clasificado como regional o distrital; Local acepta cualquier clasificación hospitalaria.

**No superposición.** Los clústeres vecinos que se solapan de forma sustancial se comparan entre sí. Un clúster dominado por un vecino más fuerte se mantiene por debajo del nivel que su composición alcanzaría por sí sola, de modo que una misma localización comercial no se cuente dos veces.

## Los cuatro niveles

| Nivel | Qué requiere |
|---|---|
| **Regional** | Un hipermercado combinado con un ancla de almacén o de estilo de vida, población de captación en la banda nacional más alta, y un hospital regional dentro del anillo cívico. El nivel más alto. |
| **Distrital** | Un hipermercado combinado con ferretería o almacén, población de captación en una banda nacional alta, y acceso hospitalario dentro del anillo cívico. |
| **Local** | Un ancla de ferretería o almacén, población de captación por encima del punto medio nacional, y cualquier hospital dentro del anillo cívico. |
| **Marginal** | Existe co-ubicación comercial, pero el alcance de captación, la composición o el respaldo cívico no alcanzan el nivel Local. |

## Aplicación en América del Norte y Europa

El sistema de niveles se aplica de forma idéntica en ambos continentes; solo cambia la red de anclas. En América del Norte, Walmart Supercentre es el ancla principal dominante, combinada con Home Depot y Costco como anclas secundarias. En Europa, IKEA es el ancla principal en España, los países nórdicos, Italia y Polonia, combinada con Leroy Merlin y Makro.

| Mercado | Ancla principal | Índice detallado |
|---|---|---|
| Estados Unidos | Walmart Supercentre | [[atlas-united-states]] |
| Canadá | Walmart Supercentre | [[atlas-canada]] |
| México | Walmart Supercentre | [[atlas-co-location-index-mexico]] |
| España | IKEA | [[atlas-spain]] |
| Países Nórdicos | IKEA | [[atlas-co-location-index-nordics]] |
| Italia | IKEA | [[atlas-italy]] |
| Polonia | IKEA | [[atlas-poland]] |

Los recuentos de nivel actuales por país se publican en vivo en la plataforma GIS en lugar de repetirse aquí; una instantánea de wiki queda desactualizada entre ciclos de actualización de datos, mientras que la plataforma se actualiza en cada ejecución de procesamiento.

La ampliación del conjunto de datos cívicos terciarios — para llevar la cobertura de universidades y hospitales en México y Canadá a la misma madurez que en Estados Unidos — es un objetivo previsto para futuras iteraciones. [ni-51-102] [osc-sn-51-721]

## Procedencia
- **Verificación:** Las definiciones de nivel y las compuertas predicativas se confirmaron contra la metodología de puntuación actual de la plataforma GIS.
- **Divulgación prospectiva:** La ampliación del conjunto de datos cívicos terciarios para México y Canadá es un resultado previsto, etiquetado conforme a [ni-51-102].

## Ver también
*   [[co-location-methodology]]
*   [[co-location-tier-nomenclature]]
*   [[co-location-ranking-system]]

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Atribución-SinDerivadas 4.0 Internacional](https://creativecommons.org/licenses/by-nd/4.0/).*
