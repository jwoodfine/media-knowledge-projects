---
schema: foundry-doc-v1
title: "Zonificación climática a nivel de Tile"
slug: tile-level-climate-zoning
category: building-design
index_group: site-and-building-standards
type: topic
content_type: topic
quality: pre-build
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-08
editor: pointsav-engineering
short_description: "El estándar de granularidad de servicios del edificio de Woodfine: cada Tile tiene su propio termostato, con Special Tiles que reciben una zona climática autocontrolada, en lugar de zonificar a nivel de espacio arrendable individual o de piso completo."
paired_with: building-design/tile-level-climate-zoning.md
---

Woodfine dimensiona el control climático según el [[key-plans-and-tiles|Tile]], no según el espacio arrendable individual ni según el piso completo: cada Tile tiene su propio termostato, y cada Key Plan que comparte ese Tile comparte también su termostato. La granularidad se fija una vez que el Tile está definido. Por eso [[design-sequence-priority|Servicios del Edificio se superpone solo después del Plan de Arrendamiento]]: una zona climática a nivel de Tile solo puede trazarse correctamente una vez que los Tiles mismos son conocidos.

## Por qué el Tile es la unidad correcta

Un [[key-plans-and-tiles|Tile]] se construye a partir de la misma geometría real de mobiliario y circulación que los Key Plans que contiene, de modo que hacer coincidir la zona climática con el Tile significa que un Colaborador de Servicios del Edificio zonifica contra un límite que ya existe en la geometría de arrendamiento, en lugar de inventar un límite de zonificación separado que luego habría que conciliar con ella. Los Special Tiles son el único caso dimensionado de otra manera — configuraciones más pequeñas y de propósito específico cerca del núcleo del edificio y los vestíbulos de ascensores, dimensionadas según lo que ese lugar realmente requiere, no según el módulo estándar de Tile. Dado que un Special Tile es un ajuste completo y autocontenido a su propia escala, recibe su propia zona climática autocontrolada en lugar de compartir la zona de tamaño estándar de Tile.

## Qué reemplaza

El estándar reemplaza el control ambiental a nivel de espacio arrendable individual como opción predeterminada de Woodfine. El control a nivel de inquilino suena como una mejor comodidad, y Woodfine lo puso a prueba. Un amplio grupo de Colaboradores de Servicios del Edificio que trabajan en Canadá, Estados Unidos, el Reino Unido y Europa continental reportó de manera independiente el mismo hallazgo. Los sistemas construidos para dar control individual a los inquilinos generaron problemas significativos de mantenimiento y confiabilidad, y las fallas de servicio resultantes crearon una insatisfacción real entre los inquilinos y sus Usuarios. El control ambiental propio de Woodfine se administra en cambio de forma centralizada, como parte de la administración de la propiedad. La premisa es que un sistema optimizado centralmente supera a un mosaico de sistemas administrados individualmente, y es lo que los inquilinos de un edificio Clase A deberían esperar por defecto.

## Dónde un inquilino todavía puede obtener más control

El comportamiento predeterminado no es absoluto. Un inquilino que arrienda una Corporate Office completa — aproximadamente del tamaño de un Tile completo, un octavo de piso como mínimo — alcanza la escala en la que el control ambiental individual se vuelve práctico de ofrecer. Un inquilino que desea distribución más allá de eso puede instalar y pagar sus propios sistemas de mayor gama, siempre que la instalación no interfiera con los sistemas compartidos del edificio. Un inquilino más pequeño que comparte un Tile con otros espacios arrendables no tiene esa opción y en su lugar escala un problema climático a través del canal de servicio para inquilinos del edificio o directamente con el administrador del edificio en el sitio.

## Consecuencia para la experiencia del inquilino y el costo de mantenimiento

El límite de zonificación se fija en el Tile en lugar de negociarse espacio por espacio. Por eso el estándar evita la falla específica que Woodfine identificó en los sistemas de control individual: un servicio poco confiable que genera llamadas de mantenimiento repetidas y una frustración creciente de los inquilinos. Dimensionar la zona según el Tile también significa que el estándar viaja sin cambios junto con la [[fixed-floor-plates|Placa de Piso Fija]] a cada despliegue de la misma clase de prototipo, en lugar de rediseñarse edificio por edificio.

## Véase también

- [[key-plans-and-tiles]] — la unidad de Tile contra la que zonifica este estándar
- [[design-sequence-priority]] — por qué la zonificación climática se fija solo después del Plan de Arrendamiento
- [[fixed-floor-plates]] — la disciplina de placa de piso con la que viaja este estándar
- [[geometry-of-sustainability]] — el enfoque basado en estándares regulatorios para el desempeño operativo a nivel de edificio
