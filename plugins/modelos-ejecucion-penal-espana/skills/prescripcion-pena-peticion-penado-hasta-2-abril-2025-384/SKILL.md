---
name: prescripcion-pena-peticion-penado-hasta-2-abril-2025-384
description: "Redacta el escrito «Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025)» (formulario 384 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025)

> Formulario 0384 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] DELITO
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… representado/a a la pena menos grave de»

## Elecciones que hay que hacer

- al no haber sido recurrida / tras ser recurrida desestimando el recurso y notificándose a las partes

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 133 y 134 CP
- art. 988 bis LECRIM
- art. 133 CP
- art. 134.2 CP
- art. 75 CP
- art. 134 Código Penal
- art. 80 CP

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

### Formulario 0384 · Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025)

- Año del modelo: 2021
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 3 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el condenado a una pena privativa de libertad solicita que no se cumpla y se archive la ejecutoria penal por haber prescrito la pena, conforme a los arts. 133 y 134 CP.

Desde la LO 1/2025, que introduce el art. 988 bis LECRIM, vigente desde el 3 de abril de 2025, todas las solicitudes relativas a la ejecución de los pronunciamientos de la sentencia se efectúan en un mismo escrito, una vez se haya dado traslado del auto de incoación de la ejecutoria.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de ejercitando la representación de [NOMBRE DEL REPRESENTADO/A] en ejecutoria nº [Nº DE PROCEDIMIENTO], que se sigue en este juzgado dimanante de juicio oral nº Procedimiento nº [Nº DE PROCEDIMIENTO] por delito de [DELITO] ante el Tribunal comparezco y, como más procedente sea en derecho,

DIGO:

Que con fecha [FECHA] se dictó sentencia en el juicio oral nº [NÚMERO] por el que se condenó a mi representado/a a la pena menos grave de [COMPLETAR], entendiendo que a día de hoy la pena está prescrita.

La prescripción de la pena ex art. 133 CP es una causa de extinción de la responsabilidad penal. Entre los fundamentos de la prescripción de la pena se encuentra la falta de necesidad de la pena por el transcurso del tiempo, el derecho a la tutela judicial efectiva y el derecho a un proceso de ejecución sin dilaciones indebidas, por cuanto es necesario determinar el equilibrio entre la necesidad de ejecutar la pena y el derecho de la personada condenada a que no se produzcan dilaciones indebidas. De lo contrario, se prolonga el período estigmatizador que se extiende desde la imposición de la condena, hasta al menos, su cumplimiento y crea incertidumbre en los planes de vida de el/la condenado/a.

La figura de la prescripción de la pena tiene una justificación constitucional, como destaca la STC 63/2005, de 14 de marzo, al señalar que «el plazo de prescripción toma en consideración la función de la pena y la situación del presunto inculpado, su derecho a que no se dilate indebidamente la situación que supone la virtual amenaza de una sanción penal», convirtiéndose la seguridad jurídica en uno de los fundamentos clásicos de la institución. La prescripción de la pena, como afirma la STC 14/2016, de 1 de febrero, se sitúa temporalmente en el espacio posterior al efectivo enjuiciamiento de los hechos y a la declaración de responsabilidad criminal, por lo que en esta vertiente de la prescripción no se produce en sentido estricto una renuncia al ius puniendi, sino una renuncia a una ejecución tardía de la pena.

El cumplimiento de la pena es la única causa de interrupción del cómputo del plazo de prescripción y dos son las únicas suspensiones del plazo previstas por el legislador, tras la reforma operada por la LO 1/2015 (art. 134.2 CP): la suspensión de la pena y el cumplimiento sucesivo, de conformidad con el art. 75 CP.

Pues bien, dicho esto debemos señalar que con fecha [FECHA] se dictó auto de firmeza de la sentencia [ELEGIR: al no haber sido recurrida / tras ser recurrida desestimando el recurso y notificándose a las partes]. Sin embargo, han transcurrido ya [Nº] años desde la notificación del auto de firmeza que corresponde al plazo de prescripción de las penas menos graves en el art. 133 CP, y hay que recordar que el dies a quo para el cómputo de la prescripción de la pena comienza desde el instante de la firmeza de la sentencia (en el caso desde la última notificación a las partes que tuvo lugar el día [FECHA]) por así establecerlo expresamente el art. 134 Código Penal, deteniéndose (interrumpiéndose), en todo caso, tan pronto como se inicia su cumplimiento, es decir, con el inicio de la ejecución de la pena, pues sólo los actos de ejecución asociados al cumplimiento de las penas, «in natura» o sustitutivas, tienen relevancia para interrumpir la prescripción de las penas. Pero en este caso no ha habido ningún acto interruptivo del plazo de [Nº] años que determina el art. 133 CP para la condena que en este caso se ha dictado, por lo que ha prescrito la pena impuesta al no existir acto alguno interruptivo, ya que ni tan siquiera se inició el trámite de la suspensión de la ejecución de la pena, pudiendo haberse llevado a cabo al ser pena no superior a dos años de prisión (art. 80 CP, en relación con el art. 134.2 CP).

La paralización de la ejecutoria penal de modo evidente y patente y del examen de las actuaciones pone de manifiesto que la pena de prisión impuesta nunca comenzó a cumplirse.

Por ello, intereso se acepte la petición y se acuerde la declaración de la prescripción de la pena en los términos interesados.

Por todo ello,

SUPLICO AL TRIBUNAL:

Se admita el presente escrito y se tenga por declarada la prescripción de la pena y se proceda al archivo de la ejecutoria penal haciéndose previamente las anotaciones oportunas en los libros correspondientes.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma del Letrado/a	Firma de Procurador/a

================================================================================
