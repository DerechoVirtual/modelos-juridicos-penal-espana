---
name: transmision-reconocimiento-mutuo-ue-reforma-subsidiaria-589
description: "Redacta el escrito «Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de lo Penal)» (formulario 589 de cooperación penal internacional, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de lo Penal)

> Formulario 0589 del plugin **Cooperación penal internacional** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…as autoridades judiciales competentes de»; «…as autoridades judiciales competentes de»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 13 de la Ley 23/2014
- artículo 766.4 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0589 · Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de lo Penal)

- Año del modelo: 2018
- Revisión 17-11-2026: 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

Don/Dª [NOMBRE Y APELLIDOS], Procurador de los Tribunales, actuando en nombre y representación de Don/Dª [NOMBRE Y APELLIDOS], según consta en el apoderamiento que obra en autos, comparezco en el Procedimiento Abreviado nº [Nº DE PROCEDIMIENTO] que se tramita en ese órgano judicial y como mejor proceda en Derecho digo:

Que al amparo de lo establecido en los artículos 13 de la Ley 23/2014, de 20 de noviembre, de reconocimiento mutuo de resoluciones penales en la Unión Europea, así como el artículo 766.4 de la Ley de Enjuiciamiento Criminal, interpongo recursos de reforma y, subsidiario, de apelación contra el Auto de fecha [FECHA] dictado por el órgano judicial al que me dirijo, en el que se acordaba la transmisión del Auto/Sentencia de fecha [FECHA] a las autoridades judiciales competentes de [COMPLETAR] para su reconocimiento y posterior ejecución.

El recurso se basa en los siguientes motivos:

En su virtud, puede servirse el órgano judicial tener por hechas las manifestaciones contenidas en el presente escrito y en las copias que se acompañan, admitir a trámite el recurso interpuesto, dar traslado del mismo a las restantes partes y al Ministerio Fiscal y reformar la resolución impugnada en el sentido de no remitir el Auto/Sentencia de fecha [FECHA] para su ejecución por las autoridades judiciales competentes de [COMPLETAR], dándose al procedimiento el curso legal que corresponda.

OTROSÍ DIGO: En el supuesto de desestimación del recurso de reforma, esta parte interesa que se tenga por interpuesto en tiempo y forma recurso de apelación contra el Auto que declare no haber lugar a la reforma y, de conformidad con lo dispuesto en el artículo 766.4 de la Ley de Enjuiciamiento Criminal, se le dé traslado de las actuaciones por un plazo de cinco días para formular alegaciones y presentar, en su caso, los documentos justificativos de las pretensiones.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del Procurador	Firma del Abogado

================================================================================
