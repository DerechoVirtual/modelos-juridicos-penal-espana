---
name: pedir-presencia-fisica-interprete-defensa-investigado-744
description: "Redacta el escrito «Pedir la presencia física del intérprete (defensa del investigado o acusado)» (formulario 744 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la presencia física del intérprete (defensa del investigado o acusado)

> Formulario 0744 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NÚMERO
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»

## Elecciones que hay que hacer

- investigado/a / acusado/a
- la Sección / la Sala
- A LA SECCIÓN / A LA SALA
- el juicio oral / las diligencias de investigación

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Seleccionar en caso de que se solicite en fase de juicio oral)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 123 de la LECRIM
- artículo 11 LO 5/2024
- artículo 123.5 LECRIM
- artículo 123.1 LECRIM

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

### Formulario 0744 · Pedir la presencia física del intérprete (defensa del investigado o acusado)

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el investigado/a, en fase de instrucción, o el acusado/a, en fase de juicio oral, solicitan que el intérprete esté físicamente en la diligencia de que se trate, en vez de hacerlo por videoconferencia o por cualquier otro medio de telecomunicación, en base al artículo 123 de la LECRIM .

Actualizado conforme a la LO 5/2024, del Derecho de Defensa, vigente desde el 4/12/2024

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD] Sección nº [NÚMERO]

D./Dña. [NOMBRE Y APELLIDOS], Procurado/a de los Tribunales en representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], [ELEGIR: investigado/a / acusado/a] en el procedimiento nº [Nº DE PROCEDIMIENTO]/[AÑO] por el supuesto delito de [DELITO] del artículo [COMPLETAR] del CP, comparezco ante [ELEGIR: la Sección / la Sala] (1) y, como mejor proceda en derecho, DIGO:

Que mi defendido/a desconoce la lengua castellana e interesa el derecho de la asistencia de intérprete, conforme al artículo 11 LO 5/2024, del Derecho de Defensa, solicitando su presencia física, en base al artículo 123.5 LECRIM que señala que:

"La asistencia del intérprete se podrá prestar por medio de videoconferencia o cualquier medio de telecomunicación, salvo que el Tribunal o Juez o el Fiscal, de oficio o a instancia del interesado o de su defensa, acuerde la presencia física del intérprete para salvaguardar los derechos del imputado o acusado."

[OPCIONAL — incluir si procede]

(Seleccionar en caso de que se solicite en fase de juicio oral)

El artículo 123.1 LECRIM extiende el derecho a la interpretación a «todas las actuaciones del juicio oral». El ejercicio del derecho de defensa implica el derecho a estar presente en el propio juicio, salvo muy limitadas excepciones, así como el derecho a entender y ser entendido.

El acusado, con independencia de su nacionalidad, tiene derecho a la asistencia de intérprete en juicio oral en garantía de su derecho de defensa.

Para que este derecho sea real y efectivo, no meramente ilusorio, el acusado debe estar en condiciones de comprender todo lo que en el juicio se diga, por ello, si no comprende la lengua en que se desarrolla deberá estar asistido de intérprete, incluida la asistencia al acusado en su derecho a la última palabra, en un ordenamiento como el nuestro en el que este derecho se configura no como una mera formalidad, sino como un derecho íntimamente vinculado al derecho de defensa, ofreciendo al acusado la oportunidad final para confesar los hechos, ratificar o rectificar sus propias declaraciones o las de sus coimputados o testigos, o incluso discrepar de su defensa o completarla de alguna manera.

Se aplica al derecho solicitado el principio de que nadie pueda ser condenado sin ser oído, audiencia personal que, aun cuando mínima, ha de separarse como garantía de la asistencia letrada, dándole todo el valor que por sí misma le corresponde. La viva voz del acusado es un elemento personalísimo y esencial para su defensa en juicio.

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

que tenga por presentado este escrito, lo admita y tenga por realizado el trámite para interesar la asistencia física de intérprete en [ELEGIR: el juicio oral / las diligencias de investigación].

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito se presentará:

- Ante la Sección de instrucción del Tribunal de Instancia, si se requiere la presencia física de intérprete en la fase de investigación.
- En la sede de la Sección de lo Penal del Tribunal de Instancia o Sección Penal de la Audiencia Provincial, si se solicita en fase de juicio oral, con la antelación suficiente al inicio del mismo, a fin de que el juez o tribunal puedan disponer lo necesario.

================================================================================
