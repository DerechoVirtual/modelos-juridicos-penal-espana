---
name: coacciones-mensajes-whatsapp-querella-719
description: "Redacta el escrito «Coacciones por mensajes de WhatsApp: querella» (formulario 719 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Coacciones por mensajes de WhatsApp: querella

> Formulario 0719 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] ESTADO CIVIL
- [ ] FECHA (3 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…untamente es culpable el/la querellado/a»

## Elecciones que hay que hacer

- unos videos / unas fotos
- a continuación / en escrito aparte
- judicialmente / mediante exhorto
- grabación / las fotos

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (9)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- -D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial siguiente:…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña acta notar…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Al amparo de lo dispuesto en el artículo 13 LECRIM, solicitamos dirigirse al prestador de servicios para qu…
- .- Dada la gravedad de los hechos, por la vía del art. 13 LECRIM y art. 544 bis LECRIM párrafo 2º, solicitamos…
- .- Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 172 CP
- artículos 277 de la LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 172.1 CP
- artículo 13 LECRIM
- art. 13 LECRIM
- art. 544 bis LECRIM
- art. 468.2 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 48.3 CP
- art. 39 h) CP

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

### Formulario 0719 · Coacciones por mensajes de WhatsApp: querella

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (6); 3 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 bloques de alternativas señalados; 8 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que pueden ser constitutivos del delito de coacciones del art. 172.1 ó 2 CP, por compeler a ex pareja, mediante mensajes de WhatsApp, a hacer algo bajo amenaza de publicar en internet grabaciones o videos suyos privados. Si cumple la amenaza y difunde las imágenes incurriría, además, en un delito de sexting del art. 197.7 CP.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

A la Sección de Violencia sobre la Mujer que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 172 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 de la LECRIM y concordantes,

EXPONGO

PRIMERO.- (2)

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Se presenta ante el Tribunal de Instancia de esta ciudad para su reparto a la Sección de Instrucción que por turno corresponda, por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

(Si el sujeto activo es hombre y la víctima es mujer)

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (3)

TERCERO.- El/la querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (4)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Querellante y querellado/a han mantenido una relación de pareja durante cinco años iniciada en fecha [FECHA] y concluida por decisión del/de la querellante en fecha [FECHA]. A raíz de la ruptura instada por el/la querellante, el/la querellado le ha enviado varios mensajes por WhatsApp en los que se indica que, en el caso de no reanudar su relación de pareja, subiría a internet [ELEGIR: unos videos / unas fotos] de contenido privado que ambos hicieron en su momento para su uso personal.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 172.1 CP de coacciones del que presuntamente es culpable el/la querellado/a [COMPLETAR].

(Si la expareja víctima es mujer y el sujeto activo hombre)

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

Prueba pericial informática, para el supuesto de que se impugne por la defensa el contenido de los WhatsApp, relativa a la prueba digital aportada consistente en acta notarial del/de la Ilustre Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Colegio de [LOCALIDAD] donde consta la lectura de los mensajes enviados por el/la querellado/a, para lo que se aporta pericial informática de parte sobre la veracidad de estos mensajes.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña acta notarial del/de la Ilustre Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Colegio de [LOCALIDAD] donde consta la lectura de los mensajes enviados por el/la querellado/a, aunque se interesa también su adveración por el/la Letrado/a de la Administración de Justicia, citando a esta parte en día y hora para aportar los originales.

SEXTO.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Al amparo de lo dispuesto en el artículo 13 LECRIM, solicitamos dirigirse al prestador de servicios para que suprima o retire de la red social la referencia o mención sobre la que se circunscribe la acción penal ejercitada.

[OPCIONAL — incluir si procede]

.- Dada la gravedad de los hechos, por la vía del art. 13 LECRIM y art. 544 bis LECRIM párrafo 2º, solicitamos se adopte la prohibición de comunicación del/de la querellado/a con el/la querellante por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos, realizándose el preceptivo requerimiento o apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que se postula. Adóptese en el auto de admisión de la querella comunicándose por cualquier medio con la parte querellante. (5)

[OPCIONAL — incluir si procede]

.- Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al/a la acusado/a con las advertencias legales.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

SEGUNDO OTROSÍ DIGO: Se interesa se requiera al/a la querellado/a para que entregue al juez el contenido de la [ELEGIR: grabación / las fotos]. (6)

Por ello,

SUPLICO A LA SECCIÓN:

Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Juez de Instrucción. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si la víctima expareja es mujer y el sujeto activo es hombre sería un delito de violencia de género competencia del Juez de Violencia sobre la Mujer.

(3) El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(4) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(5) La adopción de esta medida cautelar es fundamental para evitar la reiteración delictiva mientras se sustancie el procedimiento y concluya en sentencia condenatoria con pena del art. 48.3 CP como pena accesoria privativa de derechos del art. 39 h) CP, relativa a la prohibición de comunicarse con la víctima o con aquellos de sus familiares u otras personas que determine el juez o tribunal.

Como señala la SAP de Madrid 291/2017, de 20 de noviembre, Rec. 1591/2017:

"En muchas ocasiones las víctimas sienten temor no solo por la presencia física del condenado, sino, también, por un acto de comunicación virtual del investigado (medida cautelar) o pena (condenado), ya que una víctima que lo ha sido de un hecho del condenado puede incrementar su grado de victimización si recibe comunicaciones de quien le ha amenazado, incluso aunque estas comunicaciones no constituyan un hecho delictivo."

Es por ello por lo que, con independencia de que se interese la pena del art. 48.3 CP, se inste como medida cautelar para anticipar los efectos de la prohibición, dado el peligro de la reiteración y el temor que ello le reporta a la víctima, para quien, lo mismo que se adopta con frecuencia la medida cautelar de alejamiento, es igual de importante la de prohibición de comunicación.

(6) Resulta importante en estos casos instar en la querella la medida cautelar de la entrega de la grabación por el querellado, a fin de garantizar la protección de la víctima y evitar la difusión, aunque si el querellado, además de la coacción difundiera la grabación, ello integraría un delito de sexting del art. 197.7 CP.

================================================================================
