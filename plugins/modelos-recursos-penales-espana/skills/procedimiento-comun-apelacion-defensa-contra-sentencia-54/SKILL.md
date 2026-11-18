---
name: procedimiento-comun-apelacion-defensa-contra-sentencia-54
description: "Redacta el escrito «Procedimiento común: apelación de la defensa contra la sentencia de conformidad» (formulario 54 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Procedimiento común: apelación de la defensa contra la sentencia de conformidad

> Formulario 0054 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- La aclaración no es un recurso. Se pide en los 2 días hábiles siguientes a la publicación de la sentencia e interrumpe el plazo para recurrir, que se cuenta desde la notificación del auto que la resuelve (art. 267.2 y 9 LOPJ).
- La apelación se presenta ante la AP que dictó la sentencia, pero la resuelve la Sala de lo Civil y Penal del TSJ, por los trámites de los arts. 790 a 792 LECrim (art. 846 ter.1 y 3 LECrim).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO (2 veces)
- [ ] FECHA (4 veces)
- [ ] PENA (2 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, seguido en»; «… con la calificación más grave hecha por»; «…mites del art. 655 LECRIM. Del examen de»; «…a conformidad pactada por esta parte con»; «…icilio para notificaciones el situado en»; «…ut supra" indicados. Firma de Abogado/a:»; «…Firma de Procurador/a:»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 655 LECRIM
- artículo 655.3 LECRIM
- art. 655.5 LECRIM
- artículo 790.2 de la LECrim

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

### Formulario 0054 · Procedimiento común: apelación de la defensa contra la sentencia de conformidad

- Año del modelo: 2025
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 1 llamadas a nota sin texto retiradas; 20 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 45) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito a la Audiencia Provincial de interposición por la defensa de recurso de apelación contra la sentencia de conformidad dictada en procedimiento común, por no respetar los requisitos de la conformidad, de acuerdo con el art. 655.7 LECRIM, según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según tengo ya acreditado en el sumario número [Nº DE PROCEDIMIENTO], seguido en [COMPLETAR], por el presunto delito de [DELITO], ante la Sala, como mejor proceda en derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte la sentencia dictada el día [FECHA] y estimándola perjudicial y gravosa para mi representado/a, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado interpongo en tiempo y forma RECURSO DE APELACIÓN para ante el Tribunal Superior de Justicia de [LOCALIDAD], al amparo de lo establecido en los arts. 655.7, 790 y 846 ter de la Ley de Enjuiciamiento Criminal, con base en las siguientes:

ALEGACIONES

PRIMERA

Al cumplir el trámite de calificación, esta parte manifestó su conformidad absoluta con la calificación más grave hecha por [COMPLETAR], y con la pena de que solicitó, considerando esta defensa que no era necesaria la continuación del juicio, habiéndose observado los trámites del art. 655 LECRIM.

Del examen de [COMPLETAR] se constata el escrupuloso cumplimiento de los trámites legales, debiendo destacar que la Audiencia no utilizó la vía a la que le autoriza el artículo 655.3 LECRIM para desvincularse [NOTA DE REVISIÓN (comprobar): Desde el 3-4-2025 (LO 1/2025) el control de la calificación y de la pena conformadas figura en el art. 655.1, párrafo tercero; el art. 655.3 regula la información al acusado y las dudas sobre la libertad de su conformidad. Fuente: LECrim, BOE-A-1882-6036, art. 655 (redacción LO 1/2025, BOE-A-2025-76).] de la conformidad pactada por esta parte con [COMPLETAR] y dictó sentencia de conformidad.

SEGUNDA

La sentencia de conformidad recurrida impone a mi representado/a la pena de [PENA] por un delito de [DELITO], superior a la conformada, infringiendo manifiestamente el art. 655.5 LECRIM que establece que debe dictarse sentencia según la calificación mutuamente aceptada, sin que pueda imponer pena mayor que la solicitada.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita, y tenga por interpuesto recurso de apelación contra la sentencia de fecha [FECHA] y, previos los trámites legales, remita las actuaciones al Tribunal Superior de Justicia de para que, estimando el recurso, revoque la apelada, dictando otra sentencia de conformidad con la manifestada por la defensa, imponiendo la pena de [PENA].

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: que al amparo de lo dispuesto en el artículo 790.2 de la LECrim., designo como domicilio para notificaciones el situado en [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SALA: que tenga por hecha la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a: [COMPLETAR]

Firma de Procurador/a: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) Sería recomendable presentar primero una solicitud de aclaración de sentencia (art. 267 LOPJ). Este recurso se presenta: * Ante: la AP que dictó la resolución impugnada. * En el plazo de 10 días a partir del siguiente al de la notificación de la sentencia. Durante este período se hallarán las actuaciones en la Oficina judicial a disposición de las partes, las cuales en el plazo de los 3 días siguientes a la notificación de la sentencia podrán solicitar copia de los soportes en los que se hayan grabado las sesiones, con suspensión del plazo para la interposición del recurso. El cómputo del plazo se reanudará una vez hayan sido entregadas las copias solicitadas

[NOTA DE REVISIÓN: La aclaración no es un recurso. Se pide en los 2 días hábiles siguientes a la publicación de la sentencia e interrumpe el plazo para recurrir, que se cuenta desde la notificación del auto que la resuelve (art. 267.2 y 9 LOPJ).]

[NOTA DE REVISIÓN: La apelación se presenta ante la AP que dictó la sentencia, pero la resuelve la Sala de lo Civil y Penal del TSJ, por los trámites de los arts. 790 a 792 LECrim (art. 846 ter.1 y 3 LECrim).]
