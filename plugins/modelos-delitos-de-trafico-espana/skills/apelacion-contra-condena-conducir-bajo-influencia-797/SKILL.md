---
name: apelacion-contra-condena-conducir-bajo-influencia-797
description: "Redacta el escrito «Apelación contra la condena por conducir bajo la influencia del alcohol» (formulario 797 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por conducir bajo la influencia del alcohol

> Formulario 0797 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…os. Señala el artículo 746 de la LECrim:»; «…o la práctica de la prueba testifical de»; «…Firma de Abogado/a Firma de Procurador/a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 379 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 746 de la LECrim
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

### Formulario 0797 · Apelación contra la condena por conducir bajo la influencia del alcohol

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 10 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso contra sentencia condenatoria en procedimiento abreviado por delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, basado en quebrantamiento de las normas y garantías procesales por no haber suspendido el juicio oral ante la incomparecencia de un testigo de cargo y en error en la apreciación de la prueba, puesto que la tasa de alcohol no supera los límites legales y no consta acreditado que el recurrente tuviera signos externos de circular bajo la influencia del alcohol.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del condenado/a D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] por delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal (1), para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

PRIMERA: La sentencia recurrida ha quebrantado las normas y garantías procesales por cuanto:

El acto del juicio oral no se suspendió cuando no pudo comparecer como testigo el que propusimos y nos fue admitido en el escrito de defensa Dr./Dra. que se encontraba enfermo el día del juicio y que podía haber acreditado lo que fue nuestra justificación acerca de la inexistencia de signos externos de conducir bajo los efectos del alcohol y la negativa a ser llevado a un centro hospitalario para que se procediera a la extracción de sangre para poder realizar esta prueba, por lo que la declaración del testigo era fundamental para acreditar estos extremos.

Señala el artículo 746 de la LECrim: [COMPLETAR]

"Procederá además la suspensión del juicio oral en los casos siguientes:

3.º Cuando no comparezcan los testigos de cargo y de descargo ofrecidos por las partes y el Tribunal considere necesaria la declaración de los mismos."

En este caso no compareció un testigo de cargo por lo que se interesa la nulidad del juicio y sentencia por no haberse acordado la suspensión del juicio ante la incomparecencia del testigo de cargo propuesto en forma por la defensa.

SEGUNDA: La resolución que se recurre padece errores en la apreciación de la prueba como se explica:

No hubo delito del art. 379 CP, ya que en el mismo se recoge la presunción de conducir bajo la influencia de bebidas alcohólicas cuando la medición de alcoholemia en tasa de alcohol por litro de aire espirado sea superior a 0,6 miligramos por litro. Pero la medición de alcoholemia en tasa de alcohol por litro de aire espirado fue de 0,3 miligramos por litro, y por ello mi mandante prefería optar por la prueba de extracción de sangre, además de no existir signos externos de estar influido en su conducción por haber ingerido bebidas alcohólicas. De suyo consta en el atestado policial al folio nº [NÚMERO] de las actuaciones informe de la fuerza actuante en el que se comprueba la "inexistencia de claros y contundentes signos externos" de conducir bajo la influencia de bebidas alcohólicas, por lo que en su caso integraría una infracción administrativa, pero nunca un delito del art. 379 CP, habida cuenta que la inexistencia de signos externos excluye la posible comisión de este delito.

Con ello, no constando en el recurrente signos externos suficientes de circular bajo la influencia de bebidas alcohólicas no puede considerarse punible esta conducta, más aún cuando el recurrente interesó una prueba más fiable que la del aire espirado, como la de la extracción de sangre, que no se llevó a cabo.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado de la condena impuesta o, en su defecto, se decrete la nulidad del juicio y sentencia y se vuelva a celebrar acordando la práctica de la prueba testifical de [COMPLETAR] que no se llevó a cabo ante su incomparecencia.

OTROSÍ DIGO: Que conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

[COMPLETAR]

NOTAS DEL FORMULARIO

(1) La Ley 41/2015 de modificación de la Ley de Enjuiciamiento Criminal para la agilización de la justicia penal y el fortalecimiento de las garantías procesales, con entrada en vigor el 6 de diciembre de 2015, modifica el artículo 792 de la LECrim estableciendo que la sentencia de apelación no podrá condenar al encausado que resultó absuelto en primera instancia ni agravar la sentencia condenatoria que le hubiera sido impuesta por error en la apreciación de las pruebas en los términos previstos en el tercer párrafo del artículo 790.2 LECrim. No obstante, la sentencia, absolutoria o condenatoria, podrá ser anulada y, en tal caso, se devolverán las actuaciones al órgano que dictó la resolución recurrida. La sentencia de apelación concretará si la nulidad ha de extenderse al juicio oral y si el principio de imparcialidad exige una nueva composición del órgano de primera instancia en orden al nuevo enjuiciamiento de la causa. Cuando la sentencia apelada sea anulada por quebrantamiento de una forma esencial del procedimiento, el tribunal, sin entrar en el fondo del fallo, ordenará que se reponga el procedimiento al estado en que se encontraba en el momento de cometerse la falta, sin perjuicio de que conserven su validez todos aquellos actos cuyo contenido sería idéntico no obstante la falta cometida.

Si se tratase del procedimiento para el enjuiciamiento rápido de determinados delitos se aplicaría el art. 803 LECrim.

================================================================================
