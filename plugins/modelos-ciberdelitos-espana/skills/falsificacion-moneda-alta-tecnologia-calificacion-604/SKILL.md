---
name: falsificacion-moneda-alta-tecnologia-calificacion-604
description: "Redacta el escrito «Falsificación de moneda con alta tecnología: calificación provisional de la acusación particular» (formulario 604 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falsificación de moneda con alta tecnología: calificación provisional de la acusación particular

> Formulario 0604 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] ÓRGANO
- [ ] IMPORTE (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… art. 386.1 y 2 CP la pena de prisión de»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se han solicitado en la querella o denuncia / Si ya se solicitaron en la querella o denuncia — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se ha aportado en la querella o denuncia / Si ya se han aportado en la querella o denuncia — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- (Si no se aportó en la querella)…
- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial:…
- .- Documental.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 386.1 y 2 CP
- artículo 651 LECrim
- art. 386 CP
- art. 22 del CP
- art. 127 CP

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

### Formulario 0604 · Falsificación de moneda con alta tecnología: calificación provisional de la acusación particular

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 19 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de conclusiones provisionales de la acusación en procedimiento común u ordinario por el que se califican los hechos de delito de fabricación y distribución de moneda falsa del art. 386.1 y 2 CP al elaborar billetes falsos utilizando medios tecnológicos avanzados y efectuando compras con ellos.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento de sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], comparezco ante la Sala y como mejor proceda en derecho, DIGO:

En aplicación del artículo 651 LECrim. y concordantes formulo escrito de calificación (1), con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- El/La acusado/a, con la finalidad de obtener un beneficio ilícito, confeccionó, en unión de tercera persona no identificada, billetes falsificados con una alta tecnología, los presentó en el establecimiento comercial del/de la querellante [ÓRGANO] y adquirió bienes por valor de [IMPORTE] euros.

Al cabo de varios días, D./Dña. [NOMBRE Y APELLIDOS] gerente del establecimiento comercial citado, comprobó que todos los billetes entregados eran falsos, pero que el dispositivo técnico de que se disponía en el local no detectó la falsedad en su momento.

[OPCIONAL — incluir si procede]

(Si no se aportó en la querella)

Se aporta prueba pericial de análisis de los billetes que acredita que son falsos y elaborados con una sofisticada y alta tecnología que impidió que pudieran ser detectados.

SEGUNDA.- Tales hechos son constitutivos del delito de fabricación de moneda falsa y distribución del art. 386.1 y 2 CP. (2)

TERCERA.- Es responsable del delito del art. 386 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 386.1 y 2 CP la pena de prisión de [COMPLETAR], así como la intervención y comiso de los objetos e instrumentos utilizados para la falsificación de moneda por la vía del art. 127 CP.

SEXTA.- En concepto de responsabilidad civil se indemnizará con el importe de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

— D./Dña. [NOMBRE Y APELLIDOS], representante legal de la empresa a fin de que declare sobre el pago al establecimiento.

— D./Dña. [NOMBRE Y APELLIDOS], empleado/a del establecimiento donde se realizó la operación.

— D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes de policía que practicaron la detención y la investigación.

[OPCIONAL — incluir si procede]

.- Pericial:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se han solicitado en la querella o denuncia / Si ya se solicitaron en la querella o denuncia — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

.- Documental.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se ha aportado en la querella o denuncia / Si ya se han aportado en la querella o denuncia — el texto de cada opción no venía en el formulario original]

Por todo lo expuesto,

SUPLICO A LA SALA: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde la notificación del auto de apertura del juicio oral.

(2) a) Argumento sobre el conocimiento.

La jurisprudencia exige que el poseedor de la moneda conozca que era falsa, en el momento de adquirirla o que llegue a su poder (STS 471/2017, de 22 junio, rec. 2467/2016 y STS 293/2016, de 8 de abril, rec. 1916/2015).

b) Argumento sistemático. Si la tenencia de moneda falsa, sabiendo que lo es, aunque se hubiese adquirido ignorando tal falsedad, se castiga con pena de tres a seis meses o multa, si se hubiese expendido la moneda falsa en cantidad superior a 400 euros, la simple tenencia de la misma moneda con voluntad de expenderla puede sancionarse con la pena mucho más grave de dos a ocho años y exige el conocimiento de la falsedad desde el momento de la adquisición, además de connivencia con los falsificadores, introductores o manipuladores del párrafo primero del precepto.

El propio inciso primero del párrafo segundo del art. 386 CP gradúa la pena en función del valor de la moneda y del grado de connivencia con los autores cualificados del párrafo primero, por lo que de tal connivencia con falsificadores o introductores debe extraerse la exigencia del conocimiento de la falsedad desde el momento mismo en que el autor adquiere la moneda falsa.

================================================================================
