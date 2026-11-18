---
name: violacion-lo-4-2023-calificacion-provisional-acusador-217
description: "Redacta el escrito «Violación (LO 4/2023): calificación provisional del acusador particular» (formulario 217 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación (LO 4/2023): calificación provisional del acusador particular

> Formulario 0217 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] CIRCUNSTANCIA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…procedente de»; «… de especial vulnerabilidad por razón de»; «…con respecto a la víctima.»; «…do, para llevar a cabo la violación, usó»; «…o que el acusado suministró a la víctima»; «…icular, serán aplicables las siguientes:»; «…la víctima sobre grado de vulnerabilidad»; «…ctuado hasta el momento de la vista oral»

## Elecciones que hay que hacer

- precedida / acompañada
- una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio
- es / ha sido
- esposa / pareja
- convivencia / parentesco / superioridad
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia / Violación con intimidación / Violación a víctima con voluntad anulada / Violación con abuso de superioridad / Violación aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o con voluntad anulada / Violación básica o con abuso de superioridad o aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o víctima vulnerable / Violación básica o con abuso de superioridad o aprovechamiento de víctima especialmente vulnerable — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (11)

Inclúyelos solo si encajan en los hechos:

- Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y…
- Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la violación fue [ELEGIR: precedida / acomp…
- Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de esp…
- Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [E…
- Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la violación el acusado se ha prev…
- Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el acusado, para llevar a cabo la viola…
- Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el acusado suministró a la víctima [COM…
- 1.- Interrogatorio del acusado.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial siguiente:…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 651 LECRIM
- art. 22 CP
- art. 26 de la Ley 4/2015
- art. 681.3 LECRIM

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

### Formulario 0217 · Violación (LO 4/2023): calificación provisional del acusador particular

- Año del modelo: 2022
- Revisión 17-11-2026: 4 llamadas a nota sin texto retiradas; 4 desplegables y casillas convertidos en elección en blanco; 3 desplegables convertidos en elección en blanco; 3 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 11 párrafos opcionales señalados; 25 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular Dña. [NOMBRE Y APELLIDOS], en el procedimiento de sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de [COMPLETAR], comparezco ante la Sala y como mejor proceda en derecho, DIGO:

En aplicación del artículo 651 LECRIM y concordantes formulo escrito de calificación, con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia / Violación con intimidación / Violación a víctima con voluntad anulada / Violación con abuso de superioridad / Violación aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original]

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o con voluntad anulada / Violación básica o con abuso de superioridad o aprovechando la vulnerabilidad de la víctima — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y APELLIDOS] y D/Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la violación fue [ELEGIR: precedida / acompañada] de [ELEGIR: una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de especial vulnerabilidad por razón de [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [ELEGIR: esposa / pareja].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la violación el acusado se ha prevalido de una situación o relación de [ELEGIR: convivencia / parentesco / superioridad] con respecto a la víctima. [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el acusado, para llevar a cabo la violación, usó [COMPLETAR]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el acusado suministró a la víctima [COMPLETAR] que le anuló su voluntad para luego violarla.

TERCERA.- Es responsable del delito el acusado en concepto de autor.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al acusado ninguna circunstancia modificativa de la responsabilidad criminal.

Concurre con respecto al acusado la agravante genérica de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación con violencia, intimidación o víctima vulnerable / Violación básica o con abuso de superioridad o aprovechamiento de víctima especialmente vulnerable — el texto de cada opción no venía en el formulario original]

SEXTA.- Los hechos han causado un daño moral que se valora en la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

- Dª víctima de los hechos, a fin de que se le interrogue sobre los hechos ocurridos.

Se interesa que la declaración de la víctima de delito sexual que fue grabada en la instrucción sea reproducida en sede judicial, en base al art. 26 de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, que señala: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: [COMPLETAR]) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal."

- D./Dña. [NOMBRE Y APELLIDOS] amigo/a que estuvo en la cena con la querellante y el acusado al/a la que luego contó lo sucedido.
- D./Dña. [NOMBRE Y APELLIDOS] que la recogió en la carretera.
- D./Dña. [NOMBRE Y APELLIDOS] sobre conocimiento del grado de vulnerabilidad de la víctima y su evidencia externa y visible

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

- D./Dña. [NOMBRE Y APELLIDOS] forense que elaboró el informe médico.
- D./Dña. [NOMBRE Y APELLIDOS] perito que realizó el análisis de ADN.
- D./Dña. [NOMBRE Y APELLIDOS] perito que examinó a la víctima sobre grado de vulnerabilidad [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SALA:

Que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares enunciadas para asegurar las responsabilidades civiles y las costas.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, según redacción dada por Ley orgánica de garantía integral de la libertad sexual, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la querellante, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
