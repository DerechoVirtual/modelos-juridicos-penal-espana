---
name: violacion-internet-sextorsion-lo-4-2023-apelacion-contra-192
description: "Redacta el escrito «Violación por internet (sextorsión, LO 4/2023): apelación contra la condena» (formulario 192 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación por internet (sextorsión, LO 4/2023): apelación contra la condena

> Formulario 0192 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (6 veces)
- [ ] Nº
- [ ] COMUNIDAD AUTÓNOMA
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, esta parte propuso como prueba»; «…itos anteriormente referidos, puesto que»; «…por internet alguno entre el condenado y»; «…el ordenamiento jurídico, por cuanto que»; «…PRIMER OTROSÍ DIGO:»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al/a la apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: [COMPLETAR]…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental consistente en aportación de:.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 179.2 CP
- art. 197 CP
- artículo 846 ter.1 de la Ley de Enjuiciamiento Criminal
- artículos 24.1 y 120.3 de la Constitución
- artículo 790.2 LECrim
- artículo 24.2 de la Constitución
- art. 24.2 CE
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

### Formulario 0192 · Violación por internet (sextorsión, LO 4/2023): apelación contra la condena

- Año del modelo: 2022
- Revisión 17-11-2026: 7 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el procedimiento número [Nº DE PROCEDIMIENTO] sobre delito de violación del art. 179.2 CP y de descubrimiento y revelación de secretos del art. 197 CP, ante la Sala comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 846 ter.1 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial y para el TSJ de [LOCALIDAD], en base a las siguientes

ALEGACIONES

PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución.

Así, el fundamento jurídico nº [Nº] de la sentencia apelada, que aboca a la condena del/de la recurrente, adolece de una total falta de motivación, puesto que se limita a fundar su decisión en la mera afirmación de haber valorado la prueba documental, testifical y pericial, según las reglas de la sana crítica, de modo genérico, sin explicitar en qué ha consistido el resultado de tales pruebas, en relación a la participación del/de la recurrente en los hechos juzgados

En el acta de juicio oral consta la petición de subsanación de la falta, presentada por esta parte a efectos de cumplimiento del artículo 790.2 LECrim.

SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución.

En fecha [FECHA], esta parte propuso como prueba [COMPLETAR], que fue inadmitida por resolución de fecha [FECHA], reiterándose como cuestión previa su proposición al inicio del juicio, siendo denegada nuevamente en el acto, frente a lo que se formuló respetuosa y oportuna propuesta.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 43/2003 y 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso se cumplen cada uno de los requisitos anteriormente referidos, puesto que [COMPLETAR].

TERCERA.- La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se le condena, ya que los hechos que describe la acusación son absolutamente inciertos en cuanto a la autoría del/de la recurrente, ya que no consta acreditado que ese acceso al ordenador del/de la querellante fuera por el/la condenado/a, ya que se trata de un piso compartido por varias personas y, por ello, la autoría del delito no está demostrada. Al mismo tiempo, se pone en duda que haya sido el ordenador de su inmueble el lugar de acceso, ya que es posible técnicamente la derivación a este desde otro inmueble, no habiéndose llevado a cabo labor investigadora alguna que pudiera descubrir si la IP del ordenador fuera pirateada desde otro punto. De suyo, de la pericial propuesta por la defensa se puso en duda la de la acusación y ello evidencia que no existe prueba de cargo que permita enervar la presunción de inocencia. No ha habido prueba alguna en el plenario de contacto por internet alguno entre el condenado y [COMPLETAR], y menos aún intimidación o coacción alguna para realizar por internet actos de contenido sexual. La identidad del condenado no consta acreditada en la prueba del juicio oral. Tampoco se ha tenido en cuenta la siguiente prueba de descargo aportada por la defensa

CUARTA.- Infracción de normas del ordenamiento jurídico, por cuanto que [COMPLETAR]

En su virtud,

SUPLICO A LA SALA:

Que tenga por interpuesto, en tiempo y forma, RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita con sus copias y que, tras su tramitación, lo eleve a la SALA DE LO CIVIL Y PENAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [COMUNIDAD AUTÓNOMA] que dicte sentencia más ajustada a Derecho, por la que, estimando el recurso, revoque la sentencia de instancia.

Es justicia que pido en [LUGAR], a [FECHA].

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: [COMPLETAR]

En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al/a la apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental consistente en aportación de:.

SUPLICO A LA SALA: Que tenga por solicitadas las pruebas propuestas.

SEGUNDOOTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SALA: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
