---
name: lesiones-esterilizacion-discapacitada-apelacion-contra-387
description: "Redacta el escrito «Lesiones por esterilización de discapacitada: apelación contra la condena» (formulario 387 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones por esterilización de discapacitada: apelación contra la condena

> Formulario 0387 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] SEDE
- [ ] NÚMERO (2 veces)
- [ ] FECHA (6 veces)
- [ ] PENA
- [ ] COMUNIDAD AUTÓNOMA
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, esta parte propuso como prueba»; «…itos anteriormente referidos, puesto que»; «…e pena ante la desproporción punitiva de»; «…uesto que a partir de la declaración del»; «…, en el minuto»; «…de la grabación, el tribunal deduce que»; «…lógico habría sido tener por probado que»

## Elecciones que hay que hacer

- la madre / el padre

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 149 CP
- art. 156 CP
- art. 149 y 156 CP
- artículos 24.1 y 120.3 de la Constitución
- artículo 24.2 de la Constitución
- art. 24.2 CE
- art. 14.3 CP
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- Ley Orgánica 2/2020

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

### Formulario 0387 · Lesiones por esterilización de discapacitada: apelación contra la condena

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 21 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación del condenado por delito del art. 149 CP, alegando error vencible de desconocimiento de que ya no era posible la esterilización de discapacitada por autorización judicial del art. 156 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña [NOMBRE Y APELLIDOS] condenado/a en el sumario / procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] por delito del art. 149 y 156 CP (1), ante esta Sala comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 846 ter 1 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial y para el TSJ de [LOCALIDAD], en base a las siguientes: (3)

ALEGACIONES

PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución.

 de en los hechos que se juzgan)

SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución.

En fecha [FECHA], esta parte propuso como prueba [COMPLETAR], que fue inadmitida por resolución de fecha [FECHA], reiterándose como cuestión previa su proposición al inicio del juicio, siendo denegada nuevamente en el acto, frente a lo que se formuló respetuosa y oportuna protesta.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 1/2004, 43/2003 y 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso se cumplen cada uno de los requisitos anteriormente referidos, puesto que [COMPLETAR].

TERCERA.- Error en la apreciación de la prueba.

En este caso existe error en la valoración probatoria ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no tenía conocimiento de la modificación legal existente y estaba en la convicción absoluta de la viabilidad legal de la intervención para esterilización, por orden expresa de la autoridad judicial, como constaba en la documentación que se le presentó, por lo que apela a la doctrina del error vencible, al menos, para postular una disminución de la penalidad por la vía del art. 14.3 CP en rebaja penal en dos grados y la imposición de la pena de [PENA] de prisión con suspensión de ejecución de pena ante la desproporción punitiva de [COMPLETAR] de prisión impuestos en un hecho que fue promovido por [ELEGIR: la madre / el padre] de la discapacitada y con entrega de documentación de hechos de ataques sexuales sufridos por la víctima y la necesidad de evitar embarazados no deseados, lo cual dio pie a esa intervención en evitación de esas situaciones.

Pues bien, aplicando lo anterior al caso de autos, resulta que en el fundamento jurídico nº [NÚMERO] de la sentencia apelada incurre en una irracionalidad patente, puesto que a partir de la declaración del [COMPLETAR], en el minuto [COMPLETAR] de la grabación, el tribunal deduce que [COMPLETAR], cuando lo lógico habría sido tener por probado que [COMPLETAR].

CUARTA.- Infracción de normas del ordenamiento jurídico.

En su virtud,

SUPLICO A LA SALA:

Que tenga por interpuesto, en tiempo y forma, RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita con sus copias y que, tras su tramitación, lo eleve a la SALA DE LO CIVIL Y PENAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [COMUNIDAD AUTÓNOMA] que dicte sentencia más ajustada a Derecho, por la que, estimando el recurso, revoque la sentencia de instancia.

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SALA: que tenga por efectuada la anterior designación.

Es Justicia que reitero en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La Ley Orgánica 2/2020, de 16 de diciembre, de modificación del Código Penal para la erradicación de la esterilización forzada o no consentida de personas con discapacidad incapacitadas judicialmente reforma el art. 156 CP, prohibiendo el supuesto de que la esterilización de personas con discapacidad permanente o incapacitadas judicialmente pueda ser acordada por un Juez, por la vía que permitía el párrafo 2º del art. 156 CP, ya derogado.

Con ello, a partir de ahora, la consecuencia será que las operaciones de esterilización practicadas a incapaces constituirán, en todo caso, delito de lesiones, ya que no cabe llevarlas a cabo ni con autorización judicial.

Jurisprudencia de referencia (STS 145/2002 de 1 de febrero, Rec. 2091/2000) (STC 215/1994 de 14 de julio, Rec. 1415/1992) (SAP Madrid, 63/2000 de 4 de abril, Rec. 315/1998) (SAP Girona 235/2009 de 19 de junio, Rec. 14/2009) (Auto AP Álava, 21/2004 de 30 de marzo, Rec. 33/2004).

(2) Este recurso se presenta:

- Ante: la Audiencia que dictó la resolución impugnada.
- En el plazo de 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse, de forma ordenada, las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento abreviado o que se denegaron indebidamente, si se formuló protesta, y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012 de 25 de enero, Rec. 932/2011.

================================================================================
