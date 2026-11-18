---
name: renunciar-derecho-traductor-e-interprete-investigado-746
description: "Redacta el escrito «Renunciar al derecho a traductor e intérprete (investigado o acusado)» (formulario 746 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Renunciar al derecho a traductor e intérprete (investigado o acusado)

> Formulario 0746 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»; «…n. Preceptúa el artículo 126 LECRIM que:»; «…econocidos en los arts. 123 LECRIM y ss.»

## Elecciones que hay que hacer

- investigado/a / acusado/a
- la Sección / la Sala
- A LA SECCIÓN / A LA SALA
- del juicio oral / de las diligencias de investigación

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 126 de la LECRIM
- artículo 126 LECRIM
- art. 11 LO 5/2024
- arts. 123 LECRIM

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

### Formulario 0746 · Renunciar al derecho a traductor e intérprete (investigado o acusado)

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 4 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 15 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el investigado/acusado, renuncian al derecho a que se le designe un intérprete y/o traductor, una vez que ha recibido asesoramiento jurídico suficiente para conocer cuáles son las consecuencias de su renuncia, en base a los artículos 126 de la LECRIM.

Actualizado conforme a la LO 5/2024, del Derecho de Defensa, vigente desde el 4/12/2024

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD] Sección nº [NÚMERO]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], [ELEGIR: investigado/a / acusado/a] en el procedimiento nº [Nº DE PROCEDIMIENTO]/[AÑO] por el supuesto delito de [DELITO] del artículo [COMPLETAR] del CP, comparezco ante [ELEGIR: la Sección / la Sala] (1) y, como mejor proceda en derecho, DIGO:

Que por medio de la presente comunico que, tras haber recibido la notificación de la resolución de fecha [FECHA], en la que se nos daba traslado para que mi mandante ejerciera el derecho a ser asistido de intérprete y/o traductor, tras recibir asistencia letrada, renuncia a su designación.

Preceptúa el artículo 126 LECRIM que: [COMPLETAR]

"La renuncia a los derechos a que se refiere el artículo 123 deberá ser expresa y libre, y solamente será válida si se produce después de que el imputado o acusado haya recibido un asesoramiento jurídico suficiente y accesible que le permita tener conocimiento de las consecuencias de su renuncia. En todo caso, los derechos a los que se refieren las letras a) y c) del apartado 1 del artículo 123 no podrán ser renunciados."

Para que este derecho sea real y efectivo, no meramente ilusorio, el/la [ELEGIR: investigado/a / acusado/a] debe estar en condiciones de comprender todo lo que en el juicio o en la fase de instrucción se diga, por ello, si no comprende la lengua en que se desarrolla deberá estar asistido de intérprete, y este derecho se configura no como una mera formalidad, sino como un derecho íntimamente vinculado al derecho de defensa, conforme prevé el art. 11 LO 5/2024.

Sin embargo, mi defendido/a ya ha sido asesorado/a debidamente y desea renunciar expresamente al derecho de disponer de intérprete y/o traductor asumiendo, como señala el artículo 126 LECRIM, las consecuencias de esta decisión (2).

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]

que tenga por presentado este escrito, lo admita y se siga el trámite [ELEGIR: del juicio oral / de las diligencias de investigación] sin la asistencia de intérprete y/o traductor.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito se presentará:

- Ante la Sección de instrucción del Tribunal de Instancia si se renuncia a intérprete en la fase de investigación.
- En la sede de la Sección de lo Penal del Tribunal de Instancia o Sección Penal de la Audiencia Provincial, si se renuncia en fase de juicio oral.

(2) La consecuencia de esta decisión es que no podrá ampararse en los derechos reconocidos en los arts. 123 LECRIM y ss. [COMPLETAR], incluida la posibilidad de apelar a la nulidad del juicio por no entender el contenido de las preguntas o lectura de documentos.

================================================================================
