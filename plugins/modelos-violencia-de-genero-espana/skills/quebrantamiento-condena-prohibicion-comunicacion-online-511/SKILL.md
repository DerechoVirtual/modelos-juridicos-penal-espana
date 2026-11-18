---
name: quebrantamiento-condena-prohibicion-comunicacion-online-511
description: "Redacta el escrito «Quebrantamiento de condena (prohibición de comunicación online): querella» (formulario 511 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Quebrantamiento de condena (prohibición de comunicación online): querella

> Formulario 0511 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (3 veces)
- [ ] NÚMERO (2 veces)
- [ ] SEDE
- [ ] DELITO
- [ ] PENA
- [ ] IMPORTE (4 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a querellado/a remitió por la red social»; «…a querellante diciéndole por escrito que»; «…ue se requiera al prestador del servicio»; «…ique la titularidad del perfil de la red»; «…con el Nick»

## Elecciones que hay que hacer

- no interponerse recurso / confirmación de la sentencia por la Audiencia Provincial
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el ofendido no es alguno de los enumerados en el art. 173.2 CP o no lo es por alguno de los delitos del art. 89.5 h LOPJ / Si el ofendido es alguno de los enumerados en el art. 173.2 CP o lo es por alguno de los delitos del art. 89.5 h LOPJ — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], que ha visto el mensaje en la red social.…
- .- Pericial informática para el supuesto de que se impugne la prueba digital por la defensa acerca de la reali…
- .- Documental.…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la liberta…
- .- Se reitere una nueva orden de alejamiento respecto del/de la querellante, por la vía del art. 544 bis LECRI…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 173.2 CP
- art. 544 bis LECRIM
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 89.5 h) LOPJ
- art. 89.5 g) LOPJ
- art. 468.1 CP
- art. 14.6 d) LECRIM
- art. 14.7 LECRIM
- art. 4 LEC
- art. 24.2 LEC
- art. 544 ter LECRIM

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

### Formulario 0511 · Quebrantamiento de condena (prohibición de comunicación online): querella

- Año del modelo: 2019
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (7); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 bloques de alternativas señalados; 7 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de quebrantamiento de condena del art. 468 CP, por escribir el querellado un mensaje en una red social cuando había sido condenado a prohibición de comunicación con la víctima y esto incluye cualquier medio, también los tecnológicos o informáticos.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción que por turno de reparto corresponda

A la Sección de Violencia sobre la Mujer que por turno de reparto corresponda (1)

A la Sección de Violencia contra la Infancia y la Adolescencia que por turno de reparto corresponda

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (2),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de quebrantamiento de condena del art. 468 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 y concordantes de la LECRIM,

EXPONGO

PRIMERO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el ofendido no es alguno de los enumerados en el art. 173.2 CP o no lo es por alguno de los delitos del art. 89.5 h LOPJ / Si el ofendido es alguno de los enumerados en el art. 173.2 CP o lo es por alguno de los delitos del art. 89.5 h LOPJ — el texto de cada opción no venía en el formulario original]

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS], como queda dicho, mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (4)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] se dictó sentencia en juicio oral nº [NÚMERO] de la Sección de lo penal nº [NÚMERO] del Tribunal de Instancia de [SEDE] por la que se condenaba al/a la querellado/a por la comisión del delito de [DELITO] a la pena de [PENA] de prisión y a la prohibición de comunicación por cualquier medio, incluidos los tecnológicos, y a que no se acercara a menos de 500 metros de la víctima en su domicilio, o lugar de trabajo o cualquiera que frecuente.

La sentencia devino firme por [ELEGIR: no interponerse recurso / confirmación de la sentencia por la Audiencia Provincial] y le había sido notificada personalmente al/a la querellado/a, llevando a cabo las advertencias oportunas en la diligencia acerca de las consecuencias del incumplimiento de las prohibiciones fijadas en la sentencia.

Con fecha [FECHA] el/la querellado/a remitió por la red social [COMPLETAR] un mensaje de texto al/a la querellante diciéndole por escrito que [COMPLETAR] quebrantando, con ello, la orden de prohibición de comunicación impuesta en sentencia.

QUINTO.- Tales hechos son constitutivos del delito continuado de quebrantamiento de condena del art. 468 CP. (5)

SEXTO.- Se interesa se indemnice al/a la querellante con la suma de [IMPORTE] euros por el daño moral causado ante el estado de pánico y temor provocado por la recepción del mensaje, cuando se le había advertido al/a la querellado/a que no podría hacerlo.

SÉPTIMO- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- Declaración del/de la querellante sobre los hechos objeto de la querella

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que ha visto el mensaje en la red social.

[OPCIONAL — incluir si procede]

.- Pericial informática para el supuesto de que se impugne la prueba digital por la defensa acerca de la realidad de la existencia de ese mensaje en la red digital y la identidad del/de la querellado/a en el mismo. (6)

[OPCIONAL — incluir si procede]

.- Documental.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

- Acta notarial del/de la notario D./Dña. [NOMBRE Y APELLIDOS] de la constancia en la red social del contenido del mensaje y la mención en la red social de la identidad de su autor/a.

- Pantallazo de la red social con el contenido del mensaje y adveración por el/la Letrado/a de la Administración de Justicia entrando en la citada red social al objeto de la comprobación real de su existencia.

- Testimonio de la sentencia del Juez de lo penal y la diligencia de notificación y requerimiento a el/la querellado/a acerca de la prohibición de comunicación y, por ello, vigencia de la orden al momento de enviar esa comunicación por redes sociales, cuando estaba condenado/a a no hacerlo.

- Que se requiera al prestador del servicio [COMPLETAR] a fin de que certifique la titularidad del perfil de la red [COMPLETAR] con el Nick [COMPLETAR].

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE] euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

[OPCIONAL — incluir si procede]

.- Se reitere una nueva orden de alejamiento respecto del/de la querellante, por la vía del art. 544 bis LECRIM, a fin de que no se acerque a menos de 500 metros sea cual sea el lugar en el que el/la querellante se encuentre y nueva prohibición de comunicación por cualquier medio, incluidos los tecnológicos o informáticos. (7)

OCTAVO.- Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La competencia para la instrucción del delito de quebrantamiento de condena, cuando la persona ofendida sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por una análoga relación de afectividad aun sin convivencia, así como los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad con medidas de apoyo que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, así como cuando la persona ofendida lo sea por alguno de los delitos señalados en el art. 89.5 h) LOPJ, es de la Sección de Violencia sobre la Mujer (art. 89.5 g) LOPJ). Si no se tratase de estas víctimas, la instrucción correspondería a una Sección de instrucción y se aplicaría el art. 468.1 CP.

Si la víctima es niño, niña o adolescente el órgano competente es la Sección de Violencia contra la Infancia y Adolescencia, si la hay (art. 14.6 d) LECRIM y art. 89 bis 5 d) LOPJ). Téngase en cuenta que, si se trata de hechos que también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia le corresponderá en todo caso a la segunda (art. 14.7 LECRIM y art. 89 bis 7 LOPJ).

Es aplicable aquí el Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005, que acoge el principio de ubicuidad, de tal modo que el delito se comete en todas las jurisdicciones en las que se haya realizado algún elemento del tipo, en consecuencia, el Juez de cualquiera de ellas que primero haya iniciado las actuaciones procesales será, en principio, competente para la instrucción de la causa.

(2) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Juez de Instrucción.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(3) Para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Juez de Instrucción.

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(4) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(5) Si existe relación entre querellante y querellado de las que cita el art. 173.2 CP se aplicaría el apartado 2º del art. 468 CP y si no existe esa relación previa el art. 468.1 CP.

(6) Es positivo aportar pericial informática, dado que nos encontramos con la aportación de prueba digital en el proceso penal y ello exige que, si se impugna por la defensa, la acusación debería aportar pericial informática. Si no lo hace con la querella debería hacerlo tras impugnarlo la defensa en su escrito de defensa.

(7) El hecho de que el origen del caso sea un quebrantamiento de condena no impide que se vuelva a interesar la medida cautelar del alejamiento por el art. 544 bis LECRIM y, si se tratara de pareja o ex pareja por el art. 544 ter LECRIM, dado que la pena anterior puede expirar en su plazo y de esta manera se abre uno nuevo en este, a fin de que hasta el juicio subsista una nueva medida cautelar de alejamiento y prohibición de comunicación.

Es positivo que cuando se interesa por la acusación la pena de prohibición de comunicación se incluya la adición de que esa prohibición se extiende" a cualquier medio, incluidos los tecnológicos o informáticos", para no dejar abierta la duda de que la prohibición se extiende a estos casos.

================================================================================
