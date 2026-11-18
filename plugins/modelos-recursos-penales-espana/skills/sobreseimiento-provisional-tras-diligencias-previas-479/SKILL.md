---
name: sobreseimiento-provisional-tras-diligencias-previas-479
description: "Redacta el escrito «Sobreseimiento provisional tras las diligencias previas: reforma y subsidiaria apelación» (formulario 479 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sobreseimiento provisional tras las diligencias previas: reforma y subsidiaria apelación

> Formulario 0479 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NÚMERO (3 veces)
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… ya tengo acreditado en el procedimiento»; «…, por»; «…, a [FECHA]. Firma de Abogado/a:»; «…Firma de Procurador/a:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el auto que se recurre sobreseyó por no resultar debidamente justificada la perpetración del delito / Si el auto que se recurre sobreseyó por no haber autor conocido — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766 LECRIM
- art. 641 LECRIM
- art. 217, 222 y 766 LECRIM
- art. 766.3 LECRIM

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

### Formulario 0479 · Sobreseimiento provisional tras las diligencias previas: reforma y subsidiaria apelación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 13 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en reforma y, si no es admitido posteriormente en apelación, en base al art. 766 LECRIM, el auto de sobreseimiento provisional de la causa por alguno de los motivos del art. 641 LECRIM, es decir, porque no se cometió el delito o no hay autor conocido.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales (col. nº [NÚMERO]), en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], como ya tengo acreditado en el procedimiento [COMPLETAR], bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS] (col. nº [NÚMERO]), ante este órgano judicial comparezco y, en términos de Derecho, DIGO:

Por medio del presente escrito interpongo RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN, conforme a lo dispuesto en el art. 217, 222 y 766 LECRIM (1), contra el auto de fecha [FECHA], que acordaba el sobreseimiento provisional de las DP nº [NÚMERO], por [COMPLETAR] por considerar dicha resolución contraria a derecho y perjudicial para mi representado/a, con base en las siguientes:

ALEGACIONES

PRIMERA

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el auto que se recurre sobreseyó por no resultar debidamente justificada la perpetración del delito / Si el auto que se recurre sobreseyó por no haber autor conocido — el texto de cada opción no venía en el formulario original]

SEGUNDA

Como particulares que deberán testimoniarse señalamos los siguientes:

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias y por interpuesto en tiempo y forma recurso de reforma y subsidiario de apelación contra el auto de fecha [FECHA], lo admita, siguiendo los trámites legales que correspondan y, posteriormente, si se desestima la reforma, remita las actuaciones a la Audiencia Provincial para que resuelva, en cumplimiento de lo establecido en el art. 766.3 LECRIM.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a: [COMPLETAR]

Firma de Procurador/a: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Se interpone ante el mismo juez que dictó la resolución recurrida, por escrito autorizado con firma de Letrado y en el plazo de los tres días siguientes a su notificación. (Arts. 211 y 216 LECrim. y ss.)

Los días se consideran naturales en la fase de instrucción y hábiles en la de juicio oral.

================================================================================
