---
name: delito-sexual-procesos-previos-3-10-2025-violencia-sobre-34
description: "Redacta el escrito «Delito sexual (procesos previos al 3/10/2025): Violencia sobre la Mujer rechaza la inhibición (auto)» (formulario 34 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito sexual (procesos previos al 3/10/2025): Violencia sobre la Mujer rechaza la inhibición (auto)

> Formulario 0034 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- La LO 1/2025 entró en vigor, con carácter general, el 3-4-2025. El 3-10-2025 es solo la fecha en que la Sección de Violencia sobre la Mujer asumió la violencia sexual (DF 38ª.3). La DT 4ª fija el corte por la fecha de incoación del procedimiento, no por la fecha de comisión de los hechos: la Sección asume esas competencias «respecto de los procedimientos incoados a partir de esa fecha». Conviene apoyar el rechazo de la inhibición en esa transitoria.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] Nº
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] SEDE
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…DICOS PRIMERO.- Interpuesta denuncia por»; «…Firma del/de la Magistrado/a Juez/a:»; «…l/de la Magistrado/a Juez/a: [COMPLETAR]»

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0034 · Delito sexual (procesos previos al 3/10/2025): Violencia sobre la Mujer rechaza la inhibición (auto)

- Año del modelo: 2025
- Revisión 17-11-2026: 7 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº)
- Nota explicativa incorporada desde la colección Procesal (formulario 12) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución de una Sección de Violencia sobre la Mujer por la que rechaza la inhibición de una Sección de instrucción en un delito contra la libertad sexual, al tratarse de hechos cometidos antes del 3 de octubre de 2025, fecha de entrada en vigor de la reforma del art. 89.5 h) LOPJ hecha por la LO 1/2025 (DF 38ª.3) atribuyendo la competencia para estos delitos a la Sección de Violencia sobre la Mujer. Modelo basado en el que los integrantes del grupo de expertos y expertas del Observatorio contra la Violencia Doméstica y de Género del CGPJ destinados en órganos unipersonales ponen a disposición de la carrera judicial.

---

AUTO

En [LUGAR], a [FECHA].

ANTECEDENTES DE HECHO

ÚNICO.-

Por la Sección de Instrucción núm. [Nº] se incoaron Diligencias Previas nº [Nº DE PROCEDIMIENTO] acordando el referido órgano judicial inhibirse del conocimiento de dichas diligencias en favor de este órgano judicial especializado.

FUNDAMENTOS JURÍDICOS

PRIMERO.- Interpuesta denuncia por [COMPLETAR], considera la Sección de Instrucción que la competencia objetiva para conocer de dicha denuncia corresponde a la Sección de Violencia Sobre la Mujer.

Tal y como señala el órgano que se inhibe, el art 89.5 de la LOPJ, en la redacción dada por la LO 1/2025, dispone que:

"Las Secciones de Violencia sobre la Mujer conocerán, en el orden penal, de conformidad en todo caso con los procedimientos y recursos previstos en la Ley de Enjuiciamiento Criminal, de los siguientes supuestos:

h) De la instrucción de los procesos para exigir responsabilidad penal por los delitos contra la libertad sexual previstos en el título VIII del libro II del Código Penal, por los delitos de mutilación genital femenina, matrimonio forzado, acoso con connotación sexual y la trata con fines de explotación sexual cuando la persona ofendida por el delito sea mujer."

Se trata esta de una nueva competencia no prevista en la LO 1/2004, norma que en su art 1.1 limita el ámbito del sujeto activo del delito a la persona con la que la mujer tenga o haya tenido una relación matrimonial, o análoga relación de afectividad.

Ahora bien, teniendo en cuenta que se trata de un procedimiento incoado con anterioridad al 3 de octubre de 2025, resulta de aplicación la Disposición Transitoria 9ª de la LO 1/2025, que expresamente señala que las previsiones recogidas en la ley "serán aplicables exclusivamente a los procedimientos incoados con posterioridad a su entrada en vigor".

SEGUNDO.- En el presente caso, constando como fecha de incoación/registro del presente procedimiento el día [FECHA], entendemos que la Sección de Violencia sobre la Mujer no es competente para conocer del procedimiento cuya inhibición ha sido acordada por la Sección de Instrucción. Por todo lo expuesto, procede rechazar la inhibición causada, devolviéndose las actuaciones a la Sección remitente.

PARTE DISPOSITIVA

Se acuerda RECHAZAR LA INHIBICION EN FAVOR DE ESTA SECCIÓN acordada por la Sección de Instrucción núm. [NÚMERO].

Notifíquese esta resolución al MINISTERIO FISCAL y en su caso, demás partes personadas.

Esta resolución no es firme y frente a ella cabe recurso de reforma ante este órgano judicial, que ha de interponerse en el plazo de TRES DIAS.

Ilmo./a. Sr/a. Magistrado/a Juez/a de [SEDE]

Firma del/de la Magistrado/a Juez/a: [COMPLETAR]

[COMPLETAR]

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: La LO 1/2025 entró en vigor, con carácter general, el 3-4-2025. El 3-10-2025 es solo la fecha en que la Sección de Violencia sobre la Mujer asumió la violencia sexual (DF 38ª.3). La DT 4ª fija el corte por la fecha de incoación del procedimiento, no por la fecha de comisión de los hechos: la Sección asume esas competencias «respecto de los procedimientos incoados a partir de esa fecha». Conviene apoyar el rechazo de la inhibición en esa transitoria.]
