---
name: defraudacion-fluido-electrico-denuncia-410
description: "Redacta el escrito «Defraudación de fluido eléctrico: denuncia» (formulario 410 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Defraudación de fluido eléctrico: denuncia

> Formulario 0410 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- La LO 1/2026 añadió el art. 255.3 CP: si la defraudación, cualquiera que sea su cuantía, sirve para abastecer instalaciones de cultivo o tráfico de drogas (art. 368), la pena es prisión de seis a dieciocho meses o multa de doce a veinticuatro meses (BOE-A-2026-7966).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] LUGAR (5 veces)
- [ ] CALLE (2 veces)
- [ ] DNI/NIE
- [ ] FECHA (3 veces)
- [ ] XXXXX@DOMINIO
- [ ] NÚMERO (3 veces)
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] Nº
- [ ] IMPORTE (3 veces)
- [ ] EXPLICAR
- [ ] DATOS DE FILIACIÓN (2 veces)
- [ ] ORDINAL QUE CORRESPONDA (4 veces)
- [ ] SI
- [ ] NÚMERO QUE CORRESPONDA
- [ ] NOMBRE
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en nombre propio / en representación de]»; «…259 a 269 de la LECRIM, formulo denuncia»; «…euros, desde el año»; «…la empresa de suministro de electricidad»; «…Firma de Abogado/a Firma de Procurador/a»

## Elecciones que hay que hacer

- en nombre propio / en representación de
- Firma del/de la denunciante Firma del/de la denunciante

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- [ORDINAL QUE CORRESPONDA]. [DATOS DE FILIACIÓN], Número personal del Documento Nacional de Identidad y domicil…
- 1.- Declaración del/de la denunciado/a.…
- [ORDINAL QUE CORRESPONDA].- Testifical:— Declaración del/ de la denunciante [NOMBRE Y APELLIDOS]— Testifical d…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- [ORDINAL QUE CORRESPONDA].- Documental:— Copia de las facturas descargadas de internet de los últimos dos años…
- [ORDINAL QUE CORRESPONDA].- Que se oficie a la compañía eléctrica para que efectúe las averiguaciones en el cu…
- (Si se designa abogado y procurador ya en la denuncia) [NÚMERO QUE CORRESPONDA]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 265 y 266 LECRIM
- art. 255 CP
- artículos 259 a 269 de la LECRIM
- art. 13 de la Ley de Enjuiciamiento Criminal
- art. 24.1 LEC
- art. 4 LEC
- art. 24.2 LEC
- art. 77 RDL 6/2023
- artículo 10 de la Ley 39/2015

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

### Formulario 0410 · Defraudación de fluido eléctrico: denuncia

- Año del modelo: 2020
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); 8 llamadas a nota sin texto retiradas; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 bloques de alternativas señalados; 5 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (Nº, Nº DE DOCUMENTO)
- Avisos de la revisión: La LO 1/2026 añadió el art. 255.3 CP: si la defraudación, cualquiera que sea su cuantía, sirve para abastecer instalaciones de cultivo o tráfico de drogas (art. 368), la pena es prisión de seis a dieciocho meses o multa de doce a veinticuatro meses (BOE-A-2026-7966).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos, conforme a los arts. 265 y 266 LECRIM, que presentan los caracteres de un delito de defraudación del fluido eléctrico del art. 255 CP por enganche irregular de contador de una vivienda a otra.

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Si la presenta directamente la víctima o su representante)
— D/Dña. [NOMBRE Y APELLIDOS], mayor de edad, [ELEGIR: en nombre propio / en representación de] [COMPLETAR] con domicilio en [LUGAR], calle [CALLE], número y piso, con DNI número [DNI/NIE] expedido el día [FECHA], correo electrónico [XXXXX@DOMINIO].com, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:(Si la presenta con Procurador y Abogado)
— D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— Si el poder se otorga a través de la sede judicial electrónicamediante comparecencia electrónica, a través de la sede judicial electrónica e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizadaSi el poder se otorga mediante comparecencia apud actamediante comparecencia personal apud acta ante el Letrado de la Administración de Justicia de la oficina judicial de [LUGAR] posteriormente inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizadaSi el poder se otorga ante Notariomediante escritura de poder otorgada a mi favor, ante el/la Notario/a D./Dña. [NOMBRE Y APELLIDOS], con Notaría sita en [LUGAR] El poder se inscribió en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO]; lo cual se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nºpor si no es posible la consulta automatizadabajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [CALLE], número, ciudadcolegiado nº [Nº] del Ilustre Colegio de la Abogacía de [LUGAR], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia [COMPLETAR] con base en los siguientesHECHOSPRIMERO.- Los hechos que motivan la denuncia y que presentan caracteres delictivos son los siguientes:El/La denunciante es propietario/a y reside en el inmueble arriba indicado de forma habitual. Con fecha [FECHA] hemos recibido la factura del consumo de luz de los dos meses últimos y para nuestra sorpresa se ha multiplicado por 3 el importe de la factura cuando la media bimensual es de [IMPORTE] euros, desde el año [COMPLETAR], como consta claramente en los documentos que se acompañan a la denuncia, cuando el importe ahora facturado es de [IMPORTE] euros.

Realizadas las investigaciones oportunas nos comunica el/la conserje D./Dña. [NOMBRE Y APELLIDOS] que el piso colindante al mío cree que [EXPLICAR] las razones que haya descubierto y que puede que haya llevado a cabo un enganche ilegal, que sea la razón de la subida de la factura.

El perjuicio ocasionado es de [IMPORTE] euros, que es la diferencia entre el importe medio facturado y la factura real cursada.

SEGUNDO.- Los datos de la/s persona/s denunciada/s que se conocen son:1. [DATOS DE FILIACIÓN], Número personal del Documento Nacional de Identidad y domicilio.
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
[ORDINAL QUE CORRESPONDA]. [DATOS DE FILIACIÓN], Número personal del Documento Nacional de Identidad y domicilio.

TERCERO.- Los hechos expuestos revisten los caracteres de un delito del art. 255 CP. El importe defraudado supera los 400 euros. CUARTO.- SUPLICO A LA SECCIÓN:Que tenga por presentado este escrito de denuncia y documentos, se admita y se sirva acordar lo pertinente para la comprobación y averiguación de los hechos y sus autores.

PRIMER OTROSÍ DIGO: que como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la denunciado/a.

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Testifical:— Declaración del/ de la denunciante [NOMBRE Y APELLIDOS]— Testifical de los/as vecinos/as del inmueble:
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Documental:— Copia de las facturas descargadas de internet de los últimos dos años en las que se comprueba el importe medio facturado.— Copia de la última factura donde consta el desfase y acredita el enganche ilegal.— Que se remita orden judicial a la empresa de suministro de electricidad [COMPLETAR] a fin de que lleve a cabo un examen del contador de luz para cerciorarse de un posible enganche ilegal de luz que se haya cometido.— Que se requiera al/a la denunciado/a a que aporte su contrato de luz con la compañía de electricidad. Si el piso fuera alquilado, que se requiera al/a la titular del inmueble para ello y se le reciba declaración en testifical. Si el piso hubiera sido ocupado ilegalmente exactamente igual, a fin de saber si estaba dado de alta en la compañía eléctrica.

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Que se oficie a la compañía eléctrica para que efectúe las averiguaciones en el cuadro de contadores, a fin de comprobar quién ha llevado a cabo el enganche ilegal. [SI] no se conoce la identidad del autor del enganche ilegal

SEGUNDO OTROSÍ DIGO: que, conforme a lo dispuesto en el art. 13 de la Ley de Enjuiciamiento Criminal, se interesa se acuerde la medida cautelar de retirada del enganche ilegal en el caso de que la compañía eléctrica lo detecte, disponiendo lo necesario para que, de forma urgente, se acceda en 24 horas a la adopción de un auto de entrada en el inmueble dando orden a la compañía eléctrica para comprobar si existe ese enganche ilegal, siendo auxiliada por la comisión judicial de las Fuerzas y Cuerpos de Seguridad del Estado que garanticen su ejecución debida.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia) [NÚMERO QUE CORRESPONDA]

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE], Apellidosy al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

Es de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR: Firma del/de la denunciante Firma del/de la denunciante]

Firma de Abogado/a

Firma de Procurador/a [COMPLETAR] En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).
 Desde el 20 de marzo de 2024, fecha de entrada en vigor de la reforma operada en los arts. 265 y 266 LECRIM por el RDL 6/2023, se regula expresamente cuál debe ser el contenido de la denuncia, que hasta entonces era flexible, así como la posibilidad de realizarse por vía telemática.

Puede hacerse personalmente o por medio de mandatario con poder especial para un hecho punible determinado y por escrito o de palabra.— Por escrito: debe ir firmada por el denunciante de forma autógrafa o manuscrita, si es presencial, o por otra persona a su ruego, si no pudiese hacerlo.— Por vía telemática: con firma electrónica conforme a lo establecido en el artículo 10 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas y en el Reglamento (UE) 910/2014, de 23 de julio de 2014, relativo a la identificación electrónica y los servicios de confianza para las transacciones electrónicas en el mercado interior.

En el caso de las personas jurídicas, se firmará con certificado electrónico cualificado con atributo de representante, o los medios previstos en la regulación de firma digital que permitan identificar la persona jurídica, así como la persona física que formula la denuncia.— De palabra: la autoridad que la recibe extiende acta con cuantas noticias tenga el denunciante relativas al hecho denunciado y a sus circunstancias. Es firmada por la autoridad y el denunciante o por otra persona a su ruego.

La denuncia (escrita o verbal) debe contener: la identificación de la persona denunciante, la narración circunstanciada del hecho, la identificación de las personas que hayan cometido el hecho, si fueran conocidas y de quienes lo hayan presenciado o tengan información sobre él y la existencia de cualquier fuente de conocimiento de la que el denunciante tenga noticia, que pueda servir para esclarecer el hecho denunciado.

En caso de persona jurídica o ente sin personalidad jurídica, deberá identificarse también la persona física que formula la denuncia en su nombre, indicando su relación con la persona jurídica o el ente sin personalidad.

No es requisito legal la calificación jurídica de los hechos, pero puede aportarse, si se conoce.
 En caso de no conocer la identidad del autor del enganche ilegal se haría constar que se presenta contra el autor del enganche ilegal y se interesaría en el suplico la práctica de diligencias dirigidas a que por la compañía eléctrica se efectúen averiguaciones en el cuadro de contadores, a fin de comprobar quién ha llevado a cabo el enganche ilegal, ya que ello solo podrá hacerlo la compañía y que se comunique a este órgano judicial esa identidad, ya que se hace por orden judicial la diligencia interesada. No puede saberse de otra manera la identidad.
 En el delito del art. 255 CP deberían ser los técnicos de la empresa suministradora los que, cuando van a comprobar la lectura de contadores, detecten la existencia del enganche y den cuenta a la mercantil del hecho producido para ejercitar esta las acciones penales frente al infractor, pero no llevar a cabo un cargo al vecino que ha sufrido en su toma el enganche de aquél, o dejar que sea el vecino o la comunidad los que tengan que ejercitar las acciones civiles y/o penales frente al infractor, bien para evitar que lo siga haciendo al interesar medidas cautelares penales o la ejecución de la responsabilidad personal subsidiaria en caso de impago de la multa que se le imponga e ingreso corolario en prisión, bien para tratar de recuperar por la vía civil lo que al titular perjudicado se le ha defraudado, cuando en realidad el concepto de «perjudicado» debe atribuírsele a la empresa suministradora de la luz, no al propietario al que se le hace el enganche ilegal.

Por ello, el concepto de perjudicado en el delito de defraudación de fluido eléctrico debe ser atribuible a la compañía que es la suministradora de la luz, no el vecino a quien se engancha la toma de luz llevada a cabo de forma irregular, ya que las posibilidades de detectar la acción ilícita no son del vecino, sino de la empresa que tiene en su haber y disposición la posibilidad de saber y conocer quien ha efectuado la maniobra ilegal.

Por lo tanto, junto a la denuncia que debería presentar la empresa suministradora de la luz, se aportaría la fotografía de la acción ejecutada con la fecha, copia de los recibos de consumo de luz del vecino y un informe pericial de parte de la compañía con el cálculo estimado de la correspondencia del consumo defraudado. Pero, por ello, no se le debería cargar a este vecino al que se le practicó el enganche el cargo de la totalidad del recibo, sino efectuar un cálculo del consumo estimado y aplicarle el mismo, vigilando en lo sucesivo de forma más periódica el acceso a los cuadros de contadores, o bien que las propias comunidades de propietarios se esmeren en cerrar estos compartimentos para que solo y exclusivamente pueda entrar en ellos la empresa suministradora de la luz.

En todo caso, si es el vecino defraudado al que la empresa le ha pasado el cargo el que presenta la denuncia podría plantearle luego a la empresa la existencia de la prejudicialidad penal del caso, por haber presentado la denuncia contra el infractor, si la empresa decidiera proceder judicialmente contra él por la vía civil, dado que suscitaría en el pleito civil la paralización de la reclamación y que no le corresponde a él el control y vigilancia del cuadro de contadores, resultando evidente que se ha realizado la defraudación de fluido eléctrico, a fin de que se proceda a efectuar las investigaciones que fueran necesarias para ello.

Si cabe, el vecino en estos casos podría interesar la colaboración de la comunidad para acceder al cuadro de contadores y poder obtener pruebas acerca de quién es el inmueble que recibe la luz que es cargada en su contador de luz para que la acción penal se dirija contra el titular del inmueble o sus ocupantes.

Sería en este procedimiento donde podría personarse, en todo caso, la compañía de la luz para reclamar frente al o los denunciados la suma del importe de las cantidades que resulten de realizar el cálculo antes expuesto. No hay que olvidar que el lugar donde se encuentra el cuadro de contadores no es de libre acceso al propietario, sino que pertenece a la empresa suministradora de luz su control. Los vecinos son responsables de lo que ocurre de puertas hacia adentro de su inmueble, pero no de lo que ocurra fuera de él, y si hay una alteración de su cuadro de contadores no es su responsabilidad.

Por otro lado, la comunidad de propietarios también podría intervenir directamente presentando la denuncia acerca de que alguien ha accedido al cuadro de contadores que no es zona privada de nadie, ni común de la propia comunidad, sino un elemento al que solo puede acceder personal de la compañía que suministra la luz. Por ello, la comunidad de propietarios, si recibe la queja en este sentido de un vecino, comunicaría con la empresa suministradora de la luz para que se acceda al cuarto de contadores y que, con la presencia del presidente, el administrador de fincas o un empleado de la comunidad se pudieran obtener las pruebas tendentes a identificar al autor o autores de la defraudación.

En este tipo de casos suele alegarse que se trata de una cuestión civil por el montante económico defraudado y no penal. No obstante, nos encontramos ante un ilícito penal, como lo destaca la jurisprudencia. Y así, la SAP Guadalajara 39/2009, de 3 de marzo, rec. 73/2009.Interesante también resulta en estos casos el supuesto en el que, a raíz de una entrada y registro por un delito distinto, por ejemplo, contra la salud pública, se detecta la existencia de estos enganches ilegales, y la cuestión a resolver es si tiene validez el auto habilitante para la entrada y registro a raíz de un caso de tráfico de drogas para de ahí depurar responsabilidades también por otro del que ahora estamos analizando. Y sobre esta validez se pronuncia la SAP Balears 170/2013, de 3 de julio, rec. 175/2013.

================================================================================
