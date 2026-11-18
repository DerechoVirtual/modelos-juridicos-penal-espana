---
name: abogado-discapacidad-pedir-adapte-sala-vistas-juicio-62
description: "Redacta el escrito «Abogado con discapacidad: pedir que se adapte la sala de vistas para el juicio o la actuación» (formulario 62 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abogado con discapacidad: pedir que se adapte la sala de vistas para el juicio o la actuación

> Formulario 0062 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 18 de la Ley Orgánica 5/2024
- art. 56 del Real Decreto 135/2021

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

### Formulario 0062 · Abogado con discapacidad: pedir que se adapte la sala de vistas para el juicio o la actuación

- Año del modelo: 2024
- Revisión 17-11-2026: 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 57) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que un letrado con discapacidad solicita la asistencia, apoyos y otros recursos accesibles universalmente necesarios para desempeñar de forma eficaz el ejercicio profesional del derecho de defensa, conforme al art. 18 LO 5/2024, del Derecho de Defensa y el art. 56 RD 135/2021, de 2 de marzo, por el que se aprueba el Estatuto General de la Abogacía Española.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], como consta acreditado en las diligencias número, ante este órgano judicial comparezco y como mejor en derecho proceda,

DIGO:

Que, en la presente causa, como letrado/a de D./Dña. [NOMBRE Y APELLIDOS] asumo su dirección jurídica como consta en la personación.

Que tengo una discapacidad del %, que se acredita con el documento nº 1 que se adjunta al presente escrito consistente en [DESCRIBIR].

Que se nos ha citado para el día para la celebración del juicio oral.

Señala el art. 18 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa que:

"Artículo 18. Garantías del profesional de la abogacía con discapacidad.

El profesional de la abogacía con discapacidad tendrá derecho a utilizar la asistencia, apoyos y otros recursos accesibles universalmente que requiera para desempeñar de forma eficaz el ejercicio profesional del derecho de defensa."

Además, señala el art. 56 del Real Decreto 135/2021, de 2 de marzo, por el que se aprueba el Estatuto General de la Abogacía Española, que lleva por rúbrica Ubicación en las Salas y dependencias judiciales que:

"4. Los Colegios velarán por que en las sedes de juzgados y tribunales se ubiquen dependencias dignas y suficientes para su utilización por los profesionales de la Abogacía en el desarrollo de sus funciones."

En este caso, dada la discapacidad que tengo, es necesario que el día señalado para mi comparecencia como letrado/a se lleve a cabo la adaptación oportuna del lugar desde donde debo ejercer el derecho de defensa, a fin de que pueda acceder a la sala y ocupar el lugar que se me conceda.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y se tengan por hechas las manifestaciones que constan en él, para permitir la adaptación de la Sala a la discapacidad antes descrita, a fin de poder ejercitar debidamente y sin limitaciones el derecho de defensa.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
