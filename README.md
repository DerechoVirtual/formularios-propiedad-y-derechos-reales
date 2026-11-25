# Propiedad, posesión, servidumbres e hipotecas

> Plugin de Claude Code `formularios-propiedad-y-derechos-reales` · **43 formularios** · Civil · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Para los derechos reales: acción reivindicatoria y declarativa de dominio, tutela de la posesión, servidumbres, división de cosa común, retractos, deslinde, inmatriculación y asuntos registrales, usufructo y derecho de superficie.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 43 está al final):

- **Demandas, peticiones y solicitudes iniciales** (4). Por ejemplo: Demanda de juicio ordinario para resolver una compraventa por falta de licencia de primera ocupación; Demanda de juicio verbal para arrancar árboles plantados sin la distancia legal, con inspección; Demanda de juicio verbal de precario sobre finca urbana.
- **Contratos, pactos y cláusulas** (20). Por ejemplo: Contrato de anticresis sobre un inmueble; Contrato de cesión de un solar a cambio de vivienda, local y garaje futuros; Contrato por el que se ceden fincas en precario.
- **Estatutos, actas, certificaciones y escrituras** (12). Por ejemplo: Escritura de hipoteca mobiliaria constituida unilateralmente por el propietario; Escritura de declaración de obra nueva de vivienda unifamiliar; Escritura de compraventa de finca urbana con subrogación del comprador en la hipoteca.
- **Comunicaciones, requerimientos y cartas** (1). Por ejemplo: Solicitud conjunta de homologación de transacción en juicio de división de cosa común.
- **Escritos de trámite y otros** (6). Por ejemplo: Nota de inscripción registral de la compraventa de un bien ganancial; Nota de inscripción de bien presuntivamente ganancial con afección fiscal; Nota de inscripción de bien privativo por confesión del consorte.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Demanda de acción reivindicatoria de una finca»
   - «Demanda de división de la cosa común»
   - «Acción de retracto de colindantes»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-propiedad-y-derechos-reales:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-propiedad-y-derechos-reales:contrato-anticresis-sobre-inmueble-civ-0655`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 2.608 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-propiedad-y-derechos-reales@formularios-propiedad-y-derechos-reales`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-propiedad-y-derechos-reales
/plugin install formularios-propiedad-y-derechos-reales@formularios-propiedad-y-derechos-reales
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-propiedad-y-derechos-reales`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-propiedad-y-derechos-reales/releases/latest/download/formularios-propiedad-y-derechos-reales.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (43)

| Código | Formulario | Skill |
|---|---|---|
| CIV-0655 | Contrato de anticresis sobre un inmueble | `contrato-anticresis-sobre-inmueble-civ-0655` |
| CIV-0656 | Contrato de cesión de un solar a cambio de vivienda, local y garaje futuros | `contrato-cesion-solar-cambio-vivienda-local-garaje-civ-0656` |
| CIV-0657 | Demanda de juicio ordinario para resolver una compraventa por falta de licencia de primera ocupación | `demanda-juicio-ordinario-resolver-compraventa-falta-civ-0657` |
| CIV-0658 | Escritura de hipoteca mobiliaria constituida unilateralmente por el propietario | `escritura-hipoteca-mobiliaria-constituida-civ-0658` |
| CIV-0659 | Demanda de juicio verbal para arrancar árboles plantados sin la distancia legal, con inspección | `demanda-juicio-verbal-arrancar-arboles-plantados-sin-civ-0659` |
| CIV-0660 | Nota de inscripción registral de la compraventa de un bien ganancial | `nota-inscripcion-registral-compraventa-bien-ganancial-civ-0660` |
| CIV-0661 | Nota de inscripción de bien presuntivamente ganancial con afección fiscal | `nota-inscripcion-bien-presuntivamente-ganancial-civ-0661` |
| CIV-0662 | Nota de inscripción de bien privativo por confesión del consorte | `nota-inscripcion-bien-privativo-confesion-consorte-civ-0662` |
| CIV-0663 | Contrato por el que se ceden fincas en precario | `contrato-ceden-fincas-precario-civ-0663` |
| CIV-0664 | Contrato de constitución de derecho de habitación sobre una vivienda | `contrato-constitucion-derecho-habitacion-sobre-vivienda-civ-0664` |
| CIV-0665 | Contrato de cesión de uso en precario | `contrato-cesion-uso-precario-civ-0665` |
| CIV-0666 | Escrito para inscribir una sentencia en un registro público distinto del Registro Civil | `escrito-inscribir-sentencia-registro-publico-distinto-civ-0666` |
| CIV-0667 | Escritura de declaración de obra nueva de vivienda unifamiliar | `escritura-declaracion-obra-nueva-vivienda-unifamiliar-civ-0667` |
| CIV-0668 | Contrato de compraventa de un solar | `contrato-compraventa-solar-civ-0668` |
| CIV-0669 | Contrato por el que se cede una vivienda en precario | `contrato-cede-vivienda-precario-civ-0669` |
| CIV-0670 | Solicitud conjunta de homologación de transacción en juicio de división de cosa común | `solicitud-conjunta-homologacion-transaccion-juicio-civ-0670` |
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
| CIV-0681 | Escrito del acreedor pidiendo la administración interina de la finca hipotecada | `escrito-acreedor-pidiendo-administracion-interina-civ-0681` |
| CIV-0682 | Demanda de juicio verbal de precario sobre finca urbana | `demanda-juicio-verbal-precario-sobre-finca-urbana-civ-0682` |
| CIV-2531 | Declinatoria por falta de competencia funcional en el juicio verbal de tutela de la posesión | `declinatoria-falta-competencia-funcional-juicio-verbal-civ-2531` |
| CIV-2532 | Demanda de suspensión de obra nueva contra el propietario de la vivienda colindante | `demanda-suspension-obra-nueva-contra-propietario-civ-2532` |
| CIV-2533 | Contrato de venta a plazos de un inmueble con reserva de dominio | `contrato-venta-plazos-inmueble-reserva-dominio-civ-2533` |
| CIV-2534 | Contrato de compraventa de una finca o solar | `contrato-compraventa-finca-solar-civ-2534` |
| CIV-2535 | Escritura de compraventa de finca urbana con subrogación del comprador en la hipoteca | `escritura-compraventa-finca-urbana-subrogacion-civ-2535` |
| CIV-2536 | Escritura de compraventa de una finca urbana sujeta a condición resolutoria | `escritura-compraventa-finca-urbana-sujeta-condicion-civ-2536` |
| CIV-2537 | Escritura de compraventa con pago aplazado y posposición de la condición resolutoria a la hipoteca | `escritura-compraventa-pago-aplazado-posposicion-civ-2537` |
| CIV-2538 | Contrato para comprar una vivienda de protección oficial subrogándose en la hipoteca | `contrato-comprar-vivienda-proteccion-oficial-civ-2538` |
| CIV-2539 | Escritura en la que el deudor cede un crédito hipotecario a su acreedor para saldar la deuda | `escritura-deudor-cede-credito-hipotecario-acreedor-civ-2539` |
| CIV-2540 | Escritura pública en la que el optante ejercita una opción de compra real y unilateral | `escritura-publica-optante-ejercita-opcion-compra-real-civ-2540` |
| CIV-2541 | Acta notarial que declara extinguido el pacto de retroventa o retracto convencional | `acta-notarial-declara-extinguido-pacto-retroventa-civ-2541` |
| CIV-2542 | Escritura que hace constar la caducidad de la posposición de una hipoteca | `escritura-hace-constar-caducidad-posposicion-hipoteca-civ-2542` |
| CIV-2543 | Escritura de compraventa en la que se pospone una hipoteca voluntaria | `escritura-compraventa-pospone-hipoteca-voluntaria-civ-2543` |
| CIV-2544 | Escritura de compraventa con nueva hipoteca voluntaria y posposición de la anterior | `escritura-compraventa-nueva-hipoteca-voluntaria-civ-2544` |
| CIV-2545 | Escritura de compraventa en la que el comprador se subroga en el préstamo hipotecario | `escritura-compraventa-comprador-subroga-prestamo-civ-2545` |

## Privacidad

Ver `PRIVACY.md`.
