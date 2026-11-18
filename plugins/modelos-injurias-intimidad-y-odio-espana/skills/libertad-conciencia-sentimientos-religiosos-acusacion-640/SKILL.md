---
name: libertad-conciencia-sentimientos-religiosos-acusacion-640
description: "Redacta el escrito «Libertad de conciencia y sentimientos religiosos: acusación» (formulario 640 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Libertad de conciencia y sentimientos religiosos: acusación

> Formulario 0640 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…epresentación del acusador particular D.»; «…: CONCLUSIONES PRIMERA.- El/La acusado/a»; «… de Justicia con la siguiente referencia»; «…terio de Justicia, porque, de no hacerlo»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se exige prisión / Si se exige multa — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], testigo presente en los hechos.…
- .- Documental: cintas de grabación del lugar que grabaron la secuencia ocurrida el día [FECHA] a las [Nº] hora…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 523 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- artículo 523 CP
- art. 777.2 LECr

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

### Formulario 0640 · Libertad de conciencia y sentimientos religiosos: acusación

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 17 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el párroco de una iglesia, como acusador particular, presenta sus conclusiones provisionales calificando los hechos de delito contra los sentimientos religiosos del art. 523 CP, al haber entrado una persona en su iglesia amenazando y usando la fuerza para echar a los que allí estaban.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D. [COMPLETAR], (1) comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (2) solicitud de apertura de juicio oral ante la Audiencia Provincial, por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a [COMPLETAR] el día [FECHA] accedió a la iglesia sita en [LOCALIDAD], amenazando a los que se encontraban allí presentes para que se marcharan del templo religioso, e incluso empujó a dos señoras, Dña. y Dña. [NOMBRE Y APELLIDOS], que se encontraban en la primera fila, agarrándolas con fuerza del brazo para que salieran del lugar, lo que obligó a suspender el acto religioso que en ese momento se estaba realizando, referido a la confesión religiosa inscrita en el Ministerio de Justicia con la siguiente referencia [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos de un delito contra los sentimientos religiosos del art. 523 CP. (3)

TERCERA.- Es responsable del delito del art. 523 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a circunstancias agravantes.

Concurre con respecto al/a la acusado/a la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se exige prisión / Si se exige multa — el texto de cada opción no venía en el formulario original]

SEXTA.- En concepto de responsabilidad civil se indemnizará con el importe de [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], testigo presente en los hechos.

[OPCIONAL — incluir si procede]

.- Documental: cintas de grabación del lugar que grabaron la secuencia ocurrida el día [FECHA] a las [Nº] horas.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) El párroco es el único representante legal de la Parroquia y quien debe cuidar y responder por todos los bienes de la Parroquia y defender los intereses de la misma.

(2) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación

(3) En este tipo penal se exige la concurrencia de cualquiera de las vías de acción que constan en el tipo, es decir, violencia, amenaza, tumulto o vías de hecho y la acción consiste en impedir, interrumpir o perturbar actos, funciones, ceremonias o manifestaciones de confesiones religiosas, pero se exigen que consten inscritas en el Registro del Ministerio de Justicia, porque, de no hacerlo [COMPLETAR], no estaría incluido en el tipo y solo se sancionarían las conductas realizadas que fueran delictivas, pero fuera de este artículo 523 CP.

Si, además de los hechos descritos en el art. 523 CP se realizaran otros consistentes en daños en bienes muebles o lesiones a las personas presentes en el lugar, se aplicarían las reglas del concurso con el tipo del art. 523 CP.

La STS 835/2017, de 19 de diciembre, rec. 47/2017, por un lado, recuerda que la ley exige que se actué con violencia, amenaza, tumulto o vías de hecho, de manera que el impedimento, la interrupción o la perturbación ocasionada de cualquier otra forma no sería delictiva. Por otro, que la doctrina exige que cualquiera de esos resultados presente cierta relevancia, teniendo en cuenta el tiempo de duración, la forma en la que se ha causado y la forma en la que cesó.

En cuanto a la penalidad se impone la de 6 meses a 6 años si los actos se realizan en lugar de culto y la de multa de 4 a 10 meses si se hacen en otro lugar, es decir fuera del lugar de culto, tales como los templos religiosos.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
