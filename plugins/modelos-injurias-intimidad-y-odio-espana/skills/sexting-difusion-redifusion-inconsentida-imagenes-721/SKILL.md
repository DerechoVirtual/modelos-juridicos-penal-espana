---
name: sexting-difusion-redifusion-inconsentida-imagenes-721
description: "Redacta el escrito «Sexting (difusión o redifusión inconsentida de imágenes por internet): querella» (formulario 721 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sexting (difusión o redifusión inconsentida de imágenes por internet): querella

> Formulario 0721 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (3 veces)
- [ ] CALLE
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…: El/La querellante y el/la querellado/a»; «… al/a la querellante. El/La querellado/a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.-. Declaración de los querellados sobre los hechos de la querella y que manifiesten y prueben en particular …
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial del perito psicólogo D./Dña [NOMBRE Y APELLIDOS] a cuya consulta asiste el/la querellante a raíz d…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña acta notar…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 13 de la LECRIM
- art. 4 LEC
- art. 24.2 LEC
- art. 197.3 CP

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

### Formulario 0721 · Sexting (difusión o redifusión inconsentida de imágenes por internet): querella

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (6); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres del delito de difusión inconsentida de imágenes obtenidas con la anuencia de la víctima (sexting), así como del delito de su redifusión del art. 197.7 CP.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 197.7 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes de dicha ley,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, y del Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005 . (2)

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, de profesión [PROFESIÓN], con domicilio en la calle [CALLE] número (3)

TERCERO.- Los querellados son:

- D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]
- D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] (4)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellante y el/la querellado/a [COMPLETAR] han mantenido una relación de pareja durante cinco años, iniciada en fecha [FECHA] y concluida por decisión de el/la querellante en fecha [FECHA]. A raíz de la ruptura, varios conocidos de mi representado/a se dirigieron a él/ella comunicándole que circulaba por internet un video de él/ella y su ex pareja de contenido sexual, de relaciones mantenidas de común acuerdo, grabación que también fue consentida, pero para uso privado de la pareja, sin que conste expresa autorización de la parte querellante a que el contenido de la grabación se difundiera por internet, al contener imágenes que afectan a la privacidad de ambos y que supone un claro menoscabo grave de la intimidad de la parte querellante que se ha visto expuesta a la humillación del/de la querellado/a, en venganza por haber roto la relación con él/ella y, en consecuencia, subir a internet la citada grabación para menoscabar su intimidad y humillar al/a la querellante.

El/La querellado/a [COMPLETAR], por su parte, también subió esa grabación sin autorización de la víctima a dos grupos de WhatsApp, resultando evidente que la divulgación menoscababa gravemente la intimidad personal de la víctima, habida cuenta que en el video aparecía como

La divulgación de estas imágenes por ambos querellados le ha ocasionado una grave afectación personal al haber aparecido en varios grupos de Whatsapp sin autorización y en posición gravemente humillante para su persona.

Con ello, ha tenido que acudir a la consulta del psicólogo D./Dña. [NOMBRE Y APELLIDOS] para recibir tratamiento a raíz de estos hechos.

La víctima requirió a los querellados para que retiraran el video, tanto de internet como de los grupos, sin haberlo realizado.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 197.7 CP, (5).

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.-. Declaración de los querellados sobre los hechos de la querella y que manifiesten y prueben en particular sobre la autorización que tuvieran para difundir el video.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto], que han visionado la grabación en internet o en los grupos de WhatsApp.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial del perito psicólogo D./Dña [NOMBRE Y APELLIDOS] a cuya consulta asiste el/la querellante a raíz de los hechos.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña acta notarial del Ilustre Notario D./Dña. [NOMBRE Y APELLIDOS] del Colegio de [LOCALIDAD] donde consta un CD con la grabación del contenido difundido en internet y en WhatsApp visionado por el citado Notario como consta en el acta notarial, así como las visualizaciones llevadas a cabo a la fecha del acta notarial. (6)

-Facturas del/de la psicólogo/a.

- Requerimiento notarial a los acusados.

.- Que se oficie a la brigada de delitos tecnológicos para que proceda a averiguar si ha habido más redifusiones de la imagen mediante la orden judicial de intervención de los teléfonos móviles de los querellados y se borren las imágenes.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares, disponiendo se le exija fianza, para asegurar las responsabilidades pecuniarias, en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

PRIMER OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

SEGUNDO OTROSÍ DIGO: Se interesa se requiera a los la querellados para que entreguen al órgano judicial el contenido de la grabación, así como el ordenador y los dispositivos electrónicos de que disponga.

Y que, además, se acuerde la retirada provisional de los contenidos ilícitos y la interrupción provisional de los servicios que ofrezcan dichos contenidos, en base al art. 13 de la LECRIM.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Es aplicable aquí el Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005, que acoge el principio de ubicuidad, de tal modo que el delito se comete en todas las jurisdicciones en las que se haya realizado algún elemento del tipo, en consecuencia, el Juez de cualquiera de ellas que primero haya iniciado las actuaciones procesales será, en principio, competente para la instrucción de la causa.

(3) El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(4) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(5) Se castiga en el art. 197.7 CP, como delito de sexting, introducido en el CP en la LO 1/2015 al que, sin autorización de la persona afectada, difunda, revele o ceda a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros, cuando la divulgación menoscabe gravemente la intimidad personal de esa persona.

La pena se impondrá en su mitad superior cuando los hechos hubieran sido cometidos por el cónyuge o por persona que esté o haya estado unida a él por análoga relación de afectividad, aun sin convivencia, la víctima fuera menor de edad o una persona con discapacidad necesitada de especial protección, o los hechos se hubieran cometido con una finalidad lucrativa.

Se trata de un tipo penal que exige la existencia de tres elementos concurrentes:

1.- No consentimiento de la víctima a la difusión de una grabación obtenida con consentimiento de ambos. (Si tampoco existiera consentimiento en la grabación se sanciona con la pena prevista en el art. 197.3 CP de dos a cinco años de prisión).

En este caso la carga de la prueba de la existencia del consentimiento del afectado en difundir las imágenes correspondería al acusado al efectuar el descargo de que la víctima fue la que prestó su consentimiento a que el video o las imágenes se trasladaran a terceros y/o difundieran, ya que de lo contrario se trataría de una prueba diabólica al no poder obligarse a la víctima a que ella probara que «no prestó el consentimiento a que el video se difundiera». En cualquier caso, resultará obvio pensar que determinados videos o imágenes no están autorizadas normalmente a que se difundan, de ahí que se tenga que exigir la prueba del consentimiento al acusado si así lo alega.

2.- La conducta que se sanciona es la de difundir, revelar o ceder a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros.
3.- Que la divulgación menoscabe gravemente la intimidad personal de esa persona. No debe perderse de vista que esta exigencia es un elemento del tipo, por lo que si se efectúa una difusión de imágenes, pero no llega a considerarse que ello supone una afectación o menoscabo a su intimidad el hecho no será delito. Pero es que el bien jurídico protegido por este delito es, precisamente, la intimidad, y en conjunción con la propia imagen. Pero se exige no una mera afectación a ambas, sino que esta sea grave, de lo que se debe concluir que no se podrá derivar al ámbito de la persecución penal cualquier hecho de divulgación de imágenes o videos, sino aquellos que menoscaben de forma grave esa intimidad personal de la víctima. Se trata de un elemento valorativo del juez, lo que puede ser objeto y materia del recurso en casos de condena.

Hasta la reforma operada por LO 10/2022, de garantía integral de la libertad sexual, vigente desde el 7 de octubre de 2022, no estaba sancionado nada más que el primer envío, pero no los reenvíos sucesivos, habida cuenta que el art. 197.7 CP no se remitía al art. 197.3 CP que sí lo sancionaba, lo que se resuelve con el párrafo 2º del art. 197.7 CP que sí sanciona el segundo reenvío de quien ha recibido esa imagen sin autorización, tampoco, de la persona afectada.

(6) Este dato es importante para acreditar el número de visualizaciones de la grabación, que se cerrará a la fecha del juicio, a la hora de valorar la responsabilidad civil.

================================================================================
