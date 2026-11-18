---
name: decomiso-autonomo-designar-bienes-decomisar-756
description: "Redacta el escrito «Decomiso autónomo: designar bienes para decomisar» (formulario 756 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Decomiso autónomo: designar bienes para decomisar

> Formulario 0756 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] NÚMERO
- [ ] Nº DE RESOLUCIÓN
- [ ] FECHA (3 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…-»

## Elecciones que hay que hacer

- encausado/a / familiar de encausado / tercero afectado
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- - [COMPLETAR].…

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0756 · Decomiso autónomo: designar bienes para decomisar

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito mediante el que el encausado, o un familiar del autor condenado o un tercero afectado designa bienes sobre los que debe hacerse efectivo el decomiso declarado en sentencia dictada en procedimiento de decomiso autónomo, seguido por los trámites del juicio verbal civil, conforme a los arts. 803 ter e) y siguientes de la LECrim.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de (1)

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS] como [ELEGIR: encausado/a / familiar de encausado / tercero afectado] (2) en procedimiento de decomiso autónomo tramitado bajo el nº [NÚMERO] comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del art. 803 ter procedimiento 4 LECRIM, mediante el presente escrito formulo designación de bienes para pago de la cantidad determinada en sentencia de decomiso.

CONCLUSIONES

PRIMERA.- En sentencia nº [Nº DE RESOLUCIÓN] de fecha [FECHA] en procedimiento seguido por los trámites del juicio verbal civil se acordó contra mi representado/a el decomiso por valor de [IMPORTE] euros.

SEGUNDA.- Que, conforme consta en el art. 803 ter procedimiento 4 LECRIM:

"Cuando el decomiso se hubiera acordado por un valor determinado, se requerirá a la persona con relación a la cual se hubiera acordado para que proceda al pago de la cantidad correspondiente dentro del plazo que se le determine; o, en otro caso, designe bienes por un valor suficiente sobre los que la orden de decomiso pueda hacerse efectiva."

Que se me ha requerido para que abone la suma fijada en sentencia o proceda a la designación de bienes, optando por la segunda opción, por lo cual designo como bienes para pago el/los siguiente/s:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR].

Aporto al mismo tiempo tasación pericial del/de los bien/es inmueble/s (doc. nº 1) que cubre/n la suma fijada en sentencia, así como referencia registral de la constancia a nombre de mi representado/a de la titularidad del/de los bien/es. (doc. nº 2)

TERCERA.- En base a lo dispuesto en el art. 803 ter procedimiento 4 LECRIM intereso se proceda a la cancelación de la deuda existente y por atendido el requerimiento de pago.

Por todo lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que se acuerde cumplido el requerimiento efectuado a mi persona en fecha [FECHA] y por cumplida la obligación de pago con la entrega del/de los bien/es que consta/n en el presente escrito para que se proceda a la ejecución sobre el/los mismo/s con la correspondiente transmisión y adjudicación judicial.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este es un escrito puede presentarse también en la Audiencia Provincial si ésta es la competente para enjuiciamiento. (Art. 803 ter f LECRIM).

(2) La legitimación pasiva la puede ostentar (art. 803 ter j LECRIM):

- El encausado en un proceso penal si el fiscal se limita en su escrito de acusación a solicitar el decomiso de bienes reservando expresamente para este procedimiento su determinación, o no puede ser enjuiciado por hallarse en rebeldía o incapacidad para comparecer en juicio.
- Los familiares del autor de un hecho punible que haya fallecido.
- Un tercero que ostenta derechos sobre el bien objeto de decomiso.

================================================================================
