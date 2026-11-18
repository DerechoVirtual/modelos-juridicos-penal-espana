---
name: violacion-menor-16-anos-lo-4-2023-calificacion-87
description: "Redacta el escrito «Violación a menor de 16 años (LO 4/2023): calificación provisional del acusador particular» (formulario 87 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación a menor de 16 años (LO 4/2023): calificación provisional del acusador particular

> Formulario 0087 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] Nº (4 veces)
- [ ] CIRCUNSTANCIA
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…procedente de»; «…es: Durante el periodo comprendido entre»; «…ndo se fueron de viaje la dejaron con D.»; «…l colegio que conoce por ella los hechos»; «…tutor del colegio»; «…ocumentos que se acompañan a la querella»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Violación básica / Violación con las circunstancias del art. 181.2 CP — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS] amigo/a de la menor del colegio que conoce por ella los hechos [COMPLETAR].…
- .- Pericial de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella [COMPLETAR].…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 651 LECRIM
- art. 181.2 CP
- art. 22 CP
- art. 181.4 CP
- art. 57 CP
- art. 192.1 CP
- art. 192.3 CP
- art. 544 bis LECRIM
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

### Formulario 0087 · Violación a menor de 16 años (LO 4/2023): calificación provisional del acusador particular

- Año del modelo: 2023
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 29 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusador/a particular D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento de sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de [COMPLETAR], comparezco ante la Sala y como mejor proceda en derecho, DIGO:

En aplicación del artículo 651 LECRIM y concordantes formulo escrito de calificación, con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- Los hechos que motivan la acusación son los siguientes:

Durante el periodo comprendido entre [COMPLETAR] los padres de la menor de [Nº] años de edad cuando se fueron de viaje la dejaron con D. [COMPLETAR], su abuelo. Él se metía en su cama por las noches y la obligaba a hacerle una felación, lo que ocurrió desde que la menor tenía 8 años hasta los 11 años, diciéndole que no le contara nada a sus padres, que era un secreto entre ellos. Cuando la menor cumplió los 12 años, una de las noches tuvo acceso carnal por vía vaginal con ella, lo que repitió al menos en cuatro ocasiones, hasta que finalmente la menor se lo dijo a sus padres, formulando querella.

La menor ha sufrido de ansiedad por estos hechos estando sometida en la actualidad a tratamiento psicológico.

En el colegio el/la tutor/a D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] encargado/a del protocolo de prevención en delincuencia sexual han emitido sendos informes señalando el extraño comportamiento de la menor en temas sexuales.

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Violación básica / Violación con las circunstancias del art. 181.2 CP — el texto de cada opción no venía en el formulario original]

TERCERA.- Es responsable del delito el acusado en concepto de autor.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al acusado ninguna circunstancia modificativa de la responsabilidad criminal.

Concurre con respecto al acusado la agravante genérica de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al acusado por el delito del art. 181.4 CP la pena de prisión de [Nº] años.

Además, se le debe imponer la pena de alejamiento de la víctima del art. 57 CP, a fin de que no se le acerque a menos de [DISTANCIA EN METROS] metros durante [Nº] años, así como la pena de prohibición de comunicación por cualquier medio y la de libertad vigilada del art. 192.1 CP, por [Nº] años, después de cumplida la pena de prisión.

También se le impondrá la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

SEXTA.- Los hechos han causado un daño moral que se valora en la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

-Reproducción de la declaración grabada como prueba preconstituida de la menor.

- D./Dña. [NOMBRE Y APELLIDOS] hermano/a de la víctima.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] amigo/a de la menor del colegio que conoce por ella los hechos [COMPLETAR].

— D./Dña. [NOMBRE Y APELLIDOS] tutor del colegio [COMPLETAR]

— D./Dña. [NOMBRE Y APELLIDOS] encargado del protocolo de prevención de delincuencia sexual en el colegio.

[OPCIONAL — incluir si procede]

.- Pericial de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:

— D./Dña. [NOMBRE Y APELLIDOS] psicólogo que elaboró el dictamen sobre afectación psicológica tras los hechos ocurridos.

-— D./Dña. [NOMBRE Y APELLIDOS] sobre la credibilidad del testimonio.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SALA:

Que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares enunciadas para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: En base a lo dispuesto en el art. 544 bis LECRIM, se interesa se acuerde orden de alejamiento y, mediante resolución motivada, la utilización de dispositivos telemáticos para el control de su cumplimiento.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la querellante, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares.

SUPLICO A LA SALA: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
