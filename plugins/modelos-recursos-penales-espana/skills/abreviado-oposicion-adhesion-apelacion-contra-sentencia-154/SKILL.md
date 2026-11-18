---
name: abreviado-oposicion-adhesion-apelacion-contra-sentencia-154
description: "Redacta el escrito «Abreviado: oposición a la adhesión a la apelación contra la sentencia» (formulario 154 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abreviado: oposición a la adhesión a la apelación contra la sentencia

> Formulario 0154 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tos autos realizada por la parte apelada»; «…uicio, y de donde resulta claramente que»; «… inocencia, habiéndose practicado prueba»; «…ia expuesta ampliamente en el fundamento»; «…plica correctamente los tipos penales de»; «…da perfectamente descrita la conducta de»; «…lugar, quedan descritas las conductas de»; «…a sentencia recurrida en los fundamentos»; «…, concurre también el tipo de»; «…apelación efectuada por la parte apelada»; «… adhesión formulada por la parte apelada»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 790.1 y 790.6 de la LECrim
- art. 741 de la LECrim

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

### Formulario 0154 · Abreviado: oposición a la adhesión a la apelación contra la sentencia

- Año del modelo: 2023
- Revisión 17-11-2026: 19 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia deplaza nºpara ante la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], parte en el procedimiento abreviado seguido con el número [NÚMERO], según tengo acreditado en autos, ante este órgano judicial comparezco y como mejor proceda en derecho DIGO:

Que esta representación ha sido emplazada en fecha [FECHA] para impugnación a la adhesión a la apelación de la sentencia dictada en estos autos realizada por la parte apelada [COMPLETAR] en su escrito de fecha [FECHA], por lo que, de conformidad a lo dispuesto en el art. 790.1 y 790.6 de la LECrim, mediante el presente escrito me OPONGO A LA ADHESIÓN A LA APELACIÓN en base a los siguientes

MOTIVOS

PRIMERO.- Nos oponemos al correlativo alegado por la apelante adhesiva en relación a la infracción del principio de presunción de inocencia.

Las alegaciones del apelante adhesivo parten de la ausencia de la prueba suficiente para desvirtuar la presunción de inocencia.

La sentencia recurrida razona de forma amplia los múltiples elementos probatorios en que se basa el relato de hechos probados de la sentencia, concordantes con el resultado de la prueba practicada en el acto del juicio, y de donde resulta claramente que [COMPLETAR].

Hay una actividad probatoria suficiente, enervadora de la presunción de inocencia, habiéndose practicado prueba [COMPLETAR]. En cuanto a la participación del/de la acusado/a que impugna la sentencia, existe abundante prueba indiciaria expuesta ampliamente en el fundamento [COMPLETAR] de la sentencia, concluyéndose su participación, tal como sostenía esta parte en el acto del juicio.

En relación a dicha cuestión, debe tenerse en cuenta que, por una parte, ha declarado el Tribunal Supremo de forma reiterada, que se entiende salvaguardado el principio de presunción de inocencia cuando el Juzgador, en las apreciaciones llevadas a cabo en su resolución, ha dispuesto de una actividad probatoria mínima y suficiente, razonablemente de cargo, y revestida de todas las garantías constitucionales y procesales que la legitimen; formando su íntima convicción –estimación en «conciencia» según el art. 741 de la LECrim– y obteniendo un grado de certidumbre que, al menos, supera la simple probabilidad o el mero juicio de verosimilitud.

Teniendo en consideración dicha doctrina Jurisprudencial, del examen de la prueba practicada en el juicio oral no cabe sostener, como hacen los apelantes, que la apreciación del Juzgador no se ajusta a aquélla, pues la sentencia recoge razonadamente una lógica apreciación de la prueba practicada en el acto del juicio. En este sentido, la prueba es suficiente para desvirtuar la presunción de inocencia, y deriva de elementos probatorios de cargo de los que se prueba la participación de los acusados en los hechos delictivos descritos en el relato de hechos probados de la sentencia, debiendo desestimarse el motivo de impugnación sostenido por la parte en su escrito de adhesión.

SEGUNDO.- Nos oponemos al segundo de los motivos de la adhesión, por cuanto que no existe infracción de precepto sustantivo en la calificación de los hechos.

La sentencia recurrida aplica correctamente los tipos penales de [COMPLETAR] a la conducta descrita en los hechos probados, de acuerdo a la calificación sostenida en nuestras conclusiones definitivas. Así, en primer lugar, queda perfectamente descrita la conducta de [COMPLETAR]. En segundo lugar, quedan descritas las conductas de [COMPLETAR]. Por último, y a la vista de los hechos probados y de la argumentación realizada en la sentencia recurrida en los fundamentos [COMPLETAR], concurre también el tipo de [COMPLETAR].

Por tanto, interesamos la desestimación de la adhesión a la apelación efectuada por la parte apelada [COMPLETAR]

En base a lo anterior,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, teniéndome por opuesto a la adhesión formulada por la parte apelada [COMPLETAR] frente a la sentencia dictada por este órgano judicial, en las presentes actuaciones de fecha [FECHA], y tras la pertinente tramitación y remisión de las actuaciones a la Ilma. Audiencia Provincial, se desestime la adhesión a la apelación, manteniendo las pretensiones sostenidas en nuestro escrito de apelación principal.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
