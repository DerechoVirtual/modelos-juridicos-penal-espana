---
name: calumnias-investigado-pide-probar-verdad-imputacion-98
description: "Redacta el escrito «Calumnias: el investigado pide probar la verdad de la imputación (exceptio veritatis)» (formulario 98 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Calumnias: el investigado pide probar la verdad de la imputación (exceptio veritatis)

> Formulario 0098 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO (2 veces)
- [ ] Nº DE DOCUMENTO
- [ ] LOCALIDAD
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] FECHA (3 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…y que se reciba declaración testifical a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 205 CP
- art. 808 de la LECrim
- art. 808 LECRIM

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

### Formulario 0098 · Calumnias: el investigado pide probar la verdad de la imputación (exceptio veritatis)

- Año del modelo: 2023
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 14 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO, Nº DE DOCUMENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], parte querellada en este proceso, según consta en escritura de poder especial otorgado a mi favor, mediante

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada.

Actuando bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [LOCALIDAD] colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y, como mejor en Derecho proceda, DIGO:

1) Que esta parte ha tenido conocimiento de la querella por presuntas calumnias inferidas verbalmente del art. 205 CP, deducida por la representación de D./Dña. [NOMBRE Y APELLIDOS], al haberle sido entregada copia de la misma en fecha [FECHA] y citado a juicio verbal para el día [FECHA].
2) Que de la lectura del escrito de querella parece ser que las presuntas calumnias que se imputan a mi representado/a se derivan de que se alega que éste manifestó que el querellante «había agredido sexualmente aen diversas ocasiones».
3) Que, sin aceptar que mi representado/a vertiera dicha expresión en los términos en que está relatada en la querella, interesa al derecho de esta parte probar la veracidad de sus imputaciones, al amparo del art. 808 de la LECrim, a cuyo efecto se solicita que se requiera al/la querellante para que concrete, con toda precisión y claridad, las expresiones que se profirieron, según su versión, interesando desde este momento la suspensión del juicio verbal en tanto no se cumplimente el requerimiento.
4) Que, al amparo del mismo art. 808 LECRIM, interesa al derecho de esta parte que se practiquen diligencias tendentes a preparar la prueba sobre la excepción de verdad consistentes en que se libre exhorto a la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] para que remita copia auténtica de las diligencias previas seguidas contra el querellante por presunto delito de abusos sexuales contra [ACTO O RESOLUCIÓN], y que se reciba declaración testifical a [COMPLETAR] sobre los hechos.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta querella, con sus copias respectivas, se sirva admitirla a trámite, y, en su virtud, me tenga por personado/a y parte en defensa del/de la querellado/a, acordando la suspensión del juicio verbal, y requiriendo al/a la querellante para que determine, con toda claridad y precisión, los hechos y circunstancias de la imputación, ordenando al tiempo la práctica de las diligencias propuestas en el apartado 4 de este escrito.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
