---
name: quebrantamiento-condena-prohibicion-comunicacion-online-512
description: "Redacta el escrito «Quebrantamiento de condena (prohibición de comunicación online): acusación» (formulario 512 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Quebrantamiento de condena (prohibición de comunicación online): acusación

> Formulario 0512 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (3 veces)
- [ ] NÚMERO (2 veces)
- [ ] DELITO
- [ ] PENA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del Juez de lo Penal nº [NÚMERO] de»; «…l/la acusado/a remitió por la red social»; «…ue se requiera al prestador del servicio»; «…ique la titularidad del perfil de la red»; «…con el Nick»

## Elecciones que hay que hacer

- no interponerse recurso / confirmación de la sentencia por la Audiencia Provincial
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], que ha visto el mensaje en la red social.…
- .- Pericial informática para el supuesto de que se impugne la prueba digital por la defensa acerca de la reali…
- .- Documental.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468 CP
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 del CP
- art. 14.5 LECRIM
- art. 89.5 LOPJ
- art. 14.6 d) LECRIM
- art. 14.7 LECRIM
- art. 173.2 CP
- art. 468.1 CP
- art. 544 bis LECRIM
- art. 544 ter LECRIM

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

### Formulario 0512 · Quebrantamiento de condena (prohibición de comunicación online): acusación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 3 bloques de alternativas señalados; 4 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales calificando los hechos de quebrantamiento de condena del art. 468 CP, por escribir el acusado un mensaje en una red social cuando había sido condenado a prohibición de comunicación con la víctima y esto incluye cualquier medio, también los tecnológicos o informáticos.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

A la Sección de Violencia contra la infancia y la adolescencia nº [Nº] del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de los acusadores particulares D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Mediante el presente escrito formulo en plazo (2) solicitud de apertura de juicio oral por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] se dictó sentencia en juicio oral nº [NÚMERO] del Juez de lo Penal nº [NÚMERO] de [COMPLETAR] por la que se condenaba al/a la acusado/a por la comisión del delito de [DELITO] a la pena de [PENA] de prisión y a la prohibición de comunicación por cualquier medio, incluidos los tecnológicos, y a que no se acercara a menos de 500 metros de la víctima en su domicilio, o lugar de trabajo o cualquiera que frecuente.

La sentencia devino firme por [ELEGIR: no interponerse recurso / confirmación de la sentencia por la Audiencia Provincial] y le había sido notificada personalmente al/a la acusado/a, llevando a cabo las advertencias oportunas en la diligencia acerca de las consecuencias del incumplimiento de las prohibiciones fijadas en la sentencia.

Con fecha [FECHA] el/la acusado/a remitió por la red social [COMPLETAR] un mensaje de texto a mi representado/a diciéndole por escrito que quebrantando, con ello, la orden de prohibición de comunicación impuesta en sentencia.

SEGUNDA.- Tales hechos son constitutivos del delito del art. 468 CP. (3)

TERCERA.- Es responsable del delito del art. 468 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 468 CP la pena de [PENA] y prohibición de aproximación a la víctima a menos de 500 metros donde se encuentre por tiempo de [DURACIÓN] y de prohibición de comunicación por cualquier medio incluidos los tecnológicos por igual periodo y al pago de las costas procesales. (4)

SEXTA.- En concepto de responsabilidad civil se indemnizará a D./Dña. [NOMBRE Y APELLIDOS] con la suma de [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que ha visto el mensaje en la red social.

[OPCIONAL — incluir si procede]

.- Pericial informática para el supuesto de que se impugne la prueba digital por la defensa acerca de la realidad de la existencia de ese mensaje en la red digital y la identidad del/de la acusado/a en el mismo. (5)

[OPCIONAL — incluir si procede]

.- Documental.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

- Acta notarial del/de la notario D./Dña. [NOMBRE Y APELLIDOS] de la constancia en la red social del contenido del mensaje y la mención en la red social de la identidad de su autor/a.

- Pantallazo de la red social con el contenido del mensaje y adveración por el/la Letrado/a de la Administración de Justicia entrando en la citada red social al objeto de la comprobación real de su existencia.

- Testimonio de la sentencia del Juez de lo Penal y la diligencia de notificación y requerimiento al/a la querellado/a acerca de la prohibición de comunicación y, por ello, vigencia de la orden al momento de enviar esa comunicación por redes sociales, cuando estaba condenado/a a no hacerlo.

- Que se requiera al prestador del servicio [COMPLETAR] a fin de que certifique la titularidad del perfil de la red [COMPLETAR] con el Nick [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

SEGUNDO OTROSÍ DIGO: Se interesa el mantenimiento de la medida cautelar de prohibición de aproximación y comunicación adoptada.

SUPLICO A LA SECCIÓN: Que tenga por hecha la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Si el delito se produce contra quien sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género o si el sujeto pasivo es una mujer (desde el 3 de octubre de 2025, conforme a la redacción dada por LO 1/2025) el órgano competente es la Sección de Violencia sobre la Mujer del Tribunal de Instancia (art. 14.5 LECRIM y art. 89.5 LOPJ).

Si la víctima es niño, niña o adolescente el órgano competente es la Sección de Violencia contra la Infancia y Adolescencia, si la hay (art. 14.6 d) LECRIM y art. 89 bis 5 d) LOPJ). Téngase en cuenta que, si se trata de hechos que también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia le corresponderá en todo caso a la segunda (art. 14.7 LECRIM y art. 89 bis 7 LOPJ).

(2) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(3) Si existe relación entre querellante y querellado de las que cita el art. 173.2 CP se aplicaría el apartado 2º del art. 468 CP y si no existe esa relación previa el art. 468.1 CP.

(4) El hecho de que el origen del caso sea un quebrantamiento de condena no impide que se vuelva a interesar la medida cautelar del alejamiento por el art. 544 bis LECRIM y, si se tratara de pareja o ex pareja por el art. 544 ter LECRIM, dado que la pena anterior puede expirar en su plazo y de esta manera se abre uno nuevo en este, a fin de que hasta el juicio subsista una nueva medida cautelar de alejamiento y prohibición de comunicación.

Es positivo que cuando se interesa por la acusación la pena de prohibición de comunicación se incluya la adición de que esa prohibición se extiende" a cualquier medio, incluidos los tecnológicos o informáticos", para no dejar abierta la duda de que la prohibición se extiende a estos casos.

(5) Es positivo aportar pericial informática, dado que nos encontramos con la aportación de prueba digital en el proceso penal y ello exige que, si se impugna por la defensa, la acusación debería aportar pericial informática. Si no lo hace con la querella debería hacerlo tras impugnarlo la defensa en su escrito de defensa.

================================================================================
