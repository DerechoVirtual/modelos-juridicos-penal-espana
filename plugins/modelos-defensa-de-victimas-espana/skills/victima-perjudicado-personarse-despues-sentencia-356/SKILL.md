---
name: victima-perjudicado-personarse-despues-sentencia-356
description: "Redacta el escrito «Víctima o perjudicado: personarse después de la sentencia» (formulario 356 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima o perjudicado: personarse después de la sentencia

> Formulario 0356 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Los arts. 109 bis.1 y 110 LECrim solo permiten personarse, como máximo, hasta el inicio del juicio oral, adhiriéndose a una acusación. La ley no prevé la personación después de la sentencia para recurrirla: esa posibilidad se apoya solo en la jurisprudencia que cita el modelo.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] Nº DE DOCUMENTO
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»; «… siguiente tenor literal del fallo: "Que»

## Elecciones que hay que hacer

- Sección / Tribunal
- esta Sección / esta sección de la AP
- de la víctima / del perjudicado
- víctima / perjudicado

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Ley Orgánica 8/2021
- Ley 4/2015

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

### Formulario 0356 · Víctima o perjudicado: personarse después de la sentencia

- Año del modelo: 2021
- Revisión 17-11-2026: 4 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (Nº DE DOCUMENTO, Nº DE PROCEDIMIENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 164) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la víctima o el perjudicado se personan en un procedimiento después de dictada sentencia, para poder recurrirla, conforme a los arts. 109 bis y 110 LECRIM, según la redacción dada por LO 8/2021, de protección integral a la infancia y la adolescencia frente a la violencia, con entrada en vigor el 25 de junio de 2021 y la STS 251/2021 de 17 de marzo Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en representación de D./Dña. [NOMBRE Y APELLIDOS], como consta en escritura de poder inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme, acompañando certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada, comparezco ante [ELEGIR: Sección / Tribunal] y como mejor proceda en derecho, DIGO:

Que se ha dictado sentencia en [ELEGIR: esta Sección / esta sección de la AP] en juicio oral nº [Nº DE PROCEDIMIENTO] contra D./Dña. [NOMBRE Y APELLIDOS], por hechos constitutivos de delito de [DELITO] del artículo [COMPLETAR] CP con el siguiente tenor literal del fallo:

"Que [COMPLETAR] "

Que, en uso del derecho reconocido en los artículos 101, 109 bis(En el caso de víctima del delito), 110 y 761 de la Ley de Enjuiciamiento Criminal, tras la modificación operada en la misma por la Ley Orgánica 8/2021, de protección de la infancia y la adolescencia contra la violencia pero, sobre todo, a raíz de la STS 251/2021 de 17 de marzo, Rec. 2439/2019, que recoge que la víctima se puede personar una vez dictada sentencia para recurrirla si no está de acuerdo con su dictado, en base a las amplias opciones que le otorga la Ley 4/2015 del estatuto de la víctima del delito, me persono en el presente juicio oral para que se me notifique la sentencia para valorar mi derecho a recurrirla, comenzando el plazo para ello desde mi notificación.

Nótese que en materia de personación [ELEGIR: de la víctima / del perjudicado] por el delito ha habido jurisprudencia del Tribunal Supremo (STS 18/2018 de 17 Ene. 2018, Rec. 625/2017) proclive a «ensanchar» los contornos temporales de este acto de personación de ambos, siempre y cuando no se postule retrotraer actuaciones, pero sin que tenga que haber un impedimento al ejercicio de la personación cuando se considere oportuno.

En el presente caso, por ello, solo se postula la admisión de personación en concepto de [ELEGIR: víctima / perjudicado], sin retrotraer las actuaciones y a los efectos de que se notifique la sentencia para valorar, en su caso, la posibilidad de recurrirla.

Por lo expuesto,

SUPLICO A LA SECCIÓN
A LA AUDIENCIA

Que tenga por presentado este escrito y documentos adjuntos, los admita, teniéndome por personado en la representación de D./Dña. [NOMBRE Y APELLIDOS] y acuerde se nos notifique la sentencia para valorar, en su caso, la posibilidad de recurrirla.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:	Firma del cliente: (En caso de no adjuntar poder o designación de turno de oficio)

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: Los arts. 109 bis.1 y 110 LECrim solo permiten personarse, como máximo, hasta el inicio del juicio oral, adhiriéndose a una acusación. La ley no prevé la personación después de la sentencia para recurrirla: esa posibilidad se apoya solo en la jurisprudencia que cita el modelo.]
