---
name: indice
description: "Índice de los 43 formularios de Propiedad, posesión, servidumbres e hipotecas. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Propiedad, posesión, servidumbres e hipotecas: índice de formularios

> Plugin `formularios-propiedad-y-derechos-reales` · 43 formularios · normativa revisada el 25-11-2026.

## Qué es

Para los derechos reales: acción reivindicatoria y declarativa de dominio, tutela de la posesión, servidumbres, división de cosa común, retractos, deslinde, inmatriculación y asuntos registrales, usufructo y derecho de superficie.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Demanda de acción reivindicatoria de una finca»
- «Demanda de división de la cosa común»
- «Acción de retracto de colindantes»

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-propiedad-y-derechos-reales:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (4)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0657 | Demanda de juicio ordinario para resolver una compraventa por falta de licencia de primera ocupación | `demanda-juicio-ordinario-resolver-compraventa-falta-civ-0657` |
| CIV-0659 | Demanda de juicio verbal para arrancar árboles plantados sin la distancia legal, con inspección | `demanda-juicio-verbal-arrancar-arboles-plantados-sin-civ-0659` |
| CIV-0682 | Demanda de juicio verbal de precario sobre finca urbana | `demanda-juicio-verbal-precario-sobre-finca-urbana-civ-0682` |
| CIV-2532 | Demanda de suspensión de obra nueva contra el propietario de la vivienda colindante | `demanda-suspension-obra-nueva-contra-propietario-civ-2532` |

### Contratos, pactos y cláusulas (20)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0655 | Contrato de anticresis sobre un inmueble | `contrato-anticresis-sobre-inmueble-civ-0655` |
| CIV-0656 | Contrato de cesión de un solar a cambio de vivienda, local y garaje futuros | `contrato-cesion-solar-cambio-vivienda-local-garaje-civ-0656` |
| CIV-0663 | Contrato por el que se ceden fincas en precario | `contrato-ceden-fincas-precario-civ-0663` |
| CIV-0664 | Contrato de constitución de derecho de habitación sobre una vivienda | `contrato-constitucion-derecho-habitacion-sobre-vivienda-civ-0664` |
| CIV-0665 | Contrato de cesión de uso en precario | `contrato-cesion-uso-precario-civ-0665` |
| CIV-0668 | Contrato de compraventa de un solar | `contrato-compraventa-solar-civ-0668` |
| CIV-0669 | Contrato por el que se cede una vivienda en precario | `contrato-cede-vivienda-precario-civ-0669` |
| CIV-0671 | Contrato de compraventa de finca de una comunidad de bienes con renuncia solo al retracto legal | `contrato-compraventa-finca-comunidad-bienes-renuncia-civ-0671` |
| CIV-0672 | Contrato de compraventa de inmueble con retracto convencional a favor del vendedor | `contrato-compraventa-inmueble-retracto-convencional-civ-0672` |
| CIV-0673 | Contrato de venta de la nuda propiedad de una finca agrícola | `contrato-venta-nuda-propiedad-finca-agricola-civ-0673` |
| CIV-0674 | Contrato de compraventa de finca entre particular y sociedad con constitución de hipoteca | `contrato-compraventa-finca-entre-particular-sociedad-civ-0674` |
| CIV-0675 | Contrato de compraventa de inmueble hipotecado con subrogación del comprador en la deuda | `contrato-compraventa-inmueble-hipotecado-subrogacion-civ-0675` |
| CIV-0676 | Contrato de compraventa de solar entre particulares, libre o con cargas | `contrato-compraventa-solar-entre-particulares-libre-civ-0676` |
| CIV-0677 | Contrato de compraventa de finca rústica arrendada, con o sin notificación previa al arrendatario | `contrato-compraventa-finca-rustica-arrendada-sin-civ-0677` |
| CIV-0678 | Contrato de venta de piso con usufructo vitalicio reservado y precio aleatorio | `contrato-venta-piso-usufructo-vitalicio-reservado-civ-0678` |
| CIV-0679 | Contrato de compraventa de finca con reserva de usufructo vitalicio para el vendedor | `contrato-compraventa-finca-reserva-usufructo-vitalicio-civ-0679` |
| CIV-0680 | Contrato de compraventa de inmueble con reserva de usufructo temporal para el vendedor | `contrato-compraventa-inmueble-reserva-usufructo-civ-0680` |
| CIV-2533 | Contrato de venta a plazos de un inmueble con reserva de dominio | `contrato-venta-plazos-inmueble-reserva-dominio-civ-2533` |
| CIV-2534 | Contrato de compraventa de una finca o solar | `contrato-compraventa-finca-solar-civ-2534` |
| CIV-2538 | Contrato para comprar una vivienda de protección oficial subrogándose en la hipoteca | `contrato-comprar-vivienda-proteccion-oficial-civ-2538` |

### Estatutos, actas, certificaciones y escrituras (12)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0658 | Escritura de hipoteca mobiliaria constituida unilateralmente por el propietario | `escritura-hipoteca-mobiliaria-constituida-civ-0658` |
| CIV-0667 | Escritura de declaración de obra nueva de vivienda unifamiliar | `escritura-declaracion-obra-nueva-vivienda-unifamiliar-civ-0667` |
| CIV-2535 | Escritura de compraventa de finca urbana con subrogación del comprador en la hipoteca | `escritura-compraventa-finca-urbana-subrogacion-civ-2535` |
| CIV-2536 | Escritura de compraventa de una finca urbana sujeta a condición resolutoria | `escritura-compraventa-finca-urbana-sujeta-condicion-civ-2536` |
| CIV-2537 | Escritura de compraventa con pago aplazado y posposición de la condición resolutoria a la hipoteca | `escritura-compraventa-pago-aplazado-posposicion-civ-2537` |
| CIV-2539 | Escritura en la que el deudor cede un crédito hipotecario a su acreedor para saldar la deuda | `escritura-deudor-cede-credito-hipotecario-acreedor-civ-2539` |
| CIV-2540 | Escritura pública en la que el optante ejercita una opción de compra real y unilateral | `escritura-publica-optante-ejercita-opcion-compra-real-civ-2540` |
| CIV-2541 | Acta notarial que declara extinguido el pacto de retroventa o retracto convencional | `acta-notarial-declara-extinguido-pacto-retroventa-civ-2541` |
| CIV-2542 | Escritura que hace constar la caducidad de la posposición de una hipoteca | `escritura-hace-constar-caducidad-posposicion-hipoteca-civ-2542` |
| CIV-2543 | Escritura de compraventa en la que se pospone una hipoteca voluntaria | `escritura-compraventa-pospone-hipoteca-voluntaria-civ-2543` |
| CIV-2544 | Escritura de compraventa con nueva hipoteca voluntaria y posposición de la anterior | `escritura-compraventa-nueva-hipoteca-voluntaria-civ-2544` |
| CIV-2545 | Escritura de compraventa en la que el comprador se subroga en el préstamo hipotecario | `escritura-compraventa-comprador-subroga-prestamo-civ-2545` |

### Comunicaciones, requerimientos y cartas (1)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0670 | Solicitud conjunta de homologación de transacción en juicio de división de cosa común | `solicitud-conjunta-homologacion-transaccion-juicio-civ-0670` |

### Escritos de trámite y otros (6)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0660 | Nota de inscripción registral de la compraventa de un bien ganancial | `nota-inscripcion-registral-compraventa-bien-ganancial-civ-0660` |
| CIV-0661 | Nota de inscripción de bien presuntivamente ganancial con afección fiscal | `nota-inscripcion-bien-presuntivamente-ganancial-civ-0661` |
| CIV-0662 | Nota de inscripción de bien privativo por confesión del consorte | `nota-inscripcion-bien-privativo-confesion-consorte-civ-0662` |
| CIV-0666 | Escrito para inscribir una sentencia en un registro público distinto del Registro Civil | `escrito-inscribir-sentencia-registro-publico-distinto-civ-0666` |
| CIV-0681 | Escrito del acreedor pidiendo la administración interina de la finca hipotecada | `escrito-acreedor-pidiendo-administracion-interina-civ-0681` |
| CIV-2531 | Declinatoria por falta de competencia funcional en el juicio verbal de tutela de la posesión | `declinatoria-falta-competencia-funcional-juicio-verbal-civ-2531` |
