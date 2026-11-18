---
name: sobreseimiento-provisional-oposicion-apelacion-169
description: "Redacta el escrito «Sobreseimiento provisional: oposición a la apelación» (formulario 169 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sobreseimiento provisional: oposición a la apelación

> Formulario 0169 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] ÓRGANO O PERSONA
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nica.- Preceptúa el art. 641 LECRIM que:»; «…La comisión de delito. Para acusar a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766.3 de la Ley de Enjuiciamiento Criminal
- art. 641 LECRIM
- art. 637 LECRIM

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

### Formulario 0169 · Sobreseimiento provisional: oposición a la apelación

- Año del modelo: 2022
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procuradora de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], como consta acreditado en las diligencias previas nº [Nº DE PROCEDIMIENTO], ante el órgano judicial comparezco y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA], se me ha dado traslado del RECURSO DE APELACIÓN interpuesto por la representación procesal de contra el Auto de esta Sección de Instrucción del Tribunal de Instancia de fecha [FECHA] desestimando el recurso de apelación contra el auto de Sobreseimiento Provisional dictado por este órgano judicial de fecha [FECHA].

Por ello, mediante el presente escrito formulo oposición e impugnación al mencionado recurso, en ejercicio del derecho concedido por el art. 766.3 de la Ley de Enjuiciamiento Criminal, sobre la base de las siguientes,

CONCLUSIONES

Única.-

Preceptúa el art. 641 LECRIM que: [COMPLETAR]

"Procederá el sobreseimiento provisional:

1.º Cuando no resulte debidamente justificada la perpetración del delito que haya dado motivo a la formación de la causa.
2.º Cuando resulte del sumario haberse cometido un delito y no haya motivos suficientes para acusar a determinada o determinadas personas como autores, cómplices o encubridores."

En el presente caso, el juez de instrucción ha dictado el auto recurrido en razón a que, de las diligencias practicadas no hay indicios bastantes de:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

La comisión de delito.

Para acusar a [COMPLETAR]

No se trata, por ello, de que el juez instructor esté actuando como juez de enjuiciamiento, sino que la LECRIM faculta al juez para suspender provisionalmente la investigación para no perpetuar en el tiempo unas diligencias contra una persona cuando tras la investigación llevada a cabo no existan indicios relevantes para su continuidad, sin que ello determine que el juez esté valorando prueba sino actuando conforme le permite la LECRIM en el art. 641.

Por ello, las diligencias de investigación no pueden perpetuarse en el tiempo cuando el juez ha estimado que las practicadas no evidencian o arrojan que la causa continúe.

No se vulnera, por ello, la tutela judicial efectiva del recurrente, ya que este derecho constitucional no otorga un correlativo derecho a mantener abiertas unas diligencias cuando los indicios son endebles y no concluyentes. Como decimos, si el juez de instrucción adopta la vía del art. 641 LECRIM no está usurpando funciones del juez del juicio oral, debido a que no todo debe llevarse a juicio oral, ya que el juez puede acordar el sobreseimiento libre por la vía del art. 637 LECRIM, pero también el provisional si las diligencias practicadas no arrojan indicios suficientes. Es conocido que ello no determina el sobreseimiento libre, sino la posibilidad de la reapertura, pero solo si aparecen datos suficientes y relevantes para ello.

No existe, por ello, un derecho inveterado a la "permanencia" de la instrucción sumarial sin plazo alguno y sometiendo al/a la investigado/a al "yugo procesal" de la investigación judicial y a la calificación permanente de "investigado/a" por las negativas consecuencias que ello le repercute.

Por todo ello, solicito la confirmación del auto de sobreseimiento provisional del art. 641 LECRIM en su nº [NÚMERO] y se mantenga el archivo provisional de las diligencias incoadas.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito y me tenga por opuesto al recurso de apelación formulado por [ÓRGANO O PERSONA] ante el auto de fecha postulando el mantenimiento del auto de archivo provisional recurrido.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
