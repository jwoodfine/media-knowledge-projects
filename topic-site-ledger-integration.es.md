---
schema: foundry-doc-v1
title: "Integración del Libro Contable del Sitio"
slug: topic-site-ledger-integration
aliases:
  - topic-site-ledger-integration
category: governance
type: reference
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-06
editor: pointsav-engineering
short_description: "Vínculo operacional que conecta cada sitio de construcción físico con un contenedor de archivo digital aislado, manteniendo registros de auditoría inmutables desde el inicio hasta la puesta en servicio."
paired_with: topic-site-ledger-integration.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

Cada sitio de desarrollo activo de Woodfine genera un registro de auditoría digital inmutable mantenido por la plataforma PointSav — el registro legal de hitos de construcción, resultados de inspecciones y variaciones de cronograma que los inversores y reguladores pueden verificar de forma independiente. Cada sitio se asigna a su propio archivo aislado; los eventos en el sitio físico generan registros que no pueden sobrescribirse después de ser ingresados. El libro contable registra el cumplimiento de la [[topic-asset-architecture-standard|Norma de Arquitectura del Activo]] desde el momento de la adquisición (regulada por las [[topic-zoning-acquisition-rules|reglas de adquisición por zonificación]]) hasta la puesta en servicio.

## El modelo de contenedor digital

Cada sitio recibe un contenedor de archivo independiente — no una base de datos compartida con otros sitios. El aislamiento es estructural: un evento de datos que afecte al archivo de un sitio no puede afectar al de otro. Esto refleja la arquitectura financiera de Tenencia Directa, donde cada activo es un vehículo legalmente aislado.

## Registro diario de progreso

Los gestores de sitio generan registros de progreso diarios que documentan hitos de construcción, entregas de materiales, resultados de inspecciones y variaciones de programación. Estos registros se comprometen al contenedor digital como archivos planos — registros de texto sin formato con entradas marcadas con fecha y hora. Una vez comprometidas, las entradas son inmutables. Un registro diario para una fecha determinada no puede sobrescribirse ni corregirse — las correcciones son nuevas entradas con una notación explícita de enmienda.

## Auditorías de construcción verificables

La acumulación de registros diarios a lo largo del período de construcción constituye un rastro de auditoría verificable. Un inversor, un organismo regulador o un futuro comprador puede reconstruir el historial de desarrollo a partir del libro contable sin depender del relato auto-informado del promotor. Esta transparencia es un resultado fiduciario del Mandato de Datos Fiduciarios — la obligación de mantener la propiedad matemática de los datos relevantes para los inversores se extiende a los registros de construcción de los activos mantenidos en la cartera de Tenencia Directa.

## Véase también

- [[topic-zoning-acquisition-rules]] — verificación previa a la adquisición que activa el libro contable
- [[topic-asset-architecture-standard]] — especificación estructural cuyo cumplimiento registra el libro contable

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
