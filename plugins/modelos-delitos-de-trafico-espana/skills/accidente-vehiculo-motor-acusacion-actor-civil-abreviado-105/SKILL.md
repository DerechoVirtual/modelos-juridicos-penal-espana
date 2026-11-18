---
name: accidente-vehiculo-motor-acusacion-actor-civil-abreviado-105
description: "Redacta el escrito «Accidente con vehículo a motor: acusación del actor civil en el abreviado» (formulario 105 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Accidente con vehículo a motor: acusación del actor civil en el abreviado

> Formulario 0105 del plugin **Seguridad vial** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] MARCA/MODELO
- [ ] LOCALIDAD
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…contra el/la encausado/a en este proceso»; «…, así como contra la Entidad aseguradora»; «…conducido por»; «…y asegurado en la entidad»; «…tados hechos son responsables civilmente»; «…autor de los mismos, así como la entidad»; «…eguradora como responsable civil directa»; «…do por este Tribunal el/la perjudicado/a»; «…, con domicilio»; «… la prestación de asistencia sanitaria a»; «…(A) y»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1. Interrogatorio del/de la acusado/a.…
- 2. Testifical, debiendo ser citado por este Tribunal el/la perjudicado/a [COMPLETAR], con domicilio [COMPLETAR…
- 3. Documental consistente en:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 781.1 de la Ley de Enjuiciamiento Criminal
- arts. 650 y 651 de la LECrim

## Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero el «Texto del formulario» del final de este fichero, con su cabecera, y la parte de `../indice/marco.md` que afecte al caso (plazos, órgano, procedimiento, procedimiento aplicable, requisitos de perseguibilidad (denuncia de la persona agraviada, querella con poder especial) y prescripción).
3. Pide los datos de la lista. Lo que el usuario no sepa se queda como hueco visible.
4. Decide las elecciones y los párrafos opcionales según los hechos. Redacta las partes que el original no traía.
5. Aplica los avisos y las notas de revisión. Comprueba con `buscar_articulo` cada norma citada y, si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Indica el plazo y el cauce: desde cuándo cuenta, cuándo vence y ante qué órgano se presenta.
7. Antes de entregarlo, pasa `verificar_escrito` con las frases del escrito que citan normas o sentencias y corrige lo que señale.
8. Entrega el escrito en **Word (.docx)** con formato de escrito (usa la skill de Word disponible) y, si es corto, también en el chat.
9. Cierra con: datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator y, si algún dato sale de internet, cuál es y su enlace.

## Texto del formulario

### Formulario 0105 · Accidente con vehículo a motor: acusación del actor civil en el abreviado

- Año del modelo: 2023
- Revisión 17-11-2026: 3 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Nota explicativa incorporada desde la colección Procesal (formulario 104) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el actor civil en un procedimiento abreviado presenta sus conclusiones provisionales, conforme al art. 781.1 LECRIM y solicita que se emplace a la entidad aseguradora del vehículo a efectos de que pueda presentar su escrito de defensa, en su caso.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A], actor civil en este procedimiento, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho, DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo dispuesto en el art. 781.1 de la Ley de Enjuiciamiento Criminal, en relación los arts. 650 y 651 de la LECrim, deduzco mi solicitud de responsabilidad civil contra el/la encausado/a en este proceso [COMPLETAR], así como contra la Entidad aseguradora [COMPLETAR] en su calidad de responsable civil directa, formulando las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- Mi representado/a ha sufrido daños y perjuicios por importe de [IMPORTE] euros, como consecuencia de los gastos médicos sufragados al perjudicado Sr. [NOMBRE Y APELLIDOS] y derivados del atropello ocurrido en fecha [FECHA], provocado por el vehículo marca [MARCA/MODELO] conducido por [COMPLETAR] y asegurado en la entidad [COMPLETAR].

SEGUNDA.- De los citados hechos son responsables civilmente [COMPLETAR], en su calidad de autor de los mismos, así como la entidad [COMPLETAR], como responsable civil directa, en su calidad de aseguradora del vehículo, los cuales deberán indemnizar de forma solidaria a mi representado/a en la cantidad de [IMPORTE] euros, en concepto de gastos médicos derivados del atropello anteriormente descrito y respecto del cual se sigue este proceso.

PRIMER OTROSÍ DIGO: que no habiendo sido emplazada la entidad aseguradora como responsable civil directa [COMPLETAR], en el curso de la instrucción de la causa, intereso sea emplazada en su domicilio sito en [LOCALIDAD], a los efectos de que pueda formular escrito de defensa si a su derecho conviniere.

SEGUNDO OTROSI DIGO: Que, para el acto del juicio oral, esta representación propone los siguientes MEDIOS DE PRUEBA, necesarios para la defensa de sus intereses:

[OPCIONAL — incluir si procede]

1. Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

2. Testifical, debiendo ser citado por este Tribunal el/la perjudicado/a [COMPLETAR], con domicilio [COMPLETAR]

[OPCIONAL — incluir si procede]

3. Documental consistente en:

a) Documental privada, consistente en factura emitida por mi representado/a como consecuencia de la prestación de asistencia sanitaria a [COMPLETAR] por importe de [IMPORTE], la cual se acompaña como documento número 1 a este escrito.
b) Lectura de las siguientes diligencias sumariales: folio 20-23 (partes asistencia hospitalaria); y folio 35, 39, 70 y 89 (informes médico forense).

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por evacuado el trámite conferido, por deducidas las pretensiones de responsabilidad civil contra [ACTO O RESOLUCIÓN] (A) y [COMPLETAR] (B), por solicitado el emplazamiento de éste como responsable civil directo, y tenga por propuesta la prueba para ante el órgano de enjuiciamiento.

Es justicia que pido, en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
