---
name: delitos-cometidos-extranjero-auto-archivo-falta-38
description: "Redacta el escrito «Delitos cometidos en el extranjero: auto de archivo por falta de jurisdicción» (formulario 38 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delitos cometidos en el extranjero: auto de archivo por falta de jurisdicción

> Formulario 0038 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] DELITO
- [ ] SEDE
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… presentado por unos hechos ocurridos en»; «… ocupa, se denuncian hechos cometidos en»; «…y en lo que aparece como víctima»; «…que reside en»; «… HECHOS. Remítase copia de la denuncia a»; «…Firma del/de la Magistrado/a Juez/a:»

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

### Formulario 0038 · Delitos cometidos en el extranjero: auto de archivo por falta de jurisdicción

- Año del modelo: 2025
- Revisión 17-11-2026: 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 16) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución mediante la cual una Sección del orden penal archiva la causa por falta de jurisdicción al cometerse el delito fuera de España por extranjero no residente en este país remitiendo copia de la denuncia al órgano competente del país correspondiente. Modelo basado en el que los integrantes del grupo de expertos y expertas del Observatorio contra la Violencia Doméstica y de Género del CGPJ destinados en órganos unipersonales ponen a disposición de la carrera judicial.

---

AUTO

En [LUGAR], a [FECHA].

ANTECEDENTES DE HECHO

ÚNICO.- Las presentes actuaciones se incoaron en virtud de atestado presentado por unos hechos ocurridos en [COMPLETAR].

FUNDAMENTOS JURÍDICOS

ÚNICO.- Dispone el art 23.4 de la Ley Orgánica del Poder Judicial:

"Igualmente, será competente la jurisdicción española para conocer de los hechos cometidos por españoles o extranjeros fuera del territorio nacional susceptibles de tipificarse, según la ley española, como alguno de los siguientes delitos cuando se cumplan las condiciones expresadas:

l) Delitos regulados en el Convenio del Consejo de Europa de 11 de mayo de 2011 sobre prevención y lucha contra la violencia contra las mujeres y la violencia doméstica, siempre que:
1.º el procedimiento se dirija contra un español;
2.º el procedimiento se dirija contra un extranjero que resida habitualmente en España; o,
3.º el delito se hubiera cometido contra una víctima que, en el momento de comisión de los hechos, tuviera nacionalidad española o residencia habitual en España, siempre que la persona a la que se impute la comisión del hecho delictivo se encuentre en España."

En el caso que nos ocupa, se denuncian hechos cometidos en [COMPLETAR] que pudieran ser constitutivos de un delito de [DELITO] y en lo que aparece como víctima [COMPLETAR] que reside en [COMPLETAR].

Teniendo en cuenta que los hechos denunciados han sido cometidos fuera del territorio nacional, siendo el investigadonacional de dicho país y sin que este tenga residencia en España, la conclusión a la que se llega es que la jurisdicción española no tiene competencia para conocer de los hechos, razón por la cual procede el archivo de las presentes diligencias al estar el conocimiento de los hechos excluido de la jurisdicción española.

Sin perjuicio de lo anterior, remítase copia de la denuncia presentada a las autoridades competentes del Estado en cuyo territorio se han cometido los hechos, conforme a lo previsto en el art 17 del Estatuto de la Víctima del delito.

PARTE DISPOSITIVA

1.- Se acuerda INCOAR DILIGENCIAS PREVIAS.

2.- Se acuerda el ARCHIVO del presente procedimiento, AL CARECER LA JURISDICCIÓN ESPAÑOLA DE COMPETENCIA PARA CONOCER DE LOS HECHOS.

Remítase copia de la denuncia a [COMPLETAR].

PÓNGASE ESTA RESOLUCION EN CONOCIMIENTO DEL MINISTERIO FISCAL Y DEMÁS PARTES, previniéndoles que contra la misma podrán interponer, ante este órgano judicial, RECURSO DE REFORMA en el plazo de TRES DIAS y subsidiariamente con el anterior, o por separado, RECURSO DE APELACIÓN en el plazo de CINCO DIAS.

Ilmo./a. Sr/a. Magistrado/a Juez/a de [SEDE]

Firma del/de la Magistrado/a Juez/a: [COMPLETAR]

================================================================================
