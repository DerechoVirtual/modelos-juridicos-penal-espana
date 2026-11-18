---
name: falta-competencia-seccion-violencia-sobre-mujer-proceso-33
description: "Redacta el escrito «Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto» (formulario 33 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto

> Formulario 0033 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] ÓRGANO O PERSONA
- [ ] SEDE (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…NICO.- Por la representación procesal de»; «…, se presentó demanda de»; «…Firma del/de la Magistrado/a Juez/a:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de archivo de la ejecutoria penal / En caso de sobreseimiento de las actuaciones penales — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 89.7 de la LOPJ

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

### Formulario 0033 · Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto

- Año del modelo: 2025
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 7 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 11) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución de una Sección de Violencia sobre la Mujer por la que declara que no tiene competencia objetiva para conocer de un proceso de familia por no existir ningún procedimiento penal abierto entre las partes, en el momento de formular la demanda, al haberse archivado la ejecutoria penal o sobreseído las actuaciones penales. Modelo basado en el que los integrantes del grupo de expertos y expertas del Observatorio contra la Violencia Doméstica y de Género del CGPJ destinados en órganos unipersonales ponen a disposición de la carrera judicial.

---

AUTO

En [LUGAR], a [FECHA].

ANTECEDENTES DE HECHO

ÚNICO.-

Por la representación procesal de [COMPLETAR], se presentó demanda de [COMPLETAR]. Por Diligencia de [FECHA], se da traslado a las partes y al Ministerio Fiscal, para que se pronuncien sobre la competencia de este órgano judicial, con el resultado que consta en autos.

RAZONAMIENTOS JURÍDICOS

ÚNICO.-

El art. 89.7 de la LOPJ, de conformidad con la reforma operada por LO 1/2025, establece los requisitos para que la sección de Violencia sobre la Mujer pueda conocer de un proceso de familia.

En efecto, indica en referido precepto:

": Las Secciones de Violencia sobre la Mujer tendrán de forma exclusiva y excluyente competencia en el orden civil cuando concurran simultáneamente los siguientes requisitos:

a) Que se trate de un proceso civil que tenga por objeto alguna de las materias

indicadas en el apartado 6 del presente artículo.

b) Que alguna de las partes del proceso civil sea víctima de actos de violencia de género, en los términos a que hace referencia el apartado 5. a), o de actos de violencia sexual, en los términos a que hace referencia el apartado 5.h) del presente artículo.
c) Que alguna de las partes del proceso civil sea imputado como autor, inductor o cooperador necesario en la realización de actos de violencia de género o de violencia sexual.
d) Que se hayan iniciado ante la Sección de Violencia sobre la Mujer de un Tribunal de Instancia actuaciones penales por delito o delito leve a consecuencia de un acto de violencia de género o de un acto de violencia sexual, o se haya adoptado una orden de protección a una víctima de violencia de género.

8. Cuando el juez o la jueza apreciara que los actos puestos en su conocimiento, de forma notoria, no constituyen expresión de violencia de género o de violencia sexual, podrá inadmitir la pretensión, remitiéndola al órgano judicial competente."

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de archivo de la ejecutoria penal / En caso de sobreseimiento de las actuaciones penales — el texto de cada opción no venía en el formulario original]

Por tanto, procede declarar la falta de competencia de esta Sección.

PARTE DISPOSITIVA

Acuerdo declarar la falta de competencia objetiva de esta Sección de Violencia sobre la mujer para conocer de la demanda presentada por [ÓRGANO O PERSONA] remitiéndose las actuaciones al PRESIDENTE DEL TRIBUNAL DE INSTANCIA DE [SEDE], para su reparto ante quien corresponda.

MODO DE IMPUGNACIÓN: recurso de apelación en el plazo de 20 días, desde la notificación de esta resolución, ante este tribunal. INFORMACION SOBRE EL DEPÓSITO PARA RECURRIR De conformidad con la D.A. 15ª de la LOPJ, para que sea admitido a trámite el recurso de apelación contra esta resolución deberá constituir un depósito de 50 €, que le será devuelto sólo en el caso de que el recurso sea estimado. El depósito deberá constituirlo ingresando la citada cantidad en el banco SANTANDER, en la cuenta correspondiente a este expediente (5660-0000- 02-0036-24) indicando, en el campo "concepto" el código "02 Civil Apelación" y la fecha de la resolución recurrida con el formato DD/MM/AAAA En el caso de realizar el ingreso mediante transferencia bancaria, tras completar el Código de Cuenta Corriente (CCC, 20 dígitos), se indicará en el campo "concepto" el número de cuenta el código y la fecha que en la forma expuesta en el párrafo anterior. En ningún caso se admitirá una consignación por importe diferente al indicado. En el caso de que deba realizar otros pagos en la misma cuenta, deberá verificar un ingreso por cada concepto, incluso si obedecen a otros recursos de la misma o distinta clase. Están exceptuados de la obligación de constituir el depósito quienes tengan reconocido el derecho a litigar gratuitamente, el Ministerio Fiscal, Estado, Comunidades Autónomas, entidades locales y organismos autónomos dependientes de los tres anteriores.

Ilmo./a. Sr/a. Magistrado/a Juez/a de [SEDE]

Firma del/de la Magistrado/a Juez/a: [COMPLETAR]

================================================================================
