---
name: estafa-informatica-phishing-cuenta-bancaria-querella-434
description: "Redacta el escrito «Estafa informática (phishing) en cuenta bancaria: querella» (formulario 434 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (phishing) en cuenta bancaria: querella

> Formulario 0434 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL
- [ ] LOCALIDAD
- [ ] IMPORTE
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rriente que tiene en la entidad bancaria»; «…e se mencionan y que deberán ser citados»; «…. 120.3 CP. Es de Justicia que pido en a»

## Elecciones que hay que hacer

- sin que se nos haya contestado / y se nos ha contestado en sentido negativo

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (4) a fin de que se realicen las averig…
- .- Testifical: declaración de los testigos que se mencionan y que deberán ser citados [COMPLETAR]:…
- .- Pericial, para que por perito judicial se elabore pericial informática acerca de la estafa informática real…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 LECRIM
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 120.3 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 120.4 CP

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

### Formulario 0434 · Estafa informática (phishing) en cuenta bancaria: querella

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos que presentan los caracteres de un delito de estafa informática del art. 249.1 a) CP al haberse extraído dinero de una cuenta bancaria a través de sus claves de acceso obtenidas fraudulentamente por desconocidos y con responsabilidad penal subsidiaria del banco.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 LECRIM y siguientes, por el delito del art. 249.1 a) CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, y del Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005.

SEGUNDO.- El/la querellante es D./Dña [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El querellado se fija por la vía del art. 277.3º LECRIM en atención a quien determine la investigación efectuada por la brigada de delitos tecnológicos de la policía a fin de interesar la investigación procedente para la averiguación de la autoría.

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Persona o personas desconocidas han accedido a las claves de acceso de mi mandante a la cuenta corriente que tiene en la entidad bancaria [COMPLETAR] y han extraído, mediante transferencia bancaria, la suma de [IMPORTE] euros.

No se han adoptado por la entidad bancaria las medidas suficientes de observancia de normas reglamentarias o de control suficientes como para evitar el acceso a la cuenta, y la prueba evidente es que el acceso se ha producido al omitir la entidad el estricto cumplimiento de la evitación del acceso a la cuenta corriente, o mejorar los dispositivos de prevención informática que proteja a los clientes de sufrir estafas informáticas.

Se ha dado cuenta a la entidad bancaria por requerimiento reclamando la devolución de las sumas extraídas por quien ha realizado la sustracción informática [ELEGIR: sin que se nos haya contestado / y se nos ha contestado en sentido negativo]. Todo ello, a fin de derivar la reclamación a la entidad bancaria.

QUINTO.- Sin perjuicio de una posterior calificación jurídica más exacta, los hechos expuestos revisten los caracteres de un delito de estafa informática del art. 249.1 a) CP (2)

Existe responsabilidad civil subsidiaria de la entidad bancaria por la vía del art. 120.3 CP al haberse omitido las normas de policía o reglamentarias de la entidad bancaria que han facilitado o impedido el acceso a la cuenta corriente del querellante. (3)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (4) a fin de que se realicen las averiguaciones oportunas por investigación del ordenador de mi representado/a y sistema utilizado para acceso a sus claves de acceso al banco antes citado.

Una vez que La BIT lleve a cabo las diligencias de investigación para detectar la IP del ordenador desde el que se llevó a cabo la estafa, que se redacte oficio policial para interesar la entrada y registro para la intervención del ordenador y se lleve a cabo la intervención y pericial informática de su contenido.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan y que deberán ser citados [COMPLETAR]:

- D./Dña. [NOMBRE Y APELLIDOS] director/a de la entidad bancaria, para que explique la posible operativa de estos actos.

[OPCIONAL — incluir si procede]

.- Pericial, para que por perito judicial se elabore pericial informática acerca de la estafa informática realizada, a cuyo fin deberá designarse perito y se emita informe que sea aportado y posteriormente se ratifique en el contenido de la pericia.

[OPCIONAL — incluir si procede]

.- Documental:

-Aportación de extracto bancario de la transferencia realizada de mi cuenta a la que consta en el documento adjunto como nº1 para que se identifique la identidad del titular de la cuenta donde se efectuó la transferencia.

-Requerimiento efectuado a la entidad bancaria reclamando el reintegro en la cuenta por esta sin respuesta por parte de ésta.

-Respuesta negativa del banco, en su caso.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas oportunas para la averiguación de la autoría, ya que es investigación tecnológica sencilla y factible de identificación por los medios de la autoridad policial y, una vez conocido, que se una e incorpore en la tramitación de las presentes diligencias.

Se interesa se requiera a la entidad bancaria para que preste fianza en cantidad de como responsable civil subsidiario ex art. 120.3 CP.

Es de Justicia que pido en a [COMPLETAR]

OTROSÍ DIGO: Que conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) La estafa informática regulada hasta el 11 de enero de 2023 en el art. 248.2 a y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP, consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son: La manipulación informática y artificio semejante, transferencia patrimonial no consentida por el titular del mismo, ánimo de lucro, y perjuicio en tercero.

(3) Véase STS 108/2019 de 5 de marzo, Rec. 10024/2018

STS 53/2020 de 17 Feb. 2020, Rec. 10301/2019: se desarrolla el criterio del Tribunal Supremo con relación al ámbito de las responsabilidades del art. 120.3 CP que se extendería a las entidades bancarias en el caso de sustracción de fondos a un cliente por incumplimiento de las normas reglamentarias de protección del cliente ante estafas informáticas, lo que se indica de referencia jurisprudencial de cara al juicio oral.

STS 530/2019 de 31 de octubre, Rec. 1945/2018: responsabilidad ex delicto subsidiaria de la entidad bancaria por apropiación indebida de fondos en una cuenta por colaboración de un administrador solidario y empleado del banco. A diferencia del caso anterior, el delito se comete por un empleado del banco y en este caso opera la del art. 120.4 CP.

(4) Generalmente en los delitos de estafa informática se desconoce, o suele desconocerse la autoría e identidad del autor del delito, ya que se ha perpetrado por un procedimiento informático. Por ello, lo que se pretende es que este órgano judicial ordene a la policía judicial que realice las actividades de investigación por la vía informática para conocer quien ha cometido el delito.

Para averiguar esta autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica, encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF) que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como de la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

Su misión consiste en obtener las pruebas, perseguir a los delincuentes y poner a unas y otros a disposición judicial.

Podría ocurrir que, a la hora de acceder a determinados datos para conocer la autoría, la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a LECRIM y ss (introducidos por la LO 13/2015, de 5 de octubre), para poder conseguir pruebas en casos de delitos cometidos por medios tecnológicos.

En estos casos de estafas informáticas los agentes de la policía judicial podrán haber detectado el número de IP del ordenador desde el que se ha cometido la estafa informática y, tras ello, por la vía del art. 588 ter k LECRIM (introducido por la LO 13/2015, de 5 de octubre) se habrá interesado la orden judicial para la averiguación de la identidad del autor.

================================================================================
