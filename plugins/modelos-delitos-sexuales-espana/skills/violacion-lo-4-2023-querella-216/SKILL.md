---
name: violacion-lo-4-2023-querella-216
description: "Redacta el escrito «Violación (LO 4/2023): querella» (formulario 216 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación (LO 4/2023): querella

> Formulario 0216 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] ESTADO CIVIL
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…iamiento Criminal y siguientes contra D.»; «…dentro de este partido, concretamente en»; «…o, mayor de edad, de estado civil con D.»; «…, con domicilio en la»; «… de especial vulnerabilidad por razón de»; «…con respecto a la víctima.»; «…do, para llevar a cabo la violación, usó»; «…ue el querellado suministró a la víctima»; «…, - Dª»; «…e ellos informe de lesiones del hospital»; «… la situación personal del querellado D.»

## Elecciones que hay que hacer

- Instrucción / Violencia sobre la Mujer
- precedida / acompañada
- una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio
- es / ha sido
- esposa / pareja
- convivencia / parentesco / superioridad
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia / Violación con intimidación / Violación a víctima con voluntad anulada / Violación con abuso de superioridad / Violación aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o con voluntad anulada / Violación con abuso de superioridad o aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (11)

Inclúyelos solo si encajan en los hechos:

- Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y…
- Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la violación fue [ELEGIR: precedida / acomp…
- Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de esp…
- Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [E…
- Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la violación el querellado se ha p…
- Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el querellado, para llevar a cabo la vi…
- Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el querellado suministró a la víctima […
- 1.- Declaración del querellado sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial:…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Entre ellos informe de…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 26.1 a) de la Ley 4/2015
- art. 681.3 LECRIM
- art. 544 bis LECRIM
- art. 281 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0216 · Violación (LO 4/2023): querella

- Año del modelo: 2022
- Revisión 17-11-2026: 5 llamadas a nota sin texto retiradas; 5 desplegables y casillas convertidos en elección en blanco; 3 desplegables convertidos en elección en blanco; 3 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 11 párrafos opcionales señalados; 31 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

A la Sección de Violencia sobre la Mujer que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D. [COMPLETAR], a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de [ELEGIR: Instrucción / Violencia sobre la Mujer] del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- La querellante es Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil con D. [COMPLETAR], de profesión [PROFESIÓN], vecina de [LOCALIDAD], con domicilio en la [COMPLETAR].

TERCERO.- El querellado es D. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino de [LOCALIDAD], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia / Violación con intimidación / Violación a víctima con voluntad anulada / Violación con abuso de superioridad / Violación aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original]

QUINTO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o con voluntad anulada / Violación con abuso de superioridad o aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y APELLIDOS] y D/Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la violación fue [ELEGIR: precedida / acompañada] de [ELEGIR: una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de especial vulnerabilidad por razón de [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [ELEGIR: esposa / pareja].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la violación el querellado se ha prevalido de una situación o relación de [ELEGIR: convivencia / parentesco / superioridad] con respecto a la víctima. [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el querellado, para llevar a cabo la violación, usó [COMPLETAR]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el querellado suministró a la víctima [COMPLETAR] que le anuló su voluntad para luego violarla.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

- Dª [COMPLETAR] víctima de los hechos, a fin de que se le interrogue sobre los mismos.

Se interesa que la declaración de la víctima de delito sexual sea grabada en la instrucción y reproducida en sede judicial, en base al art. 26.1 a) de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito que señala que: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: a) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal."

- D./Dña. [NOMBRE Y APELLIDOS] amigo/a que estuvo en la cena con la querellante y el querellado al/a la que luego contó lo sucedido.

- D./Dña. [NOMBRE Y APELLIDOS] que la recogió en la carretera.

[OPCIONAL — incluir si procede]

.- Pericial:

- Que sea reconocida por el/la médico forense D./Dña. [NOMBRE Y APELLIDOS].
- Que se realice examen pericial del semen y se compare con el ADN del querellado.
- Que se realice examen pericial del grado de enfermedad mental o vulnerabilidad de la víctima

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Entre ellos informe de lesiones del hospital [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del querellado D. [COMPLETAR], disponiendo se proceda a la detención y prisión provisional del querellado, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la querellante, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares.

Del mismo modo, y para el supuesto de que pudiera adoptarse la decisión judicial de libertad provisional y en base a lo dispuesto en el art. 544 bis LECRIM, se interesa se acuerde mediante resolución motivada una orden de alejamiento y la utilización de dispositivos telemáticos para el control de su cumplimiento.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
