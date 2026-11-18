---
name: declinatoria-conexidad-favor-seccion-violencia-sobre-373
description: "Redacta el escrito «Declinatoria por conexidad a favor de la Sección de Violencia sobre la Mujer» (formulario 373 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Declinatoria por conexidad a favor de la Sección de Violencia sobre la Mujer

> Formulario 0373 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] SEDE (6 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO (3 veces)
- [ ] NÚMERO (5 veces)
- [ ] AÑO
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ivencia en el mismo, a partir del mes de»; «…y el investigado convivieron en los años»; «…en la localidad de»; «…eriodos distintos, esto es, entre el año»; «…y el año»; «…en el domicilio sito en la localidad de»; «…en el domicilio sito en la localidad de»; «…bis de la Ley de Enjuiciamiento Criminal»; «…seguidas ante dicho órgano. En»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 26 LECRIM
- artículo 15 bis de la Ley de Enjuiciamiento Criminal
- art. 18.2 LECrim
- art. 15.3 LECrim
- art. 14 LECrim
- art. 15 bis LECrim
- Ley Orgánica 1/2004

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

### Formulario 0373 · Declinatoria por conexidad a favor de la Sección de Violencia sobre la Mujer

- Año del modelo: 2021
- Revisión 17-11-2026: 25 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular plantea declinatoria a una Sección de Violencia sobre la Mujer, conforme al art. 26 LECRIM, solicitándole que se inhiba en favor de otra que ya está conociendo de unas diligencias por hechos conexos, que deben ser conocidos conjuntamente, conforme a los arts. 17, 17 bis y 18.2 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de Dña. [NOMBRE Y APELLIDOS], como acusación particular en su condición de perjudicada en este procedimiento, según consta acreditado en autos, comparezco y como proceda en Derecho, DIGO:

Que, mediante el presente escrito promuevo DECLINATORIA por falta de competencia, conforme al art. 26 LECRIM, al corresponder el conocimiento de esta causa a la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE], en el cual se siguen diligencias previas número [Nº DE PROCEDIMIENTO] contra el investigado D. [NOMBRE Y APELLIDOS], conforme dispone el art. 17, 17 bis y 18.2 de la LECrim, al amparo de los siguientes

MOTIVOS

PRIMERO.- Las presentes actuaciones se siguen por presunto delito de maltrato habitual contra el investigado, quien ha venido realizando maltratos físicos y psíquicos a mi representada, en el domicilio que ambos comparten en este partido judicial desde que reanudaron la convivencia en el mismo, a partir del mes de [COMPLETAR], tras cesar temporalmente la convivencia que habían mantenido en un domicilio anterior.

Anteriormente, mi representada y el investigado convivieron en los años [COMPLETAR] en la localidad de [COMPLETAR], donde el investigado había seguido una conducta de maltrato habitual durante todo ese tiempo, incoándose diligencias previas número [Nº DE PROCEDIMIENTO] ante la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE], plaza número [NÚMERO], correspondiente a dicho partido judicial, las cuales fueron incoadas con anterioridad a las presentes, una vez formulada denuncia por mi representada.

Por tanto, la conducta de maltrato habitual se produjo, siempre hablando en los términos indiciarios que el momento procesal exige, en dos periodos distintos, esto es, entre el año [COMPLETAR] y el año [COMPLETAR] en el domicilio sito en la localidad de [COMPLETAR], y, en un segundo periodo, tras el cese temporal de la convivencia, a partir del año [AÑO] en el domicilio sito en la localidad de [COMPLETAR], sito en este partido judicial.

En consecuencia, y al margen de la sustantividad individual de cada caso, es necesaria una perspectiva global de cara a calibrar el alcance y gravedad de la conducta de maltrato habitual durante toda la relación de convivencia, la cual pudiera quedar difuminada si cada secuencia fáctica se enjuicia aisladamente, tal como ha reiterado la jurisprudencia del Tribunal Supremo en supuestos sustancialmente idénticos al presente. En este sentido se pronuncian los Autos del Tribunal Supremo de fecha 4 de abril de 2019 (Recurso número 20074/2019) y de 15 de octubre de 2020 (Recurso núm. 20278/2020), en relación a conductas de maltrato habitual que se despliegan a lo largo del tiempo, con sucesión de dos domicilios distintos, manteniéndose en todo el periodo de convivencia la situación de constante agresividad y violencia psíquica y física del investigado contra la víctima, como ocurre en el presente caso, debiendo conocer la Sección del Tribunal de Instancia que inició la causa en primer lugar.

SEGUNDO.- Habida cuenta de la relación de conexidad, y tratándose de la comisión de un delito de maltrato habitual, que se caracteriza por una conducta persistente de maltrato físico y psíquico que desplegó el investigado a lo largo de toda la relación de convivencia con la víctima, corresponde el conocimiento del asunto a la Sección de Violencia sobre la Mujer Del Tribunal de Instancia de plaza número [NÚMERO], conforme a lo dispuesto en los arts. 17, 17 bis y 18 de la LECrim., pues fue el primero que conoció de la causa.

El artículo 15 bis de la Ley de Enjuiciamiento Criminal [COMPLETAR], incorporado por Ley Orgánica 1/2004, de 28 de diciembre, dispone que "En el caso de que se trate de algunos de los delitos o faltas cuya instrucción o conocimiento corresponda al Juez de Violencia sobre la Mujer, la competencia territorial vendrá determinada por el lugar del domicilio de la víctima..." norma que trata de favorecer la situación procesal de la víctima en su relación con el órgano jurisdiccional y que el Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo que, en reunión celebrada el día 31 de enero de 2006, acordó que por domicilio de la víctima habrá que entender el que tenía cuando se produjeron los hechos punibles, en cuanto responde mejor al principio de juez predeterminado por la Ley, no dependiendo de posibles cambios de domicilio.

En los casos de dualidad de lugares de residencia, el criterio legal debe ser completado con otros que, en este caso, apuntan en diversas direcciones. Se podría dar prevalencia al órgano judicial que empezó primero (art. 18.2 LECrim) al lugar que a la vez pueda ser residencia del investigado (art. 15.3 LECrim) o al lugar donde sucedieron los hechos (art. 14 LECrim). Pero frente a esas pautas, parece que en los casos de coexistencia de varios lugares de residencia más o menos obligados por las circunstancias, debe darse primacía, por suponer el fuero que responde con más fidelidad a la finalidad que buscaba el legislador al introducir el art. 15 bis LECrim, a aquel lugar en que sucedieron los hechos primeros donde la víctima tenía su arraigo, pues los hechos segundos derivan de aquéllos y son conexos, lo que determina la competencia de la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] plaza número [NÚMERO] al ser en ese partido judicial donde tenía la víctima su domicilio en el momento de la comisión de los hechos primeros, quien ha conocido asimismo, en primer lugar, de los hechos que guardan conexidad con los acaecidos posteriormente.

TERCERO.- Por lo anterior, instamos de la Sección a la que nos dirigimos que se inhiba del conocimiento del asunto a favor de la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] plaza número [NÚMERO], para su acumulación a las diligencias previas número, por tratarse de delitos conexos y ser el competente éste último por ser el primero en comenzar la causa.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que se acompañan, y previos los trámites legales, dicte auto inhibiéndose del conocimiento del asunto a favor la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] plaza número [NÚMERO], para su acumulación a las diligencias previas número [Nº DE PROCEDIMIENTO] seguidas ante dicho órgano.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================
