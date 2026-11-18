---
name: decomiso-contestacion-demanda-tercero-rebelde-no-pudo-762
description: "Redacta el escrito «Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse» (formulario 762 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse

> Formulario 0762 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº (4 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] NÚMERO (3 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…mente, en el Registro de la Propiedad de»; «…figura inscrita al tomo»; «…gura inscrita al tomo [COMPLETAR], libro»; «…, libro [COMPLETAR] de»; «… libro [COMPLETAR] de [COMPLETAR], folio»; «…se a la reclamación de decomiso del bien»; «…. de»

## Elecciones que hay que hacer

- como acredito mediante poder general para pleitos que acompaño para su testimonio en autos y devolución por necesitarlo para otros usos / según se acreditará mediante apoderamiento apud acta, en el día y hora que se señale por el tribunal
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 803 ter a 1 de la LECRIM

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

### Formulario 0762 · Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 25 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito mediante el que un tercero afectado por el decomiso que no tuvo oportunidad de oponerse en el proceso penal, por desconocer su existencia o porque no compareció y fue declarado rebelde en proceso penal, en caso de rescisión de la sentencia, presenta sus alegaciones en contra del decomiso de sus bienes solicitado por el fiscal.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, que actúa en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], provisto/a de D.N.I. n.º [NÚMERO], [ELEGIR: como acredito mediante poder general para pleitos que acompaño para su testimonio en autos y devolución por necesitarlo para otros usos / según se acreditará mediante apoderamiento apud acta, en el día y hora que se señale por el tribunal], y bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], (col n.º [Nº]) del Iltre. Colegio de Abogados de [COLEGIO], con despacho abierto en [LOCALIDAD], ante este órgano judicial/tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que, habiéndose emplazado a mi mandante en este proceso por la vía del art. 803 ter a 1 de la LECRIM al que no compareció por no haber sido citado en forma, (1) dentro del término conferido (2), y en base al art. 803 ter d de la LECRIM, me persono y contesto a la demanda, resistiendo a la misma, en base a los siguientes:

HECHOS

PRIMERO.- Los bienes que se citan en la demanda son propiedad exclusiva del/de la demandado/a y, además, son de lícita procedencia.

Efectivamente, en el Registro de la Propiedad de [COMPLETAR] figura inscrita al tomo [COMPLETAR], libro [COMPLETAR] de [COMPLETAR], folio [COMPLETAR], finca n.º [NÚMERO], a nombre de mi mandante, por título de herencia de su madre Dña. [NOMBRE Y APELLIDOS] (doc. nº 1).

SEGUNDO.- No es cierto que haya existido transmisión del mismo bien al/a la condenado/a D./Dña. [NOMBRE Y APELLIDOS] en procedimiento penal nº [Nº DE PROCEDIMIENTO] ya que los citados bienes no han salido del patrimonio del/de la demandado/a y por tanto no pueden quedar afectos al procedimiento penal y a la operación de decomiso al tratarse de bienes de lícita procedencia como se demuestra con el documento nº 1.

FUNDAMENTOS DE DERECHO

Primero.- Sujetos procesales y procedimiento

Esta parte no objeta nada al órgano judicial al que dirigimos la contestación como sujeto predeterminado legalmente (art 803 ter d LECRIM) para resolver este proceso, ni a que los sujetos con capacidad procesal en general, y legitimados en particular en punto al procedimiento de decomiso son demandante y demandado/a, ni en fin, al cauce procesal adecuado, (art. 803 ter d LECRIM), compareciéndose con Procurador/a y Abogado/a.

El procedimiento penal con declaración de condena del/de la encausado/a D./Dña. [NOMBRE Y APELLIDOS] finalizó por sentencia firme de fecha [FECHA] pero mi representado/a no compareció por desconocer su existencia y fue declarado/a en rebeldía, lo que dio lugar a la sentencia rescindente, tras procedimiento seguido al efecto.

Segundo.- Oposición a la pretensión

El decomiso se funda en la titularidad del bien antes citado por el/la condenado/a D./Dña. [NOMBRE Y APELLIDOS] en el Juicio oral nº [NÚMERO].

Sin embargo, pese a la reclamación de decomiso del bien [COMPLETAR] ejercitada por la Fiscalía para poder satisfacer las responsabilidades civiles fijadas sobre este bien, el mismo es propiedad del/de la demandado/a, como consta registralmente sin que se haya procedido a ningún acto traslativo de la propiedad o posesión que genere una transmisión o adquisición dominical, por lo que se insta la desestimación de la demanda respecto al decomiso de los bienes y se dicte sentencia en base al art. 803 ter d 1 b de la LECRIM dejándose, además, sin efecto las medidas adoptadas en el procedimiento penal nº [Nº DE PROCEDIMIENTO].

Por todo ello, se cumple el presupuesto básico de OPOSICIÓN del art. 803 ter d 1 b LECRIM, que habilita el mecanismo de oposición de la falta de fundamento de la acción civil ejercitada contra mi representado/a acerca de la imposibilidad de la afección de los bienes y derechos objeto de decomiso con respecto a la situación jurídica originada por la acción penal.

Se propone como prueba de la titularidad del bien la certificación del Registro de la Propiedad nº [Nº]. de [COMPLETAR] que acredita la titularidad del bien.

Tercero.- Costas

Se solicita la condena en costas de D./Dña. [NOMBRE Y APELLIDOS].

Por lo anteriormente expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, teniendo por presentado este escrito y documentos acompañados, junto con sus copias, se sirva admitirlos, tenerme por comparecida y parte en la representación que ostento, siguiéndose conmigo las sucesivas ulteriores diligencias, y por evacuado el trámite de contestación a la demanda de manera que, seguido todo el pertinente procedimiento, se venga a dictar sentencia con todos los pronunciamientos favorables para mi mandante.

Es Justicia de hacerse en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito puede interponerlo el tercero afectado por el decomiso que no tuvo oportunidad de oponerse por desconocer su existencia, o el que, habiendo sido citado en forma no compareció y fue declarado rebelde, en caso de rescisión de la sentencia.

Es preceptiva la asistencia letrada. (art. 803 ter b 2 LECRIM)

(2) En caso de rescisión de la sentencia, el tercero rebelde tendrá un plazo de 10 días para presentar este escrito de contestación a la demanda con proposición de prueba, en relación con los hechos relevantes para el pronunciamiento que le afecte.

================================================================================
