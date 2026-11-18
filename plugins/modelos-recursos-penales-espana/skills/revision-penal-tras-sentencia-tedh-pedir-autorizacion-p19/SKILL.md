---
name: revision-penal-tras-sentencia-tedh-pedir-autorizacion-p19
description: "Redacta el escrito «Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir» (formulario 19 (Procesal) de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir

> Formulario 0019 de la colección de Procesal del plugin **Recursos penales** · revisado el 17-11-2026.

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

- La solicitud de autorización se formula en el plazo de un año desde la firmeza de la sentencia del TEDH, y solo por quien fue demandante ante él (art. 954.3, párrafo 2, LECrim).
- Trámite (art. 957 LECrim): audiencia del Ministerio Fiscal, diligencias facultativas de la Sala y auto irrecurrible. Autorizado el recurso, hay quince días para interponerlo.
- Debe razonarse que los efectos de la violación persisten y no pueden cesar de otro modo (art. 954.3 LECrim; art. 5 bis LOPJ).
- Traslado a la Abogacía General del Estado desde el 20-3-2024 (art. 954.3, párrafos 3 y 4, RDL 6/2023).
- Datos del órgano de origen: la plaza de la Sección de Instrucción conserva el número del antiguo Juzgado (DT 1.ª LO 1/2025). La apelación contra sentencias de la Audiencia Provincial va al TSJ (art. 846 ter LECrim).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO (4 veces)
- [ ] Nº DE DOCUMENTO
- [ ] SEDE
- [ ] LOCALIDAD
- [ ] FECHA (3 veces)
- [ ] ÓRGANO O PERSONA
- [ ] DELITO
- [ ] PENA
- [ ] Nº DE RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ue se ha dictado sentencia por el TSJ de»; «…, actualmente preso/a en la Prisión de»; «…ue: Que señala el art. 954.3 LECRIM que:»; «…hos humanos en el procedimiento judicial»; «…ón que se postule con la consecuencia de»

## Elecciones que hay que hacer

- autor / cómplice

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 954.3 LECRIM
- artículo 5 bis LOPJ
- art. 954.3 LECRIM
- artículo 954 LECrim
- art. 954 LECRIM
- art. 954.4 LECrim
- art. 954 LECr
- Ley 41/2015
- Real Decreto-ley 6/2023

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

### Formulario 0019 · Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir

- Año del modelo: 2025
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 desplegables y casillas convertidos en elección en blanco; 21 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 2 cita(s) o dato(s) corregidos tras comprobarlos en el BOE; 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Avisos de la revisión: La solicitud de autorización se formula en el plazo de un año desde la firmeza de la sentencia del TEDH, y solo por quien fue demandante ante él (art. 954.3, párrafo 2, LECrim). · Trámite (art. 957 LECrim): audiencia del Ministerio Fiscal, diligencias facultativas de la Sala y auto irrecurrible. Autorizado el recurso, hay quince días para interponerlo. · Debe razonarse que los efectos de la violación persisten y no pueden cesar de otro modo (art. 954.3 LECrim; art. 5 bis LOPJ). · Traslado a la Abogacía General del Estado desde el 20-3-2024 (art. 954.3, párrafos 3 y 4, RDL 6/2023). · Datos del órgano de origen: la plaza de la Sección de Instrucción conserva el número del antiguo Juzgado (DT 1.ª LO 1/2025). La apelación contra sentencias de la Audiencia Provincial va al TSJ (art. 846 ter LECrim).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Modelo de escrito dirigido a la Sala Segunda del Tribunal Supremo promoviendo recurso de revisión de una sentencia penal, conforme al artículo 954.3 LECRIM y al artículo 5 bis LOPJ, como consecuencia de un pronunciamiento del Tribunal Europeo de Derechos Humanos que haya declarado que una resolución judicial ha sido dictada en violación de alguno de los derechos reconocidos en el Convenio Europeo para la Protección de los Derechos y Libertades Fundamentales.

A la Sala Segunda del Tribunal Supremo

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], como consta en escritura de poder inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme, acompañando certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada, en la causa número [NÚMERO], seguida por la Sección de Instrucción plaza número [NÚMERO] del Tribunal de Instancia de [SEDE], procedente de la Audiencia Provincial de [LOCALIDAD] y sobre la que se ha dictado sentencia por el TSJ de [COMPLETAR] con fecha [FECHA] y por el TS nº [NÚMERO], tras lo que mi representado/a acudió al TEDH, comparezco ante este órgano judicial y, como mejor proceda en derecho,

DIGO:

Que por sentencia de fecha [FECHA], que es firme, dictada por [ÓRGANO O PERSONA] en el rollo anteriormente citado, mi representado/a D./Dña. [NOMBRE Y APELLIDOS], actualmente preso/a en la Prisión de [COMPLETAR], fue condenado/a como [ELEGIR: autor / cómplice] de un delito de [DELITO], a la pena de [PENA]. Acudió al TEDH quien ha dictado la sentencia nº [Nº DE RESOLUCIÓN] de fecha [FECHA] por la que se declara que:

Que señala el art. 954.3 LECRIM que: [COMPLETAR]

"3. Se podrá solicitar la revisión de una resolución judicial firme cuando el Tribunal Europeo de Derechos Humanos haya declarado que dicha resolución fue dictada en violación de alguno de los derechos reconocidos en el Convenio Europeo para la Protección de los Derechos Humanos y libertades Fundamentales y sus Protocolos, siempre que la violación, por su naturaleza y gravedad, entrañe efectos que persistan y no puedan cesar de ningún otro modo que no sea mediante esta revisión.

En este supuesto, la revisión solo podrá ser solicitada por quien, estando legitimado para interponer este recurso, hubiera sido demandante ante el Tribunal Europeo de Derechos Humanos. La solicitud deberá formularse en el plazo de un año desde que adquiera firmeza la sentencia del referido Tribunal." (1) [NOTA DE REVISIÓN: Igual que en el Procesal 18: la cita omite los dos párrafos añadidos al art. 954.3 por el RDL 6/2023 (traslado a la Abogacía General del Estado, en vigor desde el 20-3-2024). Fuente: LECrim, art. 954.3 (RDL 6/2023, BOE-A-2023-25758, art. 101.10).]

Hay que recordar que la sentencia del TEDH, que se aporta como documento nº 1 a la presente, no acuerda la nulidad o la revocación de la sentencia que fue objeto de recurso ante el TEDH, sino que se limita a declarar la vulneración de un derecho reconocido en el Convenio por lo que se hace preciso este trámite ex art. 954.3 LECRIM.

Por ello, se ha producido la vulneración del Convenio Europeo de derechos humanos en el procedimiento judicial [COMPLETAR].

Del contenido de la sentencia del TEDH se evidencia la necesidad de proceder a la autorización de la revisión de la citada sentencia y, previos los trámites oportunos dar lugar a la estimación de la revisión que se postule con la consecuencia de [COMPLETAR].

Sin perjuicio de cuantas diligencias de comprobación se acuerden posteriormente por la Excma. Sala Segunda del Tribunal Supremo en la instrucción supletoria que al efecto se ordene formar, con este escrito acompaño los siguientes documentos:

Por todo ello, conforme a lo dispuesto en el artículo 954 LECrim., número 3 y en el artículo 5 bis LOPJ,

SUPLICO A LA SALA:

Que tenga por promovida esta solicitud motivada de autorización de revisión de la aludida sentencia, y que, previa la práctica de las diligencias procedentes, si estima oportuna tal práctica, y previa audiencia del Ministerio Fiscal, autorice la interposición del pertinente recurso de revisión, en el plazo de 15 días que legalmente se establece.

Es Justicia que pido en [LUGAR].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Esta opción del art. 954.3 LECRIM fue instaurada como un nuevo motivo del recurso de revisión con la reforma operada por la Ley 41/2015 de modificación de la Ley de Enjuiciamiento Criminal a fin de establecer un medio para la ejecución de las sentencias del Tribunal de Estrasburgo. Fue modificada por el Real Decreto-ley 6/2023, de 19 de diciembre que señala al respecto en su Exposición de motivos que: "Asimismo se introduce una modificación normativa en las distintas leyes procesales para permitir a la Abogacía General del Estado tener conocimiento y colaborar con los órganos judiciales en los procedimientos de revisión de sentencias que se sigan ante el Tribunal Supremo como consecuencia de los pronunciamientos del Tribunal Europeo de Derechos Humanos que hayan declarado que una resolución judicial ha sido dictada en violación de alguno de los derechos reconocidos en el Convenio Europeo para la Protección de los Derechos y Libertades Fundamentales; y ello con la finalidad de que, por una parte, la Abogacía General del Estado, pueda, en el ejercicio de sus funciones de Agente del Reino de España ante el Tribunal Europeo de Derechos Humanos, informar al Comité de Ministros del Consejo de Europa de las medidas adoptadas en ejecución de las sentencias del citado Tribunal, y, por otra parte, facilitar a los órganos jurisdiccionales su tarea de dar debida consideración a lo que pueda demandar la ejecución de dichas sentencias de condena"

Hasta la introducción del apartado 3 del art. 954 LECRIM se estaba dirigiendo esta opción ante sentencias del TEDH al cajón de sastre que constituía el derogado art. 954.4 LECrim. [NOTA DE REVISIÓN (comprobar): El art. 954 vigente no tiene apartado 4; el antiguo «cajón de sastre» de los hechos nuevos corresponde hoy al art. 954.1.d). Fuente: LECrim, art. 954 vigente; Ley 41/2015 (BOE-A-2015-10726).], hasta el punto de que en el Pleno no Jurisdiccional de la Sala de 21 de Octubre de 2014 adoptó el siguiente Acuerdo: "En tanto no exista en el Ordenamiento Jurídico una expresa previsión legal para la efectividad de las sentencias dictadas por el TEDH que aprecien la violación de derechos fundamentales de un condenado por los Tribunales Españoles, el recurso de revisión del art. 954 LECr cumple este cometido...".

================================================================================
