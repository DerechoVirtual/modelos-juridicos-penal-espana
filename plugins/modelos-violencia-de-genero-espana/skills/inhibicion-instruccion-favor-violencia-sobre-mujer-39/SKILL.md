---
name: inhibicion-instruccion-favor-violencia-sobre-mujer-39
description: "Redacta el escrito «Inhibición de Instrucción a favor de Violencia sobre la Mujer del domicilio de la víctima: auto» (formulario 39 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Inhibición de Instrucción a favor de Violencia sobre la Mujer del domicilio de la víctima: auto

> Formulario 0039 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- La Sección de Violencia sobre la Mujer solo es competente para la trata cuando es con fines de explotación sexual y la víctima es mujer (art. 89.5 h) LOPJ y art. 14.5 h) LECrim), y solo en los procedimientos incoados desde el 3-10-2025 (DF 38ª.3 y DT 4ª LO 1/2025). Si la víctima es menor, hay que tener en cuenta también el art. 89 bis.5 c) y 7 LOPJ.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] SEDE (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…norma general del fórum delicti comissi"»; «…inado el domicilio de la/s víctima/ s en»; «…Firma del/de la Magistrado/a Juez/a:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 774 de la Ley de Enjuiciamiento Criminal
- artículo 15 bis de la LECrim
- Ley Orgánica 1/2004

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

### Formulario 0039 · Inhibición de Instrucción a favor de Violencia sobre la Mujer del domicilio de la víctima: auto

- Año del modelo: 2025
- Revisión 17-11-2026: 7 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 menciones a juzgados penales actualizadas (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 17) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución por la que una Sección de Instrucción se inhibe a favor de una Sección de Violencia sobre la Mujer del Tribunal de Instancia del lugar del domicilio de la víctima en el momento de los hechos que presentan los caracteres de un delito de trata de seres humanos. Modelo basado en el que los integrantes del grupo de expertos y expertas del Observatorio contra la Violencia Doméstica y de Género del CGPJ destinados en órganos unipersonales ponen a disposición de la carrera judicial.

---

AUTO

En [LUGAR], a [FECHA].

ANTECEDENTES DE HECHO

ÚNICO.- Se ha recibido en este órgano judicial atestado que antecede.

FUNDAMENTOS DE DERECHO

PRIMERO.- Las actuaciones recibidas deben incoarse como diligencias previas a tenor de lo dispuesto en el artículo 774 de la Ley de Enjuiciamiento Criminal (LECr), puesto que hacen referencia a la posible existencia de un delito de trata de seres humanos que, en todo caso, estaría comprendido en el ámbito del procedimiento abreviado.

SEGUNDO.- Dispone el art 15 bis de la Ley de Enjuiciamiento Criminal "En el caso de que se trate de algunos de los delitos o faltas cuya instrucción o conocimiento corresponda al Juez de Violencia sobre la Mujer, la competencia territorial vendrá determinada por el lugar del domicilio de la víctima, sin perjuicio de la adopción de la orden de protección, o de medidas urgentes del art. 13 de la presente Ley que pudiera adoptar el Juez del lugar de comisión de los hechos", debiéndose interpretar por domicilio donde la víctima el que tuviera en el momento de los hechos, tal y como dispuso el Acuerdo del Pleno no jurisdiccional del TS de 31 de enero de 2006. Dicho criterio es el que viene manteniendo desde entonces el Tribunal Supremo, que en el Auto de 6 febrero de 2024, rec 20753/23, entre otros, señala " Esta Sala formó criterio sobre esta cuestión a partir del Acuerdo no Jurisdiccional de 21/01/2006, aplicado en numerosas resoluciones posteriores, y declaramos que el domicilio a que se refiere el artículo 15 bis de la LECrim, incorporado por la Ley Orgánica 1/2004, de 28 de diciembre, de medidas de protección integral contra la Violencia de Género "es el que tenía la víctima al ocurrir los hechos". Así en el ATS de 08/07/2020 (CC 20144/2020) dijimos que este criterio "responde mejor al principio de juez predeterminado por la Ley, no dependiendo de posibles cambios de domicilio, siendo dicho criterio el mismo que se sostiene en la Circular 4/2005, de la Fiscalía General del Estado, precisando esta Sala que la norma del art. 15 bis trata de favorecer la situación procesal de la víctima en su relación con el órgano jurisdiccional y que puede suponer una excepción a la norma general del fórum delicti comissi" [COMPLETAR]. También en el ATS de 22/09/2021 (CC 20299/2021) hemos dicho que "en principio, razones de índole práctica y que no son infrecuentes los supuestos en los que las víctimas se ven obligadas a cambiar de domicilio precisamente a consecuencia de las conductas delictivas de que son objeto, aconsejarían inclinarse por la competencia del Tribunal de Instancia (Sección de Instrucción) del lugar donde la denunciante tenga su domicilio al momento de presentar su denuncia. Sin embargo, hemos concluido que como fuero predeterminado por la Ley habrá que estar al domicilio de la víctima en el momento de comisión de los hechos, pues otra interpretación podría dejar a la voluntad de la denunciante la elección del juez territorialmente competente".

En el caso que nos ocupa, los hechos investigados presentan caracteres de un delito de trata de seres humanos, previsto y penado en el art 177 bis y ss del Código Penal, y, por tanto, incluido en la letra h) del apartado 5 del art 89 de la Ley Orgánica del Poder Judicial, por el que se determina la competencia objetiva de las Secciones de Violencia Sobre la Mujer en el ámbito penal.

Estando determinado el domicilio de la/s víctima/ s en [COMPLETAR], perteneciente al tribunal de instancia de [SEDE], y siendo de aplicación la regla de competencia territorial del art 15 bis de la Ley de Enjuiciamiento Criminal, se acuerda la inhibición de las actuaciones a la Sección de Violencia Sobre la Mujer de [LOCALIDAD].

Vistos los preceptos legales citados, concordantes y demás de general y pertinente aplicación

PARTE DISPOSITIVA

1.- Se acuerda incoar Diligencias Previas.

2.- Se acuerda la inhibición de la causa a favor de la Sección de Violencia Sobre la Mujer de [LOCALIDAD].

Notifíquese esta resolución al MINISTERIO FISCAL y en su caso, demás partes personadas.

Esta resolución no es firme y frente a ella cabe recurso de reforma ante este órgano judicial, que ha de interponerse en el plazo de TRES DIAS.

Ilmo./a. Sr/a. Magistrado/a Juez/a de [SEDE]

Firma del/de la Magistrado/a Juez/a: [COMPLETAR]

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: La Sección de Violencia sobre la Mujer solo es competente para la trata cuando es con fines de explotación sexual y la víctima es mujer (art. 89.5 h) LOPJ y art. 14.5 h) LECrim), y solo en los procedimientos incoados desde el 3-10-2025 (DF 38ª.3 y DT 4ª LO 1/2025). Si la víctima es menor, hay que tener en cuenta también el art. 89 bis.5 c) y 7 LOPJ.]
