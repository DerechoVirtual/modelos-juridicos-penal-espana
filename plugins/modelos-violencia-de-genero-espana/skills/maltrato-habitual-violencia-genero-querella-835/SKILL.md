---
name: maltrato-habitual-violencia-genero-querella-835
description: "Redacta el escrito «Maltrato habitual (violencia de género): querella» (formulario 835 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Maltrato habitual (violencia de género): querella

> Formulario 0835 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (3 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…termina la competencia, concretamente en»; «…. TERCERO.- El querellado es D»; «…con el querellado D.»; «…y su hijo mayor de edad»; «… la situación personal del querellado D.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del querellado sobre los hechos de la querella.…
- .- Testifical, declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental, teniendo por reproducido los documentos aportados, en concreto el informe pericial psicológico …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 173.2 CP
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 89.5 LOPJ
- artículo 173.2 del Código Penal
- art. 544 ter de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 24.1 LEC
- art. 4 LEC
- art. 24.2 LEC
- art. 77 RDL 6/2023

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

### Formulario 0835 · Maltrato habitual (violencia de género): querella

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 7 huecos del original que se habían perdido sin marca, marcados (IMPORTE, NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que una mujer presenta querella contra su pareja o marido (ex pareja o ex marido) por malos tratos habituales, que pueden ser constitutivos de un delito de violencia de género del art. 173.2 CP.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

A la Sección de Violencia sobre la Mujer que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D. por el delito de maltrato habitual del art. 173.2 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes,

EXPONGO

PRIMERO.- Se presenta ante el Tribunal de Instancia de esta ciudad para su reparto a la Sección de Violencia sobre la Mujer que por turno corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal y artículo 89.5 LOPJ, al haber ocurrido los hechos dentro de este partido, y, sobre todo, ser este el último domicilio conyugal de las partes que es el que determina la competencia, concretamente en [COMPLETAR].

SEGUNDO.- La querellante es Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, casada, de profesión [PROFESIÓN], vecina de [LOCALIDAD], con domicilio en [LOCALIDAD].

TERCERO.- El querellado es D [COMPLETAR], mayor de edad, casado, de profesión [PROFESIÓN], vecino de [LOCALIDAD], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

La querellante contrajo matrimonio en fecha [FECHA] con el querellado D. [COMPLETAR]. Desde el comienzo de su relación matrimonial hasta la fecha ha sido sometida a constantes situaciones de malos tratos y humillaciones por parte del querellado. Unas veces delante de sus hijos cuando eran menores de edad y otras en presencia de su madre Dña. [NOMBRE Y APELLIDOS] y hermana Dña. [NOMBRE Y APELLIDOS]. En el último año estas agresiones y situaciones de maltrato físico y psicológico (2) se han incrementado hasta el punto de hacer la vida insostenible, y producirse algunos de ellos en presencia de sus hijos menores de edad, lo que motivó que tuviera que acudir a la consulta de un psicólogo que emitió un informe en fecha [FECHA] que consta aportado como documento nº 1 a la querella donde se refleja el cuadro de estrés causado por el síndrome de "mujer maltratada" al haber llegado a un punto de afectación a la psique que es integrante de un maltrato habitual, como se evidencia por las continuas agresiones de que ha sido víctima, y psicológico. De las agresiones no existen partes médicos porque quiso ocultarlo, pero sí se hizo en algunos casos a presencia de su madre Dña. [NOMBRE Y APELLIDOS] y hermana Dña. [NOMBRE Y APELLIDOS] y su hijo mayor de edad [COMPLETAR].

Toda esta situación le ha causado una fuerte situación de estrés y depresión que se coteja en el informe pericial citado.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de maltrato habitual que define el artículo 173.2 del Código Penal, del que presuntamente es culpable el querellado.

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical, declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

- Dña. [NOMBRE Y APELLIDOS] madre de la querellante.

- D./Dña. [NOMBRE Y APELLIDOS], hermano/a de la querellante.

- D./Dña. [NOMBRE Y APELLIDOS], hijo/a de la querellante y del querellado, mayor de edad.

[OPCIONAL — incluir si procede]

.- Pericial, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS] autor/a del dictamen pericial, para que se ratifique a presencia judicial.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados, en concreto el informe pericial psicológico emitido por D./Dña. [NOMBRE Y APELLIDOS]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del querellado D. [COMPLETAR], disponiendo se proceda a la detención y prisión provisional del querellado, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Solicito que, en base al art. 544 ter de la Ley de Enjuiciamiento Criminal, se convoque la comparecencia del apartado 4 para la concesión de la orden de protección y la adopción de las medidas civiles procedentes.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el juez.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se alega maltrato psicológico o físico habitual es precisa la práctica de diligencias de investigación que impiden su tramitación rápidá que en los casos de la violencia de género se desaconseja, aunque el art. 795.1. 2º.a) LECrim permite acudir al juicio rápido cuando se trate de alguno de los siguientes delitos:

a) Delitos de lesiones, coacciones, amenazas o violencia física o psíquica habitual, cometidos contra las personas a que se refiere el artículo 173.2 del Código Penal.

No obstante, no es aconsejable porque se corre el riesgo de no poder reunir y practicar en la investigación judicial todas las pruebas que se precisan.

================================================================================
