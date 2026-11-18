---
name: estafa-informatica-phishing-denuncia-696
description: "Redacta el escrito «Estafa informática (phishing): denuncia» (formulario 696 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (phishing): denuncia

> Formulario 0696 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] LOCALIDAD
- [ ] CALLE
- [ ] NÚMERO
- [ ] DNI/NIE
- [ ] FECHA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…calle [CALLE] número [NÚMERO], piso»; «…rriente que tengo en la entidad bancaria»

## Elecciones que hay que hacer

- en nombre propio / en representación de D./Dña.
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (3) a fin de que se realicen las averig…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- .- Pericial. Para que por perito judicial se elabore pericial informática acerca de la estafa informática real…
- .- Documental, mediante la aportación de extracto bancario de la transferencia realizada de mi cuenta a la que…
- (Si se solicitan medidas cautelares)…
- (Si se designa abogado y procurador ya en la denuncia)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 265 y 266 LECRIM
- art. 249.1 a) CP
- artículos 259 a 269 de la LECRIM
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

### Formulario 0696 · Estafa informática (phishing): denuncia

- Año del modelo: 2017
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 6 párrafos opcionales señalados; 16 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian al juez, conforme a los arts. 265 y 266 LECRIM unos hechos que presentan los caracteres del delito de estafa, cometida a través de medios informáticos (phising), del art. 249.1 a) CP. Se solicita investigar la dirección IP del ordenador desde el que se cometió la estafa y la identidad del titular de la misma.

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, [ELEGIR: en nombre propio / en representación de D./Dña.] con domicilio en [LOCALIDAD] calle [CALLE] número [NÚMERO], piso [COMPLETAR] con DNI [DNI/NIE] expedido el día [FECHA], correo electrónico, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia (1) y

EXPONGO

PRIMERO.- Persona o personas desconocidas han accedido a mis claves de acceso a la cuenta corriente que tengo en la entidad bancaria [COMPLETAR] y han extraído, mediante transferencia bancaria, la suma de [IMPORTE] euros.

Sin perjuicio de una posterior calificación jurídica más exacta, los hechos expuestos revisten los caracteres de un delito de estafa informática del art. 249.1 a) CP (2)

SEGUNDO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Que se oficie al grupo de la Brigada de Investigación Tecnológica, (3) a fin de que se realicen las averiguaciones oportunas por investigación de mi ordenador y sistema utilizado para acceso a mis claves de acceso al banco antes citado.

Una vez que La BIT lleve a cabo las diligencias de investigación para detectar la IP del ordenador desde el que se llevó a cabo la estafa, que se redacte oficio policial para interesar la entrada y registro para la intervención del ordenador y se lleve a cabo la intervención y pericial informática de su contenido.

.- Declaración del denunciante como perjudicado: D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto].

.- Declaración del denunciante como perjudicado: D./Dña. [NOMBRE Y APELLIDOS]

- D./Dña. [NOMBRE Y APELLIDOS] director de la entidad bancaria, para que explique la posible operativa de estos actos.

[OPCIONAL — incluir si procede]

.- Pericial. Para que por perito judicial se elabore pericial informática acerca de la estafa informática realizada, a cuyo fin deberá designarse perito y se emita informe que sea aportado y posteriormente se ratifique en el contenido de la pericia.

[OPCIONAL — incluir si procede]

.- Documental, mediante la aportación de extracto bancario de la transferencia realizada de mi cuenta a la que consta en el documento adjunto como nº1 para que se identifique la identidad del titular de la cuenta donde se efectuó la transferencia.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta denuncia, se admita, se practiquen las diligencias interesadas y una vez se detecte la persona autora de los presentes hechos denunciados, se ejercitará la debida personación como acusación particular.

[OPCIONAL — incluir si procede]

(Si se solicitan medidas cautelares)

OTROSÍ DIGO: que solicito las siguientes medidas cautelares:

1.
2.

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

(2) La estafa informática, regulada hasta el 11 de enero de 2023 en el art. 248.2 a) y desde el 12 de enero de 2023, fecha [NOTA DE REVISIÓN: La LO 14/2022 entró en vigor el 12 de enero de 2023 (disposición final sexta). Fuente: LO 14/2022, BOE-A-2022-21800, disposición final sexta.] de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP, consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son:

— La manipulación informática y artificio semejante.

— Transferencia patrimonial no consentida por el titular del mismo.

— Ánimo de lucro, y

— Perjuicio en tercero.

Modalidades típicas de estafas informáticas son el "phishing" y el "pharming" que son dos tipos de fraudes informáticos cuya finalidad común es la de apoderarse de información personal de un usuario de Internet, para acceder a sus cuentas de correo o de redes sociales y obtener adicionalmente datos de sus contactos virtuales, a fin de comerciarlos ilícitamente, o bien, conseguir claves en su banco (por medio de internet) para de este modo ingresar a las cuentas corrientes bancarias de los titulares y disponer de su dinero en las cuentas realizando una operación de transferencia de activos a un tercero que se denomina "mule".

(3) Generalmente en los delitos de estafa informática se desconoce, o suele desconocerse la autoría e identidad del autor del delito, ya que se ha perpetrado por un procedimiento informático. Por ello, lo que se pretende es que este órgano judicial ordene a la policía judicial que realice las actividades de investigación por la vía informática para conocer quien ha cometido el delito.

Para averiguar esta autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica, que es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia: pornografía infantil, estafas y fraudes por Internet, fraudes en el uso de las comunicaciones, ataques cibernéticos, piratería...

La Brigada de Investigación Tecnológica está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF) que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como de la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

Su misión consiste en obtener las pruebas, perseguir a los delincuentes y poner a unas y otros a disposición judicial. Sus herramientas son: la formación continua de los investigadores, la colaboración de las más punteras instituciones públicas y privadas, la participación activa en los foros internacionales de cooperación policial y la colaboración ciudadana.

Podría ocurrir que, a la hora de acceder a determinados datos para conocer la autoría, la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a LECRIM y ss (introducidos por la LO 13/2015, de 5 de octubre), para poder conseguir pruebas en casos de delitos cometidos por medios tecnológicos.

================================================================================
