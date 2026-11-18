---
name: pedir-rebaja-fianza-responsabilidad-civil-477
description: "Redacta el escrito «Pedir la rebaja de la fianza por responsabilidad civil» (formulario 477 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la rebaja de la fianza por responsabilidad civil

> Formulario 0477 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] IMPORTE (5 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…legado frente a los daños reclamados que»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 612 LECRIM
- art. 783.3 LECRIM
- artículo 612 de la Ley de Enjuiciamiento Criminal
- art. 596 LECRIM
- art. 783.2 LECRIM

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

### Formulario 0477 · Pedir la rebaja de la fianza por responsabilidad civil

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se solicita al instructor que baje la cuantía de la fianza solicitada para hacer frente a las responsabilidades civiles que puedan derivarse de la comisión del hecho delictivo, por la vía del art. 612 LECRIM, ya que de la instrucción se desprende que la cantidad fijada es desproporcionada.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según tengo acreditado en las Diligencias Previas del Procedimiento Abreviado núm. [Nº DE PROCEDIMIENTO] que se tramitan en este órgano judicial, comparezco y, como mejor proceda en Derecho, DIGO:

PRIMERO.- Que con fecha [FECHA] se ha dictado auto por el que se acordaba requerir a mi representado/a al abono de la fianza por importe de [IMPORTE] euros como consecuencia de las responsabilidades civiles que pudieran fijarse en el presente procedimiento y, en el supuesto de que dicha fianza no fuese satisfecha, el embargo de bienes bastantes en cuantía equivalente a la de la fianza.

SEGUNDO.- No se ha dictado en el presente caso auto de apertura de juicio oral del art. 783.3 LECRIM que es donde, en base al apartado 2º, se fijarán las responsabilidades civiles y se exigirá fianza al acusado/a, ya que este auto sí que es irrecurrible. (1)

TERCERO.- Se han practicado diligencias de investigación y aportado facturas de [IMPORTE] euros, lo que evidencia que hay un exceso en la cuantificación de la fianza, ya que se ha alegado frente a los daños reclamados que [COMPLETAR]. Y, por ello, la cuantía fijada es desproporcionada y no ajustada a la realidad, ya que supondría un exceso en la exigencia consignativa alejado absolutamente del quantum de la responsabilidad civil que, en caso de condena, pudiera fijarse y sin que ello suponga aceptación alguna de la responsabilidad penal, pero sí necesidad de que el principio de proporcionalidad se aplique en las reclamaciones civiles por fianzas. En su defecto, habría un exceso de embargo.

Por ello, habida cuenta que del resultado de las diligencias de investigación practicadas hasta la fecha cabe inferir que el importe de las responsabilidades pecuniarias que pudieran derivarse del delito que se imputa a mi representado/a no va a superar los [IMPORTE] euros, esta representación, de conformidad con lo establecido en el artículo 612 de la Ley de Enjuiciamiento Criminal, interesa que el importe de la fianza y el embargo se reduzca hasta los [IMPORTE] euros, admitiendo su viabilidad el art. 596 LECRIM de aplicación general, salvo el supuesto del art. 783.3 LECRIM en el P.A.

En su virtud,

SUPLICO A LA SECCIÓN

Que tenga por hechas las manifestaciones contenidas en el presente escrito y en las copias que se acompañan y acuerde la práctica de las diligencias interesadas, dándose al procedimiento el curso legal que corresponda y se reduzca la fianza en la cuantía que se estime oportuna ofreciéndose la suma de [IMPORTE] euros.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Suelen darse situaciones en las que la fianza se acuerda en el P.A. en el auto de apertura de juicio oral, en base al dictado del art. 783.2 LECRIM y entonces, este auto es irrecurrible, por lo que si se interpone recurso contra la fianza se inadmitirá, pero ello no obsta a que se vuelva a plantear la petición ante el juez de lo penal o la Audiencia Provincial, es decir, ante el órgano de enjuiciamiento, pero no como recurso, sino como escrito frente a esta medida instando su rebaja.

================================================================================
