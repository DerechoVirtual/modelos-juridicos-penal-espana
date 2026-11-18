---
name: apelacion-contra-condena-narcotrafico-salud-publica-793
description: "Redacta el escrito «Apelación contra la condena por narcotráfico (salud pública)» (formulario 793 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por narcotráfico (salud pública)

> Formulario 0793 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

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

- [ ] NÚMERO (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] FECHA (4 veces)
- [ ] PENA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…prehendida es muy reducida en el peso de»; «…y con una pureza del»; «… la pena desde los que se han impuesto a»; «…de prisión en lugar de la impuesta de»; «…Documental consistente en aportación de:»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al/a la apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: no…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental consistente en aportación de: [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 368 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 20.2 CP
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 80.5 CP

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

### Formulario 0793 · Apelación contra la condena por narcotráfico (salud pública)

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 21 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso contra sentencia condenatoria en procedimiento abreviado por delito contra la salud pública de tráfico de drogas del art. 368 CP basado en errores en la apreciación de la prueba.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección Penal nº [NÚMERO] de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito contra la salud pública, ante la Audiencia Provincial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación (1) en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Sala de lo civil y penal del TSJ de [LOCALIDAD], en base a las siguientes

ALEGACIONES (2)

PRIMERA: La resolución que se recurre padece errores en la apreciación de la prueba como se explica:

Es conocido por el recurrente que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada, sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que como consta en el informe médico aportado por esta parte al juicio oral el/la acusado/a y ahora recurrente tenía una absoluta dependencia a la cocaína como resultó, también, del propio informe forense en el análisis efectuado al efecto. Además, la cantidad de droga aprehendida es muy reducida en el peso de [COMPLETAR] y con una pureza del [COMPLETAR] según el informe analítico aportado al efecto en juicio oral, lo que determinaría en todo caso, incluso, la aplicación de una pena de [PENA] de prisión que en el juicio oral planteamos como alternativa (3) en caso de condena, dadas las circunstancias del hecho, y las del/de la acusado/a, por su dependencia a las drogas, lo que, aunque no llevara a la aplicación de la eximente completa del art. 20.2 CP, sí, al menos, a la aplicación del art. 368 CP, párrafo 2º, con una rebaja en la pena desde los que se han impuesto a [COMPLETAR], de prisión, lo que permitiría, incluso, la suspensión de la ejecución de la pena y el sometimiento a un tratamiento de deshabituación cuya copia de asistencia ya se presentó en el juicio oral y se acompaña a este recurso de apelación como documento nº 1.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Sala de lo civil y penal del TSJ de [LOCALIDAD] a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta o, en su defecto, y subsidiariamente se condene a la pena de [PENA] de prisión en lugar de la impuesta de [COMPLETAR] de prisión, con suspensión de la ejecución de la pena que ya en este escrito se interesa.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al/a la apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental consistente en aportación de: [COMPLETAR].

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

SEGUNDOOTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el TSJ de [LOCALIDAD].

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta:

-Ante: el órgano judicial que dictó la resolución impugnada.

-En el plazo de 10 días a partir del siguiente al de la notificación de la sentencia.

Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento abreviado o que se denegaron indebidamente, si se formuló protesta, y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012, de 25 de enero, rec. 932/2011.

(2) Deben exponerse, de forma ordenada, las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(3) La defensa puede alegar como petición alternativa a la absolución bajar de 3 años a 1 año y 6 meses de prisión la pena por concurrir las circunstancias del párrafo 2º del art. 368 CP a las que la defensa puede apelar para conseguir una rebaja de la pena mínima de tres años del tipo penal que daría con el acusado en prisión por ser superior a dos años si no se aplica este párrafo 2º del art. 368 CP. Además, ello abriría la posibilidad de suspender la ejecución de la pena para estos casos aplicando el art. 80.5 CP.

================================================================================
