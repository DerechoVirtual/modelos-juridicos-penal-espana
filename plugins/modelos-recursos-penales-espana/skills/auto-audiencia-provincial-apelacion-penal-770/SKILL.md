---
name: auto-audiencia-provincial-apelacion-penal-770
description: "Redacta el escrito «Auto de la Audiencia Provincial: apelación penal» (formulario 770 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Auto de la Audiencia Provincial: apelación penal

> Formulario 0770 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO (3 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…ugar sede del órgano de apelación, el de»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 846 ter LECRIM
- art. 20.1 CP
- art. 24.2 CE
- artículo 24.2 de la Constitución
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- artículos 790.3 y 791.1 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0770 · Auto de la Audiencia Provincial: apelación penal

- Año del modelo: 2016
- Revisión 17-11-2026: 14 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se presenta recurso de apelación ante el TSJ contra un auto de sobreseimiento de una Audiencia Provincial, por necesitarse más diligencias de prueba, solicitadas en su día en instancia y denegadas, conforme al art. 846 ter LECRIM.

A la Sala de lo Civil y Penal del TSJ de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales (col. nº [NÚMERO]), en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], como ya tengo acreditado en el procedimiento /, bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS] (col. nº [NÚMERO]), ante el tribunal comparezco y, en términos de Derecho, DIGO:

Que, mediante el presente escrito, y según lo dispuesto en el art 846 ter de la Ley de Enjuiciamiento Criminal, en tiempo y forma formulo RECURSO DE APELACIÓN contra el auto de fecha [FECHA] de la Sección nº [NÚMERO] de la Audiencia Provincial de [LOCALIDAD] en la que se ha acordado el sobreseimiento provisional de las diligencias. Y ello por estimarla no ajustada a Derecho, de acuerdo con las siguientes,

ALEGACIONES

ÚNICA.-

Se ha dictado auto de sobreseimiento libre del art. 637.3º LECrim. por entenderse que concurre la circunstancia del art. 20.1 CP, en base al informe forense practicado. Sin embargo, esta parte ya propuso en su momento la pericial contradictoria para acreditar que la situación personal del acusado no llega al extremo de aplicar esta circunstancia del art. 20.1 CP, no siendo admitida y concluyéndose las actuaciones con remisión a la Audiencia, lo que motiva el presente auto ahora recurrido, ya que el informe forense carece de precisión y no reúne los elementos que esta parte ya exigió en su momento, por lo que se interesa se estime el recurso que conllevaría la revocación de la conclusión del sumario para la práctica de la diligencia interesada, que en su momento fue desestimada por la Audiencia cuando fue recurrida la denegación de la práctica de la prueba.

En este sentido, no se han agotado las diligencias de prueba suficientes y necesarias en la instrucción del presente procedimiento penal, lo que ha dado como consecuencia al dictado del presente auto que ahora es objeto de recurso de apelación.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 1/2004, 43/2003): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el órgano judicial la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible.

En el presente caso se cumple la necesidad de que se lleve a cabo esta diligencia, cuya ausencia es la que motiva el auto de sobreseimiento que es ahora objeto de recurso, porque el auto expone que concurre la circunstancia del art. 20.1 CP en relación con el art. 637.3º LECrim.

Se ha procedido pues, con carácter precipitado e invadiendo el derecho a la tutela judicial efectiva, al haberse archivado las diligencias sin haber procedido a la práctica de esta prueba que ya fue interesada en su momento y negada.

Por todo lo anterior,

SUPLICO A LA SALA:

que tenga por interpuesto, en tiempo y forma, RECURSO DE APELACIÓN contra el auto de fecha [FECHA], lo admita con sus copias y, que tras su tramitación, lo eleve a la SALA DE LO CIVIL Y PENAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [LOCALIDAD], y PARA ANTE ÉSTA SUPLICO, que dicte sentencia más ajustada a Derecho, por la que, estimando el recurso, revoque el auto dictado acordando reabrir las diligencias y reponiendo las actuaciones para la práctica de la diligencia expuesta y denegada en la fase de instrucción, lo que motivó el auto de sobreseimiento del art. 637.3º LECrim.

Es justicia que pido en [LUGAR].

PRIMER OTROSÍ DIGO: que de conformidad con el artículo 790.2 de la Ley de Enjuiciamiento Criminal, se designa como domicilio para notificaciones del lugar sede del órgano de apelación, el de [COMPLETAR].

SUPLICO A LA SALA: que tenga por efectuada la anterior designación.

Es justicia que reitero en el lugar y fecha ut supra indicados.

SEGUNDO OTROSÍ DIGO: que, al amparo de los artículos 790.3 y 791.1 de la Ley de Enjuiciamiento Criminal, y por las razones expuestas en la alegación primera,

SUPLICO A LA SALA: que se tenga por propuesta la diligencia de:

a.- Reconocimiento del acusado por el perito propuesto por esta parte D./Dña. [NOMBRE Y APELLIDOS]

Es Justicia que reitero en el lugar y fecha ut supra indicados.

Abogado/a	Procurador/a

================================================================================
