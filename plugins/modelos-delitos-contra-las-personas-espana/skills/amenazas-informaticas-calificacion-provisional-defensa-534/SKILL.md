---
name: amenazas-informaticas-calificacion-provisional-defensa-534
description: "Redacta el escrito «Amenazas informáticas: calificación provisional de la defensa» (formulario 534 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Amenazas informáticas: calificación provisional de la defensa

> Formulario 0534 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…las costas deberán declararse de oficio.»; «…lementarias para la audiencia preliminar»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial: (4)…
- (Si desea solicitar diligencias preliminares)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 652 de la Ley de Enjuiciamiento Criminal
- artículo 29.2 de la Ley Orgánica 5/1995
- art. 29.4 LO 5/1995
- art. 30 LO 5/1995
- art. 169 CP

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

### Formulario 0534 · Amenazas informáticas: calificación provisional de la defensa

- Año del modelo: 2018
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado por un delito de amenazas informáticas condicionales del art. 169.1 pfo 2 CP, en un procedimiento ante el Tribunal del Jurado, presenta sus conclusiones provisionales presentando pericial informática contradictoria.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en el procedimiento número [Nº DE PROCEDIMIENTO] por el supuesto delito del art. 169.1º CP párrafo 2º, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que habiéndose recibido traslado de la causa por parte del/de la Letrado/a de la Administración de Justicia y, de conformidad con los artículos 652 de la Ley de Enjuiciamiento Criminal y artículo 29.2 de la Ley Orgánica 5/1995 del Tribunal del Jurado formulamos (1) las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que los hechos que describe el/la querellante son absolutamente inciertos, y posiblemente achacable a un problema que mantenga con otra persona. De suyo, se ofreció a los agentes policiales voluntariamente el acceso al ordenador de que dispone y el material que se ha localizado por los agentes policiales no contiene el mensaje que se cita. (2)

Se impugna expresamente el resultado de la prueba tecnológica.

SEGUNDA.- Los hechos no son constitutivos de un delito del art. 169.1.2º CP. (3)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- No pueden existir circunstancias modificativas de la responsabilidad.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil y las costas deberán declararse de oficio.

[COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ 1º DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], que declararán sobre que el/la acusado/a no le reprochó la existencia de la deuda al/a la perjudicado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial: (4)

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias preliminares)

OTROSÍ 2º DIGO: De conformidad con lo dispuesto en el art. 29.4 LO 5/1995, se interesa la práctica de las siguientes diligencias complementarias para la audiencia preliminar [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica y se proceda conforme a lo prevenido en el art. 30 LO 5/1995, conforme a lo interesado.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se recibe el escrito de calificación de la acusación (art. 29. 2 LOTJ).

(2) Señala la STS 342/2013 de 17 abril, rec. 1461/2012, que el carácter de dato personal de la dirección IP ha sido reconocido por la jurisprudencia del TS en numerosas resoluciones.

Es entendible, por tanto, que el Juez instructor, a raíz de la denuncia que se pueda interponer por la víctima de una amenaza on line pueda acordar dirigir mandamiento al prestador del servicio en internet con el fin de que facilite a la Brigada Provincial de Policía Judicial de delitos tecnológicos las IP de las conexiones al ordenador en la cuenta del correo electrónico de la víctima en su generación, accesos a bandejas de correo electrónico más recientes que se conserven, así como IPs de conexión.

Una vez obtenida la información requerida, la Policía Judicial se dirigirá al Juez instructor solicitando mandamiento judicial, dirigido a las operadoras, con el fin de que faciliten a los agentes comisionados cuantos datos dispongan del usuario o usuarios a los que se les asignaron las direcciones IPs que se conozcan debiendo incluir en esa información los momentos exactos de inicio y finalización de asignación de dicha dirección IP al usuario, así como, en su caso, de las líneas telefónicas de conexión desde las que se produjeron los accesos, el titular y ubicación de las mismas.

A raíz de los datos proporcionados por las operadoras, será posible la identificación de la persona que, desde esa IP, accedía a la red y utilizaba la red como vehículo para contactar con la víctima.

Para averiguar esta autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica, que es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia. Está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF), que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal.

Podría ocurrir que, a la hora de acceder a determinados datos para conocer la autoría, la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a LECRIM y ss para poder conseguir pruebas en casos de delitos cometidos por medios tecnológicos.

(3) La modalidad comisiva del art. 169 CP puede cometerse por medios informáticos, pudiendo llevarse a cabo por Whatsapp, correo electrónico, o los medios previstos en redes sociales mediante comunicación directa por uno de los sistemas de comunicación informática direccional entre partes y no público.

La modalidad de la amenaza informática está prevista de forma expresa, pero solo en el supuesto de amenazas condicionales del art. 169.1º pfo 2 CP, en cuyo caso supone una agravaciónel método utilizado para realizar la amenaza, distinguiendo la pena a imponer según se consiga o no el propósito, no existiendo una previsión especial de agravación para la amenaza informática no condicional.

En cualquier caso, la agravación existe cuando con ese método de llevar a cabo la amenaza se busque el anonimato, no cuando el receptor de la amenaza lo puede identificar con facilidad. Así lo señala el Tribunal Supremo, en STS 838/2016 de 4 de Noviembre, Rec. 537/2016.

(4) Puede simplemente plantearse la impugnación de la prueba digital si se aportó pero no se acompañó de pericial informática. Se incluye esta mención puesto que el Tribunal Supremo tiene declarado con respecto a la aportación de una prueba digital que, de impugnarse esta prueba, es preciso proponer y aportar prueba pericial que acredite ese contenido. (STS 300/2015, de 19 de mayo)

Los informes periciales pueden aportarse por las partes personadas en el proceso durante la fase de instrucción, así como acompañarlos junto con el escrito de calificación provisional.

================================================================================
