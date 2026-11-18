---
name: acusacion-particular-pedir-victima-declare-via-77
description: "Redacta el escrito «Acusación particular: pedir que la víctima declare por vía telemática (desde el 20 de marzo de 2024)» (formulario 77 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acusación particular: pedir que la víctima declare por vía telemática (desde el 20 de marzo de 2024)

> Formulario 0077 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 258 bis.3.a) LECrim solo garantiza la declaración telemática de las víctimas de violencia de género, violencia sexual o trata de seres humanos y de las víctimas menores de edad o con discapacidad. Para cualquier otra víctima («en cualquier procedimiento»), la petición debe apoyarse en la regla general de presencia telemática preferente del art. 258 bis.1 LECrim.
- Estas víctimas pueden declarar desde el lugar en que reciban asistencia o protección o desde cualquier otro con medios que aseguren su identidad. El juez puede exigir su presencia física por resolución motivada.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…el presente caso se trata de una víctima»

## Elecciones que hay que hacer

- abreviado / por delito leve
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En procedimiento abreviado / En procedimiento común u ordinario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 5 de la Ley 4/2015
- art. 25.2 Ley 4/2015
- art. 229 LOPJ
- art. 731 bis LECRIM
- art. 258 bis.3 LECRIM
- art. 137 bis.3 LEC
- art. 258 bis.1 LECRIM
- artículo 137 bis de la Ley 1/2000
- arts. 258 bis.3 LECRIM
- artículo 137 bis.4 LEC

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

### Formulario 0077 · Acusación particular: pedir que la víctima declare por vía telemática (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 9 campos de relleno marcados en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 80) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el letrado de la acusación particular solicita que la víctima pueda declarar por videoconferencia en el acto del juicio oral en cualquier procedimiento, conforme al art. 258 bis 3.a) LECRIM y art. 137 bis LEC, según redacción dada por RDL 6/2023, de 19 de diciembre, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA OPCIÓN Y REDACTARLA: En procedimiento abreviado / En procedimiento común u ordinario — el texto de cada opción no venía en el formulario original]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusación particular en el procedimiento [ELEGIR: abreviado / por delito leve] número [NÚMERO] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.- Que en fecha [FECHA] se ha señalado la celebración del juicio oral en el procedimiento antes indicado en el que consta como testigo D./Dña [NOMBRE Y APELLIDOS] que ha sido admitido como prueba de cara al juicio oral.

SEGUNDA.- Que por medio del presente escrito intereso que la comparecencia en juicio de dicho testigo se lleve a cabo de forma telemática, a cuyo fin se nos indique en tiempo y forma el lugar donde se debe dirigir para que pueda declarar por el sistema de videoconferencia.

FUNDAMENTOS JURÍDICOS

PRIMERO.- Señala la Ley 4/2015, de 27 de abril, del Estatuto de la víctima:

En el art. 5 de la Ley 4/2015, de 27 de abril:

"1. Toda víctima tiene derecho, desde el primer contacto con las autoridades y funcionarios, incluyendo el momento previo a la presentación de la denuncia, a recibir, sin retrasos innecesarios, información adaptada a sus circunstancias y condiciones personales y a la naturaleza del delito cometido y de los daños y perjuicios sufridos, sobre los siguientes extremos:
a) Medidas de asistencia y apoyo disponibles, sean médicas, psicológicas o materiales"

En el art. 25.2 Ley 4/2015, de 27 de abril:

"Durante la fase de enjuiciamiento podrán ser adoptadas, conforme a lo dispuesto en la Ley de Enjuiciamiento Criminal, las siguientes medidas para la protección de las víctimas:

a) Medidas que eviten el contacto visual entre la víctima y el supuesto autor de los hechos, incluso durante la práctica de la prueba, para lo cual podrá hacerse uso de tecnologías de la comunicación.
b) Medidas para garantizar que la víctima pueda ser oída sin estar presente en la sala de vistas, mediante la utilización de tecnologías de la comunicación adecuadas."

SEGUNDO.- El art. 229 LOPJ prevé la posibilidad de realización telemática de actuaciones procesales -concretamente alude a declaraciones, interrogatorios, testimonios, careos, exploraciones, informes, ratificación de los periciales y vistas-.

TERCERO.- El art. 731 bis LECRIM señala que:

"El Tribunal, de oficio o a instancia de parte, por razones de utilidad, seguridad o de orden público, así como en aquellos supuestos en que la comparecencia de quien haya de intervenir en cualquier tipo de procedimiento penal como imputado, testigo, perito, o en otra condición resulte gravosa o perjudicial, podrá acordar que su actuación se realice a través de videoconferencia u otro sistema similar que permita la comunicación bidireccional y simultánea de la imagen y sonido, de acuerdo con lo dispuesto en el apartado 3 del art. 229 LOPJ ".

La STS 331/2019 de 27 de junio 2019, Rec. 1376/2018 ha validado el uso de la videoconferencia en juicios para las víctimas.

CUARTO.- Señala el art. 258 bis.3 LECRIM que:

"3. Se garantizará especialmente que lasdeclaraciones o interrogatorios de las partes acusadoras, testigos o peritosse realicen de forma telemáticaen los siguientes supuestos, salvo que el Juez o Tribunal, mediante resolución motivada, en atención a las circunstancias del caso concreto, estime necesaria su presencia física:

a) Cuando seanvíctimasde violencia de género, de violencia sexual, de trata de seres humanos o cuando sean víctimas menores de edad o con discapacidad. Todas ellas podrán intervenir desde los lugares donde se encuentren recibiendo oficialmente asistencia, atención, asesoramiento o protección, o desde cualquier otro lugar, siempre que dispongan de medios suficientes para asegurar su identidad y las adecuadas condiciones de la intervención."

Del mismo modo, señala el art. 137 bis.3 LEC que:

"3. Cuando el juez o la jueza, en atención a las circunstancias concurrentes, lo estime oportuno, estas intervenciones podrán hacerse desde cualquier lugar, siempre que disponga de los medios que permitan asegurar la identidad del interviniente conforme a lo que se determine reglamentariamente. En todo caso, cuando el declarante sea menor de edad o persona sobre la que verse un procedimiento de medidas judiciales de apoyo de personas con discapacidad, la declaración por videoconferencia solo se podrá hacer desde una oficina judicial, en los términos del apartado 2.

Las víctimas de violencia de género, violencia sexual, trata de seres humanos, y víctimas menores de edad o con discapacidad podrán intervenir desde los lugares donde se encuentren recibiendo oficialmente asistencia, atención, asesoramiento y protección, o desde cualquier otro lugar si así lo estima oportuno el juez siempre que dispongan de medios suficientes para asegurar su identidad y las adecuadas condiciones de la intervención conforme a lo que se determine reglamentariamente."

Además, el art. 258 bis.1 LECRIM añade que:

"1. Constituido el órgano judicial en su sede, los actos de juicio, vistas, audiencias, comparecencias, declaraciones y, en general, todas las actuaciones procesales, se realizarán preferentemente, salvo que el juez o jueza o tribunal, en atención a las circunstancias, disponga otra cosa, mediante presencia telemática,siempre que las oficinas judiciales o fiscales tengan a su disposición los medios técnicos necesarios para ello, con las especialidades previstas en los artículos 325, 731 bis y 306 de la Ley de Enjuiciamiento Criminal, de conformidad con lo dispuesto en el apartado 3 del artículo 229 y artículo 230 de la Ley Orgánica del Poder Judicial, y supletoriamente por lo dispuesto en la el artículo 137 bis de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil. La intervención mediante presencia telemática se practicará siempre a través de punto de acceso seguro, de conformidad con la normativa que regule el uso de la tecnología en la Administración de Justicia"

En el presente caso se trata de una víctima [COMPLETAR] por lo que concurre el presupuesto de obligatoriedad de que la declaración se lleve a cabo por videoconferencia, al estar incluida la víctima en uno de los supuestos contemplados en los arts. 258 bis.3 LECRIM y art. 137 bis.3 LEC.

Además, se presenta el escrito diez días antes del señalado para la actuación correspondiente, que no es otra que el juicio oral para el día [FECHA], cumpliendo así el plazo recogido en el artículo 137 bis.4 LEC, de aplicación supletoria.

Por todo ello, se ruega se me indique el lugar al que debe acudir la víctima para declarar por videoconferencia.

Se solicita, además, que al momento de acudir al lugar donde declare por videoconferencia se disponga la asistencia de personal especializado que pueda asistir a la víctima para evitar una revictimización de la misma al prestar declaración.

Por todo ello

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración de la víctima D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo por videoconferencia, designando, y comunicándonos en forma, el lugar al que se debe acudir para esa declaración y disponiendo lo necesario para que reciba asistencia especializada que le asista al momento de acudir a la sede desde donde se llevará a cabo la declaración por videoconferencia.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Este escrito se presenta 10 días antes del señalado para la actuación correspondiente (art. 137 bis.4 LEC)

[NOTA DE REVISIÓN: El art. 258 bis.3.a) LECrim solo garantiza la declaración telemática de las víctimas de violencia de género, violencia sexual o trata de seres humanos y de las víctimas menores de edad o con discapacidad. Para cualquier otra víctima («en cualquier procedimiento»), la petición debe apoyarse en la regla general de presencia telemática preferente del art. 258 bis.1 LECrim.]

[NOTA DE REVISIÓN: Estas víctimas pueden declarar desde el lugar en que reciban asistencia o protección o desde cualquier otro con medios que aseguren su identidad. El juez puede exigir su presencia física por resolución motivada.]
