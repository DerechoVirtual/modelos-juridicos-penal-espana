---
name: pedir-repita-declaracion-instruccion-privar-letrado-67
description: "Redacta el escrito «Pedir que se repita una declaración en instrucción por privar al letrado de su libertad de expresión» (formulario 67 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que se repita una declaración en instrucción por privar al letrado de su libertad de expresión

> Formulario 0067 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…ñalar nueva fecha para la declaración de»

## Elecciones que hay que hacer

- investigado/a / testigo / perito

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 17 de la Ley Orgánica 5/2024
- art. 58 del RD 135/2021
- art. 17 de la LO 5/2024

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

### Formulario 0067 · Pedir que se repita una declaración en instrucción por privar al letrado de su libertad de expresión

- Año del modelo: 2024
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], como consta acreditado en las diligencias número, ante este órgano judicial comparezco y como mejor en derecho proceda,

DIGO:

Que, en la presente causa, como letrado de D./Dña. [NOMBRE Y APELLIDOS] asumo su dirección jurídica como consta en la personación.

Que se nos citó para el día para la práctica de las siguientes diligencias judiciales:

Que en las declaraciones del/de la [ELEGIR: investigado/a / testigo / perito] se nos privó de realizar las preguntas que estimamos convenientes en el ejercicio del derecho de defensa, sin que hubiera en modo alguno exceso en las observaciones que llevamos a cabo, privándosenos de la actuación profesional procedente en defensa de los derechos de nuestro/a cliente.

Señala el art. 17 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa, como garantía de la libertad de expresión del profesional de la abogacía, lo siguiente:

"Los profesionales de la abogacíagozarán del derecho a manifestarse con libertad, oralmente y por escrito, en el desarrollo del procedimientoante los poderes públicos y con las partes, atendiendo al significado de las concretas expresiones, al contexto procedimental y a la necesidad para la efectividad del derecho de defensa, salvo cuando esas manifestaciones sean contrarias a la deontología profesional u otras normas de aplicación. Los colegios de la abogacía velarán por el respeto a la libertad de expresión del profesional de la abogacía, como garantía del derecho de defensa."

Además, señala el art. 58 del RD 135/2021, de 2 de marzo, por el que se aprueba el Estatuto General de la Abogacía Española, que lleva por rúbrica Protección de la libertad e independencia del profesional de la Abogacía que:

1. En su actuación ante los órganos judiciales los profesionales de la Abogacía son libres e independientes, gozarán de los derechos inherentes a la dignidad de su función ypodrán solicitar ser amparados en su libertad de expresión y defensa, en los términos previstos en las normas aplicables.
2. Si el profesional de la Abogacía considerase que la autoridad, juez o tribunal coarta la independencia y libertad necesarias para cumplir sus deberes profesionales, o que no guarda la consideración debida a su función, podrá hacerlo constar así ante el propio órgano judicial o tribunal y dar cuenta a la Junta de Gobierno. La Junta, si estimare fundada la queja, adoptará medidas activas para amparar la libertad, independencia y dignidad profesionales.
3. Los Colegios notificarán los amparos concedidos a las autoridades, jueces o tribunales que hayan coartado la libertad o independencia de los profesionales de la Abogacía y denunciarán dichas conductas, cuando proceda, ante el Consejo General del Poder Judicial y las instituciones pertinentes. Asimismo, los Colegios de la Abogacía promoverán fórmulas para ser oídos ante las Salas de Gobierno de sus respectivos Tribunales Superiores de Justicia en los expedientes gubernativos seguidos contra cualquier profesional de la Abogacía y sus recursos.

En las presentes actuaciones se ha infringido el precitado art. 17 de la LO 5/2024 al no poder hacer las preguntas que se nos tacharon de no procedentes, debido a la forma que se estaba empleando en el interrogatorio, que en modo alguno fue improcedente, sino llevadas a cabo en virtud del ejercicio del derecho de defensa y la libertad de expresión, sin exceso alguno, realizándose en su momento la protesta oportuna.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y se vuelva a señalar nueva fecha para la declaración de [COMPLETAR] al objeto de poder realizar las preguntas que se estiman pertinentes y adecuadas de las que fue impedido llevar a cabo en la anterior declaración judicial, y ello en el ejercicio del derecho de defensa y para evitar la indefensión material.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
