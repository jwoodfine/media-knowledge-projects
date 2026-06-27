---
schema: foundry-doc-v1
title: "Planos Maestros y Módulos"
slug: key-plans-and-tiles
category: co-location
type: topic
content_type: topic
quality: pre-build
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-06-26
editor: pointsav-engineering
short_description: "Un sistema de planificación espacial geométrico y autosimilar derivado de la geometría de equipos y circulación de los inquilinos, utilizado para determinar las dimensiones de las placas de piso fijas."
paired_with: co-location/key-plans-and-tiles.md
---

Planos Maestros y Módulos es la metodología de planificación espacial que traduce los requisitos de equipos y circulación de los ocupantes profesionales en unidades geométricas estandarizadas, las cuales se agregan para producir las dimensiones de la [[fixed-floor-plates|placa de piso fija]]. El sistema es geométrico y autosimilar: una unidad de módulo base — derivada de la huella física de la configuración de equipos de trabajo, la disposición del mobiliario y la ruta de circulación mínima — genera la gama completa de configuraciones de placa de piso mediante repetición y agregación, en lugar de diseño personalizado.

## De la geometría del equipo al módulo

El módulo base se deriva midiendo la geometría física de la configuración de equipos principal para cada categoría de [[mix-of-use|inquilino profesional]]:

- La huella de la estación de trabajo o área de tratamiento
- La holgura de circulación requerida en cada lado (típicamente regida por el mínimo de 3 pies de la Ley de Circulación Alemana o equivalente)
- La adyacencia secundaria — archivo, almacenamiento o equipos — que debe estar dentro de la zona inmediata de la estación de trabajo

Esta medición produce una unidad rectangular de dimensiones definidas. El módulo es la unidad espacial autónoma más pequeña que puede acomodar la geometría del equipo más la circulación requerida. Toda la planificación espacial posterior se realiza agregando módulos, no diseñando desde cero.

## El carácter autosimilar y aperiódico

Los Planos Maestros son geométricos, autosimilares y aperiódicos — el módulo se repite para llenar un área de placa de piso, pero la repetición produce un patrón no periódico. Esto significa que no dos módulos adyacentes tienen orientación idéntica con respecto a todos sus vecinos; la geometría de la placa de piso evita la monotonía de la repetición de cuadrícula ortogonal mientras permanece completamente derivable del módulo base.

Esta propiedad aperiódica tiene consecuencias prácticas para la flexibilidad espacial. Un inquilino que requiere una configuración de caso de uso diferente — una disposición de mesada de laboratorio versus una sala de tratamiento médico versus un grupo de estaciones de trabajo empresariales — puede acomodarse reorientando los módulos dentro del límite de la placa, no reconfigurando elementos estructurales.

## Módulos y subdivisiones de placa de piso

La unidad de módulo define el módulo mínimo arrendable. Las subdivisiones de la placa de piso — 1/8, 1/4, 1/2, 3/4 y piso completo — son cada una múltiplos de la unidad de módulo: el límite de una subdivisión cae en un límite de módulo, no en un punto arbitrario de la placa de piso. Esto garantiza que cualquier subdivisión de la placa siga siendo un espacio geométricamente coherente y listo para equipos, sin fragmentos residuales.

Los límites de subdivisión están fijos en la cuadrícula estructural (determinan dónde se pueden colocar los muros divisorios) antes de que el edificio sea arrendado. Un inquilino prospectivo selecciona de un conjunto definido de configuraciones espaciales geométricamente completas, sin solicitar una disposición de partición personalizada.

## Aplicación al diseño de prototipos

El proceso de derivación de Planos Maestros y Módulos se ejecuta una vez por clase de prototipo. El resultado — las dimensiones del módulo base y las reglas de agregación — se fija entonces para ese prototipo. Cuando se emprende un nuevo desarrollo de la misma clase de prototipo, la placa de piso no se rediseña; se reproduce a partir de los parámetros fijos del módulo.

Esto significa que los estándares de equipos y circulación integrados en el módulo — requisitos de proximidad a la iluminación, holguras de circulación, mínimos de adyacencia — se transmiten a cada desarrollo de la clase de prototipo sin necesidad de nueva derivación. El módulo es la especificación operativa del espacio útil del edificio, expresada como geometría en lugar de texto.
