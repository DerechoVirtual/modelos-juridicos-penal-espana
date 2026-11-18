---
name: apelacion-contra-condena-negarse-pruebas-alcoholemia-800
description: "Redacta el escrito «Apelación contra la condena por negarse a las pruebas de alcoholemia» (formulario 800 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por negarse a las pruebas de alcoholemia

> Formulario 0800 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] NÚMERO (2 veces)
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…extremos. Señala el Artículo 746 LECrim:»; «…o la práctica de la prueba testifical de»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- OTROSÍ DIGO: que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 383 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 380 del CP
- art. 379 del CP
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- artículo 792 de la LECrim
- artículo 790.2 LECrim
- art. 803 LECrim
- Ley 41/2015

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

### Formulario 0800 · Apelación contra la condena por negarse a las pruebas de alcoholemia

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación contra sentencia condenatoria en procedimiento abreviado por delito de negativa de someterse a las pruebas de alcoholemia del art. 383 CP, basado en quebrantamiento de las garantías procesales, por no suspender el juicio oral ante incomparecencia de testigo de cargo y errores en la apreciación de la prueba, por haber pedido el acusado una prueba de extracción de sangre en lugar de la de aire espirado.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], condenado en el juicio oral número [NÚMERO] por delito de negativa a someterse a las pruebas de alcoholemia del art. 383 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal (1), para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

PRIMERA: La sentencia recurrida ha quebrantado las normas y garantías procesales por cuanto:

En el acto del juicio oral no se suspendió cuando no pudo comparecer como testigo el que propusimos y nos fue admitido en el escrito de defensa Dr./a. que se encontraba enfermo el día del juicio y que podía haber acreditado lo que fue nuestra justificación acerca de la negativa a ser llevado a un centro hospitalario para que se procediera a la extracción de sangre para poder realizar esta prueba, por lo que la declaración del testigo era fundamental para acreditar estos extremos.

Señala el Artículo 746 LECrim: [COMPLETAR]

"Procederá además la suspensión del juicio oral en los casos siguientes:

3.º Cuando no comparezcan los testigos de cargo y de descargo ofrecidos por las partes y el Tribunal considere necesaria la declaración de los mismos."

En este caso no compareció un testigo de cargo por lo que se interesa la nulidad del juicio y sentencia por no haberse acordado la suspensión del juicio ante la incomparecencia del testigo de cargo propuesto en forma por la defensa.

SEGUNDA: La resolución que se recurre padece errores en la apreciación de la prueba como se explica:

No hubo negativa a someterse a la prueba de alcoholemia ya que fue un control rutinario de los agentes en el que no se negó el recurrente a someterse a la prueba de alcoholemia, sino que prefería optar por la prueba de extracción de sangre, además de no existir signos externos de estar influido por la conducción de bebidas alcohólicas. De suyo consta en el atestado policial al folio nº [NÚMERO] de las actuaciones informe de la fuerza actuante en el que se comprueba la "inexistencia de signos externos" de conducir bajo la influencia de bebidas alcohólicas, por lo que en su caso integraría una infracción administrativa, pero nunca un delito del art. 383 CP, habida cuenta que la inexistencia de signos externos excluye la posible comisión de este delito.

La Sentencia APB (10ª) de 14 Febrero 2000 Nº rec. 219/1999, concluye que:

"El art. 380 del CP, (ahora 383) exige, además de que se constate la existencia de indicios de haberse cometido el delito del art. 379 del CP, que el agente informado de la obligación legal de someterse a la prueba de alcoholemia, se niegue a ello —en el presente caso, no ha quedado probada la negativa del acusado a someterse a la prueba- puede sospecharse que el acusado utilizó un ardid para evitar la prueba, pero no es más que una sospecha -la condena debe basarse en auténticas pruebas de cargo suficientemente incriminatorias—".

También, la Sentencia de la Audiencia Provincial de Badajoz, Sección 3ª, 68/2004 de 30 Mar. 2004, Rec. 64/2004, apunta que:

"La negativa al sometimiento a la prueba de alcoholemia no constituye delito cuando no se aprecian signos de intoxicación etílica en el conductor."

Con ello, no constando en el recurrente signos externos suficientes de circular bajo la influencia de bebidas alcohólicas no puede considerarse punible esta conducta, más aún cuando el recurrente interesó una prueba más fiable como la de la extracción de sangre, que no se llevó a cabo.

En base a ello no ha existido delito del art. 383 CP.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado de la condena impuesta, o en su defecto se decrete la nulidad del juicio y sentencia y se vuelva a celebrar acordando la práctica de la prueba testifical de [COMPLETAR] que no se llevó a cabo ante su incomparecencia.

[OPCIONAL — incluir si procede]

OTROSÍ DIGO: que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: que tenga por efectuada la anterior designación.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) La Ley 41/2015 de modificación de la Ley de Enjuiciamiento Criminal para la agilización de la justicia penal y el fortalecimiento de las garantías procesales, modifica el artículo 792 de la LECrim estableciendo que la sentencia de apelación no podrá condenar al encausado que resultó absuelto en primera instancia ni agravar la sentencia condenatoria que le hubiera sido impuesta por error en la apreciación de las pruebas en los términos previstos en el tercer párrafo del artículo 790.2 LECrim. No obstante, la sentencia, absolutoria o condenatoria, podrá ser anulada y, en tal caso, se devolverán las actuaciones al órgano que dictó la resolución recurrida. La sentencia de apelación concretará si la nulidad ha de extenderse al juicio oral y si el principio de imparcialidad exige una nueva composición del órgano de primera instancia en orden al nuevo enjuiciamiento de la causa. Cuando la sentencia apelada sea anulada por quebrantamiento de una forma esencial del procedimiento, el tribunal, sin entrar en el fondo del fallo, ordenará que se reponga el procedimiento al estado en que se encontraba en el momento de cometerse la falta, sin perjuicio de que conserven su validez todos aquellos actos cuyo contenido sería idéntico no obstante la falta cometida.

Si se tratase del procedimiento para el enjuiciamiento rápido de determinados delitos se aplicaría el art. 803 LECrim.

================================================================================
