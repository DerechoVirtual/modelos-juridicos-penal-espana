---
name: recurso-amparo-acuerdo-tc-15-marzo-2023-valido-hasta-14-70
description: "Redacta el escrito «Recurso de amparo (Acuerdo TC de 15 de marzo de 2023, válido hasta el 14 de septiembre de 2026)» (formulario 70 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Recurso de amparo (Acuerdo TC de 15 de marzo de 2023, válido hasta el 14 de septiembre de 2026)

> Formulario 0070 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- El Acuerdo del Pleno del TC de 15-3-2023 (BOE-A-2023-7531) no fija fecha final de vigencia y no se ha localizado en el BOE otro posterior que lo sustituya; la indicación del título «válido hasta el 14 de septiembre de 2026» no tiene respaldo en esa publicación. El Acuerdo exige presentar el amparo por la sede electrónica con formulario y limita la demanda a 50.000 caracteres (reglas primera, segunda y cuarta).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº (8 veces)
- [ ] FECHA (9 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] NÚMERO
- [ ] SEDE (2 veces)
- [ ] DELITO
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…DEMANDANTES:»; «… de fecha [FECHA], dictada en el recurso»; «…e su ex pareja Dª. y de su hijo menor D.»; «…uncia, los hechos fueron los siguientes:»; «…estificales se estiman importantes, pues»; «… de fecha [FECHA], dictada en el recurso»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 24.2 CE

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

### Formulario 0070 · Recurso de amparo (Acuerdo TC de 15 de marzo de 2023, válido hasta el 14 de septiembre de 2026)

- Año del modelo: 2024
- Revisión 17-11-2026: 29 campos de relleno marcados en blanco
- Avisos de la revisión: El Acuerdo del Pleno del TC de 15-3-2023 (BOE-A-2023-7531) no fija fecha final de vigencia y no se ha localizado en el BOE otro posterior que lo sustituya; la indicación del título «válido hasta el 14 de septiembre de 2026» no tiene respaldo en esa publicación. El Acuerdo exige presentar el amparo por la sede electrónica con formulario y limita la demanda a 50.000 caracteres (reglas primera, segunda y cuarta).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

DEMANDANTES: [COMPLETAR].

RESOLUCIÓN O RESOLUCIONES RECURRIDAS: Sentencia del Tribunal Supremo núm. [Nº] de fecha [FECHA], contra la cual se dirige esta demanda. Se interpuso el recurso de casación contra la Sentencia de la Audiencia Provincial de [LOCALIDAD], de fecha [FECHA], dictada en el recurso [COMPLETAR], que desestimó el recurso de apelación interpuesto contra la Sentencia de la Sección de lo Penal del Tribunal de Instancia de plaza núm. [Nº] de fecha [FECHA].

MEDIDA CAUTELAR: se solicita la suspensión de la ejecución de la pena de [Nº] años de prisión impuesta al acusado, más las accesorias, en la Sentencia de la Sección de lo Penal del Tribunal de Instancia de plaza núm. [Nº] de fecha [FECHA].

HECHOS O ANTECEDENTES PROCESALES: (máximo 6.000 caracteres con espacios): mi representado fue denunciado/a por delito de maltrato físico habitual cometido contra la persona de su ex pareja Dª. y de su hijo menor D. [COMPLETAR], de tres años de edad, dando lugar a las diligencias previas núm. tramitadas por la Sección de Instrucción del Tribunal de Instancia de plaza núm. [NÚMERO].

Según la denuncia, los hechos fueron los siguientes: [COMPLETAR].

Tras incoarse diligencias previas, se practicaron como únicas diligencias de instrucción la declaración de la denunciante y del investigado, y reconocimiento médico forense, tras lo cual se dictó Auto de transformación de procedimiento abreviado, formulando acusación el Ministerio Fiscal y la acusación particular ejercida por su ex pareja. La decisión de incoación de procedimiento abreviado fue recurrida en reforma y apelación por mi representado, que solicitó la práctica de diligencias complementarias de investigación, entre ellas, la testifical de varios amigos de la pareja y vecinos del inmueble donde residían, que fueron denegadas, siendo objeto de recurso por mi representado. Los recursos fueron desestimados.

El Ministerio Fiscal y la acusación particular propusieron como prueba el interrogatorio de la denunciante, pericial médica y la testifical de la madre de la denunciante.

Por su parte, mi representado solicitó como prueba para el juicio oral, además de la propuesta por las acusaciones, la testifical de seis personas, amigos de la pareja y vecinos del inmueble donde residían, así como prueba pericial psicológica para que fueran reconocidos la denunciante y el hijo menor.

La Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº admitió, para su práctica en el juicio oral, la prueba propuesta por las acusaciones, denegando la propuesta por mi representado. Mi representado recurrió la denegación de prueba y reprodujo su pretensión en el acto del juicio oral, formulando protesta.

En el acto del juicio oral, mi representado negó la existencia de cualquier tipo de maltrato, practicándose seguidamente el interrogatorio de la denunciante y de su madre. La denunciante se ratificó en su denuncia e introdujo hechos que no habían sido relatados en la misma ni en la fase de instrucción, tales como que el acusado le zarandeó ya en varias ocasiones cuando estaba embarazada le agredió estrellando el pico de la mesa de planchar contra el lateral de su cuerpo, lo que le obligó a ir al hospital en consideración a su estado de gestación y que quince días antes de interponer la denuncia había propinado una paliza a la denunciante y al hijo menor de tres años, quien sufrió patadas en la espalda, manifestando haber llevado al hijo a urgencias para que le atendieran de sus lesiones. La madre de la denunciante, tras reconocer su mala relación con mi representado, se limitó a afirmar los hechos por referencias de su hija. Finalmente, el médico forense no objetivó lesiones ni en la denunciante ni en el hijo común.

El Juez consideró suficiente esta declaración única de la víctima para formar convicción, junto a las demás pruebas de referencia, sucintamente descritas, entendiendo que quedaba enervada la presunción de inocencia.

Se dictó Sentencia en la que se condenaba a mi representado a la pena de [Nº] años de prisión como autor de un delito de [DELITO].

La sentencia condenatoria fue recurrida en apelación por mi representado alegando, entre otros motivos, vulneración de los derechos constitucionales del art. 24.2 CE, a la presunción de inocencia y a un proceso con todas las garantías, en la vertiente del derecho a la prueba, que fue desestimado por Sentencia de la Audiencia Provincial de fecha [FECHA]. Contra esta Sentencia, mi representado interpuso recurso de casación por infracción de Ley, que fue desestimado por la Sentencia del Tribunal Supremo núm. [Nº] de fecha [FECHA], contra la cual se dirige esta demanda.

VULNERACIÓN DE DERECHOS FUNDAMENTALES(máximo 6.000 caracteres con espacios): mi representado ha visto vulnerado su derecho a la presunción de inocencia y a utilizar los medios de prueba pertinentes en su defensa, puesto que la condena se fundó exclusivamente en la declaración de la víctima, en una declaración manifiestamente insuficiente como prueba de cargo, donde, además, no se respetaron sus derechos mínimos de defensa, puesto que no pudo proponer prueba en su descargo, lesionando los derechos constitucionales de mi representado del art. 24.2 CE. Dicha declaración de la víctima tiene un móvil espurio, dado que existencia conflictos personales intensos sobre la guarda y custodia del hijo común y de naturaleza económica. Tampoco es persistente, pues introduce elementos nuevos en el plenario sobre agresiones en el periodo de embarazo o palizas al hijo común, que no figuraban en la denuncia ni en su declaración instructora. Y está ausente de corroboración, pues no se ha aportado ni un solo parte de atención médica de las supuestas lesiones.

Por otro lado, se denegó en la instancia la testifical de varios amigos de la pareja y vecinos del inmueble donde residían, que fueron denegadas, tanto como diligencia de investigación como medio de prueba a practicar en el juicio oral. Dichas testificales se estiman importantes, pues [COMPLETAR].

CUESTIÓN DE ESPECIAL TRASCENDENCIA CONSTITUCIONAL(máximo 4.000 caracteres con espacios): considera esta parte que la aplicación de la jurisprudencia sobre el valor probatorio de las declaraciones de la víctima no ha sido la correcta, con vulneración de la presunción de inocencia, por lo que tanto el juzgador de instancia, como el de apelación, como el de casación, han incurrido en una negativa manifiesta del deber de acatamiento de la doctrina de este Tribunal. Consideramos que la condena pese el incumplimiento de los requisitos jurisprudencialmente establecidos para la declaración de la víctima, prueba no corroborada, tiene una trascendencia superior al caso en concreto, pues supondría la aceptación de una doctrina contraria a la mantenida por el TS y el TC.

Y, asimismo, la denegación de las pruebas debidamente propuestas ha supuesto una merma del derecho de defensa. Tanto la Sección de lo Penal del Tribunal de Instancia, como la Audiencia Provincial y el TS, han prejuzgado la falta de trascendencia de las testificales propuestas, cuando, en realidad, hubiesen contradicho la versión de la denunciante, puesto que, según se narra en la propia denuncia, los hechos, al producirse en el ámbito doméstico, hubiesen debido ser advertido por los vecinos y causado una afectación de la relación sentimental apreciable por el entorno de las amistades. Al no aceptarse estas testificales, que, quizás hubiesen sido un elemento corroborador de las declaraciones de la víctima, se deja a esta declaración como único medio de prueba, por lo que se reitera lo anteriormente dicho: la insuficiencia de la declaración de la víctima como medio de prueba único, en el caso de que no se cumplan los requisitos establecidos por la jurisprudencia para ser tenida como prueba de cargo.

AGOTAMIENTO DE LA VÍA JUDICIAL PREVIA(máximo 4.000 caracteres con espacios): se adjunta con la demanda la Sentencia de la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza núm. [Nº], de fecha [FECHA], así como la Sentencia de apelación de la Sentencia de la Audiencia Provincial de [LOCALIDAD], de fecha [FECHA], dictada en el recurso [COMPLETAR].

Finalmente, se aporta Sentencia del Tribunal Supremo núm. [Nº] de fecha [FECHA].

De esta forma, y tras este iter procesal, la vía previa se entiende agotada al haberse utilizado todos los medios procesales de impugnación, conforme al art. 44 de la LOTC.

================================================================================
