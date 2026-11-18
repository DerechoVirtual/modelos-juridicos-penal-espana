---
name: impugnar-apelacion-contra-condena-quebrantamiento-medida-451
description: "Redacta el escrito «Impugnar la apelación contra la condena por quebrantamiento de medida cautelar de alejamiento» (formulario 451 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impugnar la apelación contra la condena por quebrantamiento de medida cautelar de alejamiento

> Formulario 0451 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] FECHA (3 veces)
- [ ] Nº DE RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…bidamente acreditado en el procedimiento»; «…sión fijado en la pena de alejamiento de»; «…, dictada por el titular de la Sección»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468 CP
- art. 803.2 CP
- artículo 803.1.2 LECRIM
- art. 803 LECRIM

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

### Formulario 0451 · Impugnar la apelación contra la condena por quebrantamiento de medida cautelar de alejamiento

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de alegaciones frente al recurso de apelación interpuesto por el condenado en juicio rápido por delito de quebrantamiento de condena del art. 468 CP, por la vía del art. 803.2 CP, argumentando que quedó probado que el condenado incumplió la pena de alejamiento.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según tengo debidamente acreditado en el procedimiento [COMPLETAR], ante este órgano judicial comparezco y como mejor proceda en Derecho, DIGO:

Que por el/la Letrado/a de la Administración de Justicia se nos ha dado traslado del recurso de apelación interpuesto por el condenado en los autos de referencia nº [Nº DE PROCEDIMIENTO] frente a la sentencia n.º [NÚMERO] de fecha [FECHA], dictada en este procedimiento por juicio rápido y, en aplicación del artículo 803.1.2 LECRIM de la Ley de Enjuiciamiento Criminal, procedemos a oponernos e impugnar dicho recurso con base en las siguientes

ALEGACIONES

PRIMERA.- Ha existido prueba bastante valorada debidamente en la sentencia como de cargo para la condena, habida cuenta que el recurrente fue sorprendido por la víctima dentro del arco de extensión fijado en la pena de alejamiento de [COMPLETAR] metros, ante lo cual dio traslado a las Fuerzas y Cuerpos de seguridad del Estado, quienes comparecieron de inmediato en el lugar donde estaba la víctima, procediendo a la detención, declarando los agentes en el juicio rápido.

SEGUNDA.- La declaración de la víctima ha sido convincente y debidamente valorada por el juez explicando en el juicio la situación producida ante el quebrantamiento de condena, valorándola el Tribunal con arreglo a los parámetros de la valoración de la declaración de la víctima que ha marcado el Tribunal Supremo en la STS 119/2019, de 6 de marzo, rec. 779/2018.

TERCERA.- No es cierto que haya sido la víctima la que ha provocado el acercamiento en modo alguno como quedó acreditado en el juicio.

CUARTA.- El tipo penal del art. 468 CP es un delito de componente estrictamente objetivo que solo exige la acreditación del quebrantamiento, sin permitir en modo alguno circunstancias subjetivas, de culpa, o explicativas del incumplidor acerca de razones que postula, ya que no existen circunstancias subjetivas que justifiquen el acercamiento, como se recoge en la STS 664/2018, de 17 de diciembre, rec. 504/2017, que no admite causas de justificación en modo alguno.

QUINTA.- Ello determina que las alegaciones efectuadas por el recurrente se desestimen en la impugnación del recurso por existir prueba de cargo debidamente explicada en la sentencia que reúne la debida motivación para enervar la presunción de inocencia, ya que la condena está basada en el dato puramente objetivo del quebrantamiento que no admite circunstancias justificativas del acercamiento, ya que el condenado no puede modular o tratar de explicar las razones de su quebrantamiento. La pena de alejamiento no es interpretable, como parece sostener el recurrente en su recurso.

Es por ello, por lo que,

SUPLICO A LA SECCIÓN:

Se tenga por cumplimentada en el plazo de cinco días concedido (1) la impugnación al recurso de apelación formulado por el recurrente a la sentencia nº [Nº DE RESOLUCIÓN] de fecha [FECHA], dictada por el titular de la Sección [COMPLETAR] y se eleven los autos a la Audiencia Provincial para que, en su día, se dicte sentencia confirmatoria de la condena recurrida.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) El plazo para presentar este escrito de alegaciones será de cinco días (art. 803 LECRIM).

La tramitación y resolución de estos recursos de apelación tendrán carácter preferente.

================================================================================
