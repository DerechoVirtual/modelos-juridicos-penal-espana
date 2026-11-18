---
name: pedir-revision-condena-retroactividad-norma-penal-mas-142
description: "Redacta el escrito «Pedir la revisión de la condena por retroactividad de la norma penal más favorable» (formulario 142 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la revisión de la condena por retroactividad de la norma penal más favorable

> Formulario 0142 del plugin **Ejecución penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (6 veces)
- [ ] DELITO (5 veces)
- [ ] PENA (6 veces)
- [ ] Nº (9 veces)
- [ ] LUGAR
- [ ] Otros 21 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del art. del Código Penal, en grado de»; «…entró en vigor la Ley»; «…norma penal más favorable. Aunque la Ley»; «… más favorable será oído el reo". La Ley»; «…años de prisión, a la vigente pena de»; «…mite mínimo; esto es, de la extensión de»; «…dacción del art. del CP, antes de la Ley»; «… le impuso a mi representado/a fue la de»; «…sto es en la mitad inferior del tramo de»; «…r la pena inferior en grado fijándola en»; «…esultando que, tras la reforma de la Ley»; «…, con una pena prevista de»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 2.2 del Código Penal
- art. 2.2 del CP

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

### Formulario 0142 · Pedir la revisión de la condena por retroactividad de la norma penal más favorable

- Año del modelo: 2023
- Revisión 17-11-2026: 51 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de la Audiencia Provincial de [LOCALIDAD]

D/Dª [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D/Dª [NOMBRE Y APELLIDOS], según consta acreditado en la Ejecutoria número, procedente del Rollo, seguida ante el Tribunal al que me dirijo, comparezco y como proceda en Derecho, DIGO:

1) Que en fecha [FECHA] se dictó Sentencia en este proceso por el cual se condenaba a mi representado/a D/Dª [NOMBRE Y APELLIDOS], como autor/a de un delito de [DELITO] del art. del Código Penal, en grado de [COMPLETAR], a la pena de [PENA] de prisión. Dicha Sentencia fue declarada firme en fecha [FECHA].
2) Que en fecha [FECHA] se dictó auto de ejecución de la referida sentencia firme, acordando el ingreso en prisión de mi representado/a, el cual se produjo efectivamente el día [FECHA].
3) Que el pasado día [FECHA] entró en vigor la Ley [COMPLETAR], que minora la pena contemplada para el delito de [DELITO], por el que fue condenado mi representado/a, por lo que, de conformidad a lo dispuesto en el art. 2.2 del Código Penal, solicito la REVISIÓN de la pena impuesta en la expresada Sentencia, con arreglo a los siguientes

HECHOS Y FUNDAMENTOS

PRIMERO.- Por medio del presente escrito se solicita la revisión de la pena impuesta a mi representado/a en la Sentencia expresada, de conformidad a lo dispuesto en el art. 2.2 del Código Penal, por aplicación de la norma penal más favorable.

Aunque la Ley [COMPLETAR] no contempla previsión normativa alguna relativa a la revisión de las sentencias firmes, es de aplicación el art. 2.2 del CP que sienta la retroactividad "pro reo" de las leyes penales más favorables, cuando establece que: "tendrán efecto retroactivo aquellas leyes penales que favorezcan al reo, aunque al entrar en vigor hubiera recaído sentencia firme y el sujeto estuviese cumpliendo condena. En caso de duda sobre la determinación de la ley más favorable será oído el reo".

La Ley [COMPLETAR] ha modificado la pena del delito de [DELITO] tipificado en el art. del CP, reduciendo su franja mínima, que pasa de ser de [Nº] años a [Nº] años, lo cual supone que la pena en abstracto para dicho delito pasa de la pena de [PENA] a [Nº] años de prisión, a la vigente pena de [COMPLETAR] a [Nº] años de prisión.

En el caso de mi representado/a, se le condenó por un delito de [DELITO] del art. del CP, con imposición de la pena inferior en grado, la cual, conforme al art. 70.1.2ª de CP, se forma partiendo de la cifra mínima señalada para el delito de que se trate y deduciendo de esta la mitad de su cuantía, constituyendo el resultado de tal deducción su límite mínimo; esto es, de la extensión de [COMPLETAR] en la redacción del art. del CP, antes de la Ley [COMPLETAR], se pasa a la de [Nº] años en la vigente redacción.

La pena concreta que se le impuso a mi representado/a fue la de [COMPLETAR], esto es en la mitad inferior del tramo de [COMPLETAR], y además próxima al mínimo legal. La traslación de la nueva regulación al caso implicaría que se impusiera una pena en la mitad inferior, que es de [Nº] años, y próxima al mínimo legal, lo que supondría la pena de [PENA], trasladando los mismos criterios seguidos en la individualización de la pena por la Sentencia firme cuya revisión se solicita.

Debemos subrayar que el Tribunal Supremo ya ha sentado la procedencia de la revisión y de la nueva "individualización de la pena cuando, por cualquier razón, los criterios o principios sobre la imposición de la misma resulten alterados o desajustados de acuerdo con la nueva legalidad"(STS nº 346/2016 de 21 de abril). En este sentido, debemos citar, asimismo, por su carácter ejemplificativo, la STS núm. 470/2011, de 26 de mayo, que estima procedente la revisión de la sentencia de condena por delito de tráfico de drogas de las que causan grave daño a la salud por el que el penado fue condenado a la pena de prisión de cinco años y once meses, siendo la pena prevista de tres a nueve años, y tras la reforma operada por la LO 5/2010 de tres a seis años. La Audiencia Provincial estimó improcedente la revisión, lo cual fue rechazado por el Tribunal Supremo, que subraya que, de haber sido juzgado el recurrente conforme a la reforma operada por la citada LO 5/2010 no se le habría impuesto la pena en esa extensión de cinco años y once meses tan próxima al límite máximo (seis años).

Esto es precisamente lo que acontece en el caso de mi representado/a, puesto que, una vez que el Tribunal al que me dirijo se decantó por imponer la pena inferior en grado fijándola en [COMPLETAR], imponiéndola así en la mitad inferior y próxima al mínimo legal, resultando que, tras la reforma de la Ley [COMPLETAR], con una pena prevista de [COMPLETAR], en ningún caso se hubiera impuesto la pena de [PENA], ni atendiendo al principio de proporcionalidad a que debe atender toda resolución judicial, ni atendiendo a las reglas de individualización penal, porque prácticamente está situada en el máximo legal actualmente permitido.

SEGUNDO.- Conforme a lo expuesto anteriormente, la solicitud de revisión de la condena impuesta se funda en el principio de retroactividad de la norma penal más favorable, establecido expresamente en art. 2.2 del Código Penal, como consecuencia de la reforma operada por la Ley [COMPLETAR], por la que, entre otros, se modifica el art. del Código Penal castigando con pena de prisión de [COMPLETAR] el delito de [DELITO].

Por este mismo delito del art. del CP en grado de tentativa fue condenado mi representado/a por el tribunal al que me dirijo, razonando literalmente en su fundamento cuarto: "Respecto a la pena impuesta, el artículo 62 C.P. obliga a imponer la inferior en un grado a los autores de tentativa de delito, siendo del exclusivo arbitrio del Tribunal rebajarle en dos, en la extensión que se estime adecuada, y en atención al "peligro inherente al intento y al grado de ejecución alcanzado." Pues bien, de conformidad con lo dispuesto en dicho precepto, la Sala se inclina por rebajar en un solo grado la pena de prisión prevista en el artículo [COMPLETAR] CP (de [COMPLETAR] a [Nº] años), de manera que su extensión iría de [COMPLETAR] a [Nº] años, inclinándose por fijarla en [COMPLETAR] y todo ello teniendo en cuenta sobre manera que el/la acusado/a realizó la práctica totalidad de los actos que hubiesen conducido a la consumación del delito y que si no lo alcanzó fue, como sabemos, por la oposición de la víctima.

Tras la reforma operada por la Ley [COMPLETAR], la pena correspondiente a la tentativa del art. CP, con rebaja de un grado, es de una extensión de [COMPLETAR] a [Nº] años, por lo que la traslación de los criterios expresados por el Tribunal al que me dirijo nos sitúan en una pena de [PENA] de prisión, solicitando que se revise la pena en esta concreción, por ser conforme al principio de retroactividad de la ley penal más favorable.

Por todo ello;

SUPLICO A LA SALA:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y tenga por solicitada la revisión de la pena impuesta a mi representado/a por la Sentencia firme dictada en este proceso y, tras los trámites correspondientes, acuerde sustituir la pena de [PENA] de prisión impuesta en este proceso, por la de [COMPLETAR] de prisión, por aplicación retroactiva de la ley penal más favorable.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
