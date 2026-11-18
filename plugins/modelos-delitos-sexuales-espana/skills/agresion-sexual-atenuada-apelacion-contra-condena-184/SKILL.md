---
name: agresion-sexual-atenuada-apelacion-contra-condena-184
description: "Redacta el escrito «Agresión sexual atenuada: apelación contra la condena» (formulario 184 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual atenuada: apelación contra la condena

> Formulario 0184 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (6 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, esta parte propuso como prueba»; «…itos anteriormente referidos, puesto que»; «…onalidad patente, puesto que a partir de»; «… de la grabación, el tribunal deduce que»; «…lógico habría sido tener por probado que»; «…edita que, no es cierto lo declarado por»; «…el ordenamiento jurídico, por cuanto que»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- Subsidiariamente, y en el caso de que no sea aceptado este alegato, se interesa que la pena impuesta no sea la…
- PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: n…
- -D./Dña. [NOMBRE Y APELLIDOS]…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículos 24.1 y 120.3 de la Constitución
- artículo 790.2 LECrim
- artículo 24.2 de la Constitución
- art. 24.2 CE
- art. 178.3 CP
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

### Formulario 0184 · Agresión sexual atenuada: apelación contra la condena

- Año del modelo: 2022
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 6 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre el delito del art. 178.1 o 3 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación, en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución.

Así, el fundamento jurídico nº [Nº] de la sentencia apelada, que aboca a la condena del/de la recurrente, adolece de una total falta de motivación, puesto que se limita a fundar su decisión en la mera afirmación de haber valorado la prueba documental, testifical y pericial, según las reglas de la sana crítica, de modo genérico, sin explicitar en qué ha consistido el resultado de tales pruebas en relación a la participación del/de la recurrente en los hechos juzgados

En el acta de juicio oral consta la petición de subsanación de la falta, presentada por esta parte a efectos de cumplimiento del artículo 790.2 LECrim.

SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución

En fecha [FECHA], esta parte propuso como prueba [COMPLETAR], que fue inadmitida por resolución de fecha [FECHA], reiterándose como cuestión previa su proposición al inicio del juicio, siendo denegada nuevamente en el acto, frente a lo que se formuló respetuosa y oportuna protesta.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 43/2003, 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso se cumplen cada uno de los requisitos anteriormente referidos, puesto que [COMPLETAR].

TERCERA.- La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Pues bien, aplicando lo anterior al caso de autos, resulta que en el fundamento jurídico nº [Nº] de la sentencia apelada incurre en una irracionalidad patente, puesto que a partir de [COMPLETAR], en el minuto de la grabación, el tribunal deduce que [COMPLETAR], cuando lo lógico habría sido tener por probado que [COMPLETAR].

El juzgador ha llevado a cabo una valoración de la prueba contra el reo, vulnerando la presunción de inocencia y no teniendo en cuenta la prueba de descargo practicada sin una debida motivación. Prueba que acredita que, no es cierto lo declarado por [COMPLETAR], habida cuenta que simplemente se cruzó con ella e intercambió unas palabras nada más, pero no es cierto que él le tocara en modo alguno. De suyo, nadie vio esos hechos, y todo parte de una invención de la querellante. Lo único que ocurrió es que al salir ella y entrar el recurrente chocaron de frente y este fue el único contacto que tuvo, pero que fue totalmente fortuito.

[OPCIONAL — incluir si procede]

Subsidiariamente, y en el caso de que no sea aceptado este alegato, se interesa que la pena impuesta no sea la de prisión, sino la de multa de 18 meses imponible, en base a la menor entidad del hecho, conforme recoge el art. 178.3 CP [NOTA DE REVISIÓN: Numeración de la LO 10/2022 (hechos del 7-10-2022 al 28-4-2023). Para hechos posteriores el tipo atenuado es el art. 178.4 CP (LO 4/2023): mitad inferior de la pena o multa de 18 a 24 meses, excluido si hay violencia, intimidación, voluntad anulada o circunstancias del art. 180. Fuente: Código Penal, BOE-A-1995-25444, art. 178 (redacción LO 4/2023, BOE-A-2023-10213).].

CUARTA.- Infracción de normas del ordenamiento jurídico, por cuanto que [COMPLETAR]

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

[OPCIONAL — incluir si procede]

PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

2.- Pericial: A cuyo fin deberá ser citado a través de la oficina judicial el siguiente perito:

-D./Dña. [NOMBRE Y APELLIDOS]

3.- Documental consistente en aportación de:

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

SEGUNDOOTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
