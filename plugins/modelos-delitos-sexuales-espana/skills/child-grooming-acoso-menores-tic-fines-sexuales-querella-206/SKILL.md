---
name: child-grooming-acoso-menores-tic-fines-sexuales-querella-206
description: "Redacta el escrito «Child grooming (acoso a menores por TIC con fines sexuales): querella» (formulario 206 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Child grooming (acoso a menores por TIC con fines sexuales): querella

> Formulario 0206 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] NOMBRE Y APELLIDOS (12 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (3 veces)
- [ ] PROFESIÓN (3 veces)
- [ ] LOCALIDAD (6 veces)
- [ ] FECHA (4 veces)
- [ ] Nº
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…estuvo comunicándose por la red social»; «…con»; «…ente de confianza, consiguió convencer a»; «…a detención. Los hechos han provocado en»; «…eclaración de los querellantes Dña. y D.»; «…ular, serán aplicables las siguientes: a»; «…querellado/a y víctima por la red social»

## Elecciones que hay que hacer

- Instrucción / Violencia sobre la Mujer / Violencia contra la Infancia y la Adolescencia
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial:…
- .- Documental, teniendo por reproducido los documentos aportados. Entre ellos la transcripción de las conversa…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Dada la gravedad de los hechos por la vía del art. 13 LECrim. y art. 544 bis LECrim. 2º párrafo, solicitamo…
- .- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECrim., de la prohibición…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 183 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 183 del Código Penal
- art. 449 ter LECrim
- art. 26 de la Ley 4/2015
- art. 13 LECrim
- art. 544 bis LECrim
- art. 468.2 CP
- art. 681.3 LECrim
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

### Formulario 0206 · Child grooming (acoso a menores por TIC con fines sexuales): querella

- Año del modelo: 2022
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; 7 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 7 párrafos opcionales señalados; 41 campos de relleno marcados en blanco; 3 huecos del original que se habían perdido sin marca, marcados (IMPORTE, NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mis mandantes, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de child grooming del art. 183 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de [ELEGIR: Instrucción / Violencia sobre la Mujer / Violencia contra la Infancia y la Adolescencia] de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- Los querellantes son D. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino de [LOCALIDAD], con domicilio en [LOCALIDAD] y Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL] de profesión [PROFESIÓN], vecina de [LOCALIDAD] con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes: el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] a lo largo del periodo comprendido entre el día [FECHA] hasta el día [FECHA] estuvo comunicándose por la red social [COMPLETAR] con [COMPLETAR] de [Nº] años de edad, hijo/a de los querellantes. El/La querellado/a, haciéndose pasar por un/a menor de edad también, para crear un ambiente de confianza, consiguió convencer a [COMPLETAR] para concertar una cita para tener contacto sexual al haberle convencido de ello, acto que no se llevó a cabo al detectar casualmente el/la querellante las conversaciones. El día [FECHA] ya habían concertado la cita para ello, que fue comunicada por D./Dña. [NOMBRE Y APELLIDOS] a los agentes de policía, quienes montaron un dispositivo para detener a D./Dña. [NOMBRE Y APELLIDOS], lo que se produjo al llegar a la cita y ser detenido/a por los agentes cuando se disponía a contactar con el/la menor que acudió al lugar fuertemente vigilado/a por los agentes para poder localizar y detener al/a la querellado/a, al no disponerse de sus datos físicos hasta el momento de la detención.

Los hechos han provocado en [COMPLETAR] un cuadro de depresión fuerte que consta en el dictamen pericial adjunto.

Sin perjuicio de una más concreta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de child grooming que define el artículo 183 del Código Penal, del que presuntamente es culpable el/la querellado/a.

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as:

- Declaración de los querellantes Dña. y D. [COMPLETAR].
- Declaración del/de la menor que se interesa que se lleve a efecto como prueba preconstituida, procediéndose a su grabación en la instrucción para posteriormente procederse a su reproducción en el juicio oral, al tratarse de menor de 14 años de edad (art. 449 ter LECrim..).

En base a lo dispuesto en el art. 26 de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, conforme a la redacción dada por LO 10/2022, de garantía integral de la Libertad sexual, se interesa que la declaración de la víctima de delito sexual sea grabada en la instrucción y reproducida en sede judicial en base a que señala que: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: a [COMPLETAR]) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal".

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial:

-Declaración del/de la perito D./Dña. [NOMBRE Y APELLIDOS] psicólogo/a autor/a del informe de exploración de la víctima que consta adjunto.
-Pericial informática sobre los mensajes recibidos a realizar por un perito judicial informático.
-Que se oficie a la brigada de delitos tecnológicos a fin de que se averigüe la identidad de la dirección de IP y autoría del envío de los mensajes.

Una vez que La BIT lleve a cabo las diligencias de investigación para detectar la IP del ordenador desde el que se llevó a cabo el delito, que se redacte oficio policial para interesar la entrada y registro para la intervención del ordenador y se lleve a cabo la intervención y pericial informática de su contenido.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados. Entre ellos la transcripción de las conversaciones entre querellado/a y víctima por la red social [COMPLETAR] que solicita su adveración por el/la Letrado/a de la Administración de Justicia.

SEXTO.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Dada la gravedad de los hechos por la vía del art. 13 LECrim. y art. 544 bis LECrim. 2º párrafo, solicitamos se adopte la prohibición de comunicación del/de la querellado/a con el/la querellante por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos, realizándose el preceptivo requerimiento o apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que se postula. Adóptese en el auto de admisión de la querella comunicándose por cualquier medio con la parte querellante.

Del mismo modo, se interesa que se adopte también la prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al/a la querellado/a con las advertencias legales

También, en base al art. 13 LECrim., según redacción dada por la LO 10/2022 [NOTA DE REVISIÓN: El art. 13 LECrim fue redactado de nuevo por la LO 1/2026 (vigente desde el 10-4-2026), que conserva el párrafo segundo sobre retirada, interrupción o bloqueo provisional de contenidos ilícitos. Fuente: LO 1/2026, BOE-A-2026-7966, art. primero.uno (art. 13 LECrim).], se solicita que, al ser un delito cometido a través la tecnología, el juez acuerde, como primeras diligencias, las medidas cautelares consistentes en la retirada provisional de contenidos ilícitos, en la interrupción provisional de los servicios que ofrezcan dichos contenidos o en el bloqueo provisional de unos y otros cuando radiquen en el extranjero.

De conformidad con lo dispuesto en el art. 681.3 LECrim., según redacción dada por LO 10/2022, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre mis necesidades de protección, así como la obtención, divulgación o publicación de imágenes de la víctima o de sus familiares.

Del mismo modo, y para el supuesto de que pudiera adoptarse la decisión judicial de libertad provisional, y en base a lo dispuesto en el art. 544 bis LECrim., según redacción dada por la LO 10/2022 [NOTA DE REVISIÓN: El art. 544 bis LECrim tiene hoy la redacción de la LO 1/2026 (vigente desde el 10-4-2026), que mantiene en su último párrafo los dispositivos telemáticos para los delitos del art. 3 LO 10/2022 y añade la finalidad de evitar la reiteración delictiva. Fuente: LO 1/2026, BOE-A-2026-7966, art. primero.tres (art. 544 bis LECrim).] de garantía integral de la libertad sexual, se interesa se acuerde mediante resolución motivada la utilización de dispositivos telemáticos para el control de su cumplimiento.

[OPCIONAL — incluir si procede]

.- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECrim., de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. Todo ello en base a la STS Pleno 547/2022 de 2 de junio de 2022, Rec. 1615/2020.

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
