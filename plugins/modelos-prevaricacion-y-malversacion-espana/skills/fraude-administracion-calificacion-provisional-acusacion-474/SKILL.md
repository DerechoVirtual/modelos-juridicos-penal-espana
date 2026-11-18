---
name: fraude-administracion-calificacion-provisional-acusacion-474
description: "Redacta el escrito «Fraude a la Administración: calificación provisional de la acusación» (formulario 474 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Fraude a la Administración: calificación provisional de la acusación

> Formulario 0474 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] Nº (5 veces)
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] DNI/NIE
- [ ] DESCRIBIR
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…con DNI [DNI/NIE] y domicilio»; «…a provocado el perjuicio al ente público»; «… adjudicado a éste/a el contrato, sino a»; «…, Jefe/a de servicio del área»; «…o/a General de la Administración Pública»; «…el autor. Fraude frente a prevaricación:»; «… 974/2017) Fraude frente a malversación:»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de los/as acusados/as.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Documental, teniendo por reproducido los documentos aportados en cuanto a la tramitación del expediente adm…
- (Si desea solicitar diligencias preliminares)…
- OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la suspensión cau…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 436 CP
- artículo 29 de la Ley Orgánica 5/1995
- art. 650 LECRIM
- artículo 436 CP
- art. 22 del CP
- art. 432 CP

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

### Formulario 0474 · Fraude a la Administración: calificación provisional de la acusación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular presenta sus conclusiones provisionales en procedimiento ante el Tribunal del Jurado calificando los hechos como delito de fraude a la Administración Pública del art. 436 CP, puesto que un funcionario se concierta con un particular para defraudar a la Administración.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Evacuando en el plazo concedido (1) por el traslado bajo el amparo del art. 27.4 LOTJ, que se ha verificado a los fines dispuestos en el artículo 29 de la Ley Orgánica 5/1995 del Tribunal del Jurado, en relación al art. 650 LECRIM, solicitamos la apertura de juicio oral y formulamos, por medio del presente escrito de calificación provisional, contra D./Dña. [NOMBRE Y APELLIDOS] con DNI [DNI/NIE] y domicilio [COMPLETAR] las siguientes,

CONCLUSIONES

PRIMERA.- En el seno de la contratación administrativa consistente en sacar a concurso público el contrato relativo a [DESCRIBIR] el/la funcionario/a D./Dña. [NOMBRE Y APELLIDOS] se concertó con D./Dña. [NOMBRE Y APELLIDOS] para conseguir éste/a el contrato mediante la plasmación en la oferta de condiciones que ya había pactado éste/a con aquél/aquélla que no se iban a cumplir, lo que hubiera provocado el perjuicio al ente público [COMPLETAR], aunque finalmente no le fue adjudicado a éste/a el contrato, sino a [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos del delito de fraude a la Administración Pública previsto en el artículo 436 CP. (2)

TERCERA.- Son responsables del delito en concepto de autores los/as acusados/as.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en los/as acusados/as circunstancias agravantes.

Concurre en el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 436 CP la pena de prisión de [Nº] años e inhabilitación especial para empleo o cargo público y para el ejercicio del derecho de sufragio pasivo por tiempo de [Nº] años. Y a D./Dña. [NOMBRE Y APELLIDOS] la misma pena de prisión de [Nº] años y la de inhabilitación para obtener subvenciones y ayudas públicas para contratar con entes, organismos o entidades que formen parte del sector público y para gozar de beneficios o incentivos fiscales o de seguridad social por tiempo de [Nº] años.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Se tenga por presentado este escrito, evacuadas las conclusiones y se tenga por solicitada la apertura de juicio oral contra D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS].

Es de Justicia que pido en [LUGAR], a [FECHA].

(Optionally: PRIMER) OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio de los/as acusados/as.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- D./Dña. [NOMBRE Y APELLIDOS], Jefe/a de servicio del área [COMPLETAR] donde ejercía su cargo el/la funcionario/a público/a.

- Declaración de los/as siguientes funcionarios/as públicos/as:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS], Secretario/a General de la Administración Pública [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados en cuanto a la tramitación del expediente administrativo donde consta la carencia del trámite que debe seguirse en su tramitación.

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias preliminares)

SEGUNDO OTROSÍ DIGO: Se proponen, además, como diligencias complementarias para su práctica en la audiencia preliminar, y que no son reiteración de las que han sido practicadas con anterioridad, las siguientes:

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir si procede]

OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la suspensión cautelar de las funciones del/de la funcionario/a acusado/a, por la vía del art 13 LECRIM, dada la gravedad de los hechos y la posible reiteración delictiva u ocultación de pruebas o su destrucción, menos restrictiva que la medida de prisión.

SUPLICO A LA SECCIÓN: Que adopte las medidas cautelares solicitadas y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se le da traslado de la causa (art. 27.4 LOTJ).

(2) El fraude de subvenciones es un tipo penal circunscrito a la contratación pública o en liquidaciones de efectos o haberes públicos. Pero exige el artificio en la acción del autor.

Fraude frente a prevaricación: [COMPLETAR]

La pena por delito de fraude es de prisión de dos a seis años y la de prevaricación es de inhabilitación, lo que puede incidir en que se plantee como subsidiaria a la absolución la condena por prevaricación si se acusa de fraude a la Administración. (STS 200/2018, de 25 de abril, rec. 974/2017)

Fraude frente a malversación: [COMPLETAR]

La condena por delito de fraude es la misma que para la malversación del art. 432 CP, pero en este último caso el apartado 2 las agrava de 4 a 8 años e, incluso en su mitad superior, agravación que no opera para el fraude, por lo que en este caso la vía subsidiaria a la absolución de malversación sería la de fraude, aunque en este caso téngase en cuanta lo que dice la STS 163/2019, de 26 de marzo, rec. 2263/2017.

================================================================================
