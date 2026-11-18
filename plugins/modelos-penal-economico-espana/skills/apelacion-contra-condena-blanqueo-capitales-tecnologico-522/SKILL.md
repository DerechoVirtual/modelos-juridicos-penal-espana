---
name: apelacion-contra-condena-blanqueo-capitales-tecnologico-522
description: "Redacta el escrito «Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática» (formulario 522 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática

> Formulario 0522 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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

- [ ] LUGARD
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO
- [ ] FECHA (5 veces)
- [ ] LUGAR (2 veces)
- [ ] EXPONER
- [ ] (EJ.:
- [ ] Nº
- [ ] NDICAR LA PRUEBA PROPUESTA Y DENEGADA
- [ ] EXPRESAR
- [ ] EN
- [ ] COMUNIDAD AUTÓNOMA
- [ ] ÓRGANO
- [ ] ORDINAL QUE CORRESPONDA (2 veces)
- [ ] ORDINAL QUE CORRESPONDAOTROSÍDIGO
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…/Dña. [NOMBRE Y APELLIDOS], Procurador/a»; «…e y representación del/de la condenado/a»; «…49.1 a) (LO 14/2022, BOE-A-2022-21800).]»; «…[COMPLETAR] ante la Sala»; «…tricta defensa, dentro del término legal»; «…Firma de Abogado/a Firma de Procurador/a»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que no se pudi…
- - D./Dña. [ORDINAL QUE CORRESPONDA].- Pericial: A cuyo fin deberá ser citado a través de la oficina judicial e…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) y 301 CP
- artículos 24.1 y 120.3 de la Constitución
- artículo 24.2 de la Constitución
- art. 24.2 CE
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 301 CP

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

### Formulario 0522 · Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 10 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la condena por delito de estafa informática y blanqueo de capitales del art. 249.1 a) y 301 CP, alegando que no ha quedado acreditada la autoría y solicitando que se practiquen más pruebas.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia. A la Audiencia Provincial de [LUGARD]./Dña. [NOMBRE Y APELLIDOS], Procurador/a [COMPLETAR], actuando en nombre y representación del/de la condenado/a [COMPLETAR] en el juicio oral número [NÚMERO] sobre delito del art. 249.1 a) y 301 CP [NOTA DE REVISIÓN: Errata en la cita: la estafa informática está en el art. 249.1 a) CP, como recoge el resto del escrito. Fuente: Código Penal, BOE-A-1995-25444, art. 249.1 a) (LO 14/2022, BOE-A-2022-21800).] [COMPLETAR] ante la Sala [COMPLETAR] comparezco y, como más procedente sea en derecho, DIGO:Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal [COMPLETAR] interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 846 ter 1 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial y para el TSJ de [LUGAR], en base a las siguientes,

ALEGACIONES PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución. [EXPONER] en qué consiste el defecto de motivación (por ausencia de la misma, por incongruencia, por irracional, etc.). [(EJ.:] El fundamento jurídico nº [Nº] de la sentencia apelada que aboca a la condena/absolución de..., adolece de una total falta de motivación, puesto que se limita a fundar su decisión en la mera afirmación de haber valorado la prueba documental, testifical y pericial, según las reglas de la sana crítica, de modo genérico, sin explicitar en qué ha consistido el resultado de tales pruebas en relación a la participación (o falta de participación)deen los hechos que se juzgan)SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución.

En fecha [FECHA], esta parte propuso como prueba [NDICAR LA PRUEBA PROPUESTA Y DENEGADA], que fue inadmitida por resolución de fecha [FECHA], reiterándose como cuestión previa su proposición al inicio del juicio, siendo denegada nuevamente en el acto, frente a lo que se formuló respetuosa y oportuna protesta.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 43/2003, 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso se cumplen cada uno de los requisitos anteriormente referidos, puesto que [EXPRESAR] cómo la prueba habría servido para desvirtuar el falloTERCERA.- Error en la apreciación de la pruebaLa resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se condena, ya que la cuenta corriente que se abrió se hizo por quien envió el correo electrónico y no por esta parte, ya que le solicitó el DNI para unas gestiones y, sin su conocimiento ni consentimiento, abrió la cuenta desde la que realizó la transacción. De hecho, no consta que desde el ordenador de mi mandante se haya llevado a cabo operación alguna.

Por otro lado, se condena por delito del art. 249.1 a) y 301 CP lo que supone una vulneración del non bis in ídem y prohibición de doble incriminación, ya que no puede ser sancionado por dos delitos ante un solo hecho objeto de acusación.

Señala el Tribunal Supremo, STS 637/2015 de 29 Oct. 2015, Rec. 10507/2015 que, en efecto, tal forma de concebir la prohibición constitucional de doble valoración de un mismo hecho, se aleja de su fundamento constitucional. El principio non bis in idem no es otra cosa que la expresión de la exigencia de que la pena sea siempre la medida de la culpabilidad. De ahí que un mismo hecho no pueda ser utilizado para una doble incriminación.

Se interesa, pues, la absolución, o en su defecto, la condena por un solo delito a la pena mínima de 6 meses de prisión con suspensión de la ejecución de la pena.CUARTA.- Infracción de normas del ordenamiento jurídico. [EN] este apartado se justificará la concurrencia o la ausencia de los requisitos del delito o de cualquier circunstancia excluyente o modificativa de la responsabilidad penal no apreciados por la sentencia recurridaEn su virtud,

SUPLICO A LA SALA:Que tenga por interpuesto, en tiempo y forma, RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita con sus copias y, que tras su tramitación, lo eleve a la SALA DE LO CIVIL Y PENAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [COMUNIDAD AUTÓNOMA] que dicte sentencia más ajustada a Derecho, por la que, estimando el recurso, revoque la sentencia de instancia.

Es justicia que pido en [LUGAR], día, mes, año

[OPCIONAL — incluir si procede]

PRIMER OTRO SÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas, que no se pudieron proponer en primera instanciase denegaron indebidamente habiéndose formulado protestano se practicaron por causas no imputables al apelante [ÓRGANO]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
- D./Dña. [ORDINAL QUE CORRESPONDA].- Pericial: A cuyo fin deberá ser citado a través de la oficina judicial el siguiente perito:- D./Dña. [ORDINAL QUE CORRESPONDA].- Documental consistente en aportación de:

SUPLICO A LA SALA: Que tenga por solicitadas las pruebas propuestas. [ORDINAL QUE CORRESPONDAOTROSÍDIGO]: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SALA: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a

Firma de Procurador/a [COMPLETAR] Los requisitos según la jurisprudencia para el delito de blanqueo son (SSTS 672/2016 de 21 Julio, rec. 552/2015, 928/2006, 5 de octubre, rec. 1255/2005, 154/2008, 8 de abril, rec. 1696/2007):1.- No se exige condena previa por el delito antecedente.2.- Se exige un dolo específico de la acción a sabiendas en cualquiera de las modalidades de acción de aprovechamiento u ocultación previstas en los apartados 1 y 2 del art. 301 CP.3.- La prueba de la actividad delictiva antecedente se puede probar por prueba indiciaria.

El autor del delito antecedente tecnológico puede serlo del delito de blanqueo de capitales con lo que se trata de "autoblanqueo tecnológico" (STS 265/2015 de 29 de Abril, rec. 10496/2014).

La estafa informática consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son: La manipulación informática y artificio semejante, transferencia patrimonial no consentida por el titular del mismo, ánimo de lucro, y perjuicio en tercero.
 Este recurso se presenta ante la Audiencia Provincial que dictó la resolución impugnada.
 Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.
 Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.
 Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012 de 25 de enero, Rec. 932/2011.

================================================================================
