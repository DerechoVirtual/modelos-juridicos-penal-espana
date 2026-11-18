---
name: auto-libertad-provisional-investigado-encausado-618
description: "Redacta el escrito «Auto de libertad provisional del investigado o encausado: apelación» (formulario 618 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Auto de libertad provisional del investigado o encausado: apelación

> Formulario 0618 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…– plaza n.º [Nº] D./Dña.»; «…dad, pues está sancionado en el artículo»; «…del Código Penal con pena de»; «…raigo del detenido/a que se desprende de»; «…estado policial, presentando un total de»

## Elecciones que hay que hacer

- con / sin
- investigado/a / encausado/a

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (En caso de que no se haya convocado la comparecencia para decidir sobre la libertad o prisión)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 507 de la LECRIM
- artículo 766 de la LECRIM
- artículo 507 y 766 LECRIM
- arts. 503, 504 y 505 de la LECRIM
- artículo 503 de la LECRIM
- artículo 505 de la LECRIM
- artículo 503 y 504 de la LECRIM
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

### Formulario 0618 · Auto de libertad provisional del investigado o encausado: apelación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular en un procedimiento abreviado presenta recurso de apelación, sin necesidad de previo recurso de reforma, contra el auto que acuerda la libertad provisional del investigado o encausado, conforme autoriza el artículo 507 de la LECRIM, por la vía del artículo 766 de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [COMPLETAR], Procurador/a de los Tribunales, en nombre y representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], según tengo ya acreditado en el Procedimiento Abreviado número [Nº DE PROCEDIMIENTO], por presunto delito de [DELITO], como mejor proceda en derecho, DIGO:

Que, al amparo de los artículo 507 y 766 LECRIM, interpongo directamente recurso de apelación (1) en un efecto contra el auto de fecha [FECHA], que se me ha notificado el día [FECHA], que dispone la libertad provisional [ELEGIR: con / sin] fianza del [ELEGIR: investigado/a / encausado/a]; por suponer para mi representado/a un grave perjuicio, dicho sea, con el debido respeto y en términos de defensa y ser susceptible de apelación, con base en las siguientes:

RAZONES

Única.-

El auto que se recurre conculca lo dispuesto en los arts. 503, 504 y 505 de la LECRIM, puesto que se reúnen todos y cada uno de los requisitos establecidos para decretar la prisión provisional, siendo necesaria tal medida para asegurar la presencia del [ELEGIR: investigado/a / encausado/a] en el proceso y para evitar el riesgo de que cometa nuevos hechos delictivos.

En efecto, la medida cautelar que se pretende se ajusta a la finalidad que debe cumplir la prisión provisional, que se recoge expresamente en el artículo 503 de la LECRIM puesto que es necesaria a los efectos del aseguramiento del proceso, teniendo en cuenta que el hecho objeto de procedimiento es de notable gravedad, pues está sancionado en el artículo [COMPLETAR] del Código Penal con pena de [COMPLETAR] de prisión.

Por su parte, existen indicios sólidos sobre la autoría del hecho por parte del [ELEGIR: investigado/a / encausado/a] puesto que; y existe un evidente riesgo de fuga por la falta de arraigo del detenido/a que se desprende de [COMPLETAR] y atendidos los antecedentes que obran en el atestado policial, presentando un total de [COMPLETAR] detenciones policiales que ponen de manifiesto una conducta ilícita continuada, constatándose un evidente riesgo de reiteración delictiva.

[OPCIONAL — incluir si procede]

(En caso de que no se haya convocado la comparecencia para decidir sobre la libertad o prisión)

El auto recurrido, al decretar la libertad sin fianza sin tan siquiera convocar a la comparecencia del artículo 505 de la LECRIM, infringe los presupuestos establecidos en el artículo 503 y 504 de la LECRIM, por lo que se interesa que se reforme la medida cautelar y se decrete la prisión provisional, tras la celebración de la comparecencia prevenida en el citado artículo 505 de la LECRIM.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias y por interpuesto en tiempo y forma el presente recurso de apelación contra el auto de fecha [FECHA], lo admita en un efecto, y que, puesto de manifiesto a las partes por plazo de cinco días, aleguen lo que estimen conveniente y, transcurrido el referido plazo, remita las actuaciones a la Audiencia Provincial para resolución.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO

Que designo los siguientes particulares para que sean remitidos a la Audiencia Provincial para la resolución del recurso, de acuerdo con lo establecido en el artículo 766.3 LECRIM: (2)

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) El recurso de apelación puede interponerse:

-Subsidiariamente con el de reforma.
-Por separado, primero reforma y luego apelación.
-Directamente, sin necesidad de interponer previamente recurso de reforma.

Interesa destacar esta posibilidad de presentar este recurso de forma separada al de reforma, ya que por regla general, salvo que la Ley no establezca lo contrario, es preceptivo presentar con carácter previo o subsidiariamente el de reforma.

Plazo: dentro de los 5 días siguientes a la notificación de la resolución.

(2) En este escrito:

-Se señalarán los particulares que hayan de testimoniarse.
-Se acompañarán los documentos justificativos de las peticiones formuladas.

================================================================================
