---
schema: foundry-doc-v1
title: "Registro de Monitoreo de Sitios de Desarrollo"
slug: development-site-monitoring-register
category: gis
type: topic
content_type: topic
quality: complete
short_description: "El sistema de seguimiento pasivo que mantiene los sitios de co-ubicación calificados retirados del pipeline activo de Sitios de Desarrollo debido a la no disponibilidad de terreno adyacente — mantenido como un inventario puntuado actualizado en el mismo ciclo anual o bienal que los datos de ventas por pie cuadrado del Objetivo Primario, con criterios de re-entrada documentados cuando cambian las condiciones del terreno."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: development-site-monitoring-register.md
cites: []
---

El **Registro de Monitoreo de Sitios de Desarrollo** mantiene las ubicaciones de Objetivos Primarios que logran una puntuación de clúster de co-ubicación calificada pero no pueden ingresar al pipeline activo de Sitios de Desarrollo porque el terreno adyacente no está disponible actualmente para su adquisición. El registro es un inventario puntuado — no una lista inactiva o archivada — actualizado en el mismo ciclo anual o bienal que los datos de ventas por pie cuadrado del Objetivo Primario. Los sitios en el registro conservan su puntuación de clúster y perfil demográfico. Vuelven a ingresar al pipeline activo cuando la disponibilidad de terreno adyacente es confirmada a través del proceso de evaluación de profesionales inmobiliarios.

## Por Qué la Disponibilidad de Terreno es una Puerta Separada

Un Objetivo Primario que logra una puntuación de clúster calificante (T1 Valid ≥ 150 en el sistema de puntuación de cinco grados) ha demostrado las condiciones de co-ubicación que Woodfine requiere: Home Depot y Costco dentro del umbral de radio primario, y presencia de Objetivo Terciario calificante dentro del umbral de radio terciario. La puntuación del clúster verifica que el entorno comercial es correcto para un Woodfine Building.

La disponibilidad de terreno adyacente es una condición separada. Un sitio puede tener la configuración de co-ubicación correcta y el perfil demográfico correcto, pero carecer de una parcela adyacente al Objetivo Primario disponible para adquisición en el momento de la evaluación. Esto es particularmente común en los Mercados Regionales donde la huella del Centro Comercial ha sido completamente desarrollada y las parcelas circundantes están ocupadas por edificios existentes cuyos propietarios no son vendedores actuales.

El Registro de Monitoreo preserva la inversión realizada en la puntuación y elaboración de perfiles de estos sitios en lugar de descartarlos del conjunto de datos. Las características de clúster calificantes del sitio no se espera que cambien — el Objetivo Primario es típicamente un minorista de gran formato con un contrato de arrendamiento a largo plazo y capital sustancial invertido en el sitio — y la probabilidad de que el terreno adyacente eventualmente esté disponible es una función de la rotación inmobiliaria comercial normal en el área circundante.

## Cadencia de Actualización y Mantenimiento de Puntuación

Los sitios del Registro de Monitoreo se revisan en el mismo calendario que el pipeline activo: anualmente o bienalmente cuando se actualizan los datos de ventas por pie cuadrado del Objetivo Primario. En cada ciclo de actualización, los profesionales inmobiliarios comprometidos por Woodfine en el mercado relevante evalúan la disponibilidad de terreno para cada sitio del Registro de Monitoreo en su área. Un sitio donde el terreno adyacente ha quedado disponible es escalado desde el Registro de Monitoreo al pipeline activo y avanza a la etapa del Informe de Resumen de Transacción.

La puntuación del clúster para cada sitio del Registro de Monitoreo también se recalcula en cada ciclo de actualización, utilizando la misma metodología aplicada a toda la población de Objetivos Primarios. Un sitio que era T2 Hub en la evaluación inicial puede ser actualizado a T3 Apex si las ventas por pie cuadrado del Objetivo Primario han mejorado en relación con el promedio de la cadena, o si un Objetivo Terciario ha abierto dentro del umbral de radio relevante desde la fecha de puntuación inicial.

## Criterios de Re-Entrada

Un sitio del Registro de Monitoreo vuelve a ingresar al pipeline activo de Sitios de Desarrollo cuando se satisfacen dos condiciones:

1. **Disponibilidad de terreno confirmada.** El profesional inmobiliario comprometido en el mercado identifica una parcela adyacente al Objetivo Primario — definida como contigua o inmediatamente accesible al sitio del Centro Comercial — disponible para adquisición o arrendamiento de terreno en términos consistentes con los parámetros de suscripción de la Direct-Hold Solution aplicable.

2. **Puntuación del clúster mantenida o mejorada.** La puntuación del clúster del sitio en el momento de la evaluación de re-entrada debe estar en o por encima del umbral T1 Valid (≥ 150). Un sitio que ha caído por debajo del umbral calificante — por ejemplo, porque un Objetivo Secundario ha cerrado — no vuelve a ingresar al pipeline activo hasta que se restauren las condiciones de co-ubicación calificantes.

Los sitios que satisfacen ambas condiciones proceden a la preparación del Informe de Resumen de Transacción y al proceso de revisión de los Directores Independientes. El período de monitoreo no tiene una duración máxima definida: un sitio permanece en el registro hasta que cumpla ambas condiciones, o hasta que las condiciones de co-ubicación se deterioren permanentemente, momento en el cual el sitio se elimina del conjunto de datos por completo.

## Relación con los Conteos del Pipeline

Los conteos de desarrollo requeridos para cada Direct-Hold Solution — 26 sitios para Canadá, 52 para Estados Unidos, 26 para México — se basan únicamente en sitios del pipeline activo. Los sitios del Registro de Monitoreo no se contabilizan para el total de desarrollo requerido. La proporción mínima de preselección de 2:1 se aplica a los sitios del pipeline activo; el Registro de Monitoreo es una reserva de candidatos futuros del pipeline, no un componente del cálculo actual de la preselección.
