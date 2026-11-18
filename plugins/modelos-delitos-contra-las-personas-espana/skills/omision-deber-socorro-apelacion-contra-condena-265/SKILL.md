---
name: omision-deber-socorro-apelacion-contra-condena-265
description: "Redacta el escrito «Omisión del deber de socorro: apelación contra la condena» (formulario 265 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Omisión del deber de socorro: apelación contra la condena

> Formulario 0265 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…san como hechos probados los siguientes:»; «…endida la prueba practicada en el juicio»; «…aso, que han quedado acreditadas, fueron»

## Elecciones que hay que hacer

- quebrantamiento de las normas y garantías procesales / infracción de precepto constitucional o legal / desestimación indebida a la petición de la disolución del Jurado al no existir prueba de cargo / disolución del Jurado improcedente / vulneración del derecho a la presunción de inocencia
- favorable / desfavorable

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 196 CP

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

### Formulario 0265 · Omisión del deber de socorro: apelación contra la condena

- Año del modelo: 2022
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 13 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Al Magistrado/a Presidente/a del Tribunal del Jurado de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS], que tengo ya acreditada en el procedimiento número [Nº DE PROCEDIMIENTO] del Tribunal del Jurado, seguido por el delito de omisión del deber de socorro del art. 196 CP, como mejor proceda en derecho, comparezco y DIGO:

Que con fecha [FECHA] le ha sido notificada la sentencia dictada por este Tribunal condenando a mi representado/a a la pena de [PENA] y, no estimándola ajustada a derecho y considerándola lesiva a sus intereses, vengo a interponer recurso de apelación para ante la Sala de lo Civil y Penal del Tribunal Superior de Justicia de [LOCALIDAD] por [ELEGIR: quebrantamiento de las normas y garantías procesales / infracción de precepto constitucional o legal / desestimación indebida a la petición de la disolución del Jurado al no existir prueba de cargo / disolución del Jurado improcedente / vulneración del derecho a la presunción de inocencia], al amparo del artículo 846 bis a de la Ley de Enjuiciamiento Criminal.

ANTECEDENTES

PRIMERO.- En el acta de la votación de los/as Jurados de fecha [FECHA] se contiene el veredicto donde se expresan como hechos probados los siguientes:

[COMPLETAR]

SEGUNDO.- El veredicto considera al/a la acusado/a culpable del delito de omisión del deber de socorro del art. 196 CP, expresando su criterio [ELEGIR: favorable / desfavorable] a la remisión condicional de la pena que se impusiese y también sobre la petición del indulto en la sentencia.

TERCERO.- En el veredicto los/as Jurados han expresado como elementos de convicción para hacer dicha declaración de culpabilidad los siguientes:

CUARTO.- El fallo de la sentencia es del tenor siguiente:

MOTIVOS

ÚNICO.-

Al amparo del artículo 846 bis c de la Ley de Enjuiciamiento Criminal, letra e), se ha vulnerado el derecho a la presunción de inocencia porque, atendida la prueba practicada en el juicio [COMPLETAR], quedó probado que no hubo actuación omisiva alguna por el/la médico, ahora recurrente, sino un mero retraso hasta poder atender al paciente.

Las razones del mínimo retraso, que han quedado acreditadas, fueron [COMPLETAR]

En su virtud,

SUPLICO AL/A LA MAGISTRADO/A-PRESIDENTE/A DEL TRIBUNAL DEL JURADO:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado al Tribunal Superior de Justicia, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

Es de Justicia que pido en [LUGAR], a [FECHA].

Abogado/a:	Procurador/a:

================================================================================
