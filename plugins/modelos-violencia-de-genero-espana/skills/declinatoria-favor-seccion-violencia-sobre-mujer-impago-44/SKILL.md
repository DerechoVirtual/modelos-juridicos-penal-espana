---
name: declinatoria-favor-seccion-violencia-sobre-mujer-impago-44
description: "Redacta el escrito «Declinatoria a favor de la Sección de Violencia sobre la Mujer por impago de alimentos a hijo menor» (formulario 44 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Declinatoria a favor de la Sección de Violencia sobre la Mujer por impago de alimentos a hijo menor

> Formulario 0044 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- La cita del art. 89 bis.5 b) LOPJ es correcta, porque el impago de pensiones es un delito contra las relaciones familiares. Pero si además hay un acto de violencia de género sobre la madre, la Sección de Violencia sobre la Mujer también es competente para los delitos contra los hijos (art. 89.5 a) y b) LOPJ) y prevalece sobre la de Infancia (art. 89 bis.7 LOPJ).
- Solo hay Secciones de Violencia contra la Infancia y la Adolescencia en Madrid, Barcelona y Málaga (RD 422/2025, BOE-A-2025-11069). En los demás partidos, la remisión será a la Sección de Instrucción o a la Sección Única (art. 89 bis.1 y 4 LOPJ).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…elito de impago de pensión alimenticia a»; «…os Títulos del Código Penal relativos a:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si lo presenta la acusación particular / Si lo presenta la defensa — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 227 CP
- art. 89 bis.5 b) LOPJ
- art. 14.6 b) LECRIM
- artículo 89.5.b) LOPJ
- artículo 227 del Código Penal
- artículo 89 bis.5 b) LOPJ

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

### Formulario 0044 · Declinatoria a favor de la Sección de Violencia sobre la Mujer por impago de alimentos a hijo menor

- Año del modelo: 2025
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Nota explicativa incorporada desde la colección Procesal (formulario 24) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito dirigido a la Sección de Violencia sobre la Mujer, donde se sigue procedimiento por delito de impago de pensión alimenticia del art. 227 CP a su hijo menor, instándole a que se inhiba en favor de la Sección de Violencia contra la Infancia y la Adolescencia por ser la competente conforme al art. 89 bis 5 b LOPJ, según redacción dada por LO 1/2025.

---

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS] según consta acreditado en procedimiento nº [Nº], seguido ante el órgano al que me dirijo, comparezco y como proceda en Derecho, DIGO:

Que en fecha [FECHA] se incoaron las presentes diligencias en virtud de querella interpuesta por presunto delito de impago de pensión alimenticia a [COMPLETAR] del art. 227 CP en el que aparece como investigado el padre. Se están practicando diligencias de instrucción cuando la competencia objetiva no pertenece a esta Sección del Tribunal de Instancia sino a la Sección de Violencia contra la Infancia y la Adolescencia donde se tramita la denuncia por agresión sexual a la madre.

En consecuencia, mediante el presente escrito, de conformidad con los arts. 19 y ss LECRIM, se promueve declinatoria interesando a la Sección de Violencia sobre la Mujer que se inhiba en favor de la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de instancia de [SEDE], en base a las siguientes

ALEGACIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si lo presenta la acusación particular / Si lo presenta la defensa — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Como prevé el art. 89 bis.5 b) LOPJ:

"5. Las Secciones de Violencia contra la Infancia y la Adolescencia conocerán, en el orden penal, de conformidad en todo caso con los procedimientos y recursos previstos en la Ley de Enjuiciamiento Criminal, de la instrucción de los procesos para exigir responsabilidad penal por los delitos recogidos en los Títulos del Código Penal relativos a:

[COMPLETAR]

b) Delitos contra la libertad, delito de torturas y contra la integridad moral, delitos contra la intimidad, el derecho a la propia imagen y la inviolabilidad del domicilio, delitos contra la libertad e indemnidad sexual, delitos contra el honor,delitos contra las relaciones familiares, o cualquier otro delito cometido con violencia o intimidación, cuando la víctima sea niño, niña o adolescente."

La misma previsión recoge el art. 14.6 b) LECRIM.

Señala el documento de unificación de criterios elaborado por el Observatorio de Violencia doméstica y de género del CGPJ que:

"En los delitos de impago de pensiones, el bien jurídico protegido no es el cumplimiento de una resolución judicial, sino el derecho de asistencia económica de determinados miembros de la unidad familiar.

Conforme al artículo 89.5.b) LOPJ, las Secciones de Violencia sobre la Mujer conocen de la instrucción de los procesos para exigir responsabilidad penal porcualquier delito contra las relaciones familiares, cuando la víctima sea alguna de las personas señaladas en la letra anterior. Entre estos delitos se encuentra el de abandono de familia en la modalidad de impago de pensiones del artículo 227 del Código Penal (CP).

... 1º) Cuando la pensión presuntamente impagada sea la de los hijos, en aplicación del artículo 89 bis.5 b) LOPJ, la competencia para conocer del delito de impago corresponderá a la Sección de Instrucción o a la Sección de Violencia contra la Infancia y Adolescencia en caso de existir, pues son aquellos los sujetos pasivos del tipo penal, sin perjuicio de la legitimidad de la madre para denunciar el impago de la pensión alimenticia de sus hijos menores, con discapacidad, o de los hijos mayores con los que conviva (STS, Pleno, 557/2020, de 29 de octubre de 2020, ROJ: STS 3554/2020 – ECLI:ES:TS:2020:3554). Y ello por cuanto la Sección de Violencia contra la Infancia y Adolescencia es la competente para conocer de la instrucción de los procesos para exigir responsabilidad penal por los delitos contra las relaciones familiares "cuando la víctima sea niño, niña o adolescente".

En consecuencia, la competencia del impago de pensión alimenticia a menores exclusivamente es competencia de la Sección de Violencia contra la Infancia y la Adolescencia.

Por todo ello

SUPLICO A LA SECCIÓN:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se interesa que la Sección de Violencia sobre la Mujer se inhiba y, tras el trámite correspondiente y la audiencia al Ministerio Fiscal, se remitan las diligencias a la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE].

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: La cita del art. 89 bis.5 b) LOPJ es correcta, porque el impago de pensiones es un delito contra las relaciones familiares. Pero si además hay un acto de violencia de género sobre la madre, la Sección de Violencia sobre la Mujer también es competente para los delitos contra los hijos (art. 89.5 a) y b) LOPJ) y prevalece sobre la de Infancia (art. 89 bis.7 LOPJ).]

[NOTA DE REVISIÓN: Solo hay Secciones de Violencia contra la Infancia y la Adolescencia en Madrid, Barcelona y Málaga (RD 422/2025, BOE-A-2025-11069). En los demás partidos, la remisión será a la Sección de Instrucción o a la Sección Única (art. 89 bis.1 y 4 LOPJ).]
