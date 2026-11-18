---
name: estafa-falsedad-documento-publico-querella-520
description: "Redacta el escrito «Estafa y falsedad en documento público: querella» (formulario 520 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa y falsedad en documento público: querella

> Formulario 0520 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- El cálculo de pena del concurso medial responde al art. 77 anterior a la LO 1/2015; el art. 77.3 CP vigente fija una pena superior a la concreta del delito más grave y limitada por la suma de las penas concretas.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (19 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (3 veces)
- [ ] PROFESIÓN (3 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] Nº DE DOCUMENTO
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «… y era titular de los siguientes bienes:»; «… otorgara documento de venta a precio de»; «…ebajo del real, de las fincas siguientes»; «…ica, otorgara los siguientes documentos:»; «…fraudación delictiva cometida, radica en»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se dispone del mismo / Si no se dispone del mismo — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración de los/as querellados/as D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], a fin de…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- — D./Dña. [NOMBRE Y APELLIDOS], que conoce la existencia de los hechos por trabajar en las dependencias del or…
- .- Pericial del/de la perito D./Dña. [NOMBRE Y APELLIDOS] que valora los daños causados en la cantidad de [IMP…
- .- Documental:…

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 248 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 248 del Código Penal
- art. 77 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 77.3 CP

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

### Formulario 0520 · Estafa y falsedad en documento público: querella

- Año del modelo: 2019
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 42 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)
- Avisos de la revisión: El cálculo de pena del concurso medial responde al art. 77 anterior a la LO 1/2015; el art. 77.3 CP vigente fija una pena superior a la concreta del delito más grave y limitada por la suma de las penas concretas.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres del delito de estafa del art. 248 CP y falsedad en documento público del art. 390.1.3º CP, al haberse efectuado ante notario una venta de unas fincas por parte de una persona con discapacidad por debajo del precio de mercado.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal por los hechos y contra la persona que se menciona a continuación, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD].

TERCERO.- Los/as querellados/as son D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] y D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

D./Dña. [NOMBRE Y APELLIDOS] padecía una situación de enfermedad mental evidente que le producía un retraso mental profundo y era titular de los siguientes bienes: [COMPLETAR].

Con la intención de apoderarse de su patrimonio, D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] en combinación y puestos de acuerdo con el/la Notario/a D./Dña. [NOMBRE Y APELLIDOS], acudieron a su notaría para que, a sabiendas de este/a último/a de la evidencia de su discapacidad, les otorgara documento de venta a precio de [COMPLETAR], muy por debajo del real, de las fincas siguientes [COMPLETAR]. Pero, sin que el/la perjudicado/a acudiera a la Notaría, el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] consiguió que el/la Notario/a, también acusado/a, sin haber adoptado la diligencia más elemental para cerciorarse sobre la capacidad de D./Dña. [NOMBRE Y APELLIDOS] para intervenir en cualquier operación jurídica, otorgara los siguientes documentos: [COMPLETAR]. En ellos se hace constar que D./Dña. [NOMBRE Y APELLIDOS] compareció ante el fedatario y expuso sus circunstancias familiares, cuando no lo hizo. Ello ha provocado una transmisión de bienes fraudulenta en manos del/de la querellado/a D./Dña. [NOMBRE Y APELLIDOS] por medio de la actuación del/de la también querellado/a D./Dña. [NOMBRE Y APELLIDOS].

QUINTO.- Los hechos expuestos revisten para el/la Notario/a querellado/a los caracteres de un delito de falsedad en documento público del art. 390.1.3º CP, en concurso medial con un delito de estafa, que define el artículo 248 del Código Penal, del que presuntamente son culpables los/as querellados/as, puesto que el lucro, como elemento esencial de la defraudación delictiva cometida, radica en [COMPLETAR] y además para cometer la estafa se han servido de un documento público cual es el documento notarial con la intervención de fedatario público. Ambos delitos operan en concurso medial por el art. 77 CP, a efectos de punibilidad. (3)

SEXTO- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración de los/as querellados/as D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], a fin de que manifiesten cuanto se relacione con los precedentes hechos.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], que conoce la existencia de los hechos por trabajar en las dependencias del organismo público donde se perpetra la falsedad de documento público.

[OPCIONAL — incluir si procede]

.- Pericial del/de la perito D./Dña. [NOMBRE Y APELLIDOS] que valora los daños causados en la cantidad de [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Documental:

Únanse a las actuaciones como documento número [Nº DE DOCUMENTO] consistente en [DESCRIBIR]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se dispone del mismo / Si no se dispone del mismo — el texto de cada opción no venía en el formulario original]

 (4)

.- Cuantas diligencias complementarias sean convenientes para la adecuada averiguación de los hechos.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal y sobre los bienes de los/as querellados/as, disponiendo se proceda a la detención y prisión provisional de los/as querellados/as, o se les exija fianza por la libertad en la cantidad de [IMPORTE] euros, y otra fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) En los casos de estafa perpetrada por medio de falsedad documental pública ésta es el medio idóneo para cometer aquella y por ello estamos ante un concurso medial del art. 77.3 CP [NOTA DE REVISIÓN: Desde la LO 1/2015 la pena del concurso medial está en el art. 77.3 CP: pena superior a la que correspondería en el caso concreto por la infracción más grave, sin exceder la suma de las penas concretas. Fuente: Código Penal, BOE-A-1995-25444, art. 77.3 (LO 1/2015, BOE-A-2015-3439).] en el que un hecho constituye dos delitos de falsedad en documento público y de estafa al defraudar al perjudicado haciéndole perder sus bienes (o causarle el perjuicio económico que se cuantifique en la querella) mediante el instrumento de la falsedad en documento público. Con ello la penalidad se iría entre 4 años y seis meses y 6 años de prisión y multa de 15 a 24 meses e inhabilitación especial al aplicarse la pena por delito más grave en su mitad superior [NOTA DE REVISIÓN: Cálculo propio del art. 77 anterior a la LO 1/2015; con el art. 77.3 vigente el mínimo es una pena superior a la concreta del delito más grave (falsedad del art. 390: prisión de tres a seis años) y el máximo la suma de las penas concretas. Fuente: Código Penal, BOE-A-1995-25444, arts. 77.3 y 390.1.].

Tipificación de los hechos para el particular que se auxilia de funcionario público para cometer delito de falsedad en documento público:

En estos casos la penalidad para el particular se remite al art. 390.1.3º CP en concurso medial con la estafa (art. 77.3 CP) [NOTA DE REVISIÓN: El art. 77.2 CP regula el concurso ideal; el medial se pena conforme al art. 77.3 CP. Fuente: Código Penal, BOE-A-1995-25444, art. 77 (LO 1/2015, BOE-A-2015-3439).]

Doctrina jurisprudencial del TS de supuestos de estafa y falsedad en documento público:

STS 825/2009 de 16 Jul. 2009, Rec. 2507/2008

STS 580/2016 de 30 Jun. 2016, Rec. 1706/2015

STS 825/2009 de 16 Jul. 2009, Rec. 2507/2008

STS 683/2008 de 29 Oct. 2008, Rec. 34/2008

STS 797/2011 de 7 Jul. 2011, Rec. 2601/2010

STS 195/2015 de 16 Mar. 2015, Rec. 1164/2014

STS 1005/2016 de 24 Ene. 2017, Rec. 1093/2016

(4) Al tratarse de acción penal por falsedad en documento público debe incorporarse el documento sobre el que se refiere el objeto de la querella, o bien si no se dispone del mismo el archivo público donde conste a fin de proceder a la solicitud judicial por el juez de instrucción a fin de que se requiera su aportación.

Del mismo modo, al tratarse de acción penal de falsedad en documento público mediante el que se comete una estafa deberían aportarse los documentos en que esta consiste, así como aquellos que sirvan para cuantificar los daños y perjuicios causados por la defraudación con determinación —de conocerse— de su importe económico.

================================================================================
