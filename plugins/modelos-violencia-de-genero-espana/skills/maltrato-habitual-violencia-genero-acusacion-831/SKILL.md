---
name: maltrato-habitual-violencia-genero-acusacion-831
description: "Redacta el escrito «Maltrato habitual (violencia de género): acusación» (formulario 831 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Maltrato habitual (violencia de género): acusación

> Formulario 0831 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…con el acusado D.»; «…y su hijo mayor de edad D.»; «…a denunciante a una distancia inferior a»; «…tuado hasta el momento de la vista oral.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- Concurre el subtipo agravado específico del art. 173.2.2 CP de haberse cometido el hecho en presencia de menor…
- 1.- Interrogatorio del acusado.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 173.2 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 173.2 del Código Penal
- art. 173.2.2 CP
- artículo 22 CP
- art. 57.2 CP
- artículo 173.2 CP
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

### Formulario 0831 · Maltrato habitual (violencia de género): acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 4 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular en procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos como delito de maltrato habitual del art. 173.2 CP

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Dña. contrajo matrimonio en fecha [FECHA] con el acusado D. [COMPLETAR]. Desde el comienzo de su relación matrimonial hasta la fecha ha sido sometida a constantes situaciones de malos tratos, humillaciones por parte del acusado. Unas veces delante de sus hijos cuando eran menores de edad y otras en presencia de su madre Dña. [NOMBRE Y APELLIDOS] y hermana Dña. [NOMBRE Y APELLIDOS]. En el último año estas agresiones y situaciones de maltrato físico y psicológico se han incrementado hasta el punto de hacer la vida insostenible, y producirse algunos de ellos en presencia de sus hijos menores de edad, lo que motivó que tuviera que acudir a la consulta de un psicólogo que emitió un informe en fecha [FECHA] que consta aportado como documento nº 1 a la querella donde se refleja el cuadro de estrés causado por el síndrome de "mujer maltratada" al haber llegado a un punto de afectación a la psique que es integrante de un maltrato habitual, como se evidencia por las continuas agresiones de que ha sido víctima, y psicológico. De las agresiones no existen partes médicos porque quiso ocultarlo, pero sí se hizo en algunos casos a presencia de su madre Dña. [NOMBRE Y APELLIDOS] y hermana Dña. [NOMBRE Y APELLIDOS] y su hijo mayor de edad D. [COMPLETAR].

Toda esta situación le ha causado una fuerte situación de estrés y depresión que se coteja en el informe pericial.

SEGUNDA.- Tales hechos son constitutivos del delito de maltrato habitual del art. 173.2 del Código Penal.

[OPCIONAL — incluir si procede]

Concurre el subtipo agravado específico del art. 173.2.2 CP de haberse cometido el hecho en presencia de menores, que tiene su reflejo en la pena en su mitad superior.

TERCERA.- Es responsable del delito de maltrato habitual del art. 173.2.2 CP, en concepto de autor, el acusado.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre, con respecto al acusado, ninguna circunstancia modificativa de la responsabilidad criminal.

Concurre, con respecto al acusado, la circunstancia agravante de [CIRCUNSTANCIA] prevista en el artículo 22 CP.

QUINTA.- Procede imponer al acusado por el delito de maltrato habitual la pena de [PENA] de prisión, (párrafo 2º del art. 173.2 CP al cometerse en presencia de menores) privación de la tenencia y porte de armas por [Nº] años, prohibición de acercarse a la denunciante a una distancia inferior a [COMPLETAR] metros de su domicilio, lugar de trabajo sito en [LOCALIDAD], o cualesquiera que frecuente y prohibición de comunicación por cualquier medio por tiempo de [DURACIÓN]. (2)

SEXTA.- Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el juicio oral, intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

- Dña. [NOMBRE Y APELLIDOS]. madre de Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS], hermano/a de Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS], hijo/a de Dña. .y del acusado, mayor de edad.

[OPCIONAL — incluir si procede]

.- Pericial, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS] autor/a del dictamen pericial, para que se ratifique en el juicio oral.

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles que se recibe traslado de las actuaciones.

(2) La pena de prohibición de aproximación es preceptiva imponerla por aplicación del art. 57.2 CP, pero resulta obvia que la acusación debe instarla. No obstante, la de prohibición de comunicación debe solicitarse expresamente hasta el punto de que el juez no puede imponerla si no hay expresa solicitud de la acusación.

Con respecto a la distancia, lo normal es instarlo a una distancia de 500 metros, aunque pueden darse circunstancias particulares (por ejemplo, tener el acusado un piso a 300 metros de la víctima) que permitan su reducción. La distancia establecida en la orden de alejamiento debe medirse en la forma que determine la resolución judicial y, en su defecto, en línea recta. (STS 691/2018, de 21 de diciembre, Rec. 2357/2017)

Si, además de la habitualidad delictiva (STS 609/2020, de 13 de noviembre, Rec. 327/2019), se pudiesen concretar cada uno de los hechos que se hayan realizado, en cuanto a fechas concretas, se castigarán por separado, además de la habitualidad, no suponiendo una infracción del non bis in idem, ya que lo permite el art. 173.2 CP. (STS 2/2021, de 13 de enero, Rec. 891/2019)

El número de personas directamente afectadas por un clima familiar violento puede servir como parámetro para evaluar los indicadores de antijuridicidad de la acción y el alcance de la culpabilidad del responsable, pero no transforma la naturaleza unitaria del delito de maltrato habitual del artículo 173.2 CP en tantos delitos homogéneos como personas afectadas. (STS 66/2021, de 28 de enero, Rec. 10638/2020)]

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
