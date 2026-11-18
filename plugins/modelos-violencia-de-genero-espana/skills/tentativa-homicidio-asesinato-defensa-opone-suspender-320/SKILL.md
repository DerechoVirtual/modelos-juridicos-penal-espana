---
name: tentativa-homicidio-asesinato-defensa-opone-suspender-320
description: "Redacta el escrito «Tentativa de homicidio o asesinato: la defensa se opone a suspender la patria potestad» (formulario 320 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tentativa de homicidio o asesinato: la defensa se opone a suspender la patria potestad

> Formulario 0320 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] Nº DE DOCUMENTO
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, en representación de D.»; «…contra D.»; «…tipificado en el artículo»; «…ento, tutela, curatela o guarda de hecho»; «… dicho matrimonio nacieron dos hijos: 1º»; «…de [Nº] años de edad y el 2º»

## Elecciones que hay que hacer

- homicidio / asesinato

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 544 ter.3 LECRIM
- art. 544 ter.4 LECRIM
- artículo 544 ter.7 LECRIM
- artículo 158 del Código Civil
- Ley Orgánica 8/2021

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

### Formulario 0320 · Tentativa de homicidio o asesinato: la defensa se opone a suspender la patria potestad

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de D. [COMPLETAR], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia, que fue turnada a ese órgano judicial, por Dña. [NOMBRE Y APELLIDOS] contra D. [COMPLETAR], por la comisión de un delito de tentativa de [ELEGIR: homicidio / asesinato] tipificado en el artículo [COMPLETAR] CP, habiéndonos personado en las actuaciones por la defensa en escrito de fecha [FECHA] en las DP nº [Nº DE PROCEDIMIENTO]

Que para el supuesto de que por la vía del art. 544 ter.3 LECRIM se inste el dictado de la orden de protección y el juez acuerde la celebración de la audiencia previa del art. 544 ter.4 LECRIM, mediante el presente escrito formulo solicitud instando la no suspensión de la patria potestad como medida cautelar que se interesaría por la denunciante, en su caso.

ALEGACIONES

PRIMERA.- Señala el artículo 544 ter.7 LECRIM, en su redacción dada por la Ley Orgánica 8/2021 de protección de la infancia y adolescencia contra la violencia, que.

«Las medidas de naturaleza civil deberán ser solicitadas por la víctima o su representante legal, o bien por el Ministerio Fiscal cuando existan hijos menores o personas con la capacidad judicialmente modificada, determinando su régimen de cumplimiento y, si procediera, las medidas complementarias a ellas que fueran precisas, siempre que no hubieran sido previamente acordadas por un órgano del orden jurisdiccional civil, y sin perjuicio de las medidas previstas en el artículo 158 del Código Civil. Cuando existan menores o personas con discapacidad necesitadas de especial protección que convivan con la víctima y dependan de ella, el Juez deberá pronunciarse en todo caso, incluso de oficio, sobre la pertenencia de la adopción de las referidas medidas.

Estas medidas podrán consistir en la forma en que se ejercerá la patria potestad, acogimiento, tutela, curatela o guarda de hecho [COMPLETAR], atribución del uso y disfrute de la vivienda familiar, determinar el régimen de guarda y custodia, suspensión o mantenimiento del régimen de visitas, comunicación y estancia con los menores o personas con discapacidad necesitadas de especial protección, el régimen de prestación de alimentos, así como cualquier disposición que se considere oportuna a fin de apartarles de un peligro o de evitarles perjuicios».

SEGUNDA.- La denunciante Dña. contrajo matrimonio con el denunciado D. [NOMBRE Y APELLIDOS] en fecha [FECHA] como consta en el documento nº [Nº DE DOCUMENTO] aportado de la inscripción en el registro civil de [LOCALIDAD]. De dicho matrimonio nacieron dos hijos: 1º [COMPLETAR] de [Nº] años de edad y el 2º [COMPLETAR] de [Nº] años de edad. Por lo tanto, ambos menores de edad.

Por ello, y no habiendo procedimiento civil abierto de separación o divorcio, existe la vía del dictado de las medidas civiles en el auto resolviendo sobre la orden de protección que tendrán una vigencia temporal de 30 días hasta la presentación de la demanda de divorcio que se presentará ante este órgano judicial por la vía del párrafo 4º del artículo 544 ter.7 LECRIM [NOTA DE REVISIÓN: La LO 8/2021 intercaló en el art. 544 ter.7 LECrim un párrafo tercero sobre la suspensión del régimen de visitas; la vigencia de 30 días de las medidas civiles figura ahora en el párrafo cuarto. Fuente: LECrim, BOE-A-1882-6036, art. 544 ter.7 (redacción LO 8/2021, BOE-A-2021-9347).].

Pues bien, con independencia de negar la veracidad de los hechos que son objeto de la denuncia en este caso y ante la petición que se haga de suspensión de la patria potestad, interesamos la no adopción de la suspensión, habida cuenta que en "interés de los menores", que es el parámetro que la doctrina jurisprudencial requiere para la adopción de estas medidas, sería perjudicial para ellos impedir la relación con su padre, ya que los hechos se van a negar en esa audiencia o a lo largo del procedimiento, por no ser real el contenido de la denuncia, y romper esta relación mientras se sustancia el procedimiento sería construir una presunción de culpa no acorde con la buena relación que existe padre-hijos y que se rompería si mientras dure el procedimiento se adopta la drástica medida de la suspensión de la patria potestad, mucho más grave que la del régimen de visitas ex art. 544 ter 7 LECRIM, la cual estará prevista cuando conste notoriamente ese perjuicio de las relaciones para los menores, lo que no es el caso, ya que se niega de forma tajante la comisión del delito del que se acusa.

La adopción de esta medida conllevaría el dictado de una pena anticipada hasta la firmeza de la sentencia, la cual estamos convencidos de que será absolutoria.

Es cierto que el art. 544 quinquies LECRIM prevé la adopción de esta medida cautelar de suspensión de la patria potestad y que el art. 140 bis. 2 CP lo introduce como pena, pero este automatismo no puede predicarse sin más en el ámbito de las medidas cautelares, sino en sentencia y como pena, por cuanto la "anticipación" de la misma sin prueba y sin juicio supondría una indefensión patente al denunciado y un grave daño a unos hijos ante una denuncia que no es cierta y unos hechos que no han ocurrido, convirtiendo a los menores en víctimas del propio sistema y también en víctima del mismo a su padre si se adoptara la prohibición del ejercicio de la patria potestad.

Por ello, y para evitar esa ruptura temporal de las relaciones que perjudicaría a los menores que no tienen culpa de lo ocurrido, es por lo que:

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizada la oposición a la posible petición de suspensión de la patria potestad que pudiera llevarse a cabo por la denunciante, en interés de los menores.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
