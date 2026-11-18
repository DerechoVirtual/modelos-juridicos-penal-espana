---
name: victima-pedir-ir-acompanada-declaracion-ante-juez-754
description: "Redacta el escrito «Víctima: pedir ir acompañada en su declaración ante el juez» (formulario 754 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima: pedir ir acompañada en su declaración ante el juez

> Formulario 0754 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (3 veces)
- [ ] LOCALIDAD
- [ ] NÚMERO
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…edacción RDL 6/2023, BOE-A-2023-25758).]»

## Elecciones que hay que hacer

- testigo / víctima

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 109.4 LECRIM

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

### Formulario 0754 · Víctima: pedir ir acompañada en su declaración ante el juez

- Año del modelo: 2016
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 20 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito mediante el que la víctima de un delito solicita poder ser acompañada por una persona de su elección cuando vaya a tomársele declaración ante el juez, conforme permite el artículo 4 c) de la L 4/2015, del Estatuto de la Víctima del Delito.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD] Sección nº [NÚMERO]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] (1) (2) en el Juicio oral nº [Nº DE PROCEDIMIENTO]/[AÑO] que se sigue por delito de [DELITO] del art. del CP, contra D./Dña. [NOMBRE Y APELLIDOS], ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se ha citado a mi representado/a para que comparezca en su calidad de [ELEGIR: testigo / víctima] a fin de recibirle declaración.

El artículo 4. c) de la L 4/2015, de 27 de abril, del Estatuto de la Víctima, permite que la víctima sea acompañada por una persona de su elección, al establecer que:

"c) La víctima podrá estar acompañada de una persona de su elección desde el primer contacto con las autoridades y funcionarios."

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita el presente escrito y se autorice a D./Dña. [NOMBRE Y APELLIDOS]. a acudir acompañada por D./Dña. [NOMBRE Y APELLIDOS].el día de su declaración.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito puede presentarse tanto en la Sección de Instrucción del Tribunal de Instancia o violencia sobre la mujer (para casos de violencia de género), si es fase de instrucción, o en la Sección de lo Penal del Tribunal de Instancia o en la Sección Penal de la Audiencia Provincial; si es en fase de enjuiciamiento.

(2) No es obligatorio que la víctima se persone en el proceso penal para presentar este escrito. Puede hacerlo por sí misma y, en base al artículo 109.4 LECRIM [NOTA DE REVISIÓN (comprobar): El art. 109 LECrim no tiene apartados numerados; desde el 20-3-2024 (RDL 6/2023) incluye un párrafo nuevo sobre personas con discapacidad, y la comunicación a la víctima de los actos que afecten a su seguridad es su último párrafo. Fuente: LECrim, BOE-A-1882-6036, art. 109 (redacción RDL 6/2023, BOE-A-2023-25758).] [COMPLETAR], este órgano judicial debería ofrecerle esta opción en la citación a juicio a fin de que pueda presentarlo, si lo desea.

================================================================================
