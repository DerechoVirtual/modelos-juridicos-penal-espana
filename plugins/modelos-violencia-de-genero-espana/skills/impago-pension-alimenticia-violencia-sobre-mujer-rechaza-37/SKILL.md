---
name: impago-pension-alimenticia-violencia-sobre-mujer-rechaza-37
description: "Redacta el escrito «Impago de pensión alimenticia: Violencia sobre la Mujer rechaza la inhibición de Instrucción (auto)» (formulario 37 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impago de pensión alimenticia: Violencia sobre la Mujer rechaza la inhibición de Instrucción (auto)

> Formulario 0037 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] Nº
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] SEDE
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… muchas, STS 557/2020, de 29 de octubre)»; «…Firma del/de la Magistrado/a Juez/a:»

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

### Formulario 0037 · Impago de pensión alimenticia: Violencia sobre la Mujer rechaza la inhibición de Instrucción (auto)

- Año del modelo: 2025
- Revisión 17-11-2026: 5 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº)
- Nota explicativa incorporada desde la colección Procesal (formulario 15) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución por la que una Sección de Violencia sobre la Mujer rechaza la inhibición de una Sección de Instrucción por delito de impago de pensión alimenticia al considerar que no es de su competencia. Modelo basado en el que los integrantes del grupo de expertos y expertas del Observatorio contra la Violencia Doméstica y de Género del CGPJ destinados en órganos unipersonales ponen a disposición de la carrera judicial.

---

AUTO

En [LUGAR], a [FECHA].

ANTECEDENTES DE HECHO

ÚNICO.- Por la Sección de Instrucción núm. [Nº] se incoaron Diligencias Previas nº [Nº DE PROCEDIMIENTO] acordando el referido órgano judicial inhibirse del conocimiento de dichas diligencias en favor de este órgano especializado.

FUNDAMENTOS JURÍDICOS

ÚNICO.- Interpuesta denuncia por impago de pensión alimenticia, considera la Sección de Instrucción que la competencia objetiva para conocer de dicha denuncia corresponde a la Sección de Violencia Sobre la Mujer.

Tal y como señala el órgano que se inhibe, dispone el art 89.5 de la LOPJ, en la redacción dada por la LO 1/2025, que:

"Las Secciones de Violencia sobre la Mujer conocerán, en el orden penal, de conformidad en todo caso con los procedimientos y recursos previstos en la Ley de Enjuiciamiento Criminal, de los siguientes supuestos:

a) De la instrucción de los procesos para exigir responsabilidad penal por los delitos recogidos en los Títulos del Código Penal relativos a homicidio, aborto, lesiones, lesiones al feto, delitos contra la libertad, delitos contra la integridad moral, contra la libertad e indemnidad sexual, contra la intimidad y el derecho a la propia imagen, contra el honor o cualquier otro delito cometido con violencia o intimidación, siempre que se hubiesen cometido contra quien sea o haya sido su esposa o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género.
b) De la instrucción de los procesos para exigir responsabilidad penal por cualquier delito contra las relaciones familiares, cuando la víctima sea alguna de las personas señaladas en la letra anterior."

Aun cuando de la pura literalidad de este apartado b), interpretado aisladamente, pudiera dar lugar a entender que siempre que alguno de estos delitos tenga como sujeto pasivo a la mujer o a los descendientes, menores o personas con discapacidad mencionadas en el apartado a), las Secciones de Violencia sobre la Mujer son competentes para conocer de los mismos, es necesario precisar que para que ello acontezca, debe concurrir de manera simultánea el requisito de ese apartado a), esto es, que el delito se haya cometido contra quien sea o haya sido su esposa o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género.

En el caso del delito de impago de pensiones alimenticias, el sujeto pasivo del delito no es la mujer, sino los y las hijas comunes a cuyo favor se ha establecido la pensión de alimentos, que son los beneficiarios de la misma, por más que la madre actué como representante legal y perceptora material del pago, y el bien jurídico protegido en este delito es el derecho de los alimentos de los hijos, y no los intereses patrimoniales del progenitor/a custodio (vid, entre otras muchas, STS 557/2020, de 29 de octubre) [COMPLETAR]. Y prueba de ello es que de manera expresa en el art 89 bis 5 b) de la LOPJ, sobre la competencia de las Secciones de Violencia contra la Infancia y la Adolescencia, se establece que las mismas conocerán, en el ámbito penal, de la instrucción de los procesos para exigir responsabilidad penal por los "delitos contra las relaciones familiares ... cuando la víctima sea niño, niña o adolescente".

En atención a dicho criterio, procede rechazar la inhibición causada por la Sección de Instrucción, en favor de esta Sección de Violencia sobre la Mujer, devolviéndose las actuaciones al órgano judicial remitente.

PARTE DISPOSITIVA

Se acuerda RECHAZAR LA INHIBICIÓN EN FAVOR DE ESTA SECCIÓN acordada por la Sección de Instrucción núm. [NÚMERO].

Notifíquese esta resolución al MINISTERIO FISCAL y en su caso, demás partes personadas.

Esta resolución no es firme y frente a ella cabe recurso de reforma ante este órgano judicial, que ha de interponerse en el plazo de TRES DIAS.

Ilmo./a. Sr/a. Magistrado/a Juez/a de [SEDE]

Firma del/de la Magistrado/a Juez/a: [COMPLETAR]

================================================================================
