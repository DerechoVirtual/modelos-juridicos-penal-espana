---
name: oponerse-recurso-reforma-subsidiario-apelacion-contra-24
description: "Redacta el escrito «Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado» (formulario 24 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado

> Formulario 0024 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] ÓRGANO O PERSONA
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, que acordaba»; «…IMERA.– El auto objeto de recurso acordó»; «…, al considerar que»; «… que llevaron al Tribunal a concluir que»; «…desestimado. La resolución que dictamina»; «…s la solicitud de la parte recurrente de»; «…vestigación realizadas, se desprende que»; «…780 de la Ley de Enjuiciamiento Criminal»; «…gencias practicadas son las suficientes.»

## Elecciones que hay que hacer

- acusación / defensa

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si el recurso se presentó contra el auto de transformación en PA)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 222 y 766 de la Ley de Enjuiciamiento Criminal
- art. 779.1 de la LECrim
- art. 780.1 LECRIM
- art. 780 de la Ley de Enjuiciamiento Criminal
- art. 777 de la Ley de Enjuiciamiento Criminal
- art. 785 LECRIM
- art. 787.3 LECRIM
- artículo 24 de la Constitución

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

### Formulario 0024 · Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado

- Año del modelo: 2026
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos opcionales señalados; 17 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 3) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la parte no recurrente impugnando el recurso de reforma y subsidiario de apelación, presentado contra un auto dictado en un procedimiento abreviado, conforme a los arts. 222 y 766 LECRIM. Recoge el supuesto de que el auto que se recurra sea el de transformación en PA.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre de D./Dña. [NOMBRE Y APELLIDOS], cuya representación consta acreditada en las Diligencias previas nº [Nº DE PROCEDIMIENTO], ante este órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

Que el día [FECHA] se nos notificó el escrito de interposición de recurso de reforma y subsidiario de apelación, presentado por [ÓRGANO O PERSONA] contra el auto de fecha [FECHA], que acordaba [COMPLETAR]. Por ello, y conforme a lo establecido en los arts. 222 y 766 de la Ley de Enjuiciamiento Criminal, procedemos a formular las siguientes alegaciones contra dicho recurso planteado, fundamentando nuestra oposición en las siguientes

ALEGACIONES

PRIMERA.– El auto objeto de recurso acordó [COMPLETAR], al considerar que [COMPLETAR].

Dicho auto se emitió después de haberse llevado a cabo todas las diligencias de instrucción pertinentes, conforme al art. 779.1 de la LECrim, y se fundamentó adecuadamente en las razones que llevaron al Tribunal a concluir que [COMPLETAR].

En consecuencia, consideramos que el recurso de reforma y subsidiario de apelación interpuesto por carece de fundamento y debe ser desestimado.

La resolución que dictamina [COMPLETAR] se encuentra en consonancia con la legalidad, ya que se emitió tras la realización de todas las diligencias necesarias para esclarecer los hechos. Rechazamos la solicitud de la parte recurrente de [COMPLETAR].

De acuerdo con las diligencias de investigación realizadas, se desprende que [COMPLETAR]

[OPCIONAL — incluir si procede]

(Si el recurso se presentó contra el auto de transformación en PA)

Hay que tener en cuenta que no puede entenderse que la fase previa de investigación precedente al auto de transformación en PA constituye la necesidad de practicar absolutamente todas las diligencias que la parte que recurre el auto interese para realizar un "agotamiento" de práctica de diligencias de la fase de diligencias previas, ya que el auto de PA tiene un significado y objetivo, cual es que cuando existen indicios racionales de que se haya podido cometer un delito procede concluir la fase previa y dictar el auto de PA para proseguir el trámite hasta la celebración del juicio oral, y es entonces, en los respectivos escritos de conclusiones provisionales, donde las partes podrán realizar la proposición de prueba, aun respecto a medios de prueba que no se hayan llevado a cabo como diligencias de investigación, ya que la sentencia que se dicte se basará en las pruebas que se practiquen en el plenario, no en las diligencias de investigación.

Por ello, no existe el derecho de la parte a interesar, en virtud de un recurso, la práctica de "más diligencias" cuando las que han dado lugar al dictado de auto de PA son suficientes para cumplir el objetivo del dictado de este auto.

Señala la STS 150/2024 de 21 de febrero, Rec. 6509/2021: "Completaba el Tribunal Constitucional su consideración indicando que la apertura de la fase intermedia -a través del Auto de incoación del procedimiento abreviado previsto en el art. 780.1 LECRIM- supone necesariamente la clausura de la fase anterior de instrucción, sin posibilidad de replantear lo ya decidido en ella. Y como consecuencia de lo anterior, el Auto de incoación del procedimiento abreviado no solo tiene el significado de clausurar de manera implícita la anterior fase de instrucción (STC 186/1990, FJ 8), sino que, por la propia naturaleza y características de esta fase procesal, impide al imputado solicitar nuevas diligencias o tener conocimiento de las ya practicadas o pedir el sobreseimiento."

Además, la STS 197/2018 de 25 de abril, Rec. 1278/2017 añade:

"El auto previsto en el art. 779.1.4º de la LECrim . cumple una triple función:

a) da por finalizadas las diligencias previas;
b) efectúa una valoración del resultado de la instrucción apreciando la existencia de indicios bastantes de la existencia de un delito de los previstos en el art. 757 de la misma Ley, por lo que ordena la acomodación de los trámites a los propios del procedimiento abreviado, y
c) acuerda dar traslado a las partes acusadoras para que opten entre alguna de las posibilidades previstas en el art. 780.1, es decir, solicitar el sobreseimiento, la apertura del juicio oral (formulando simultáneamente en ese caso escrito de acusación) o la práctica de diligencias complementarias.

No se exige en puridad que en el auto de transformación se realice una detallada relación de hechos, sino que debe incluir los elementos fácticos que integran el tipo delictivo objeto de imputación, pero no requiere que sea exhaustivo."

Por ello, no es preciso acordar más diligencias si las practicadas son suficientes para seguir adelante con la causa, por cuanto el auto de PA es solo un paso para seguir adelante la causa, sin ser preciso que se "agote" la investigación.

Del mismo modo, el Tribunal Supremo, Sala Segunda, de lo Penal, Sentencia 108/2019 de 5 Mar. 2019, Rec. 10024/2018 añade:

No es finalidad del auto acordando la continuación por la tramitación por el procedimiento abreviado, la de suplantar la función acusatoria del Ministerio Público, ni por lo tanto es esencial efectuar en el mismo una calificación jurídica concreta y específica, sino que ello es cometido de las partes acusadoras, en una fase posterior del procedimiento, donde el Ministerio Fiscal y en su caso las demás partes personadas formularan, escrito de acusación en base a los hechos que consideren penalmente atribuibles a determinadas personas.

En definitiva, el auto por el que se acuerda la continuación de las Diligencias Previas por los cauces del Procedimiento Abreviado tiene el significado procesal de identificar los hechos que revisten apariencia de delito y la identidad del presunto autor/res, con basamento en unos elementos indiciarios que se han traído a la causa durante la instrucción judicial, a fin de darlos a las partes acusadoras para que interesen el sobreseimiento o archivo, la práctica de más diligencias o la apertura de juicio oral formulando escrito de acusación, conforme establecen el art. 779.1.4 y art. 780 de la Ley de Enjuiciamiento Criminal [COMPLETAR].

Por su parte, la finalidad de las diligencias previas (art. 777 de la Ley de Enjuiciamiento Criminal) es la de determinar la naturaleza y circunstancias del hecho, las personas que en el han participado y el órgano competente para su enjuiciamiento. En la fase intermedia la investigación realizada debe permitir tipificar los hechos y conocer la identidad de los partícipes. Ello no obstante, cuando faltan los datos para determinar esos elementos esenciales para la acusación, por inadecuada tramitación de las diligencias previas, cabe que las partes acusadoras soliciten diligencias complementarias del juzgado de instrucción. El artículo 780.2 parece permitir únicamente esa posibilidad en los casos de los elementos esenciales para la tipificación de los hechos, pero es indudable que también es posible en los supuestos en que resulte indispensable la práctica de alguna diligencia para determinar la identidad o participación de alguna persona ya que la expresión "diligencias indispensables para formular acusación" empleada por el art. 780.2 permite esta interpretación.

Pero es solo preciso que se practiquen las imprescindibles para la acusación o defensa en casos puntuales y necesarios a la primera para acusar y al segundo en algún punto concreto, aunque no en lo relativo a que se practiquen más diligencias para poder decretar el archivo, porque si se consideran que las practicadas permiten la imputación no caben más diligencias y todo se reconduce de cara a la proposición de prueba de cara al plenario.

En definitiva, no cabe "eternizar" la fase de diligencias previas, que deben concluir cuando las existentes son suficientes para el dictado de PA y, en su caso, se verifique en debida forma la proposición de medios de prueba en el escrito de calificación, con independencia de que puedan llevarse también en la audiencia preliminar del art. 785 LECRIM (LO 1/2025, de 2 de enero) o en el acto del juicio oral por la vía del art. 787.3 LECRIM.

Por eso, nos oponemos a la revocación del auto de PA por entender que las diligencias practicadas son las suficientes.

[COMPLETAR]

SEGUNDA. – También impugnamos las afirmaciones del recurso que se refieren a la vulneración del derecho a utilizar medios de prueba del artículo 24 de la Constitución, ya que en ningún caso se ha vulnerado la tutela efectiva ni se ha vulnerado el derecho de defensa ni asistencia a letrado durante este procedimiento.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias y que se considere impugnado el recurso de reforma, y con ello también el de apelación, presentado por la [ELEGIR: acusación / defensa] contra el auto de de fecha [FECHA] y que se acuerde su desestimación, confirmando la resolución impugnada.

Es Justicia que pido en [LUGAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================
