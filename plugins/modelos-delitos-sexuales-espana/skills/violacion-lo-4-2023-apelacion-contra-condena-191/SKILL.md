---
name: violacion-lo-4-2023-apelacion-contra-condena-191
description: "Redacta el escrito «Violación (LO 4/2023): apelación contra la condena» (formulario 191 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación (LO 4/2023): apelación contra la condena

> Formulario 0191 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] FECHA (6 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, condenándole a»; «…, esta parte propuso como prueba»; «…itos anteriormente referidos, puesto que»; «…tancias del caso" fueron las siguientes:»; «…lugar sede del órgano de apelación el de»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: n…
- -D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 179.2 CP
- artículos 24.1 y 120.3 de la Constitución
- artículo 790.2 LECrim
- artículo 24.2 de la Constitución
- art. 24.2 CE
- art. 178.1 CP
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0191 · Violación (LO 4/2023): apelación contra la condena

- Año del modelo: 2022
- Revisión 17-11-2026: 6 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D. [NOMBRE Y APELLIDOS] en el procedimiento /, ante la Sala comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha sido notificado a esta parte la sentencia recaída en fecha de [FECHA], condenándole a [COMPLETAR] por un delito de violación del art. 179.2 CP y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 846 ter 1 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial y para el TSJ de [LOCALIDAD], en base a las siguientes:

ALEGACIONES

PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución.

Así, el fundamento jurídico nº [Nº] de la sentencia apelada, que aboca a la condena del/de la recurrente, adolece de una total falta de motivación, puesto que se limita a fundar su decisión en la mera afirmación de haber valorado la prueba documental, testifical y pericial, según las reglas de la sana crítica, de modo genérico, sin explicitar en qué ha consistido el resultado de tales pruebas en relación a la participación del/de la recurrente en los hechos juzgados

En el acta de juicio oral consta la petición de subsanación de la falta, presentada por esta parte a efectos de cumplimiento del artículo 790.2 LECrim.

SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución.

En fecha [FECHA], esta parte propuso como prueba [COMPLETAR], que fue inadmitida por resolución de fecha [FECHA], reiterándose como cuestión previa su proposición al inicio del juicio, siendo denegada nuevamente en el acto, frente a lo que se formuló respetuosa y oportuna protesta.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 43/2003, 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso se cumplen cada uno de los requisitos anteriormente referidos, puesto que [COMPLETAR]

TERCERA.- La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido por el recurrente que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó probado que fue Dña. [NOMBRE Y APELLIDOS], la que le insinuó iniciar una relación al recurrente, tal y como este aseguró en el juicio oral y lo contó al día siguiente al/a la testigo D./Dña. [NOMBRE Y APELLIDOS] que declaró en el juicio, y que ella le acompañó voluntariamente al coche, obviamente para estar juntos, siendo absolutamente incierto que éste la forzara, sino que la relación fue consentida aunque, dado que lo hicieron en un vehículo, y en un lugar apartado, puede que ella tuviera algunas marcas fruto de la dificultad del lugar, que es lo que explica el parte médico forense.

Sin embargo, al terminar empezaron a discutir porque ella quería acudir a su domicilio a lo que él se negó, siendo ella la que se bajó del vehículo ante el enfado que tuvo y él se fue del lugar ante la discusión existente, lo que no integra delito alguno.

El hecho de que se hayan encontrado restos de semen del acusado es fruto de una relación sexual consentida, ya que el acto sexual lo hicieron de manera voluntaria. Lo que ocurrió es que, al día siguiente, cuando ella se levantó, se pudo arrepentir de lo que hizo y fue por lo que le pudo querellarse, o fue una venganza porque este no quiso que ella la acompañara a su casa e iniciar una relación juntos, lo que generó una discusión.

En consecuencia, la sentencia infringe lo dispuesto en la redacción dada al art. 178.1 CP por la LO 10/2022 y ratificada por LO 4/2023, en cuanto a la existencia del consentimiento, porque éste concurrió. Nótese que el citado artículo señala en su párrafo 2º que "Sólo se entenderá que hay consentimiento cuando se haya manifestado libremente mediante actos que, en atención a las circunstancias del caso, expresen de manera clara la voluntad de la persona". Y en el presente caso las "circunstancias del caso" fueron las siguientes: [COMPLETAR], de lo que se evidencia que el consentimiento existió.

Se interesa se revoque la sentencia y se absuelva al recurrente.

CUARTA.- Infracción de normas del ordenamiento jurídico.

En su virtud,

SUPLICO A LA SALA:

Que tenga por interpuesto, en tiempo y forma, RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita con sus copias y que, tras su tramitación, lo eleve a la SALA DE LO CIVIL Y PENAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [LOCALIDAD] que dicte sentencia más ajustada a Derecho, por la que, estimando el recurso, revoque la sentencia de instancia.

Es justicia que pido en [LUGAR], a [FECHA].

[OPCIONAL — incluir si procede]

PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

1.- TESTIFICAL: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

2.- PERICIAL: A cuyo fin deberá ser citado a través de la oficina judicial el siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS]

3.- DOCUMENTAL consistente en aportación de:

SUPLICO A LA SALA: Que tenga por solicitadas las pruebas propuestas.

SEGUNDOOTROSÍ DIGO: Que, de conformidad con el artículo 790.2 de la Ley de Enjuiciamiento Criminal, se designa como domicilio para notificaciones del lugar sede del órgano de apelación el de [COMPLETAR].

SUPLICO A LA SALA: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
