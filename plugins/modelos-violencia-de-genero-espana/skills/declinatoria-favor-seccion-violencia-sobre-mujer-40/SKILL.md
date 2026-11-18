---
name: declinatoria-favor-seccion-violencia-sobre-mujer-40
description: "Redacta el escrito «Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor» (formulario 40 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor

> Formulario 0040 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- Solo hay tres Secciones de Violencia contra la Infancia y la Adolescencia: Madrid, Barcelona y Málaga (RD 422/2025, BOE-A-2025-11069, con efectos desde el 31-12-2025). En los demás partidos, la declinatoria debe pedir la remisión a la Sección de Instrucción o a la Sección Única, salvo que el CGPJ haya designado un juez concreto (art. 89 bis.1 y 4 LOPJ).
- Si la víctima es una niña, el art. 89.5 h) LOPJ (delitos sexuales cuando la víctima «sea mujer») y el art. 89 bis.7 LOPJ (preferencia de la Sección de Violencia sobre la Mujer) pueden llevar a la conclusión contraria. Hay que argumentar por qué «mujer» no incluye a la menor.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA
- [ ] ACTO O RESOLUCIÓN
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…. Es Justicia que pido en a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si lo presenta la acusación particular / Si lo presenta la defensa — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 89 bis.5 b) LOPJ
- artículo 14.6 LECrim
- art. 181 CP

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

### Formulario 0040 · Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor

- Año del modelo: 2025
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Nota explicativa incorporada desde la colección Procesal (formulario 20) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito dirigido a la Sección de Violencia sobre la mujer, donde se sigue procedimiento por delito de agresión sexual del art. 181 CP a menor, instándole a que se inhiba en favor de la Sección de Violencia contra la Infancia y la Adolescencia, por ser la competente conforme al art. 89 bis 5 b LOPJ, según redacción dada por LO 1/2025.

---

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS] según consta acreditado en procedimiento nº [Nº], seguido ante el órgano al que me dirijo, comparezco y como proceda en Derecho, DIGO:

Que en fecha [FECHA] se incoaron las presentes diligencias en virtud de querella interpuesta por presunto delito de agresión sexual contra [ACTO O RESOLUCIÓN] en el que aparece como investigado. Se están practicando diligencias de instrucción cuando la competencia objetiva no pertenece a esta Sección del Tribunal de Instancia sino a la Sección de Violencia contra la Infancia y la Adolescencia donde se tramita la denuncia por agresión sexual a la madre.

En consecuencia, mediante el presente escrito, de conformidad con los arts. 19 y ss LECRIM, se promueve declinatoria interesando a la Sección de Violencia sobre la Mujer que se inhiba en favor de la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de instancia de [SEDE], en base a las siguientes

ALEGACIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si lo presenta la acusación particular / Si lo presenta la defensa — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Como prevé el art. 89 bis.5 b) LOPJ:

"5. Las Secciones de Violencia contra la Infancia y la Adolescencia conocerán, en el orden penal, de conformidad en todo caso con los procedimientos y recursos previstos en la Ley de Enjuiciamiento Criminal, de la instrucción de los procesos para exigir responsabilidad penal por los delitos recogidos en los Títulos del Código Penal relativos a:...

b) Delitos contra la libertad, delito de torturas y contra la integridad moral, delitos contra la intimidad, el derecho a la propia imagen y la inviolabilidad del domicilio, delitoscontra la libertad e indemnidad sexual, delitos contra el honor, delitos contra las relaciones familiares, o cualquier otro delito cometido con violencia o intimidación, cuando la víctima sea niño, niña o adolescente."

Señala el documento de unificación de criterios elaborado por el Observatorio de Violencia doméstica y de género del CGPJ que:

"Conforme al artículo 14.6 LECrim, en relación con el artículo 89 bis 5 LOPJ, son competencia de las Secciones de Violencia contra la Infancia y Adolescencia los procedimientos de agresiones sexuales en los que la víctima sea una niña o adolescente. Cuando la víctima menor de edad no tuviera ni hubiera tenido relación sentimental con el investigado, la competencia para conocer de tales delitos corresponderá a las Secciones de Violencia contra la Infancia y Adolescencia".

Los hechos de que ha sido víctima la menor..., que no es pareja del autor, son constitutivos de delito del art. 181 CP, competencia de la Sección de Violencia contra la Infancia y la Adolescencia.

Por ello,

SUPLICO A LA SECCIÓN:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se interesa que la Sección de Violencia sobre la Mujer se inhiba y, tras el trámite correspondiente y la audiencia al Ministerio Fiscal, se remitan las diligencias a la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE].

Es Justicia que pido en a [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: Solo hay tres Secciones de Violencia contra la Infancia y la Adolescencia: Madrid, Barcelona y Málaga (RD 422/2025, BOE-A-2025-11069, con efectos desde el 31-12-2025). En los demás partidos, la declinatoria debe pedir la remisión a la Sección de Instrucción o a la Sección Única, salvo que el CGPJ haya designado un juez concreto (art. 89 bis.1 y 4 LOPJ).]

[NOTA DE REVISIÓN: Si la víctima es una niña, el art. 89.5 h) LOPJ (delitos sexuales cuando la víctima «sea mujer») y el art. 89 bis.7 LOPJ (preferencia de la Sección de Violencia sobre la Mujer) pueden llevar a la conclusión contraria. Hay que argumentar por qué «mujer» no incluye a la menor.]
