---
name: quebrantamiento-medida-cautelar-alejamiento-acusacion-857
description: "Redacta el escrito «Quebrantamiento de medida cautelar de alejamiento: acusación» (formulario 857 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Quebrantamiento de medida cautelar de alejamiento: acusación

> Formulario 0857 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] NÚMERO
- [ ] HORA
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] PROFESIÓN
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de»; «…. QUINTA.- Procede imponer al acusado D.»; «…-»; «….-»

## Elecciones que hay que hacer

- cónyuges / excónyuges / pareja de hecho / ex pareja de hecho
- que se mencionan a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado.…
- .- Testifical: interrogatorio de los/as testigos [ELEGIR: que se mencionan a continuación / en escrito aparte]…
- - [COMPLETAR]…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.…
- .- [COMPLETAR]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468.2 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 650 LECRIM
- artículo 468.2 del Código Penal
- art. 22 CP
- art. 89.5 h) LOPJ
- art. 89.5 g) LOPJ
- art. 468.1 CP
- art. 48 CP
- art. 173.2 CP
- art. 777.2.3 LECrim

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

### Formulario 0857 · Quebrantamiento de medida cautelar de alejamiento: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la acusación en procedimiento abreviado solicitando la apertura del juicio oral y presentando sus conclusiones provisionales calificando los hechos de delito de quebrantamiento de condena del art. 468.2 CP contra su pareja por haber incumplido una orden de alejamiento.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/ade los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial (1) y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (2) solicitud de apertura de juicio oral, por la vía del art. 781 LECRIM, en relación con el art. 650 LECRIM, contra D. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] y en las diligencias previas nº [Nº DE PROCEDIMIENTO]/[AÑO] se dictó por el Juez de Violencia sobre la Mujer nº [NÚMERO] de [COMPLETAR] una orden de alejamiento por la que el acusado D. no podía acercarse a menos de 500 metros a Dña. durante [Nº] meses. Esta resolución fue notificada al acusado en fecha [FECHA] requiriéndole para que acatara la orden con los apercibimientos legales correspondientes, teniendo con ello conocimiento el acusado de la existencia de la citada orden.

Estando vigente la orden de alejamiento, el acusado se personó en el domicilio de mi representada el día [FECHA] a las [HORA] exigiéndole ver a los dos hijos comunes habidos en el matrimonio entre ellos, cerrando Dña. la puerta inmediatamente. En ese instante se encontraba la víctima con su madre Dña. [NOMBRE Y APELLIDOS].

Acusado y víctima son [ELEGIR: cónyuges / excónyuges / pareja de hecho / ex pareja de hecho].

SEGUNDA.- Tales hechos son constitutivos del delito de quebrantamiento de medida cautelar del artículo 468.2 del Código Penal.

TERCERA.- Es responsable del delito el acusado, en concepto de autor.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al acusado ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al acusado la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al acusado D. [COMPLETAR], por el delito de quebrantamiento de medida cautelar, la pena de [PENA] de prisión. (3)

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

.- Testifical: interrogatorio de los/as testigos [ELEGIR: que se mencionan a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

- La madre de la querellante que se encontraba en el domicilio en el momento de los hechos:

Dña. [NOMBRE Y APELLIDOS] mayor de edad, de profesión [PROFESIÓN], con domicilio en.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR]

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.

[OPCIONAL — incluir si procede]

.- [COMPLETAR]

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La competencia para la instrucción del delito de quebrantamiento de condena, cuando la persona ofendida sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por una análoga relación de afectividad aun sin convivencia, así como los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad con medidas de apoyo que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, así como cuando la persona ofendida lo sea por alguno de los delitos señalados en el art. 89.5 h) LOPJ, es de la Sección de Violencia sobre la Mujer (art. 89.5 g) LOPJ).

Si no se tratase de estas víctimas, la instrucción correspondería a una Sección de instrucción y se aplicaría el art. 468.1 CP.

(2) Este escrito debe presentarse en el plazo de 10 días hábiles desde que se le da traslado de las actuaciones.

(3) Debe tenerse en cuenta que en estos casos la circunstancia de ser cónyuge o excónyuge, pareja o expareja de hecho del querellante y querellado hace aplicable el art. 468.2 CP que impone pena de prisión de seis meses a un año cuando se quebrantare un pena del art. 48 CP o una medida cautelar impuesta en procesos en los que el ofendido sea una de las personas del art. 173.2 CP.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2.3 LECrim).

================================================================================
