---
name: propiedad-industrial-internet-acusacion-622
description: "Redacta el escrito «Propiedad industrial por internet: acusación» (formulario 622 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Propiedad industrial por internet: acusación

> Formulario 0622 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…: CONCLUSIONES PRIMERA.- El/La acusado/a»; «…d, ha estado ofreciendo en la página web»; «…el producto denominado»; «… su registro y titularidad de la empresa»; «…va en circulación comercial desde el año»; «…la entrada por orden judicial en la nave»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- (Si no se hubiera adoptado ya)…
- (Si no se hubiera adoptado ya)…
- (Si no se hubiera adoptado ya)…
- 1.- Interrogatorio del/de la acusado/a.…
- 2.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y qu…
- -D./Dña. [NOMBRE Y APELLIDOS]…
- 3.- Pericial del perito D./Dña. [NOMBRE Y APELLIDOS] que ha evaluado el perjuicio causado al querellante cuyo …
- 4.- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 273.1 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- artículo 273.1 CP
- art. 22 CP
- art. 48.1 y 57 CP
- art. 48 CP
- art. 57 CP
- art. 777.2 LECrim

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

### Formulario 0622 · Propiedad industrial por internet: acusación

- Año del modelo: 2018
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (7); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 7 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento abreviado presenta sus conclusiones provisionales y califica los hechos de delito relativo a la propiedad industrial del art. 273.1 CP, al fabricar y ofrecer por internet el acusado un producto patentado, sin autorización de su titular.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a [COMPLETAR], mayor de edad, ha estado ofreciendo en la página web [COMPLETAR] el producto denominado [COMPLETAR] con expresa conciencia y voluntad de que realizaba la vulneración del derecho de uso o explotación exclusivo de una propiedad industrial derivada de su registro y titularidad de la empresa [COMPLETAR] y con una clara finalidad industrial y comercial, sin consentimiento alguno de mi representado/a, habida cuenta que era perfecto conocedor del previo registro de la patente del citado producto, que lleva en circulación comercial desde el año [COMPLETAR] del registro de la patente y, siendo notoria su implementación en el mercado, ha estado fabricando el mismo producto y, además, lo ha ofrecido en el mercado por medio de internet sin autorización alguna del titular y con una elevada potencialidad difusora ante el tremendo efecto expansivo de internet.

El/La acusado/a ha llevado a cabo esta actividad en los últimos [Nº] años calculándose un perjuicio de [IMPORTE] euros.

El/La acusado/acusada fue requerido por conducto notarial para que cesara en su actividad sin resultado alguno.

SEGUNDA.- Tales hechos son constitutivos del delito relativo a la propiedad industrial del artículo 273.1 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al acusado/a circunstancias agravantes.

Concurre en el acusado/a la agravante del del art. 22 CP.

QUINTA.- Procede imponer al acusado/a por el delito contra la propiedad industrial la pena de [PENA] de prisión y multa de [Nº] meses, a razón de [IMPORTE] euros por día.

Además, procede imponer la pena de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. (3)

SEXTA.- Los daños y perjuicios causados al autor titular de la patente asciende a la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a

SÉPTIMA.- Se interesan las siguientes medidas cautelares:

[OPCIONAL — incluir si procede]

(Si no se hubiera adoptado ya)

- La orden de paralización inmediata de la fabricación y distribución de los productos del/de la acusado/a y la orden de prohibición inmediata de la repetición de los actos que son objeto de acción penal, así como la entrada por orden judicial en la nave [COMPLETAR] sita en [LOCALIDAD] para la oportuna incautación de todos los productos y equipos de fabricación, así como orden de retirada de los que se hallan distribuido en los establecimientos comerciales donde se haya servido previo control de los libros comerciales de clientes.

[OPCIONAL — incluir si procede]

(Si no se hubiera adoptado ya)

- La orden de clausura de la página web desde donde se realiza la difusión de la oferta del producto vulnerador de la marca registrada.

[OPCIONAL — incluir si procede]

(Si no se hubiera adoptado ya)

-Se interesa, además, se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. (4)

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (5)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

2.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados
judicialmente
mediante exhorto

-D./Dña. [NOMBRE Y APELLIDOS], representante legal del centro comercial donde aparecieron productos del/ de la querellado/a vulnerando la patente del/de la querellante

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

- D./Dña. [NOMBRE Y APELLIDOS] agente de la brigada de delitos tecnológicos que investigó la IP desde la que se accedió a internet para la distribución de los productos. (6)

[OPCIONAL — incluir si procede]

3.- Pericial del perito D./Dña. [NOMBRE Y APELLIDOS] que ha evaluado el perjuicio causado al querellante cuyo informe se adjunta como documento nº 3.

[OPCIONAL — incluir si procede]

4.- Documental:

-Documento nº 1: acreditación del registro de la patente.

-Documento nº 2: acta notarial del Notario D./Dña. [NOMBRE Y APELLIDOS] respecto al requerimiento.

-Documento nº 4: acta notarial del Notario D./Dña. [NOMBRE Y APELLIDOS] respecto a la existencia de la página web y la publicidad del producto que era objeto de ataque a la propiedad industrial del/de la querellante. (7)

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) La jurisprudencia ha establecido una serie de condicionamientos para la protección de los derechos de la Propiedad Industrial, a saber:

a) En cuanto a la acción o conducta, una actuación como sinónimo de transgresión o quebrantamiento de los derechos de la propiedad industrial con encaje en los tipos delictivos.
b) En cuanto a la antijuridicidad que la infracción del derecho se haga en atención a la norma reguladora de la propiedad industrial, siendo preciso que la titularidad se encuentre protegida por la previa inscripción registral, además que concurra repulsa social para captar la existencia del atentado defraudatorio.
c) Sobre la culpabilidad, no solamente es preciso el dolo genérico sobre la acción realizada sino el específico de tener intención o ánimo defraudatorio, elemento subjetivo del injusto, originando con ello la imposibilidad de apreciar formas imprudentes.

(3) En este caso, ante la inexistencia de una previsión de esta pena se ha optado por acudir al mecanismo de la "prohibición de acudir al lugar del delito" que se configura en este caso por medio de identificar el "lugar" con "internet", en cuyo caso se acuerda esta pena por la vía del art. 48 CP, en relación con el art. 57 CP. (SJP Barcelona 243/2019, de 29 de mayo, Rec. 7/2018)

(4) La cautelar que se solicita tiene su base y razón de ser, no solo en la protección de los derechos del perjudicado por el delito, sino en aras a una protección general para evitar la reiteración delictiva de la comisión del ilícito penal por medio de las tecnologías de la comunicación y especialmente por el uso de internet a cualquier futuro perjudicado mientras se tramita la causa y hasta sentencia y su posible transformación en pena.

(5) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

(6) La brigada de delitos tecnológicos investiga cuál es la IP del ordenador desde el que se cometieron los hechos. Los agentes declararán ante el juez de instrucción para acreditar que esa IP corresponde al ordenador del que es titular el querellado.

(7) Dado que se trata de delito cometido on line es necesario aportar acta notarial de constancia on line y probar su difusión.

================================================================================
