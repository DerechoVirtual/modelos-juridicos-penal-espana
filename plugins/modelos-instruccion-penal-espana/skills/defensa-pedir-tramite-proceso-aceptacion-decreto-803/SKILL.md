---
name: defensa-pedir-tramite-proceso-aceptacion-decreto-803
description: "Redacta el escrito «Defensa: pedir que se tramite por el proceso por aceptación de decreto» (formulario 803 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Defensa: pedir que se tramite por el proceso por aceptación de decreto

> Formulario 0803 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] DELITO
- [ ] Nº DE PROCEDIMIENTO
- [ ] IMPORTE
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…trabajos en beneficio de la comunidad de»

## Elecciones que hay que hacer

- multa / trabajos en beneficio de la comunidad / prisión que no exceda de un año y que pueda ser suspendida de conformidad con lo dispuesto en el art. 80 CP

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 801 LECRIM
- artículo 80 del Código Penal
- art. 80 CP

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

### Formulario 0803 · Defensa: pedir que se tramite por el proceso por aceptación de decreto

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 desplegables convertidos en elección en blanco; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la defensa en un procedimiento abreviado solicitando que la Fiscalía inste el proceso por aceptación de decreto del art. 803 bis a de la LECRIM, porque le interesa más que la conformidad en el procedimiento abreviado, ya que ello no lleva rebaja de la pena, y la vía del proceso por aceptación de decreto permite la imposición de penal de multa o TBC, en vez de prisión, aunque estas penas no estén previstas en el tipo penal sobre el que versa el proceso.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento / por el supuesto delito de [DELITO] del art. CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, teniendo conocimiento de la incoación de unas diligencias previas nº [Nº DE PROCEDIMIENTO] y por la vía del art. 803 bis a LECRIM, solicito la tramitación del proceso por aceptación de decreto, interesando se dé traslado al Ministerio Fiscal de la presente al no haberse tramitado las diligencias como urgentes y no haber podido verificar la conformidad privilegiada de rebaja de un tercio de la pena que prevé el art. 801 LECRIM. (1)

Concurren los presupuestos del art. 803 bis a LECRIM, dado que el delito que es objeto de investigación es el del art. CP y por ello:

1.º Que el delito esté castigado con pena de multa o de trabajos en beneficio de la comunidad o con pena de prisión que no exceda de un año y que pueda ser suspendida de conformidad con lo dispuesto en el artículo 80 del Código Penal, con o sin privación del derecho a conducir vehículos a motor y ciclomotores.
2.º Que el Ministerio Fiscal entienda que la pena en concreto aplicable es la pena de multa o trabajos en beneficio de la comunidad y, en su caso, la pena de privación del derecho a conducir vehículos a motor y ciclomotores.
3.º Que no esté personada acusación popular o particular en la causa.

En este sentido, la defensa solicita se dé traslado del presente escrito a la Fiscalía para que sea ésta la que inste el proceso por aceptación de decreto del art. 803 bis a LECRIM, en base a lo dispuesto y con el contenido del art. 803 bis c LECRIM.

Al estar sancionado el delito del art. CP con pena de [ELEGIR: multa / trabajos en beneficio de la comunidad / prisión que no exceda de un año y que pueda ser suspendida de conformidad con lo dispuesto en el art. 80 CP] es viable que se aplique esta vía y que la pena interesada por la Fiscalía sea la de multa de [IMPORTE], dada la ausencia de actividad laboral del/de la acusado/a o de trabajos en beneficio de la comunidad de [COMPLETAR] y en cualquier caso la privación del permiso de conducir por tiempo de [DURACIÓN] al posibilitarlo el art. 803 bis a 2º LECRIM.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite y por interesado el traslado a la Fiscalía en los términos interesados, a fin de que se dicte auto por este órgano judicial y se me cite a la comparecencia prevista en el art. 803 bis f LECRIM, a fin de aceptar la propuesta contenida en el decreto.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de acusado/a:

NOTAS DEL FORMULARIO

(1) La ventaja de este sistema es que se evita el acusado la aplicación de la pena de prisión y su régimen de suspensión de ejecución de pena, pasando por una pena de multa o TBC que incluso puede no estar prevista como alternativa en el delito de que se trate y puede utilizarse esta vía del proceso por aceptación de decreto previsto a instancia de la fiscalía para hechos no graves y que reúnan las características del art. 803 bis a LECRIM.

Puede utilizarse esta vía para cuando este órgano judicial no haya tramitado las diligencias como urgentes y el abogado del acusado no quiera acudir a la conformidad en procedimiento abreviado, ya que ello no lleva rebaja penal y esta vía del art. 803 bis a LECRIM permite la imposición de pena alternativa de multa o TBC, aunque no estén previstas en el tipo penal.

================================================================================
