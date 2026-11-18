---
name: agresion-sexual-sin-acceso-carnal-lo-4-2023-escrito-94
description: "Redacta el escrito «Agresión sexual sin acceso carnal (LO 4/2023): escrito de acusación» (formulario 94 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual sin acceso carnal (LO 4/2023): escrito de acusación

> Formulario 0094 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (4 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… de especial vulnerabilidad por razón de»; «…con respecto a la víctima.»; «…. 180.1.6ª CP, puesto que el acusado usó»; «…o que el acusado suministró a la víctima»; «…ncias agravantes. Concurre en el acusado»; «…la víctima sobre grado de vulnerabilidad»; «…umentos que se acompañaron a la querella»

## Elecciones que hay que hacer

- precedida / acompañada
- una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio
- es / ha sido
- esposa / pareja
- convivencia / parentesco / superioridad
- que estuvo con ella cuando ocurrieron los hechos / conoce los hechos por la víctima

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Agresión sexual con violencia / Agresión sexual con intimidación / Agresión sexual a víctima con la voluntad anulada / Agresión sexual con abuso de superioridad / Agresión sexual con aprovechamiento de la vulnerabilidad de la víctima o de su situación mental o privada de sentido — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Agresión sexual con abuso de superioridad o aprovechamiento de vulnerabilidad de la víctima o de su situación mental o privada de sentido / Agresión sexual con violencia, intimidación o víctima con voluntad anulada — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (13)

Inclúyelos solo si encajan en los hechos:

- Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y…
- Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la agresión sexual fue [ELEGIR: precedida /…
- Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de esp…
- Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [E…
- Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la agresión sexual el acusado se h…
- Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el acusado usó [COMPLETAR]…
- Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el acusado suministró a la víctima [COM…
- 1.- Interrogatorio del/de la querellado/a.…
- .- Testifical de los/as testigos que se mencionan y que deberán ser citados/as:…
- -D./Dña. [NOMBRE Y APELLIDOS], amigo/a de la víctima [ELEGIR: que estuvo con ella cuando ocurrieron los hechos…
- .- Pericial de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:…
- .- Documental: teniendo por reproducidos los documentos que se acompañaron a la querella [COMPLETAR].…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 22 del CP
- art. 57 CP
- art. 192.1 CP
- art. 192.3 CP
- art. 26.1 a) de la Ley 4/2015
- art. 544 bis LECRIM

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

### Formulario 0094 · Agresión sexual sin acceso carnal (LO 4/2023): escrito de acusación

- Año del modelo: 2023
- Revisión 17-11-2026: 5 llamadas a nota sin texto retiradas; 4 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 bloques de alternativas señalados; 12 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO], comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL, al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- Los hechos son los siguientes:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Agresión sexual con violencia / Agresión sexual con intimidación / Agresión sexual a víctima con la voluntad anulada / Agresión sexual con abuso de superioridad / Agresión sexual con aprovechamiento de la vulnerabilidad de la víctima o de su situación mental o privada de sentido — el texto de cada opción no venía en el formulario original]

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Agresión sexual con abuso de superioridad o aprovechamiento de vulnerabilidad de la víctima o de su situación mental o privada de sentido / Agresión sexual con violencia, intimidación o víctima con voluntad anulada — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.1ª CP, puesto que actuaron conjuntamente D/Dña. [NOMBRE Y APELLIDOS] y D/Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.2ª CP, ya que la agresión sexual fue [ELEGIR: precedida / acompañada] de [ELEGIR: una violencia de extrema gravedad / actos que revistan un carácter particularmente degradante o vejatorio].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.3ª CP, ya que la víctima se halla en una situación de especial vulnerabilidad por razón de [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.4ª CP, puesto que la víctima [ELEGIR: es / ha sido] su [ELEGIR: esposa / pareja].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.5ª CP, puesto que para la agresión sexual el acusado se ha prevalido de una situación o relación de [ELEGIR: convivencia / parentesco / superioridad] con respecto a la víctima. [COMPLETAR].

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.6ª CP, puesto que el acusado usó [COMPLETAR]

[OPCIONAL — incluir si procede]

Concurre, además, el subtipo agravado del art. 180.1.7ª CP, puesto que el acusado suministró a la víctima [COMPLETAR] que le anuló su voluntad para luego agredirla sexualmente.

TERCERA.- Es responsable del delito en concepto de autor el acusado.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el acusado circunstancias agravantes.

Concurre en el acusado [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al acusado por el delito de agresión sexual la pena de [Nº] años de prisión; así como la pena de alejamiento de la víctima del art. 57 CP, a fin de que no se le acerque a menos de [DISTANCIA EN METROS] metros durante [Nº] años, así como la pena de prohibición de comunicación por cualquier medio y la de libertad vigilada del art. 192.1 CP, por [Nº] años, después de cumplida la pena de prisión.

Además, se le impondrá la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Testifical de los/as testigos que se mencionan y que deberán ser citados/as:

-Dª. víctima de los hechos.

Se interesa que la declaración de la víctima de delito sexual que fue grabada en la instrucción sea reproducida en juicio oral, en base al art. 26.1 a) de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, conforme a la redacción dada por la Disposición final 10ª de la LO 10/2022 que señala que: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: a) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal."

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS], amigo/a de la víctima [ELEGIR: que estuvo con ella cuando ocurrieron los hechos / conoce los hechos por la víctima].

-D./Dña. [NOMBRE Y APELLIDOS], sobre conocimiento del grado de vulnerabilidad de la víctima y su evidencia externa y visible.

[OPCIONAL — incluir si procede]

.- Pericial de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:

-Perito psicólogo D./Dña. [NOMBRE Y APELLIDOS] que realizó examen de la querellante como consecuencia del impacto emocional sufrido por los hechos

- Perito D./Dña. [NOMBRE Y APELLIDOS] que examinó a la víctima sobre grado de vulnerabilidad [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Documental: teniendo por reproducidos los documentos que se acompañaron a la querella [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: En base a lo dispuesto en el art. 544 bis LECRIM, se interesa se acuerde orden de alejamiento y, mediante resolución motivada, la utilización de dispositivos telemáticos para el control de su cumplimiento.

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
