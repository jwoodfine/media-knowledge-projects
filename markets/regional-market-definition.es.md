---
schema: foundry-doc-v1
title: "Definición de mercado regional"
slug: regional-market-definition
short_description: "Contenedores espaciales del mapa de inteligencia de ubicaciones — en qué difiere la cobertura de un Mercado Regional calificado, y por qué la cobertura por sí sola no es una afirmación de fortaleza de mercado."
category: markets
index_group: coverage-methodology
type: concept
content_type: topic
quality: complete
status: stable
audience: customer-woodfine
bcsc_class: public-disclosure-safe
language: es
language_protocol: TRANSLATE-ES
last_edited: 2026-09-07
editor: pointsav-engineering
paired_with: markets/regional-market-definition.md
cites: []
---

El mapa de inteligencia de ubicación de Woodfine distingue dos contenedores espaciales para un asentamiento con actividad de co-ubicación minorista. Un asentamiento entra en la **capa de cobertura** en el momento en que un clúster de co-ubicación cae dentro de su límite. Se convierte en **Mercado Regional** solo cuando sus clústeres superan las condiciones de composición de anclas de la plataforma. Un tercer contenedor, más amplio — el **Mercado Metro** — sitúa a cada Mercado Regional en su contexto metropolitano. La distinción importa porque la cobertura mide qué tan ampliamente se han observado las cadenas de ancla rastreadas por la plataforma; no mide dónde se concentra realmente la demanda minorista.

## Asentamiento con presencia de co-ubicación

Un asentamiento con presencia de co-ubicación es cualquier polígono municipal incorporado o CSD que contenga al menos un clúster de co-ubicación, asignado mediante coincidencia de punto en polígono contra los límites TIGER 2023 en Estados Unidos y GISCO LAU 2021 más GADM GBR en la Unión Europea y el Reino Unido. Según la ejecución de procesamiento más reciente, **12.689 asentamientos en 24 países** llevan esta bandera de cobertura; **12.578** de ellos — cerca del 99% — llevan la bandera de geocodificación de alta confianza.

Esto es una estadística de cobertura. Registra qué tan ampliamente se han observado las cadenas de ancla rastreadas por la plataforma, no dónde se concentra la demanda minorista: un pueblo con una única co-ubicación calificante y un área metropolitana con decenas superan este umbral en los mismos términos. La confianza de geocodificación mide la precisión de la asignación de límites, no la fortaleza del mercado subyacente, y no se trata como señal de calidad en ninguna parte de la plataforma.

## Mercado Regional

Un Mercado Regional es un asentamiento cuyos clústeres de co-ubicación superan las condiciones de composición de anclas de la plataforma — la misma lógica de composición aplicada a los clústeres individuales bajo el [[co-location-tier-system|sistema de niveles]], evaluada a nivel de asentamiento. Cada continente extrae su conjunto calificado de todo asentamiento que supera las condiciones — 1.121 asentamientos en tres países en América del Norte, 650 en quince países en Europa. [[about-regional-markets-system|Sistema de Inteligencia de Mercados Regionales]] documenta el método de calificación completo.

La distinción frente a la cobertura bruta es deliberada: un asentamiento de ancla única supera el umbral de cobertura sin llevar la diversidad de anclas que requiere un Mercado Regional. La condición de composición, no el conteo de asentamientos, es lo que determina si un nombre aparece en las tablas de Mercados Regionales de la plataforma.

## El Top 400 — un conjunto calificado, no una clasificación

La publicación está limitada a 400 mercados por continente, presentados en un orden fijo y alfabético que no constituye una posición declarada. Todo mercado publicado ya superó las condiciones de composición de anclas descritas arriba. Donde el conjunto calificado de un continente supera los 400, se publican los mercados con la composición de anclas más fuerte — 400 de 1.121 en América del Norte, 400 de 650 en Europa. Existe una puntuación compuesta de uso interno que apoya esa selección, pero no se publica y no incide en cómo se describe un mercado en este wiki. Las listas publicadas están en [[atlas-top-400-north-america]] y [[atlas-top-400-europe]].

## Mercado Metro

El Mercado Metro es un contenedor contextual más amplio: un área metropolitana principal en una lista de referencia publicada (MSA/CBSA de EE. UU., AMC canadiense). Un Mercado Regional se anida dentro de como máximo un Mercado Metro y nunca se disuelve en él. El Mercado Metro es solo contexto — nunca es el nivel de zoom de co-ubicación o anillo, ni un nivel de ruta de navegación por sí mismo.

## Resolución de límites

La resolución de límites sigue una sola regla sin excepciones por asentamiento. Una co-ubicación cerca de Sherwood Park, Alberta, se resuelve a su polígono contenedor, el condado de Strathcona, en los mismos términos que cualquier otro asentamiento.

## Conteos

| Objeto | Definición | Conteo |
|---|---|---|
| Asentamientos con presencia de co-ubicación | Al menos un clúster de co-ubicación dentro del polígono del asentamiento | 12.689 en 24 países |
| Mercados Regionales — América del Norte | Superaron las condiciones de composición de anclas; publicados como los 400 más fuertes de un conjunto calificado de 1.121 mercados | 400 |
| Mercados Regionales — Europa | Superaron las condiciones de composición de anclas; publicados como los 400 más fuertes de un conjunto calificado de 650 mercados | 400 |

*Cifras de Mercados Regionales de la compilación del conjunto de datos del 2026-08-07. Cifras de la capa de cobertura (asentamientos con presencia de co-ubicación) de la ejecución de procesamiento del 2026-08-06.*

## Véase también

- [[about-regional-markets-system|Sistema de Inteligencia de Mercados Regionales]] — el conjunto de datos completo, el sistema de niveles y el método de calificación de los que parten las definiciones de este artículo
- [[catchment-ranking-methodology]] — cómo se calculan los niveles y el puntaje de fortaleza planeado para cada co-ubicación dentro de un Mercado Regional
- [[trade-area-methodology]] — cómo se define el área de atracción para cada co-ubicación
- [[spend-population-provenance]] — la cadena de estimación para las cifras de población y gasto
