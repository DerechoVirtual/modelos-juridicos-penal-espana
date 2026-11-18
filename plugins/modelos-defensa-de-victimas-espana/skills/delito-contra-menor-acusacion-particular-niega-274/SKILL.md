---
name: delito-contra-menor-acusacion-particular-niega-274
description: "Redacta el escrito «Delito contra menor: la acusación particular niega la prescripción (hasta el 2 de abril de 2025)» (formulario 274 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contra menor: la acusación particular niega la prescripción (hasta el 2 de abril de 2025)

> Formulario 0274 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] FECHA (3 veces)
- [ ] FECHA DEL ESCRITO
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ún consta acreditado en el Procedimiento»; «…tipificado en el artículo»

## Elecciones que hay que hacer

- de tentativa de homicidio / de lesiones / de maltrato habitual / contra la libertad sexual / de trata de seres humanos

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 131 CP

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

### Formulario 0274 · Delito contra menor: la acusación particular niega la prescripción (hasta el 2 de abril de 2025)

- Año del modelo: 2022
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 3 huecos del original que se habían perdido sin marca, marcados (FECHA DEL ESCRITO, NOMBRE Y APELLIDOS, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D/Dña [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento [COMPLETAR] seguido ante ese Tribunal, comparezco y como proceda en Derecho DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese juzgado por Dña. [NOMBRE Y APELLIDOS] contra D. por la comisión de un delito [ELEGIR: de tentativa de homicidio / de lesiones / de maltrato habitual / contra la libertad sexual / de trata de seres humanos] tipificado en el artículo [COMPLETAR] CP habiéndonos personado en las actuaciones por escrito de fecha [FECHA DEL ESCRITO] en el procedimiento nº [Nº DE PROCEDIMIENTO]

Que con fecha [FECHA] se ha presentado escrito por la defensa del denunciado Interesando que se declaren prescritos los hechos por haber transcurrido el plazo de años del art. 131 CP desde que ocurrieron los hechos.

Que el CP en el art. 132.1.3º CP recoge que:

"En los delitos de tentativa de homicidio, de lesiones de los artículos 149 y 150, en el delito de maltrato habitual previsto en el artículo 173.2, en los delitos contra la libertad sexual y en los delitos de trata de seres humanos, cuando la víctima fuere una persona menor de dieciocho años, los términos se computarán desde que la víctima cumpla los treinta y cinco años de edad, y si falleciere antes de alcanzar esa edad, a partir de la fecha del fallecimiento."

Que en este caso la víctima tenía menos de 18 años cuando ocurrieron los hechos, por lo que el plazo no empieza a contar sino desde que la víctima cumpla los 35 años de edad, y no desde la comisión del hecho, por lo que el cómputo que se lleva a cabo es erróneo por la defensa al no haber transcurrido el plazo de años que prevé el art. 131 CP para la prescripción del delito.

Por lo expuesto.

SUPLICO AL TRIBUNAL:

Que tenga por presentado este escrito, lo admita y tenga por realizada la alegación de esta parte como acusación particular de la no prescripción de los hechos con motivo de lo dispuesto en el art. 132.1º.3º CP.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
