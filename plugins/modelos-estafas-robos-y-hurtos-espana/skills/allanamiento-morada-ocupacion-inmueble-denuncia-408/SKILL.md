---
name: allanamiento-morada-ocupacion-inmueble-denuncia-408
description: "Redacta el escrito «Allanamiento de morada por ocupación de inmueble: denuncia» (formulario 408 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Allanamiento de morada por ocupación de inmueble: denuncia

> Formulario 0408 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- Desde el 3-4-2025 los delitos de allanamiento de morada (art. 202 CP) y de usurpación (art. 245 CP) pueden tramitarse por juicio rápido si hay atestado policial (art. 795.1.2.ª i) y j) LECrim, LO 1/2025, BOE-A-2025-76).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] DNI/NIE
- [ ] CORREO ELECTRÓNICO
- [ ] TELÉFONO
- [ ] PROFESIÓN
- [ ] LOCALIDAD (2 veces)
- [ ] CALLE
- [ ] FECHA (2 veces)
- [ ] IMPORTE
- [ ] Nº DE DOCUMENTO
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e que ha sido ocupado son los siguientes»; «…abitual, ya que ocupa ese inmueble desde»; «…última vez que fuimos a nuestra casa fue»; «…, y es ahora cuando, en el transcurso de»; «…e la fecha de acceso está entre los días»; «…y»; «… La fecha de adquisición del inmueble es»; «…del contrato de arrendamiento firmado el»; «…e consta que los inquilinos actuales son»; «…en la siguiente dirección web»; «…y/o anunciada en»

## Elecciones que hay que hacer

- a la venta / en alquiler

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (12)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de los denunciados.…
- .-Declaración del/de la denunciante.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS] vecino/a del inmueble…
- D./Dña. [NOMBRE Y APELLIDOS] familiar del/de la denunciante acerca del uso habitual del inmueble y su consider…
- - La fecha de adquisición del inmueble es [COMPLETAR] según consta en el documento nº [Nº DE DOCUMENTO] adjunt…
- - Copia de los recibos de los suministros de luz, agua, gas, etc, que tiene dados de alta.…
- - Fotografías del acceso al inmueble con el cambio de cerradura.…
- - Prueba digital de video grabado del/de la denunciante intentando convencer a los ocupantes del inmueble y su…
- (Si el inmueble está alquilado)…
- (Si el inmueble está puesto a la venta o alquiler)…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 265 y 266 LECRIM
- art. 202.1 CP
- art. 13 LECRIM
- artículos 259 a 269 de la LECRIM
- art. 13 de la Ley de Enjuiciamiento Criminal
- art. 202 CP
- art. 245.2 CP
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

### Formulario 0408 · Allanamiento de morada por ocupación de inmueble: denuncia

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 2 bloques de alternativas señalados; 10 párrafos opcionales señalados; 29 campos de relleno marcados en blanco
- Avisos de la revisión: Desde el 3-4-2025 los delitos de allanamiento de morada (art. 202 CP) y de usurpación (art. 245 CP) pueden tramitarse por juicio rápido si hay atestado policial (art. 795.1.2.ª i) y j) LECrim, LO 1/2025, BOE-A-2025-76).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Denuncia, conforme a los arts. 265 y 266 LECRIM, de unos hechos que presentan los caracteres de un delito de allanamiento de morada del art. 202.1 CP, por ocupación de inmueble, con solicitud de medida cautelar urgente de desalojo y restitución del art. 13 LECRIM. Se incluyen los requisitos exigidos en la Instrucción no 6/2020 de la Secretaría de Estado de Seguridad.

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

Al Juez en servicio de Guardia

D./Dña. [NOMBRE Y APELLIDOS], con DNI núm. [DNI/NIE], correo electrónico [CORREO ELECTRÓNICO] y teléfono [TELÉFONO] a los efectos de notificaciones, en su propio nombre y derecho, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia (1) con base en los siguientes

HECHOS

PRIMERO.- El/La denunciante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en calle [CALLE].

Se desconoce la identidad de los denunciados que han entrado ilegalmente en mi inmueble.

Los datos del inmueble que ha sido ocupado son los siguientes [COMPLETAR].

SEGUNDO.- Los hechos que motivan la denuncia y que presentan caracteres delictivos son los siguientes:

El denunciante es propietario y reside en el inmueble arriba indicado de forma habitual, ya que ocupa ese inmueble desde [COMPLETAR], por lo que lo tiene amueblado y con los servicios de suministros de luz, agua, y gas dados de alta.

El día [FECHA] me dispuse a entrar con mi familia, como lo hacemos de forma habitual, en la que también constituye nuestra morada, cuando nos dimos cuenta de que nos habían cambiado la cerradura de acceso. Tocamos la puerta y al otro lado una persona que no se identificó nos dijo que han entrado ellos y que ahora es suya, negándonos la entrada. Incluso nos dijeron que se la habían alquilado a una persona de la que no nos dio datos, lo cual es absolutamente incierto, porque es nuestra casa y no hemos dado poder alguno de disposición de la misma.

La última vez que fuimos a nuestra casa fue [COMPLETAR], dejando la puerta cerrada con llave, y es ahora cuando, en el transcurso de [COMPLETAR], han entrado en el inmueble estas personas, forzando el acceso y cambiando la cerradura. Se calcula, por tanto, que la fecha de acceso está entre los días [COMPLETAR] y [COMPLETAR].

No existe absolutamente ninguna relación de los denunciantes con los ocupantes.

Solicitamos la devolución inmediata de la posesión del inmueble como medida cautelar sin mayor retardo.

Sin perjuicio de una tasación posterior de los daños y perjuicios que resulten finalmente, se calcula que los perjuicios causados pueden ascender a la suma de [IMPORTE], comprensivos del daño moral que nos están causando y los que resulten de no poder ingresar en nuestra morada.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de allanamiento de morada del art. 202.1 CP. (2)

En consecuencia, y dado que me considero víctima de un delito,

SUPLICO A LA SECCIÓN:

Que se sirva acordar lo pertinente para la comprobación y averiguación de los hechos y sus autores.

PRIMER OTROSÍ DIGO que como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de los denunciados.

[OPCIONAL — incluir si procede]

.-Declaración del/de la denunciante.

[OPCIONAL — incluir si procede]

.- Testifical:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] vecino/a del inmueble

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] familiar del/de la denunciante acerca del uso habitual del inmueble y su consideración de morada:

.- Documental:

Tal y como se señala en la Instrucción 1/2020 FGE y en la Instrucción 6/2020 de la Secretaría de Estado de seguridad de interior, se adjunta:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Título de propiedad del inmueble sito en [LOCALIDAD] a nombre del/de la denunciante.

No se dispone del título de propiedad por estar dentro del inmueble allanado por lo que, en la adopción de la medida cautelar de acceso al inmueble se solicita se permita al/a la denunciante localizar los documentos que acreditan su titularidad.

La correspondiente certificación registral firmada electrónicamente por el Registrador y con el pertinente código seguro de verificación.

[OPCIONAL — incluir si procede]

- La fecha de adquisición del inmueble es [COMPLETAR] según consta en el documento nº [Nº DE DOCUMENTO] adjunto.

[OPCIONAL — incluir si procede]

- Copia de los recibos de los suministros de luz, agua, gas, etc, que tiene dados de alta.

[OPCIONAL — incluir si procede]

- Fotografías del acceso al inmueble con el cambio de cerradura.

[OPCIONAL — incluir si procede]

- Prueba digital de video grabado del/de la denunciante intentando convencer a los ocupantes del inmueble y su negativa en la conversación mantenida tras la puerta.

[OPCIONAL — incluir si procede]

(Si el inmueble está alquilado)

-Copia del contrato de arrendamiento firmado el [COMPLETAR] donde consta que los inquilinos actuales son [COMPLETAR].

[OPCIONAL — incluir si procede]

(Si el inmueble está puesto a la venta o alquiler)

El inmueble ocupado se encuentra puesto [ELEGIR: a la venta / en alquiler] en la siguiente dirección web [COMPLETAR] y/o anunciada en [COMPLETAR].

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 13 de la Ley de Enjuiciamiento Criminal, se interesa se acuerde la medida cautelar de expulsión inmediata de los ocupantes del inmueble de mi propiedad de forma urgente, al tratarse de un delito de allanamiento de morada, disponiendo lo necesario para que, de forma urgente se acceda en 24 horas a la adopción de un auto de entrada y expulsión del inmueble, siendo auxiliada la comisión judicial de las Fuerzas y Cuerpos de seguridad del Estado que garanticen dicha expulsión inmediata.

Se solicita que la adopción de la medida cautelar se haga por el juez en servicio de guardia, y no por la Sección de Instrucción del Tribunal de Instancia que le corresponda atendiendo a las normas de reparto, dada la urgencia de la misma, por tratarse de morada y no poder esperar al trámite correspondiente de que sea turnada la denuncia, con independencia de que, adoptada la medida cautelar y expulsados los ocupantes del inmueble, pueda derivarse al curso del procedimiento a este órgano judicial que por turno de reparto corresponda.

TERCER OTROSÍ DIGO: Que el día del lanzamiento se proceda a la ejecución de la sentencia o medida cautelar contra todos aquellos que se encuentren en el inmueble, aunque sean sujetos distintos a aquellos con los que se hicieron las primeras diligencias o recibieron las iniciales notificaciones, no pudiendo instarse por ellos la suspensión de la diligencia de lanzamiento, lo que se ruega se haga constar en las primeras diligencias que se lleven a cabo, haciendo la advertencia judicial de que se ejecutará lo resuelto contra cualquier "tercero" que se encuentre en el inmueble al momento del lanzamiento, haya sido emplazado o no con anterioridad.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

Por ello,

SUPLICO A LA SECCIÓN:

Que se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares solicitadas, al tratarse el inmueble de morada del art. 202 CP, y no siendo aplicable el art. 245.2 CP que se aplica para cuando "no se trata de morada" y se tenga por designado Abogado y Procurador.

En [LUGAR], a [FECHA].

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

Para estos hechos hay que tener en cuenta lo establecido en la Instrucción nº 6/2020 de la Secretaría de Estado de seguridad.

(2) En este caso nos encontramos ante unos hechos de allanamiento de morada en los que no se conoce la identidad de los que han entrado en el inmueble propiedad del denunciante, y que previsiblemente habrán cambiado la cerradura para evitar que acceda el propietario denunciante. Para ello bastará con la mera cita del acceso sin poder exigirse la constancia de la identidad del denunciado al desconocer la misma, ya que lo que se postula son las diligencias de investigación y la medida cautelar de acceso y expulsión inmediata al ser la morada del denunciante.

Estas diligencias no deben admitir demora alguna, ya que, a diferencia de la ocupación de casas deshabitadas, cuando se ocupa casa habitada con muebles y con los servicios esenciales de luz, agua, gas, etc dados de alta, se evidencia que se está utilizando con la amplitud que debe darse al concepto de morada.

Las vías para perseguir la ocupación ilegal de inmuebles son:

1.- Acceso a casa que constituye morada, es decir, amueblada y con los servicios esenciales de suministro dados de alta evidenciando un uso del inmueble, aunque no sea permanente, pero sí ocasional: delito de allanamiento de morada del art. 202 CP.

Dice la STS 731/2013, de 7 de octubre, rec. 11142/2012: "Encontrarán la protección dispensada al domicilio aquellos lugares en los que, permanente o transitoriamente, desarrolle el individuo esferas de su privacidad, alejadas de la intromisión de terceros no autorizados. "

Por lo tanto, el concepto de domicilio es más amplio que el que se deriva de una mera constatación administrativa o tributaria relativa al lugar donde se fija la residencia a esos efectos para constituir el lugar cerrado que una persona dedica al desarrollo de todos o de algunos aspectos de su privacidad. (STS 852/2014, de 11 de diciembre, rec. 1068/2014; STS 509/2012, de 19 de junio, rec. 11121/2011; STS 1775/2000, de 17 de noviembre 2000, rec. 1458/1999).

2.- Acceso a inmueble que no constituya morada, es decir, no amueblada y no usada, ni siquiera ocasionalmente, sin suministro de servicios que evidencian la falta de uso, sin violencia o intimidación en las personas: delito leve de usurpación del art. 245.2 CP, o bien demanda civil.

Véase Instrucción 1/2020 FGEº, de 15 de septiembre, sobre criterios de actuación para la solicitud de medidas cautelares en los delitos de allanamiento de morada y usurpación de bienes inmuebles.

================================================================================
