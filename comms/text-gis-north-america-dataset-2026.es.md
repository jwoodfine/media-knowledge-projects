---
schema: foundry-doc-v1
title: "Conjunto de Datos GIS América del Norte — Estado del Pipeline de Sitios (2026)"
slug: text-gis-north-america-dataset-2026
short_description: "Comunicación interna para clientes sobre el estado del conjunto de datos de co-ubicación de América del Norte — conteos actuales de clústeres puntuados por jurisdicción, requisitos de preselección del pipeline activo y el enfoque de calibración del conjunto de datos aplicado cuando la concentración de Clústeres de Quinto Grado supera el 10% de la población de Objetivos Primarios."
category: comms
type: release-text
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: text-gis-north-america-dataset-2026.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

**Para uso interno — Comunicaciones con clientes Woodfine**

---

El conjunto de datos de co-ubicación de América del Norte se mantiene como tres poblaciones puntuadas separadas — Canadá, Estados Unidos y México — aplicando cada una la metodología de clústeres de cinco grados a la red de Walmart Supercentre en la jurisdicción aplicable. El grado de clúster y la puntuación de nivel (T3 Apex ≥ 700, T2 Hub ≥ 450, T1 Valid ≥ 150) se determinan mediante los umbrales de co-ocurrencia estándar: radio de 1,0 km Primario-Secundario, radio de 5,0 km Terciario.

---

**Requisitos del pipeline por jurisdicción:**

| Jurisdicción | Direct-Hold Solution | Sitios requeridos (capital + deuda) | Preselección mínima |
|---|---|---|---|
| Canadá | Professional Centres Canada LP | 26 | 52 |
| Estados Unidos | Professional Centres United States LP (planificada) | 52 | 104 |
| México | Professional Centres Mexico FIBRA (planificada) | 26 | 52 |

El requisito de preselección se establece en una proporción mínima de 2:1 frente al número de desarrollo requerido para dar cuenta de los sitios donde el terreno adyacente no está disponible o donde los plazos de permisos y producción se extienden más allá de la tolerancia aplicable.

---

**Nota sobre calibración del conjunto de datos:**

Si los Clústeres de Quinto Grado — sitios donde ambos Objetivos Secundarios (Home Depot y Costco) y ambos Objetivos Terciarios (institución de educación superior y centro médico importante) están confirmados dentro de los umbrales de radio aplicables — representan más del 10% de todas las entradas de Objetivo Primario en el conjunto de datos de una jurisdicción dada, los umbrales de radio se recalibran a la baja. El umbral de proximidad terciaria se reduce de 5,0 km a 3,0 km; el umbral Primario-Secundario se reduce de 1,0 km a menos de 1,0 km. Esta recalibración preserva el poder discriminante del nivel de clúster superior en conjuntos de datos de tamaño y densidad geográfica variables.

Las verificaciones de calibración se realizan cada vez que el conjunto de datos se actualiza con nuevos datos de ventas por pie cuadrado del Objetivo Primario. El disparador de recalibración no se ha activado en los conjuntos de datos de Canadá, Estados Unidos o México durante el período de informe actual.

---

**Cadencia de actualización de ventas por pie cuadrado:**

Las clasificaciones de ventas por pie cuadrado del Objetivo Primario se actualizan anualmente o cada dos años para generar datos de tendencias y permitir la reclasificación de toda la población de Objetivos Primarios. Los datos de tendencias de ventas por pie cuadrado, acumulados a través de ciclos de actualización, proporcionan una visión longitudinal de qué mercados regionales están ganando o perdiendo productividad comercial en relación con el promedio de la cadena.

---

*Todas las cifras reflejan la metodología de puntuación V2 actual. Los conteos de clústeres están sujetos a cambios a medida que los cambios en la red del Objetivo Primario (nuevas aperturas de tiendas, cierres de tiendas, conversiones de formato) se incorporan al conjunto de datos. Los conteos del pipeline de sitios reflejan los objetivos de preselección aprobados; la disponibilidad individual del sitio se evalúa a través del proceso de Informe de Resumen de Transacción.*
