---
name: suplantacion-identidad-redes-sociales-falsedad-documento-691
description: "Redacta el escrito «Suplantación de identidad en redes sociales (falsedad en documento privado): denuncia» (formulario 691 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplantación de identidad en redes sociales (falsedad en documento privado): denuncia

> Formulario 0691 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] LOCALIDAD
- [ ] CALLE
- [ ] NÚMERO
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] CORREO ELECTRÓNICO
- [ ] COLEGIO
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…calle [CALLE] número [NÚMERO], piso»; «…as han creado un perfil en la red social»; «…meses desde que un amigo, cuyo nombre es»; «…cter esencial." El artículo 395 CP dice:»; «…a creado ese perfil mío en la red social»; «…se dirija orden judicial a la red social»

## Elecciones que hay que hacer

- en nombre propio / en representación de D / en representación de Dña.
- a continuación / en escrito aparte
- judicialmente / mediante exhorto
- b.- / c.-

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (3) a fin de que se realicen las averig…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial. Para que por perito judicial informático se elabore pericia acerca de la intervención en la citad…
- .- Documental, mediante la aportación de acta notarial de fecha [FECHA] donde el/la notario/a del Ilustre Cole…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 265 y 266 LECRIM
- art. 395 CP
- artículos 259 a 269 de la LECRIM
- art. 390 CP
- artículo 395 CP
- artículo 10 de la Ley 39/2015
- art. 401 CP
- art. 26 CP

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

### Formulario 0691 · Suplantación de identidad en redes sociales (falsedad en documento privado): denuncia

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (3); 3 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos, conforme a los arts. 265 y 266 LECRIM, que pueden ser constitutivos de delito de falsedad en documento privado del art. 395 CP, por haber sido víctima de suplantación de identidad en una red social.

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, [ELEGIR: en nombre propio / en representación de D / en representación de Dña.] con domicilio en [LOCALIDAD] calle [CALLE] número [NÚMERO], piso [COMPLETAR] con DNI [DNI/NIE] expedido el día [FECHA], correo electrónico [CORREO ELECTRÓNICO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia (1) y

EXPONGO

ÚNICO.-

Los hechos que motivan la denuncia y que presentan caracteres delictivos son los siguientes:

Persona o personas desconocidas han creado un perfil en la red social [COMPLETAR] con mi identidad subiendo comentarios, fotografías y expresiones de forma constante, ofreciendo servicios sexuales, haciéndolo en mi nombre y creando un desprestigio hacia mi persona. Los hechos se calcula que se han producido desde hace aproximadamente dos meses desde que un amigo, cuyo nombre es [COMPLETAR] me advirtió de la existencia de un perfil a mi nombre en esta red social, causándome un serio perjuicio a mi honor por los contenidos que se han subido a mi nombre y que me perjudican.

Sin perjuicio de una posterior calificación jurídica más exacta, los hechos expuestos revisten los caracteres de un delito del art. 395 CP, en relación con el art. 390 CP (2), que prevé:

"1. Será castigado con las penas de prisión de tres a seis años, multa de seis a veinticuatro meses e inhabilitación especial por tiempo de dos a seis años, la autoridad o funcionario público que, en el ejercicio de sus funciones, cometa falsedad:

1.º Alterando un documento en alguno de sus elementos o requisitos de carácter esencial."

El artículo 395 CP dice: [COMPLETAR]

"El que, para perjudicar a otro, cometiere en documento privado alguna de las falsedades previstas en los tres primeros números del apartado 1 del artículo 390, será castigado con la pena de prisión de seis meses a dos años."

SEGUNDO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (3) a fin de que se realicen las averiguaciones oportunas para identificar la identidad de la persona que ha creado ese perfil mío en la red social [COMPLETAR].

Una vez que La BIT lleve a cabo las diligencias de investigación para detectar la IP del ordenador desde el que se llevó a cabo la suplantación de la identidad, que se redacte oficio policial para interesar la entrada y registro para la intervención del ordenador y se lleve a cabo la intervención y pericial informática de su contenido.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto].

-Declaración del/de la perjudicado/a como denunciante.

-D./Dña. [NOMBRE Y APELLIDOS] persona que me advirtió de la existencia de la mención en la red social a mi nombre.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial. Para que por perito judicial informático se elabore pericia acerca de la intervención en la citada red social por persona investigada cuando sea detectada por la Brigada de delitos tecnológicos.

[OPCIONAL — incluir si procede]

.- Documental, mediante la aportación de acta notarial de fecha [FECHA] donde el/la notario/a del Ilustre Colegio Oficial de [COLEGIO] da fe del contenido detectado en la fecha del acta notarial en la citada red social y de los contenidos que se exponen como si los hubiera subido el/la denunciante consistentes en:

a.- [ELEGIR: b.- / c.-]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta denuncia, se admita, se practiquen las diligencias interesadas, se acuerden las medidas cautelares solicitadas y, una vez se detecte la persona autora de los presentes hechos denunciados, se ejercitará la debida personación como acusación particular.

OTROSÍ DIGO que solicito las siguientes medidas cautelares:

- Que se dirija orden judicial a la red social [COMPLETAR] para que retire de su red la referencia identificativa a mi nombre a la mayor brevedad posible. Se adjunta impreso enviado de esta petición a la citada sin respuesta hasta la fecha.
-

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

Es de Justicia que pido en [LUGAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Desde el 20 de marzo de 2024, fecha de entrada en vigor de la reforma operada en los arts. 265 y 266 LECRIM por el RDL 6/2023, se regula expresamente cuál debe ser el contenido de la denuncia, que hasta entonces era flexible, así como la posibilidad de realizarse por vía telemática.

Puede hacerse personalmente o por medio de mandatario con poder especial para un hecho punible determinado y por escrito o de palabra.

— Por escrito: debe ir firmada por el denunciante de forma autógrafa o manuscrita, si es presencial, o por otra persona a su ruego, si no pudiese hacerlo.

— Por vía telemática: con firma electrónica conforme a lo establecido en el artículo 10 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas y en el Reglamento (UE) 910/2014, de 23 de julio de 2014, relativo a la identificación electrónica y los servicios de confianza para las transacciones electrónicas en el mercado interior.

En el caso de las personas jurídicas, se firmará con certificado electrónico cualificado con atributo de representante, o los medios previstos en la regulación de firma digital que permitan identificar la persona jurídica, así como la persona física que formula la denuncia.

— De palabra: la autoridad que la recibe extiende acta con cuantas noticias tenga el denunciante relativas al hecho denunciado y a sus circunstancias. Es firmada por la autoridad y el denunciante o por otra persona a su ruego.

La denuncia (escrita o verbal) debe contener: la identificación de la persona denunciante, la narración circunstanciada del hecho, la identificación de las personas que hayan cometido el hecho, si fueran conocidas y de quienes lo hayan presenciado o tengan información sobre él y la existencia de cualquier fuente de conocimiento de la que el denunciante tenga noticia, que pueda servir para esclarecer el hecho denunciado.

En caso de persona jurídica o ente sin personalidad jurídica, deberá identificarse también la persona física que formula la denuncia en su nombre, indicando su relación con la persona jurídica o el ente sin personalidad.

No es requisito legal la calificación jurídica de los hechos, pero puede aportarse, si se conoce.

(2) Se ha intentado ubicar la persecución de este tipo de hechos en el delito del art. 401 CP, que prevé que el que usurpare el estado civil de otro será castigado con la pena de prisión de seis meses a tres años. No obstante, la doctrina y la jurisprudencia han puesto de manifiesto las serias dificultades para perseguir estos hechos antes expuestos por este tipo penal. Y ello porque, aunque aparentemente se trataría de una suplantación de la identidad de otra persona para crear ese perfil de otro, la jurisprudencia lo relaciona con la usurpación del "estado civil", que no se produce en estos supuestos. Nótese que si se tratara de un perfil falso de alguien que no existe no habría problema, porque el autor está creando un perfil falso de una identidad supuesta para enmascararse en esa identidad para que no se conozca su autoría.

En estos casos podría acudirse a la vía de considerar los supuestos de suplantación de identidad como un delito de falsificación de documento del art. 395 CP. Y ello porque los servicios prestados por Internet suelen estar soportados por un contrato mercantil, y la página web no deja de ser un documento, aunque sea electrónico, por lo que el falseamiento de los datos implica que se ha falsificado un documento mercantil. Además, el art. 26 CP considera documento todo soporte material que exprese o incorpore datos, hechos o narraciones con eficacia probatoria o cualquier otro tipo de relevancia jurídica, y, por lo tanto, no solo el documento papel, sino también los archivos electrónicos, han de ser considerados documentos, al contener información con aquellas características. Así lo ha entendido la Audiencia Provincial de Madrid en su Auto AP Madrid 461/2017, de 25 de mayo, Rec. 706/2017.

Se configura la creación de un perfil de una red social como un "archivo electrónico", y, por consecuencia, como un documento, de tal manera que si creamos ese perfil a nombre de otra persona se estará actuando de forma falsaria y faltando a la verdad en la identidad de la persona que ha abierto ese perfil, y se hace pasar por ella, por lo que no tendrá cabida en el art. 401 CP por no suplantarse "el estado civil", pero sí que se estará cometiendo una falsedad en "archivo electrónico".

(3) Para averiguar esta autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica. Es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia: pornografía infantil, estafas y fraudes por Internet, fraudes en el uso de las comunicaciones, ataques cibernéticos, piratería...

La Brigada de Investigación Tecnológica está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF), que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

Podría ocurrir que a la hora de acceder a determinados datos para conocer la autoría la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a LECRIM y ss en su nueva redacción para poder conseguir pruebas en casos de delitos cometidos por medio de la informática, como requerir a los administradores de la red social la dirección IP desde la que fue creada la cuenta, la dirección de correo electrónico a la que está asociada, la dirección IP desde la que se accedió a la mencionada cuenta en determinado plazo; requerir al operador que prestó el servicio el nombre y dirección del abonado o del usuario registrado al que se le ha asignado la dirección de Protocolo de Internet (IP) desde la que se creó la cuenta suplantadora en la red social.

================================================================================
