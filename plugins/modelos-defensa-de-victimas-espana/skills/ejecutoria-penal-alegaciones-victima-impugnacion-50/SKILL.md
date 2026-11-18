---
name: ejecutoria-penal-alegaciones-victima-impugnacion-50
description: "Redacta el escrito «Ejecutoria penal: alegaciones de la víctima a la impugnación de la liquidación de condena» (formulario 50 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: alegaciones de la víctima a la impugnación de la liquidación de condena

> Formulario 0050 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 988 bis.4 LECRIM
- art. 988 bis.4 LECRIM

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

### Formulario 0050 · Ejecutoria penal: alegaciones de la víctima a la impugnación de la liquidación de condena

- Año del modelo: 2025
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 35) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la víctima presenta alegaciones frente a la impugnación del condenado de la liquidación de condena efectuada por el LAJ ante el órgano judicial que dictó la sentencia condenatoria, en base al art. 988 bis.4 LECRIM, introducida por LO 1/2025, vigente desde el 3 de abril de 2025.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala de lo Penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según tengo debidamente acreditado en la Ejecutoria nº [Nº DE PROCEDIMIENTO], ante este órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 988 bis.4 LECRIM, mi representado/a manifiesta su oposición a la impugnación de la liquidación de condena formulada por la representación del/de la condenado/a, en base a las siguientes

ALEGACIONES

ÚNICA.-

"Señala el art. 988 bis.4 LECRIM que: 4. El letrado o la letrada de la Administración de Justicia citará al condenado a una comparecencia en la que le requerirá de cumplimiento de las penas, decomiso y responsabilidades civiles que le hubieran sido impuestas y le informará de las responsabilidades en que pueda incurrir en el supuesto de incumplimiento.

Asimismo, practicará las liquidaciones de condena, que comprenderán, en todo caso, los siguientes particulares:

a) la fecha de inicio del cumplimiento,
b) el tiempo abonable por haber estado privado de libertad provisionalmente en la causa o por la aplicación de cualquier otra medida cautelar,
c) el tiempo de duración de la condena, y
d) el tiempo de cumplimiento.

A tales efectos, el cómputo se hará por años, meses y días, de acuerdo con las siguientes reglas: los meses completos serán de treinta días y los años completos serán de trescientos sesenta y cinco días.

De dichas liquidaciones, que se notificarán personalmente al condenado, se dará traslado al Ministerio Fiscal y a las partes, que podrán impugnarlas en el plazo de dos días. Transcurrido el plazo sin impugnación, el letrado o la letrada de la Administración de Justicia la aprobará mediante decreto.

Si fueran impugnadas por alguna de las partes, se dará traslado al resto para alegaciones por de dos días. Transcurrido el mismo, hubieren o no presentado escrito las demás partes, el juez, la jueza o el tribunal resolverá mediante auto, que será dictado en el plazo de dos días. Una vez firme éste, si corrigiere la liquidación de condena será notificado personalmente al condenado. "

Respecto de la queja por el periodo de tiempo que resta de pena por cumplir, en base a la liquidación de condena practicada, exponemos que:

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que tenga por presentado este escrito con sus copias, los admita y por opuesto a la impugnación de la liquidación de condena hecha por el condenado en la presente causa, siendo válida la efectuada por el LAJ.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Plazo para alegaciones: las partes tienen 2 días desde que se les da traslado de la impugnación de la liquidación de condena hecha por el LAJ. Si se tratara de escrito de víctima no personada como acusación particular, se interesaría que el Fiscal apoye la liquidación practicada
