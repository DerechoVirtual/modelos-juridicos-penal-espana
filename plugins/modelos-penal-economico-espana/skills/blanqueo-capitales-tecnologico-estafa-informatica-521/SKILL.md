---
name: blanqueo-capitales-tecnologico-estafa-informatica-521
description: "Redacta el escrito «Blanqueo de capitales tecnológico y estafa informática: querella» (formulario 521 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Blanqueo de capitales tecnológico y estafa informática: querella

> Formulario 0521 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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

- [ ] LUGARD
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] NÚMERO (5 veces)
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] LUGAR (4 veces)
- [ ] CALLE
- [ ] Nº
- [ ] ESTADO CIVIL
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD
- [ ] ÓRGANO
- [ ] FECHA
- [ ] IMPORTE (2 veces)
- [ ] ORDINAL QUE CORRESPONDA (2 veces)
- [ ] DATOS (3 veces)
- [ ] DATOS IDENTIFICATIVOS DEL TESTIGO Y D
- [ ] DATOS IDENTIFICATIVOS DEL TESTIGO
- [ ] SEDE (2 veces)
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…se nos ha contestado en sentido negativo»; «…estigo empleado/a de la entidad bancaria»; «…ituación personal del/de la querellado/a»; «…Firma de Abogado/a Firma de Procurador/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.-. Declaración de el/la querellado/a sobre los hechos de la querella.…
- [ORDINAL QUE CORRESPONDA].- Testifical: declaración de los testigos que se mencionan a continuaciónen escrito …
- [ORDINAL QUE CORRESPONDA].- Documental, (prueba digital) teniendo por reproducido los documentos aportados, en…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 301.1 CP
- art. 249.1 a) CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 de la LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 120.3 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 301 CP
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

### Formulario 0521 · Blanqueo de capitales tecnológico y estafa informática: querella

- Año del modelo: 2018
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 8 llamadas a nota sin texto retiradas; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 3 huecos del original que se habían perdido sin marca, marcados (Nº, Nº DE DOCUMENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos que presentan los caracteres de un delito de blanqueo de capitales del art. 301.1 CP a través de las tecnologías, puesto que, previa estafa informática del art. 249.1 a) CP, se consiguen datos bancarios que se usan luego para transferir dinero de la cuenta del querellante a la propia con el fin de convertir en lícita la transferencia por aparentar su legalidad al disponer del PIN de acceso.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [LUGARD]./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— Si el poder se otorga a través de la sede judicial electrónicamediante comparecencia electrónica, a través de la sede judicial electrónica e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizadaSi el poder se otorga mediante comparecencia apud actamediante comparecencia personal apud acta ante el Letrado de la Administración de Justicia de la oficina judicial de [LUGAR] posteriormente inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizadaSi el poder se otorga ante Notariomediante escritura de poder otorgada a mi favor, ante el/la Notario/a D./Dña. [NOMBRE Y APELLIDOS], con Notaría sita en [LUGAR] El poder se inscribió en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; lo cual se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nºpor si no es posible la consulta automatizadabajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [CALLE], número, ciudadcolegiado nº [Nº] del Ilustre Colegio de la Abogacía de [LUGAR], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de blanqueo de capitales del art. 301.1 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 de la LECRIM y concordantes,EXPONGOPRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, y del Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005.

SEGUNDO.- El/la querellante es D./Dña. [NOMBRE Y APELLIDOS], como queda dicho, mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, estado civil, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:El/La querellante [ÓRGANO] con fecha [FECHA] recibió un correo electrónico en el que se hacía constar el logo de su entidad bancaria instándole a acceder e indicar sus datos bancarios y clave de PIN de acceso, a fin de evitar el cierre de su cuenta por motivos técnicos, ante lo cual, y no sospechando que el mensaje fuera falso, accedió a lo solicitado. Al día siguiente detectó que le habían extraído de la cuenta la cantidad de [IMPORTE] euros. Tras presentar la denuncia correspondiente e iniciarse el procedimiento penal se condenó a la persona que le había enviado el primer mensaje, aunque no se llegó a descubrir quién había utilizado una cuenta corriente para hacer el traspaso de su cuenta a la del/de la autor/a de la transferencia. Una vez ya dictada sentencia ha tenido conocimiento, por la investigación policial que se llevó a cabo, de la identidad del/de la autor/a de la cuenta corriente que hizo la transferencia de la cuenta del/de la querellante a la propia con el fin de ayudar al/a la autor/a del envío del correo electrónico y convertir en lícita la transferencia por aparentar su legalidad al disponer del PIN de acceso y aparentar transferencia del titular de la cuenta.

No se han adoptado por la entidad bancaria las medidas suficientes de observancia de normas reglamentarias o de control suficientes como para evitar el acceso a la cuenta, y la prueba evidente es que el acceso se ha producido al omitir la entidad el estricto cumplimiento de la evitación del acceso a la cuenta corriente, o mejorar los dispositivos de prevención informática que proteja a los clientes de sufrir estafas informáticas.

Se ha dado cuenta a la entidad bancaria por requerimiento reclamando la devolución de las sumas extraídas por quien ha realizado la sustracción informática sin que se nos haya contestadoy se nos ha contestado en sentido negativo [COMPLETAR]. Todo ello, a fin de derivar la reclamación a la entidad bancaria.

QUINTO.- Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de estafa informática del art. 249.1 a) CP y de blanqueo de capitales del art. 301.1 CP del que presuntamente es culpable el/la querellado/a. Existe responsabilidad civil subsidiaria de la entidad bancaria por la vía del art. 120.3 CP al haberse omitido las normas de policía o reglamentarias de la entidad bancaria que han facilitado o impedido el acceso a la cuenta corriente del querellante. SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.-. Declaración de el/la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Testifical: declaración de los testigos que se mencionan a continuaciónen escrito aparte y que deberán ser citados judicialmentemediante exhorto - D./Dña. [DATOS] identificativos del testigo director/a de la entidad bancaria .- D./Dña. [DATOS] identificativos del testigo empleado/a de la entidad bancaria [COMPLETAR] que atendió al /a la querellante.-D./Dña. [DATOS IDENTIFICATIVOS DEL TESTIGO Y D]./Dña. [DATOS IDENTIFICATIVOS DEL TESTIGO], agentes de la brigada de delitos tecnológicos que llevaron a cabo la investigación en el Juicio oral nº [NÚMERO] celebrado ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Documental, (prueba digital) teniendo por reproducido los documentos aportados, en concreto el correo electrónico recibido. Acta notarial del/de la Ilmo./Ilma. Sr./Sra. Notario/a [DATOS] identificativos del notario donde consta la constatación de ajustarse el documento anterior a la realidad al ser adverada notarialmente.

Que se aporte testimonio de lo tramitado ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] con relación al delito de estafa informática Por lo expuesto,

SUPLICO A LA SECCIÓN:Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a [COMPLETAR], disponiendo se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], día, mes, año

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a

Firma de Procurador/a [COMPLETAR] En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).
 Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.
 Los requisitos según la jurisprudencia para el delito de blanqueo son (SSTS 672/2016 de 21 Julio, rec. 552/2015, 928/2006, 5 de octubre, rec. 1255/2005, 154/2008, 8 de abril, rec. 1696/2007):1.- No se exige condena previa por el delito antecedente.2.- Se exige un dolo específico de la acción a sabiendas en cualquiera de las modalidades de acción de aprovechamiento u ocultación previstas en los apartados 1 y 2 del art. 301 CP.3.- La prueba de la actividad delictiva antecedente se puede probar por prueba indiciaria.

El autor del delito antecedente tecnológico puede serlo del delito de blanqueo de capitales con lo que se trata de "autoblanqueo tecnológico" (STS 265/2015 de 29 de Abril, rec. 10496/2014).

La estafa informática consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son: La manipulación informática y artificio semejante, transferencia patrimonial no consentida por el titular del mismo, ánimo de lucro, y perjuicio en tercero.
 Véase STS 108/2019 de 5 de marzo, Rec. 10024/2018STS 53/2020 de 17 Feb. 2020, Rec. 10301/2019: se desarrolla el criterio del Tribunal Supremo con relación al ámbito de las responsabilidades del art. 120.3 CP que se extendería a las entidades bancarias en el caso de sustracción de fondos a un cliente por incumplimiento de las normas reglamentarias de protección del cliente ante estafas informáticas, lo que se indica de referencia jurisprudencial de cara al juicio oral.STS 530/2019 de 31 de octubre, Rec. 1945/2018: responsabilidad ex delicto subsidiaria de la entidad bancaria por apropiación indebida de fondos en una cuenta por colaboración de un administrador solidario y empleado del banco. A diferencia del caso anterior, el delito se comete por un empleado del banco y en este caso opera la del art. 120.4 CP.

================================================================================
