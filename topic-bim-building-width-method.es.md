---
schema: foundry-doc-v1
title: "El método inverso — dimensionado de edificios a partir del mobiliario"
slug: topic-bim-building-width-method
aliases:
  - topic-bim-building-width-method
short_description: "El Calculador de Ancho de Edificio invierte la planificación de oficinas convencional derivando el ancho del edificio de dimensiones de mobiliario real — escritorio, mesa de examen, banco de laboratorio, banco de sala de justicia — en lugar de ajustar inquilinos a una cuadrícula estructural predeterminada."
category: bim
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
last_edited: 2026-05-17
editor: pointsav-engineering
paired_with: topic-bim-building-width-method.md
---

Los edificios de oficinas convencionales parten de una anchura de edificio —sesenta pies para la iluminación natural es la regla general en la oficina especulativa de Clase A en América del Norte— y el acondicionamiento del inquilino se adapta a continuación. La Calculadora de Anchura del Edificio invierte esa secuencia. Parte del mobiliario del inquilino (escritorio, camilla de exploración, mesa de laboratorio, banco de sala de vistas) y la anchura del edificio es la que exige la disposición. El método alimenta los valores por tipo de uso catalogados en [[topic-bim-zone-depths-per-use-type|profundidades de zona por tipo de uso]] y rige la geometría del [[topic-bim-tile-system|sistema de teselas]] que compone la [[topic-bim-floor-plate-methodology|planta]].

Fuente: V12 (enero 2025), *Taxonomía Espacial — Calculadora de Anchura del Edificio*.

## La sección transversal especular

La sección transversal es una franja de siete filas:

```
Fachada
Zona 1 — Hábitat    (escritorios/puestos de trabajo)     6,0 m
Zona 2 — Almacén    (almacenamiento, estanterías, etc.)  3,0 m  ← Por definir según uso
Zona 3 — Corredor   (único, línea central)               3,0 m  ← Por definir según uso
Zona 2 — Almacén    (especular)                          3,0 m
Zona 1 — Hábitat    (especular)                          6,0 m
Fachada
──────────────────────────────────────────────────────────────
TOTAL                                                   21 m / 69 ft
```

V12 establece la Oficina Profesional en **21 m / 69 ft** de anchura total como referencia. La Zona 2 Almacén y la Zona 3 Corredor se marcan como "por definir" — se dimensionan por tipo de uso una vez que el mobiliario está seleccionado.

El hecho geométrico clave: **la Zona 3 Corredor es una única fila central, no especular**. El Hábitat y el Almacén aparecen a ambos lados del corredor; el corredor aparece una sola vez.

## La fórmula

```
Anchura del Edificio = 2 × (Zona 1 Hábitat + Zona 2 Almacén) + Zona 3 Corredor
```

Confirmada por dos fuentes independientes:

- V12 Oficina Profesional: 2 × (6 + 3) + 3 = **21 m** ✓
- Notas de Negocio V3 Opción A/A: 2 × (5,51 + 9,26) + 2,75 = **32,29 m** — el documento tabula explícitamente este total.

Un error frecuente es duplicar también el corredor. Duplicar el corredor produce una anchura del edificio sobreestimada (la Oficina Profesional pasa a ser 23,6 m en lugar de 21 m; la Cívica, 33,66 m en lugar de 30,06 m). Verifique cualquier implementación de terceros con la fórmula anterior.

## Por qué tres zonas

### Zona 1 — Hábitat

La profundidad de iluminación natural de 6 m es la intención de diseño para espacios ocupados por puestos de trabajo. Aproxima las directrices de la Norma Europea de Iluminación para la luz natural en un puesto de trabajo (EN 12464-1 / EN 17037, pendiente de cita precisa en el archivo de tokens regulatorio).

El valor de 6 m no es universal. Tres de los siete tipos de uso establecidos se desvían:

- **Académico** comprime el Hábitat a **4,7 m** porque el asiento mira hacia adelante (hacia un podio o pizarra) y no hacia la fachada.
- **[[topic-bim-medical-key-plans|Médico]]** amplía el Hábitat a **7,28 m** para alojar la profundidad de la camilla de exploración junto con las distancias de circulación de paciente y personal sanitario según los códigos de accesibilidad.
- **Laboratorio** amplía el Hábitat a **6,78 m** para alojar la profundidad de la mesa de trabajo y el espacio libre alrededor de la campana de extracción.

### Zona 2 — Almacén

El Almacén es la variable de ajuste. Alberga almacenamiento, estanterías, archivos, salas de servidores y salas de personal. La anchura la fija lo que el inquilino necesita para equilibrar la planta — V12 indica que la profundidad de la Zona 2 "puede utilizarse para equilibrar las dimensiones de la planta y evitar obtener simplemente un rectángulo largo y estrecho."

En la práctica, la Zona 2 es la zona más ancha en los usos de [[topic-bim-business-key-plans|Negocio]] (9,26 m, Opción A/A) y Cívico (7,23 m), y la más estrecha en [[topic-bim-private-office-key-plans|Oficina Privada]] (1,37 m, 4'6") porque los despachos individuales requieren muy poco almacenamiento compartido.

### Zona 3 — Corredor

El corredor es una única línea central. Su anchura la fijan los requisitos de evacuación y accesibilidad: mínimos de camilla del IBC para uso Médico, evacuación de alta peligrosidad del IBC para Laboratorio, evacuación de asamblea pública para uso Cívico. V12 establece que los corredores deben ser **sobredimensionados en un 20 %** para favorecer el bienestar y absorber el tráfico de entrada y salida.

Dos tipos de uso — [[topic-bim-private-office-key-plans|Oficina Privada]] y Académico — **no tienen Zona 3**. Sus arrendamientos abren directamente al corredor del edificio compartido, que forma parte del núcleo del edificio y queda fuera del arrendamiento.

## La adición de 0,7 m por escritorios perpendiculares

El Resumen V2 (mayo 2025) registra un suplemento por escritorios perpendiculares:

> Con escritorios colocados de forma perpendicular a la fachada, hay que tener cuidado, ya que se necesitan 0,7 metros adicionales para la circulación correcta de tres escritorios en serie en la Zona 1—Hábitat. Sin tener en cuenta la circulación, los 6 metros exactos hasta la fachada permiten solo dos escritorios perpendiculares a la fachada en la Zona 1—Hábitat en lugar de tres.

Token: `bim.circulation-addition.perpendicular-desk = 0,7 m`.

Se trata de un suplemento de la Zona 1, no de una zona separada. Cambia la profundidad efectiva del Hábitat de 6,0 m a 6,7 m cuando se requieren disposiciones de escritorios perpendiculares para sentar tres escritorios en serie.

## Por qué importa este método

El método inverso plantea tres afirmaciones que la práctica especulativa de oficinas convencional no contempla:

1. **El mobiliario determina la geometría.** Un propietario no puede reducir la profundidad de la camilla de exploración de un inquilino ajustando la planta; el edificio debe adaptarse al uso y no al contrario.
2. **Cada tipo de inquilino tiene una anchura conocida.** Una vez seleccionado el tipo de uso, la anchura del edificio se calcula, no se negocia.
3. **Las plantas con múltiples inquilinos deben reconciliar las anchuras en la fase de diseño.** Una planta con un ancla Médica (27,2 m) y un conjunto de Oficinas Privadas (14,7 m) debe absorber 12,5 m de tolerancia de tabiquería — la anchura de la planta debe coincidir con el inquilino más ancho; los inquilinos más estrechos aceptan el excedente como zonas de Almacén más amplias.

## Estado y ratificación

| Componente | Fuente | Estado |
|---|---|---|
| Diagrama de sección transversal especular | V12 (enero 2025) | Ratificado |
| Z1 = 6 m por defecto | V12 + EN 12464-1 (citada) | Ratificado |
| Z2 = por definir según uso | V12 | Ratificado |
| Z3 = línea central, única | V12 (gráfico); totales Negocio V3 | Ratificado |
| Fórmula `2(Z1+Z2) + Z3` | V12; enumeración Negocio V3 | Ratificado |
| Adición de 0,7 m por escritorios perpendiculares | Resumen V2 (mayo 2025) | Ratificado |
| Oficina Profesional Z2/Z3 | V12 ("por definir", valores provisionales 3 m / 3 m) | Pendiente |
| Negocio Z1/Z2/Z3 | Notas V3 (21 opciones enumeradas) | Pendiente de decisión del operador |
| Cívico Z1/Z2/Z3 | Sin boceto completado | Pendiente |

## Investigación futura

- [ ] Añadir cita reglamentaria precisa para los 6 m de Hábitat (cláusula de EN 12464-1, referencia cruzada con ArbStättV)
- [ ] Documentar la distancia de accesibilidad referenciada en los usos Médico y de Laboratorio
- [ ] Confirmar si la Zona 3 corredor es siempre una única línea central, o si en una planta muy grande puede introducirse un corredor secundario
- [ ] Resolver los valores provisionales de Z2/Z3 en Oficina Profesional (V12 los deja en 3 m / 3 m por definir)
- [ ] Decidir cuál de las 21 opciones de anchura de Negocio es canónica para el almacén de tokens (propuesta actual: Opción A/A, 32,29 m)
- [ ] Verificar si la adición de 0,7 m por escritorios perpendiculares es un suplemento de Hábitat (Z1 efectivo = 6,7 m) o una contribución de zona separada

## Véase también

- [[topic-bim-zone-depths-per-use-type]]
- [[topic-bim-floor-plate-methodology]]
- [[topic-bim-tile-system]]
