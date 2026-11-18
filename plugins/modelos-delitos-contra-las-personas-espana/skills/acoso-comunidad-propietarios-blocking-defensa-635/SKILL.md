---
name: acoso-comunidad-propietarios-blocking-defensa-635
description: "Redacta el escrito «Acoso en una comunidad de propietarios (blocking): defensa» (formulario 635 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acoso en una comunidad de propietarios (blocking): defensa

> Formulario 0635 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…uno en torno a la responsabilidad civil.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- -D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] vecino/as del inmueble. Para que declare sobre la…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 172 ter CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECrim
- art. 777.2 LECrim

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

### Formulario 0635 · Acoso en una comunidad de propietarios (blocking): defensa

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en procedimiento abreviado presenta sus conclusiones provisionales alegando que la conducta del acusado no puede calificarse de acoso entre vecinos o blocking porque no ha supuesto alteración grave de la vida del querellante, requisito exigido jurisprudencialmente para entender cometido el delito del art. 172 ter CP.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito de acoso del art. 172 ter CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto en plazo (1) mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a simplemente ha comentado a los querellantes que no hagan ruidos porque le molestan en la convivencia diaria, no siendo ciertas las expresiones relativas a que les ha amenazado, ni presionado o que desea que se vayan de la comunidad, sino que lo único que les solicita es que no hagan ruido porque son una familia que pone la música a elevado volumen y el perro ensucia la entrada de su inmueble habiendo detectado que ha orinado en su puerta en algunas ocasiones. Se trata simplemente de reproches para que no molesten, pero lejos de la situación de acoso que se describe en el escrito de acusación, y menos la persistencia que se relata, ya que se limita a solicitarles que no molesten. Por ello, se ha dirigido al/a la presidente/a de la comunidad y al/a la administrador/a de fincas interesando se les aplique el art. 7.2 L 49/1960, de 21 de julio, de Propiedad Horizontal, por ejercicio de actividades molestas por su actitud en la comunidad. Tampoco es cierto que haya sido el/la autor/a de los pinchazos en las ruedas, de lo que no hay prueba alguna, ni tampoco de la autoría de las cartas.

Además, la conducta del/de la acusado/a no ha supuesto alteración de la vida del/de la querellante en modo alguno, ni alterado los hábitos de vida (2).

SEGUNDA.- Los hechos no son constitutivos de un delito del art 172 ter CP. (3)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

[COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (4)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] vecino/as del inmueble. Para que declare sobre las molestias de la familia del/de la querellante y que el/la denunciante en modo alguno ha quedado afectado por la conducta que reprocha al/a la denunciado/a.

-D./Dña. [NOMBRE Y APELLIDOS] presidente/a de la comunidad. Para que declare sobre la petición del/de la acusado/a acerca de haberle comunicado las molestias de los querellantes.

-D./Dña. [NOMBRE Y APELLIDOS] administrador/a de fincas colegiado/a de la comunidad. Para que declare sobre la petición del/de la acusado/a acerca de haberle comunicado las molestias de los querellantes.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECrim por el/la Letrado/a de la Administración de Justicia.

(2) Esta afectación de la vida del denunciante es clave, como está reconociendo la jurisprudencia. Si ello no consta habrá que dictar sentencia absolutoria, por lo que es un elemento a alegar por la defensa para conseguir la absolución. A partir del 7 de octubre de 2022, fecha de entrada en vigor de la LO 10/2022, ya no se exige que la alteración de la vida cotidiana sea grave, basta con que altere su normal desarrollo.

(3) Las situaciones de acoso vienen contempladas en el art. 172 ter CP. Estas situaciones de acoso en el ámbito de las comunidades de propietarios se denominan actualmente con el término "blocking".

La STS 324/2017 de 8 Mayo 2017, Rec. 1775/2016 ha dictado una primera doctrina sobre el denominado delito de "stalking" o acoso, fijando como doctrina la siguiente:

El tipo de ‘stalking’ del art. 172 ter CP requiere una voluntad de imponer un patrón de conducta sistemático de acoso –insistente y reiterado- con vocación de cierta perpetuación temporal. Se requiere una vocación de persistencia o una intencionalidad, latente o explícita, de sistematizar o enraizar una conducta intrusiva sistemática (persecución, reiteración de llamadas...) capaz de perturbar los hábitos, costumbres, rutinas o forma de vida de la víctima. Se exige implícitamente una cierta prolongación en el tiempo; o, al menos, que quede patente, que sea apreciable, esa voluntad de perseverar en esas acciones intrusivas, que no se perciban como algo puramente episódico o coyuntural, pues en ese caso no serían idóneas para alterar las costumbres cotidianas de la víctima. El tipo no exige planificación pero sí una metódica secuencia de acciones que obligan a la víctima, como única vía de escapatoria, a variar, sus hábitos cotidianos.

El tipo no exige planificación pero sí una metódica secuencia de acciones que obligan a la víctima, como única vía de escapatoria, a variar sus hábitos cotidianos. Para valorar esa idoneidad de la acción secuenciada para alterar los hábitos cotidianos de la víctima hay que atender al estándar del "hombre medio", aunque matizado por las circunstancias concretas de la víctima (vulnerabilidad, fragilidad psíquica, ...) que no pueden ser totalmente orilladas.

Es preciso describir con detalle en la querella los hechos de acoso significando que lo sean de forma repetitiva y que perduran en el tiempo, siguiendo la doctrina del Tribunal Supremo antes expuesta, a fin de evitar que se archiven las diligencias por no suponer la descripción de los hechos una entidad tal que pueda dar a entender una situación de acoso.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

================================================================================
