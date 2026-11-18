---
name: denegacion-traductor-interprete-reforma-defensa-742
description: "Redacta el escrito «Denegación de traductor o intérprete: reforma de la defensa del investigado» (formulario 742 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Denegación de traductor o intérprete: reforma de la defensa del investigado

> Formulario 0742 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] LUGAR

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 125.2 de la LECRIM
- artículo 125.2 LECRIM
- artículo 216 LECRIM
- artículo 11 LO 5/2024

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

### Formulario 0742 · Denegación de traductor o intérprete: reforma de la defensa del investigado

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el investigado/a, en fase de instrucción, presenta recurso de reforma contra el auto que deniega que se le designe un intérprete y/o traductor, en base al artículo 125.2 de la LECRIM.

Actualizado conforme a la LO 5/2024, del Derecho de Defensa, vigente desde el 4/12/2024

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en el Procedimiento abreviado nº [Nº DE PROCEDIMIENTO]/[AÑO] por el supuesto delito contra [ACTO O RESOLUCIÓN] comparezco ante este órgano judicial (1) y, como mejor proceda en derecho, DIGO:

Que por medio de la presente interpongo recurso de reforma contra la resolución de fecha [FECHA] (2) por la que se le deniega a mi defendido/a el derecho a repetir la declaración realizada en fecha [FECHA] en la que se le denegó la asistencia de intérprete para la traducción del documento que consta en las actuaciones al folio nº [NÚMERO] y ello con base en las siguientes

ALEGACIONES

ÚNICA.-

Se interpone este recurso en base a lo dispuesto en el artículo 125.2 LECRIM que dice:

"La decisión del Juez o Tribunal por la que se deniegue el derecho a la interpretación o a la traducción de algún documento o pasaje del mismo que la defensa considere esencial, o por la que se rechacen las quejas de la defensa con relación a la falta de calidad de la interpretación o de la traducción, será documentada por escrito.

Contra estas decisiones judiciales podrá interponerse recurso de conformidad con lo dispuesto en esta Ley."

Por su parte, el artículo 216 LECRIM señala que "Contra las resoluciones del Juez de instrucción podrán ejercitarse los recursos de reforma, apelación y queja."

Se hace constar que ya se advirtió con antelación el problema que tiene mi defendido/a con el conocimiento exacto de la lengua castellana, pese a lo cual no se le proveyó de intérprete y ante las preguntas del Fiscal en orden al reconocimiento del citado documento antes expuesto mi defendido no entendió bien su contenido y realizó una declaración errónea por no comprender lo que se le preguntaba y menos aún sobre el contenido de un documento que es esencial para la defensa.

El investigado, con independencia de su nacionalidad, tiene derecho a la asistencia de intérprete, conforme prevé el artículo 11 LO 5/2024, en garantía de su derecho de defensa.

Para que este derecho sea real y efectivo, no meramente ilusorio, el investigado debe estar en condiciones de comprender todo lo que en la fase de instrucción se diga. Por ello, si no comprende la lengua en que se desarrolla deberá estar asistido de intérprete, y este derecho se configura no como una mera formalidad, sino como un derecho íntimamente vinculado al derecho de defensa.

Por lo expuesto,

SUPLICO A LA SECCIÓN

que tenga por presentado este escrito y por interpuesto recurso de reforma contra la resolución de fecha [FECHA], lo admita y se vuelva a repetir la declaración anteriormente citada, proveyendo a mi defendido/a de intérprete de la lengua

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Si la decisión hubiera sido adoptada durante el juicio oral, la defensa del acusado podrá hacer constar en el acta su protesta al objeto de interesar en el recurso de apelación la nulidad del juicio.

(2) Puede presentarse escrito solicitando que se repita la diligencia llevada a cabo sin intérprete o traductor y, si se deniega, interponer recurso de reforma o presentar recurso de reforma directamente contra la resolución denegatoria de intérprete o traductor.

================================================================================
