---
name: orden-proteccion-violencia-genero-reforma-subsidiario-374
description: "Redacta el escrito «Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado» (formulario 374 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado

> Formulario 0374 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La LO 1/2026 (BOE-A-2026-7966) añadió al art. 544 bis LECrim la finalidad de «evitar la reiteración delictiva»; el argumento de falta de necesidad para proteger a la víctima no basta si se invoca riesgo de reiteración.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] LOCALIDAD
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ctuando en representación y defensa de D»; «… comunicación con la presunta víctima Dª»; «…estos en la LECRIM., y en el art. 57 C.P»; «…de conformidad. Es justicia que pido, en»; «…y»; «…y [COMPLETAR]»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766 LECRIM
- art. 544 ter LECRIM
- art. 766 de la LECrim
- art. 17 CE
- artículo 57 del Código Penal
- art. 766.5 de la LECrim

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

### Formulario 0374 · Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado

- Año del modelo: 2021
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La LO 1/2026 (BOE-A-2026-7966) añadió al art. 544 bis LECrim la finalidad de «evitar la reiteración delictiva»; el argumento de falta de necesidad para proteger a la víctima no basta si se invoca riesgo de reiteración.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa del acusado presenta recurso de reforma y subsidiario de apelación, conforme al art. 766 LECRIM, contra el auto que acuerda una orden de protección del art. 544 ter LECRIM en favor de su pareja en un procedimiento abreviado.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Abogado/a, actuando en representación y defensa de D [COMPLETAR], según consta acreditado en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Que el día [FECHA] se ha notificado a esta defensa el auto de fecha [FECHA], decretando la medida de alejamiento a más de metros y prohibición de comunicación con la presunta víctima Dª [COMPLETAR], y entendiendo dicha resolución no ajustada a derecho, dicho sea en términos de defensa, por medio del presente escrito, al amparo de lo dispuesto en el art. 766 de la LECrim y preceptos concordantes INTERPONGO RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN, en base a los siguientes

MOTIVOS

PRIMERO.- Nulidad de la resolución recurrida por falta de motivación.

La resolución recurrida decreta la orden de protección sin motivar los elementos en que se funda la adopción de tan grave medida para mi representado. Esta exigencia de motivación deviene esencial desde el momento en que la medida cautelar afecta a las prescripciones constitucionales a la presunción de inocencia, así como a las relativas a la libertad de las personas y, en concreto, al derecho individual a elegir libremente el lugar de residencia (art. 19 en relación con el art. 17 CE), siendo un derecho fundamental que solo puede ser restringido en supuestos de estricta necesidad para proteger a la víctima, además de que deba de ser adecuado a la finalidad perseguida, proporcional (en cuanto a los hechos denunciados y las consecuencias que se pretenden) y siempre que no existan otros medios menos lesivos, con los que se pueda atender a los fines perseguidos, todo lo cual debe exteriorizarse suficientemente en la resolución que adopta la medida.

En el presente caso se utiliza un mero formulario de resolución para la adopción de la medida, de manera que la motivación de la resolución objeto de recurso no es tal, puesto que carece de los debidos datos individualizadores (concretas expresiones, identidades, folios...), sin hacer mención a cuáles son los elementos indiciarios que aprecia, ni a las razones de las que se derivaría una situación objetiva de riesgo para la víctima, ni tan siquiera a la situación personal de mi defendido, con todo lo cual se vulneran no solo sus derechos fundamentales a la libertad ambulatoria y de residencia, sino también los de presunción de inocencia y los de proscripción de la indefensión.

Respecto de la motivación, es conocida y reiterada la doctrina que aclara que la Constitución no autoriza a exigir un razonamiento judicial exhaustivo y pormenorizado de todos los aspectos y perspectivas que las partes puedan tener de la cuestión que se decide, sino que deben considerarse suficientemente motivadas aquellas resoluciones judiciales que vengan apoyadas en razones que permitan conocer cuáles han sido los criterios jurídicos esenciales fundamentadores de la decisión, es decir la ratio decidendi que ha determinado aquélla. Sin embargo, en este caso no se cumplen tales mínimos, puesto que no existe ningún elemento que exteriorice las razones que determinan la concurrencia de los requisitos establecidos en los arts. 544 bis y 544 ter de la LECrim. Estos preceptos exigen además una motivación reforzada al exigir al Juez o Tribunal que adopte las medidas de "forma motivada" y de manera excepcional, "cuando resulte estrictamente necesario al fin de protección de la víctima [NOTA DE REVISIÓN: Desde la LO 1/2026 (vigente desde el 10-4-2026) el art. 544 bis LECrim admite también la medida cuando sea estrictamente necesaria para evitar la reiteración delictiva. Fuente: LO 1/2026, BOE-A-2026-7966, art. primero.tres (art. 544 bis LECrim).]", todo lo cual se ha incumplido en este caso.

La afectación a derechos fundamentales de la persona a la que se impone una medida cautelar como la decretada en la resolución recurrida, que restringe los derechos a la libertad deambulatoria, y a la presunción de inocencia, en sus dos vertientes tradicionales, requiere que cualquier decisión que se adopte por parte del Juzgador, además de cumplir el deber general de motivación (expresivo de las razones jurídicas que le han movido a adoptar la decisión), se pondere específicamente la adecuación de la medida desde la contemplación de los riesgos que con ella se quieren conjurar, lo que exige un análisis específico del "fumus boni iuris", de que el riesgo puede ser conjurado (teniendo en cuenta la proporcionalidad), mediante el alejamiento de la persona a quien se imputan indiciariamente unos hechos graves, de la o las personas sobre las que se temen ataques a su vida, a su integridad física, a su libertad y al resto de los bienes jurídicos expuestos en la LECRIM., y en el art. 57 C.P [COMPLETAR]. Y nada de esto se cumple con la resolución recurrida, por lo que deviene nula de pleno derecho.

Por ello, alegamos en primer lugar la falta absoluta de motivación de la resolución que debe dar lugar a la nulidad de pleno derecho de la misma, con el consecuente alzamiento de las medidas decretadas.

SEGUNDO.- Inexistencia de elementos indiciarios y de riesgo para decretar la medida cautelar.

La total ausencia de motivación impide identificar los elementos indiciarios en que se ha fundado la adopción judicial de las medidas, mas el examen de fondo permite afirmar que, en ningún caso, existen tales indicios de comisión de delito y de situación objetiva de riesgo que permitan fundar la medida adoptada.

La medida decretada se ampara aparentemente en los artículos 544 bis y 544 ter de la Ley de Enjuiciamiento Criminal, que exige que la resolución que las acuerda ha de analizar la concurrencia de las propuestas que la condicionan, esto es, el llamado "fumus boni iuris" o apariencia de buen derecho, que en el procedimiento penal se concreta en la existencia de indicios racionales de criminalidad y el "periculum in mora" o peligro de mora. Así como efectuar un ponderado análisis de la finalidad que se pretende con la medida cautelar y de los intereses en conflicto valorando su necesidad y proporcionalidad.

En este caso no hay ninguna referencia al delito de los mencionados en el artículo 57 del Código Penal que se está investigando, ni a los indicios, ni al peligro para la víctima, ni a la necesidad de la medida. La medida se adopta con base a la denuncia de la víctima, que relata unos episodios de agresión lejanos en el tiempo, que carecen de la mínima corroboración, existiendo una situación de separación de la pareja desde hace más de un año, donde únicamente han coincidido casualmente el día anterior al de la denuncia, manifestando la denunciante que mi defendido le amenazó de muerte, sin ningún elemento que lo corrobore. No existen ni antecedentes violentos de mi representado, ni tan siquiera relación personal entre ambos después de la separación, de manera que no hay ningún elemento objetivo que permita identificar una situación de riesgo para la denunciante.

A los efectos de determinación del peligro, deben evaluarse los antecedentes de los que se pueda inferir que el denunciado puede seguir cometiendo hechos violentos atentatorios contra la integridad física o moral de la víctima, con objeto de determinar si es necesaria la medida con objeto de evitar nuevos actos de agresión. Pero nada de esto se produce en este caso, donde el auto recurrido se limita a afirmar, sin más, que existen indicios de haberse cometido hechos delictivos -lesiones/maltrato en el ámbito de la Violencia de Género y una discusión que derivó en amenazas por el denunciado-, y que está presente una situación de riesgo derivada de aquellos indicios, pretendiendo justificar la medida con un supuesto riesgo de posible reiteración delictiva, sin que se justifique ni concretice ningún riesgo específico que, por su novedad o por su urgencia, debe ser prevenido mediante la adopción de las medidas cautelares de protección interesadas.

En todo caso, los hechos nucleares denunciados son la existencia de un encuentro casual donde supuestamente se vertieron amenazas por mi defendido, los cuales son negados rotundamente por esta parte, que no revelan la existencia de una situación de riesgo para la integridad física/psíquica respecto a la denunciante, no obstante denunciarse también supuestos actos agresivos con anterioridad, expresiones amenazantes, además de otros actos de acoso, los cuales, no constan adverados más allá de las manifestaciones incriminatorias de la propia denunciante. En este sentido, es inexplicable que la calificación policial de riesgo alto, pues no constan denuncias anteriores, ni episodios de amenazas o maltrato después de la separación, residiendo cada uno de los implicados en su propio domicilio y llevando su vida personal, familiar y social por caminos separados.

Por todas estas razones, no hay elementos indiciarios bastantes y, en todo caso, no hay situación objetiva de riesgo, sin que la orden de protección dictada cumpla su finalidad de proteger una situación de riesgo objetivo, que lógicamente no puede residenciarse únicamente en la manifestación de temor de la denunciante, ni en la posibilidad meramente teórica de que sufra una agresión o amenaza, sino que debe poder efectuarse un juicio de prognosis positivo de probable reiteración delictiva, siendo que en el caso se carece de los mínimos indicios para ello.

Por todo ello, solicitamos que se estime el recurso y se revoque la resolución, al no existir elementos indiciarios suficientes y no darse una situación objetiva de riesgo para la presunta víctima.

TERCERO.- Falta de proporcionalidad de la medida cautelar decretada.

Se alega finalmente la falta de proporcionalidad de la medida cautelar decretada pues, a los gravísimos defectos y vicios ya denunciados, se añade que se fija un radio de alejamiento de 1.000 metros, lo cual determinaría que mi defendido tuviera que abandonar su domicilio actual, así como su trabajo, el cual se encuentra a una distancia inferior a la acordada, tal como se acreditó en la declaración de mi defendido y se reconoció por la propia denunciante.

Ello supone que la medida decretada es totalmente desproporcionada, puesto que en ningún momento se ha ponderado específicamente la adecuación de la medida a la situación de mi defendido y las consecuencias que le supone, incluso desde la contemplación de los riesgos que con ella se pretenden conjurar. Habiéndose adoptado una decisión estandarizada de fijar una distancia de 1.000 metros, sin tener en cuenta que a los mismos fines se podría haber establecido una distancia muy inferior que permitiera a mi defendido seguir con su vida personal y laboral, máxime cuando los hechos que se denuncian, aunque fueran ciertos, no revisten especial gravedad ni ponen de manifiesto una peligrosidad relevante para la víctima, desde un punto de vista objetivo y atendidas todas las circunstancias antes expuestas.

Por estas razones se alega la falta de proporcionalidad de las medidas decretadas, solicitando subsidiariamente que, de mantenerse el alejamiento, se imponga una distancia no superior a 100 metros.

Por lo expuesto, es de justicia y

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, por formulado RECURSO DE REFORMA y, caso de no ser estimado, SUBSIDIARIO DE APELACIÓN contra el auto de fecha [FECHA] y, previos los trámites legales, se revoque y se deje sin efecto la citada resolución. Subsidiariamente, se solicita la estimación parcial del recurso y que se decrete un alejamiento por distancia no superior a 100 metros.

OTROSÍ DIGO I que para el caso que se desestime el recurso de reforma, designo los siguientes particulares para su remisión a la Audiencia:

SUPLICO A LA SECCIÓN se acuerde de conformidad.

OTROSÍ DIGO II que, en caso de ser desestimado el recurso de reforma, al formularse el recurso de apelación con carácter subsidiario, se eleven las actuaciones a la Audiencia Provincial de [LOCALIDAD] para la resolución del recurso, a cuyo efecto interesa a esta parte la celebración de vista conforme al art. 766.5 de la LECrim, al entenderla necesaria para la mejor resolución del recurso.

SUPLICO A LA SECCIÓN se acuerde de conformidad.

Es justicia que pido, en [COMPLETAR] y [COMPLETAR]

[COMPLETAR]

(Firma de Abogado)

================================================================================
