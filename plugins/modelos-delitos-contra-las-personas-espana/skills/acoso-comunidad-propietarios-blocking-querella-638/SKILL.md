---
name: acoso-comunidad-propietarios-blocking-querella-638
description: "Redacta el escrito «Acoso en una comunidad de propietarios (blocking): querella» (formulario 638 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acoso en una comunidad de propietarios (blocking): querella

> Formulario 0638 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (18 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] CALLE (2 veces)
- [ ] AÑO
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…comunidad de propietarios»; «…. Desde aproximadamente el mes de»; «…- y»

## Elecciones que hay que hacer

- a la mujer / al marido
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - y [COMPLETAR] hijo/a del/de la querellante.…
- -D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] vecino/as del inmueble.…
- .- Pericial. Se aporta informe pericial del/de la perito médico D./Dña. [NOMBRE Y APELLIDOS] donde se incluye …
- .- Documental, aportando cartas depositadas en el buzón de correos por el/la querellado/a al objeto de que se …
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Dado la gravedad de los casos de acoso en comunidad por la convivencia, se interesa se adopte la medida cau…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 172 ter CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 de la LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 57.1 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC

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

### Formulario 0638 · Acoso en una comunidad de propietarios (blocking): querella

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 2 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 párrafos opcionales señalados; 34 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un vecino de una comunidad se querella contra otro vecino que le envía reiteradas notas amenazadoras, hechos que presentan los caracteres de un delito de acoso (blocking) del art. 172 ter CP.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS], por el delito del art. 172 ter CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 de la LECRIM y concordantes,

EXPONGO

PRIIMERO.-

Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] calle [CALLE].

TERCERO- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a es propietario/a del inmueble sito en la calle [CALLE] comunidad de propietarios [COMPLETAR]. Desde aproximadamente el mes de [COMPLETAR] del año [AÑO] hasta la fecha, este/a comunero/a lleva realizando actos de acoso y hostigamiento a la persona de mi mandante y a su familia mediante cartas que deposita en el buzón donde se hacen constar frases como: "hasta que no te vayas de esta comunidad no pararé..." "atente a las consecuencias". Estas cartas no llevan firma alguna, pero es evidente que son del/de la querellado/a porque constantemente llama a la puerta para que mi representado/a baje el volumen de la televisión, o que su familia hable más bajo, diciéndoles que a él/ella le molesta, o reprendiendo la forma en la que aparcan el vehículo en el parking, habiendo encontrado ya dos veces las cuatro ruedas pinchadas y sospechando la autoría del/de la querellado/a. En otras ocasiones, habiendo coincidido con él/ella en el ascensor, les ha advertido de que deberían marcharse del edificio y que no pararía hasta conseguirlo, con el reproche de que "le molesta" y que él/ella no quiere tener ningún vecino en su misma planta, porque le molestan los ruidos. En varias ocasiones se ha dirigido [ELEGIR: a la mujer / al marido] del/de la querellante D./Dña. [NOMBRE Y APELLIDOS], advirtiéndole de que "lo van a pagar caro" si no se van del edificio porque no les quiere ver por allí cerca de su casa, y que no quiere vecinos. En otros casos, les ha reprochado a los hijos del/de la querellante que suban con el perro en el ascensor, de malos modos, advirtiéndoles de que un día se iban a encontrar muerto al perro si siguen haciéndolo, habiendo llegado sus hijos a casa llorando por el temor a que el/la querellado/a cumpla su amenaza. Estas situaciones las han presenciado algunos/as vecinos/as como D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS]. Se ha comunicado tal circunstancia, tanto al/a la administrador/a de fincas D./Dña. [NOMBRE Y APELLIDOS], como al/a la presidente/a de la comunidad D./Dña. [NOMBRE Y APELLIDOS] para que se pongan en contacto con el/la querellado/a para que cese en su actitud, pero sin resultado positivo.

Todo ello, prolongado a lo largo de dos años, ha creado una situación de temor lógico y ansiedad en la familia de mi mandante, alterando la vida normal y provocando un cuadro de ansiedad en los 4 miembros de dicha familia, ante el acoso permanente de esta persona, hasta el punto de estar valorando la venta del inmueble para evitar esta situación de hostigamiento personal por el/la querellado/a.

QUINTO.- Los hechos expuestos revisten los caracteres de un delito de acoso del art. 172 ter CP, del que presuntamente es culpable el/la querellado/a. (2)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto] (3)

-D./Dña. [NOMBRE Y APELLIDOS] esposo/a del/de la querellante.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- y [COMPLETAR] hijo/a del/de la querellante.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] vecino/as del inmueble.

-D./Dña. [NOMBRE Y APELLIDOS]. Presidente/a de la comunidad de vecinos.

-D./Dña. [NOMBRE Y APELLIDOS] administrador/a de fincas colegiado/a de la comunidad de vecinos.

[OPCIONAL — incluir si procede]

.- Pericial. Se aporta informe pericial del/de la perito médico D./Dña. [NOMBRE Y APELLIDOS] donde se incluye una valoración del/de la experto/a de los 4 miembros de la familia y la afectación personal ante la conducta del/de la querellado/a. (4)

- Informe pericial de D./Dña. [NOMBRE Y APELLIDOS] del cuerpo de escritura de las cartas.

[OPCIONAL — incluir si procede]

.- Documental, aportando cartas depositadas en el buzón de correos por el/la querellado/a al objeto de que se proceda a una diligencia de cotejo del cuerpo de escritura del/de la querellado/a para averiguar si coincide la forma de la escritura.

Séptimo.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Dado la gravedad de los casos de acoso en comunidad por la convivencia, se interesa se adopte la medida cautelar del art. 13 y 544 bis LECRIM de alejamiento del/de la querellado/a para evitar coincida con el/la querellante y la de prohibición de comunicación por cualquier medio hasta el día del juicio sin perjuicio de la posterior imposición de la pena prevista en el art. 57.1 CP. (5)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se adopten las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Las situaciones de acoso vienen contempladas en el art. 172 ter CP. Estas situaciones de acoso en el ámbito de las comunidades de propietarios se denominan actualmente con el término "blocking".

La STS 324/2017 de 8 Mayo 2017, Rec. 1775/2016 ha dictado una primera doctrina sobre el denominado delito de "stalking" o acoso, fijando como doctrina la siguiente:

El tipo de ‘stalking’ del art. 172 ter CP requiere una voluntad de imponer un patrón de conducta sistemático de acoso –insistente y reiterado- con vocación de cierta perpetuación temporal. Se requiere una vocación de persistencia o una intencionalidad, latente o explícita, de sistematizar o enraizar una conducta intrusiva sistemática (persecución, reiteración de llamadas...) capaz de perturbar los hábitos, costumbres, rutinas o forma de vida de la víctima. Se exige implícitamente una cierta prolongación en el tiempo; o, al menos, que quede patente, que sea apreciable, esa voluntad de perseverar en esas acciones intrusivas, que no se perciban como algo puramente episódico o coyuntural, pues en ese caso no serían idóneas para alterar las costumbres cotidianas de la víctima. El tipo no exige planificación pero sí una metódica secuencia de acciones que obligan a la víctima, como única vía de escapatoria, a variar, sus hábitos cotidianos.

El tipo no exige planificación pero sí una metódica secuencia de acciones que obligan a la víctima, como única vía de escapatoria, a variar sus hábitos cotidianos. Para valorar esa idoneidad de la acción secuenciada para alterar los hábitos cotidianos de la víctima hay que atender al estándar del "hombre medio", aunque matizado por las circunstancias concretas de la víctima (vulnerabilidad, fragilidad psíquica, ...) que no pueden ser totalmente orilladas.

Es preciso describir con detalle en la querella los hechos de acoso significando que lo sean de forma repetitiva y que perduran en el tiempo, siguiendo la doctrina del Tribunal Supremo antes expuesta, a fin de evitar que se archiven las diligencias por no suponer la descripción de los hechos una entidad tal que pueda dar a entender una situación de acoso.

(3) El objetivo de estas testificales es acreditar que los actos del querellado han alterado el normal desarrollo de la vida del denunciante y producido una afectación en sus hábitos de vida, elementos de afectación claves para entender cometido este delito. A partir del 7 de octubre de 2022, fecha de entrada en vigor de la LO 10/2022, ya no se exige que la alteración de la vida cotidiana sea grave.

Es preciso proponer testifical de los órganos de gobierno de la comunidad y vecinos para que declaren sobre los actos de acoso, bien como testigos de referencia, bien como testigos directos si los hubieran presenciado.

(4) No se precisa que se aporte pericial médica psicológica, pero dado que el tipo exige una alteración grave del desarrollo de su vida cotidiana es positivo aportar este informe para acreditar el grado de afectación psicológica derivado de las situaciones de acoso.

(5) En este delito de blocking no hay que descartar la imposición de la pena del art. 57.1 CP por tratarse de un delito contra la libertad y estar incluido en el Título VI del Código Penal y ser una garantía de evitación de reincidencia pero, al ser un matiz relevante que viven las partes en el mismo edificio, la pena de prohibición de aproximación se impondrá en la medida en que no se acerque al querellante de ninguna manera y, en caso de coincidir con él, evitar su aproximación física y eludir todo tipo de contacto, dado que sería imposible poner la distancia normal que se fija en estos casos de 500 metros al obligar al querellado a abandonar el inmueble. No obstante, en los casos de acoso grave, incluso podría dictarse esta medida, ya que sabemos que en vía civil el art. 7.2 de la Ley de Propiedad Horizontal prevé que a los vecinos molestos se les pueda expulsar de su inmueble durante un periodo de tres años, por lo que en el ámbito penal podría llegarse en casos graves a una condena de un año de alejamiento a más de 500 metros.

================================================================================
