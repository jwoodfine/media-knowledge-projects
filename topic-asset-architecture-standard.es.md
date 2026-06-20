---
schema: foundry-doc-v1
title: "Estándar de Arquitectura de Activos"
slug: topic-asset-architecture-standard
aliases:
  - topic-asset-architecture-standard
category: governance
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-06
editor: pointsav-engineering
short_description: "Requisitos estructurales uniformes para los desarrollos Woodfine: construcción de concreto y acero, dimensionamiento previo a la adquisición y configuración estandarizada en toda la cartera."
paired_with: topic-asset-architecture-standard.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

Cada desarrollo de MCorp debe satisfacer una especificación estructural antes de que proceda la adquisición del terreno — construcción de hormigón y acero, placas de piso pre-dimensionadas, sin excepciones por sitio. El estándar elimina la negociación de diseño posterior a la adquisición y la variación presupuestaria que resulta de ella. Se aplica junto con las [[topic-zoning-acquisition-rules|reglas de adquisición por zonificación]] y el requisito de adyacencia de [[topic-co-location-anchors|anclas]], y su cumplimiento se registra en el tiempo mediante la [[topic-site-ledger-integration|integración del registro del sitio]].

## Configuración estructural

Cada activo apunta a una configuración de oficinas profesionales. La especificación central exige construcción de hormigón y acero — no estructura de madera ligera, no sistemas metálicos preingeniados. Esta decisión estructural se toma a nivel de política de cartera, no de proyecto. El razonamiento es la durabilidad del activo a largo plazo y las expectativas de arrendatarios de grado institucional.

## Dimensionamiento previo a la adquisición

Los límites de superficie se definen antes de que proceda cualquier adquisición de terreno. La envolvente dimensional — dimensiones de planta, área construible, ratios de aparcamiento — se calcula contra el contexto de co-ubicación de anclaje objetivo. Si un sitio no puede soportar la envolvente requerida dentro del área construible aprobada por zonificación, el sitio se rechaza antes de la compra.

## Eliminación de la variación de diseño

El efecto operacionalmente más significativo del estándar es que elimina las decisiones de diseño subjetivas del flujo de trabajo de adquisición y desarrollo. Un comité no puede negociar el sistema estructural, la planta o la configuración. Estas son resultados del estándar aplicado al sitio, no entradas de un equipo de diseño.

Esta disciplina mantiene el costo de desarrollo predecible entre mercados. Un activo de oficinas de hormigón y acero en un mercado se comporta, estructural y financieramente, como un activo de oficinas de hormigón y acero en otro.

## Véase también

- [[topic-co-location-anchors]] — requisito de adyacencia al ancla que se aplica junto con el estándar de arquitectura
- [[topic-zoning-acquisition-rules]] — verificación de zonificación que aplica antes de que proceda cualquier desarrollo
- [[topic-site-ledger-integration]] — cómo se registra el cumplimiento del estándar durante la construcción
- [Arquitectura de Tres Anillos](https://documentation.pointsav.com/architecture/three-ring-architecture) — el estándar de arquitectura del proveedor referenciado en este artículo

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
