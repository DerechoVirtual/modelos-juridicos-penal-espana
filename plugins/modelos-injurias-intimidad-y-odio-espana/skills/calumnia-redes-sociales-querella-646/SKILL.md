---
name: calumnia-redes-sociales-querella-646
description: "Redacta el escrito «Calumnia en redes sociales: querella» (formulario 646 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Calumnia en redes sociales: querella

> Formulario 0646 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO (2 veces)
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] CALLE
- [ ] DELITO
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… Por ello, esta difusión ha provocado en»; «…ue ha visto la publicación en red social»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (11)

Inclúyelos solo si encajan en los hechos:

- Ello fue hecho en la red social desde el propio ordenador del/de la querellado/a con el pseudónimo de descubie…
- 1.-. Declaración del/de la querellado/a/a sobre los hechos de la querella.…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- D/Dña que ha visto la publicación en red social [COMPLETAR]…
- .- Pericial.…
- .- Documental, teniendo por reproducido los documentos aportados. Entre ellos acta notarial del Notario/a D./D…
- .- Que se oficie a la Brigada tecnológica para llevar a cabo las diligencias de identificación del autor del d…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al querellado …
- .- Al amparo de lo dispuesto en el artículo 13 LECRIM, solicitamos dirigirse al prestador de servicios para qu…
- .- Dada la gravedad de los hechos por la vía del art. 13 LECRIM y art. 544 bis, 2º párrafo LECRIM solicitamos …
- .- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 205 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- arts. 205 y 206 CP
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 205 CP
- artículo 13 LECRIM
- art. 13 LECRIM
- art. 468.2 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- artículo 207 CP
- art. 211 CP
- artículo 212 CP
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

### Formulario 0646 · Calumnia en redes sociales: querella

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (9); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 10 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que pueden ser constitutivos de delito de calumnia con publicidad del art. 205 CP, al haber subido el querellado a una red social un comentario atribuyendo al querellante la comisión de un delito conociendo su falsedad.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de calumnia con publicidad de los arts. 205 y 206 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 y concordantes de la LECRIM,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, y del Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005

SEGUNDO.- El/La querellante es D./Dña, como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] calle

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] calle [CALLE] (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a subió por la red social un comentario consistente en que el/la querellante había perpetrado los siguientes hechos.

Estos hechos son constitutivos del delito [DELITO] tipificado en el art. CP, siendo estos falsos.

[OPCIONAL — incluir si procede]

Ello fue hecho en la red social desde el propio ordenador del/de la querellado/a con el pseudónimo de descubierto por la brigada de delitos tecnológicos.

En ningún momento el/la querellante ha cometido los hechos ni se han probado y la difusión por esta red social ha propiciado un elevado descrédito en él/ella. Por ello, esta difusión ha provocado en [COMPLETAR]. un cuadro de depresión fuerte, que consta en dictamen pericial que se acompaña, por la gran difusión que ha tenido esta acusación falsa al utilizar un medio de gran repercusión social.

QUINTO.- Sin perjuicio de una calificación jurídica posterior más exacta, los hechos expuestos revisten los caracteres de un delito de calumnia con publicidad que define el artículo 205 CP y pena el art. 206 del Código penal, del que presuntamente es culpable el/la querellado/a. (3)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.-. Declaración del/de la querellado/a/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D/Dña que ha visto la publicación en red social [COMPLETAR]

[OPCIONAL — incluir si procede]

.- Pericial.

-Del psicólogo D./Dña. [NOMBRE Y APELLIDOS] autor del informe que consta adjunto. (4)

-Informática con dictamen del perito informático que llevó a cabo esta pericial específica del examen del ordenador desde el que se realizó la operación. (5)

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados. Entre ellos acta notarial del Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Ilustre colegio de [COLEGIO] sobre la publicidad de los hechos denunciados. (6)

[OPCIONAL — incluir si procede]

.- Que se oficie a la Brigada tecnológica para llevar a cabo las diligencias de identificación del autor del delito y las diligencias de investigación para detectar el IP del ordenador desde el que vertieron las injurias, así como se interese la entrada y registro para la intervención del ordenador. (7)

SÉPTIMO.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al querellado para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Al amparo de lo dispuesto en el artículo 13 LECRIM, solicitamos dirigirse al prestador de servicios para que suprima o retire de la red social la referencia o mención sobre la que se circunscribe la acción penal ejercitada.

[OPCIONAL — incluir si procede]

.- Dada la gravedad de los hechos por la vía del art. 13 LECRIM y art. 544 bis, 2º párrafo LECRIM solicitamos se adopte la prohibición de comunicación del/de la querellado/a con el/la querellante por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos, realizándose el preceptivo requerimiento o apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que se postula. Adóptese en el auto de admisión de la querella comunicándose por cualquier medio con la parte querellante. (8)

[OPCIONAL — incluir si procede]

.- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. (9)

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se adopten las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) A tenor del artículo 205 CP es calumnia la imputación de un delito hecha con conocimiento de su falsedad o temerario desprecio hacia la verdad.

El artículo 207 CP incluye la exceptio veritatis de que el acusado por delito de calumnia quedará exento de toda pena probando el hecho criminal que hubiese imputado.

Es un delito estrictamente doloso.

El art. 211 CP aclara que la calumnia y la injuria se reputarán hechas con publicidad cuando se propaguen por medio de la imprenta, la radiodifusión o por cualquier otro medio de eficacia semejante. Se entiende que incluye la publicidad on line por medio de redes sociales.

Si el hecho se cometiese en un periódico, por ejemplo, se aplica el artículo 212 CP que señala que: "En los casos a los que se refiere el artículo anterior, será responsable civil solidaria la persona física o jurídica propietaria del medio informativo a través del cual se haya propagado la calumnia o injuria."

En la reforma del CP que se está tramitando en el Parlamento con ocasión de la reforma sobre violencia de género se ha propuesto en el informe del Senado de propuestas de reforma la inclusión de la pena menos grave de prohibición de uso de redes sociales para todos los delitos cometidos utilizando internet o por publicidad, y así estarán incluidos los delitos de calumnias realizados utilizando redes sociales por la gravedad del alcance de la difusión que se produce cuando se calumnia a una persona por redes como Facebook, twitter, o cualesquiera otras redes sociales con gran capacidad de difusión.

(4) No es preciso aportar pericial psicológica de afectación para reclamar daño moral. Este se desprende ya de los hechos probados. Ahora bien, para poder reclamar más, si esa afectación se ha producido, es positivo aportar un informe que acredite la afectación psicológica realizada, lo que permitirá reclamar una cuantía mayor.

(5) Es importante la pericial informática en estos casos, dado que puede el querellado impugnar la prueba digital. En casos de impugnación de prueba digital es carga de la prueba del denunciante/querellante comprobar la veracidad de su contenido por pericial informática, por lo que o bien se acompaña a la querella la misma, o se propone la pericial judicial, o bien una vez se haya impugnado por el denunciado/querellado es cuando puede proponerse la práctica de la pericial informática, ya que sin esta carece de valor probatorio su aportación, si es impugnada por el investigado.

(6) Dado que se trata de delito cometido on line es necesario aportar acta notarial de constancia on line y probar su difusión.

(7) En el caso de desconocer la identidad del autor instar la intervención de la brigada policial de delitos tecnológicos para poder averiguarla identidad del autor de los hechos.

Del mismo modo también se podrá intentar contactar con los prestadores de servicios para dar a conocer la identidad del autor por orden judicial. Si se conoce y así lo acepta el investigado no hará falta esta prueba.

(8) La adopción de esta medida cautelar es fundamental para evitar la reiteración delictiva mientras se sustancie el procedimiento y concluya en sentencia condenatoria con pena del art. 48.3 CP como pena accesoria privativa de derechos del art. 39 h) CP, relativa a La prohibición de comunicarse con la víctima o con aquellos de sus familiares u otras personas que determine el juez o tribunal.

Como señala la SAP de Madrid 291/2017, de 20 de Noviembre, Rec. 1591/2017 "En muchas ocasiones las víctimas sienten temor no solo por la presencia física del condenado, sino, también, por un acto de comunicación virtual del investigado (medida cautelar) o pena (condenado), ya que una víctima que lo ha sido de un hecho del condenado puede incrementar su grado de victimización si recibe comunicaciones de quien le ha amenazado, incluso aunque estas comunicaciones no constituyan un hecho delictivo."

Es por ello, por lo que con independencia de que se interese la pena del art. 48.3 CP, se inste como medida cautelar para anticipar los efectos de la prohibición, dado el peligro de la reiteración y el temor que ello le reporta a la víctima, para quien, lo mismo que se adopta con frecuencia la medida cautelar de alejamiento, es igual de importante la medida cautelar de prohibición de comunicación.

(9) La cautelar que se solicita tiene su base y razón de ser, no solo en la protección de los derechos del perjudicado por el delito, sino en aras a una protección general para evitar la reiteración delictiva de la comisión del ilícito penal por medio de las tecnologías de la comunicación y especialmente por el uso de internet a cualquier futuro perjudicado mientras se tramita la causa y hasta sentencia y su posible transformación en pena.

================================================================================
