---
name: auto-libertad-provisional-investigado-encausado-reforma-617
description: "Redacta el escrito «Auto de libertad provisional del investigado o encausado: reforma y subsidiaria apelación» (formulario 617 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Auto de libertad provisional del investigado o encausado: reforma y subsidiaria apelación

> Formulario 0617 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dad, pues está sancionado en el artículo»; «…puesto que»; «…raigo del detenido/a que se desprende de»; «…estado policial, presentando un total de»

## Elecciones que hay que hacer

- con / sin
- investigado/a / encausado/a
- con fianza / sin fianza

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (En caso de que no se haya convocado la comparecencia para decidir sobre la libertad o prisión)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 507 de la LECRIM
- artículo 766 de la LECRIM
- artículos 507 y 766 LECRIM
- arts. 503, 504 y 505 de la LECRIM
- artículo 503 de la LECRIM
- artículo 505 de la LECRIM
- artículo 503 y 504 de la LECRIM
- artículo 766.4 LECRIM
- artículo 766.3 LECRIM

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

### Formulario 0617 · Auto de libertad provisional del investigado o encausado: reforma y subsidiaria apelación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 5 desplegables y casillas convertidos en elección en blanco; 1 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular en un procedimiento abreviado presenta recurso de reforma y, si este no es admitido, de apelación contra el auto que acuerda la libertad provisional del investigado o encausado, conforme autoriza el artículo 507 de la LECRIM, por la vía del artículo 766 de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación del acusador particular D/Dña. [NOMBRE Y APELLIDOS], según consta acreditado en las Diligencias Previas nº [Nº DE PROCEDIMIENTO], seguidas ante este órgano judicial, ante el mismo comparezco y, como mejor proceda en Derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte el auto dictado el día [FECHA] por el que se acordaba la libertad provisional [ELEGIR: con / sin] fianza para el/la
investigado/a
encausado/a
  y estimándolo perjudicial y gravoso para mi representado/a, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado (1) interpongo en tiempo y forma recurso de reforma y subsidiario de apelación (2), al amparo de lo establecido en los artículos 507 y 766 LECRIM, con base en las siguientes:

ALEGACIONES

Única.-

El auto que se recurre conculca lo dispuesto en los arts. 503, 504 y 505 de la LECRIM, puesto que se reúnen todos y cada uno de los requisitos establecidos para decretar la prisión provisional, siendo necesaria tal medida para asegurar la presencia del [ELEGIR: investigado/a / encausado/a] en el proceso y para evitar el riesgo de que cometa nuevos hechos delictivos.

En efecto, la medida cautelar que se pretende se ajusta a la finalidad que debe cumplir la prisión provisional, que se recoge expresamente en el artículo 503 de la LECRIM puesto que es necesaria a los efectos del aseguramiento del proceso, atendidos que el hecho objeto de procedimiento es de notable gravedad, pues está sancionado en el artículo [COMPLETAR] del Código Penal con pena de de prisión. Por su parte, existen indicios sólidos sobre la autoría del hecho por parte del [ELEGIR: investigado/a / encausado/a] puesto que [COMPLETAR]; y existe un evidente riesgo de fuga por la falta de arraigo del detenido/a que se desprende de [COMPLETAR] y, atendidos los antecedentes que obran en el atestado policial, presentando un total de [COMPLETAR] detenciones policiales que ponen de manifiesto una conducta ilícita continuada, constatándose un evidente riesgo de reiteración delictiva.

[OPCIONAL — incluir si procede]

(En caso de que no se haya convocado la comparecencia para decidir sobre la libertad o prisión)

El auto recurrido, al decretar la libertad sin fianza sin tan siquiera convocar a la comparecencia del artículo 505 de la LECRIM infringe los presupuestos establecidos en el artículo 503 y 504 de la LECRIM por lo que se interesa que se reforme la medida cautelar y se decrete la prisión provisional, tras la celebración de la comparecencia prevenida en el citado artículo 505 de la LECRIM .

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por formulado recurso de reforma y, en caso de no ser estimado, subsidiario de apelación, contra el auto de fecha [FECHA] por el que se acordaba la libertad provisional [ELEGIR: con fianza / sin fianza] del
investigado/a
encausado/a
  y, previos los trámites legales, se revoque el mismo y se acuerde la prisión provisional sin fianza del [ELEGIR: investigado/a / encausado/a].

Es de Justicia que pido en [LUGAR]

PRIMER OTROSÍ DIGO

Que, en caso de desestimarse total o parcialmente el recurso de reforma, solicito que se conceda nuevo traslado a esta parte por plazo de cinco días a los efectos prevenidos en el artículo 766.4 LECRIM .

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por hecha la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

SEGUNDO OTROSÍ DIGO

Que, en caso de tramitarse la apelación interpuesta con carácter subsidiario, designo los siguientes particulares para que sean remitidos a la Audiencia Provincial para la resolución del recurso, de acuerdo con lo establecido en el artículo 766.3 LECRIM:

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que remita a la Audiencia Provincial los anteriores particulares.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Se interpone ante el mismo juez que dictó la resolución recurrida, por escrito autorizado con firma de Letrado y en el plazo de los 3 días siguientes a su notificación.

Los días se consideran naturales en la fase de instrucción y hábiles en la de juicio oral.

(2) El recurso de apelación podrá interponerse subsidiariamente con el de reforma o por separado. En ningún caso será necesario interponer previamente el de reforma para presentar la apelación.

Con ello, resulta potestativo acudir a la reforma previa pudiendo directamente acudir a la apelación si se considera más ágil que estar a la espera de que se resuelva la reforma.

================================================================================
