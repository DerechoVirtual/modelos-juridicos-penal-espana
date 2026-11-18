---
name: conduccion-temeraria-denuncia-370
description: "Redacta el escrito «Conducción temeraria: denuncia» (formulario 370 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción temeraria: denuncia

> Formulario 0370 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] MATRÍCULA
- [ ] NÚMERO
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] ...
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, y contra la entidad aseguradora»; «…bilidad civil con la entidad aseguradora»; «…do la fecha de su envío a la aseguradora»; «…portó oferta motivada por la aseguradora»; «… LECRIM que se requiera a la aseguradora»; «…igo Penal, contra la entidad aseguradora»; «…uradora. Es Justicia que pido en [LUGAR]»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la denunciante.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS] que presenció el accidente.…
- .- Pericial médico forense para lo que se interesa sea reconocido por el médico forense.…
- .- Documental siguiente:…
- (Otrosí ejercitando acción contra la Compañía Aseguradora)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 380 CP
- art. 152 CP
- art. 382 CP
- arts. 9.3 y 24.1 CE
- artículos 1, 100, 111 LECRIM
- artículos 112 y 259 a 269 LECRIM
- art. 152.1 CP
- artículo 380 y 382 CP
- art. 765 LECRIM
- art. 7.2 RDLeg. 8/2004
- art. 20.3 Ley 50/1980
- artículo 76 de la Ley 50/1980
- artículo 117 del Código Penal
- artículo 20 de la Ley 50/1980
- art. 9 del RDLeg. 8/2004
- art. 24.1 LEC
- art. 4 LEC
- art. 24.2 LEC
- art. 77 RDL 6/2023
- arts. 265 y 266 LECRIM
- artículo 10 de la Ley 39/2015
- Ley 35/2015

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

### Formulario 0370 · Conducción temeraria: denuncia

- Año del modelo: 2021
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (6); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 bloques de alternativas señalados; 5 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (FECHA)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de un delito de conducción temeraria del art. 380 CP con resultado de lesiones del art. 152 CP, por lo que se aplicará la pena del delito más grave en su mitad superior, conforme al art. 382 CP

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original]

Que, por medio del presente escrito, formula DENUNCIA (2) en base a los arts. 9.3 y 24.1 CE, y artículos 1, 100, 111 LECRIM, artículos 112 y 259 a 269 LECRIM y ss, contra D./Dña. [NOMBRE Y APELLIDOS], y contra la entidad aseguradora [COMPLETAR], con base en los siguientes

HECHOS

PRIMERO.- Los hechos que motivan la denuncia y que presentan caracteres delictivos son los siguientes:

El día [FECHA] circulaba el/la denunciante por la avenida con el vehículo matrícula [MATRÍCULA] cuando detrás lo hacía el vehículo con matrícula conducido por D/Dña. [NOMBRE Y APELLIDOS] quien, de una forma claramente temeraria comenzó a darle la luz larga con la intención de que acelerara la velocidad, al mismo tiempo que hacía gestos ostensibles de que fuera más rápido, como el/la denunciante pudo detectar por el espejo retrovisor. Tras esta presión que ejercía poniéndose, incluso, detrás del vehículo de el/la denunciante a escasos cm, adelantó en una curva con grave riesgo para su integridad y, cuando estaba justo a su lado, dio un volantazo y golpeó con su vehículo el de el/la denunciante colisionando y sacándole de la carretera, éste último, colisionando con la pared de un edificio.

Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de lesiones del art. 152.1 CP, y de conducción temeraria del artículo 380 y 382 CP. (3)

SEGUNDO.- El vehículo de el/la denunciado/a tenía concertado contrato de seguro de responsabilidad civil con la entidad aseguradora [COMPLETAR], con póliza n.º [NÚMERO] (4)

TERCERO.- Como consecuencia de los hechos antes descritos, el/la denunciante sufrió lesiones por las que precisó asistencia hospitalaria.

Asimismo, como consecuencia de la colisión, se produjeron desperfectos materiales en el vehículo que conducía el/la denunciante, cuya reparación asciende a la suma de [IMPORTE] euros.

CUARTO.- Se ha formulado, de igual modo, reclamación del perjudicado por la vía del art. 7.2 RD Leg. 8/2004, conforme se acompaña como documento adjunto, constando la fecha de su envío a la aseguradora [COMPLETAR].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No se aportó oferta motivada por la aseguradora [COMPLETAR]. (5)

Se aportó la siguiente oferta motivada por la aseguradora

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de denuncia y documentos, se admita, se practiquen las diligencias interesadas y se acuerde como medida cautelar ex art. 765 LECRIM que se requiera a la aseguradora [COMPLETAR] para que presente en concepto de pensión provisional la suma de [IMPORTE] euros al mes en la cuenta de consignaciones de este órgano judicial a disposición de el/la denunciante hasta la fecha del juicio. (6)

OTROSÍ DIGO que como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la denunciante.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de el/la denunciado/a

-Declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] que presenció el accidente.

- D./Dña. [NOMBRE Y APELLIDOS], representante del taller donde se efectuó la reparación o se efectuará

- D./Dña. [NOMBRE Y APELLIDOS] representante del centro de trabajo donde está de baja.

[OPCIONAL — incluir si procede]

.- Pericial médico forense para lo que se interesa sea reconocido por el médico forense.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

— Atestado elaborado por la guardia civil.
— Fotografías del estado del vehículo y el lugar del accidente y el resultado de cómo quedó la casa.
— Facturas del vehículo y reparación.
— Facturas de los gastos médicos.
— Reclamación del perjudicado a la aseguradora de el/la denunciado/a del art. 7.2 RDLeg. 8/2004 y al objeto del devengo de los intereses de demora desde la fecha del siniestro ex art. 20.3 Ley 50/1980 de Contrato de Seguro.

[OPCIONAL — incluir si procede]

(Otrosí ejercitando acción contra la Compañía Aseguradora)

OTROSÍ DIGO: que, ejercitando la acción directa prevista en el artículo 76 de la Ley 50/1980 de 8 de octubre, del Contrato de Seguro y en el artículo 117 del Código Penal, contra la entidad aseguradora [COMPLETAR], intereso su citación a juicio y su condena en sentencia y,

A LA SECCIÓN VUELVO A SUPLICAR: se cite a juicio y, en su día, se condene como responsable directo a la aseguradora indicada, condenándole a que abone, además, el interés que corresponda de conformidad con lo establecido en el artículo 20 de la Ley 50/1980 de 8 de octubre, del Contrato de Seguro y en el art. 9 del RDLeg. 8/2004, texto refundido de la Ley sobre Responsabilidad Civil y Seguro en la Circulación de Vehículos a Motor, aplicándose el interés moratorio al no haberse contestado la oferta motivada por la aseguradora.

Es Justicia que pido en [LUGAR]

[COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Desde el 20 de marzo de 2024, fecha de entrada en vigor de la reforma operada en los arts. 265 y 266 LECRIM por el RDL 6/2023, se regula expresamente cuál debe ser el contenido de la denuncia, que hasta entonces era flexible, así como la posibilidad de realizarse por vía telemática.

Puede hacerse personalmente o por medio de mandatario con poder especial para un hecho punible determinado y por escrito o de palabra.

— Por escrito: debe ir firmada por el denunciante de forma autógrafa o manuscrita, si es presencial, o por otra persona a su ruego, si no pudiese hacerlo.

— Por vía telemática: con firma electrónica conforme a lo establecido en el artículo 10 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas y en el Reglamento (UE) 910/2014, de 23 de julio de 2014, relativo a la identificación electrónica y los servicios de confianza para las transacciones electrónicas en el mercado interior.

En el caso de las personas jurídicas, se firmará con certificado electrónico cualificado con atributo de representante, o los medios previstos en la regulación de firma digital que permitan identificar la persona jurídica, así como la persona física que formula la denuncia.

— De palabra: la autoridad que la recibe extiende acta con cuantas noticias tenga el denunciante relativas al hecho denunciado y a sus circunstancias. Es firmada por la autoridad y el denunciante o por otra persona a su ruego.

La denuncia (escrita o verbal) debe contener: la identificación de la persona denunciante, la narración circunstanciada del hecho, la identificación de las personas que hayan cometido el hecho, si fueran conocidas y de quienes lo hayan presenciado o tengan información sobre él y la existencia de cualquier fuente de conocimiento de la que el denunciante tenga noticia, que pueda servir para esclarecer el hecho denunciado.

En caso de persona jurídica o ente sin personalidad jurídica, deberá identificarse también la persona física que formula la denuncia en su nombre, indicando su relación con la persona jurídica o el ente sin personalidad.

No es requisito legal la calificación jurídica de los hechos, pero puede aportarse, si se conoce.

(3) Aunque en la denuncia no es necesario una calificación jurídica sí puede contenerla. En este caso los hechos son constitutivos del delito de conducción temeraria del art. 380 CP, pero nótese que generalmente cuando se formule denuncia por la víctima será porque el conductor responsable ha causado un accidente con su temeraria conducción, lo que determinará que entre en juego el art. 382 CP que prevé que cuando con los actos sancionados en el art. 380 CP se ocasionase, además del riesgo prevenido, un resultado lesivo constitutivo de delito, bien de homicidio imprudente, bien de lesiones, cualquiera que sea su gravedad, se apreciará tan sólo la infracción más gravemente penada, aplicando la pena en su mitad superior y condenando, en todo caso, al resarcimiento de la responsabilidad civil que se hubiera originado. (STS 350/2020 de 25 de junio, Rec. 3491/2018).

Con ello, el delito de conducción temeraria es un delito de riesgo concreto pero, salvo que sea la policía la que levante atestado por un hecho como tal de conducción temeraria, en cuyo caso no hay perjudicado, al no existir daño, habría denuncia si alguien lo fuera, como en este ejemplo.

El Tribunal Supremo (SSTS 2251/2001, de 29 de noviembre, y 1039/2001, de 29 de mayo) ha precisado que «la simple conducción temeraria, creadora por sí misma de un peligro abstracto no sería suficiente, debiendo quedar acreditada la existencia de un peligro concreto [...] peligro que ha de ser efectivo, constatable para la vida o integridad física de personas concretas, distintas del sujeto pasivo».

(4) Si desconocemos la identidad de la compañía de seguros que cubre la RC del causante, podemos solicitar a este órgano judicial que requiera al Consorcio de Compensación de Seguros para que éste aporte a los autos certificado de seguro del vehículo causante, bien por Otrosí, bien mediante escrito presentado al efecto. También cabe la posibilidad de interesar que el juez requiera al denunciado para que acredite la existencia de póliza de seguro de RC.

Para conocer el contenido del contrato de seguro del vehículo causante del accidente de circulación, se puede solicitar a el juez que requiera a la compañía de seguros para que lo aporte a los autos.

(5) El contenido de esta reclamación que se debe adjuntar está incluido en el art. 7.1 RD Leg. 8/2004. Recordemos, pues, que la Ley 35/2015 ha modificado el RDLeg 8/2004 en sus arts 7 y 9, y en concreto en el art. 7 regula la figura de la reclamación del perjudicado que debe efectuar este a la aseguradora a fin de instar de ésta la consignación y la oferta motivada que haga ante su reclamación reflejándose en el art. 7 los requisitos que debe reunir la reclamación del perjudicado, la cual se adjuntará a la denuncia. Recuérdese que ésta debe llevarse a cabo de forma fehaciente con indicación de fecha [FECHA], ya que solo de esa forma podremos saber si el plazo de que dispone la aseguradora de tres meses para presentar la oferta se ha cumplido, lo que es importante para reclamar luego los intereses de demora.

(6) Es importante la posibilidad de interesar la pensión provisional con cargo a la aseguradora del vehículo del responsable ex art. 765 LECRIM para poder asumir el perjudicado los primeros gastos médicos del siniestro que pudiese haber ocurrido.

================================================================================
