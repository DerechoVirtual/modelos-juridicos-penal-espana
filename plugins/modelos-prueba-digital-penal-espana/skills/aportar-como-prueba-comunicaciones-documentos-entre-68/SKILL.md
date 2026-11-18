---
name: aportar-como-prueba-comunicaciones-documentos-entre-68
description: "Redacta el escrito «Aportar como prueba comunicaciones o documentos entre defensores con autorización» (formulario 68 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Aportar como prueba comunicaciones o documentos entre defensores con autorización

> Formulario 0068 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… quien este escrito firma y el letrado/a»; «…respecto a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- -.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 16.2 y 3 de la Ley Orgánica 5/2024
- art. 23 del Real Decreto 135/2021

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

### Formulario 0068 · Aportar como prueba comunicaciones o documentos entre defensores con autorización

- Año del modelo: 2024
- Revisión 17-11-2026: 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 61) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que un abogado presenta como prueba en la instrucción las comunicaciones que mantuvo con el abogado de la parte contraria, o documentos intercambiados, con ocasión de otro procedimiento de mediación o judicial, ya que pueden utilizarse con autorización, pudiendo tener valor probatorio, conforme al art. 16.2 y 3 LO 5/2024, del Derecho de Defensa y art. 23 RD 135/2021, de 2 de marzo, por el que se aprueba el Estatuto General de la Abogacía Española.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales y de D/Dña. [NOMBRE Y APELLIDOS], como consta acreditado en las diligencias número, ante este órgano judicial comparezco y como mejor en derecho proceda,

DIGO:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Que en el procedimiento de mediación intrajudicial que se llevó a cabo por derivación judicial en fecha [FECHA] se aportaron documentos por los letrados de ambas partes para intentar llegar a un acuerdo y, además, los letrados del presente procedimiento nos fuimos enviando mensajes, bien por correo electrónico y por otros medios de comunicación bidireccional, constando la debida autorización mutua para su uso en el procedimiento judicial.

Que, con ocasión del procedimiento judicial número [Nº DE PROCEDIMIENTO], las partes del presente procedimiento nos enviamos comunicaciones profesionales reservadas a sabiendas de que no podían ser utilizados judicialmente. Ello a salvo de que existiera una debida autorización de su utilización en juicio, como en este caso hubo.

Señala el art. 16.2 y 3 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa, que:

"2. Las comunicaciones mantenidas exclusivamente entre los defensores de las partes con ocasión de un litigio o procedimiento, cualquiera que sea el momento en el que tengan lugar o su finalidad, incluso en fase extrajudicial, son confidenciales y no podrán hacerse valer en juicio ni tendrán valor probatorio, excepto en los casos en los que se hayan obtenido de acuerdo con lo previsto en la Ley de Enjuiciamiento Criminal u otras leyes de aplicación o en que su aportación o revelación haya sido autorizada conforme a la regulación profesional vigente.
3. No se admitirán los documentos, cualquiera que sea su soporte, que contravengan la anterior prohibición,salvo que expresamente sea aceptada su aportación por los profesionales de la abogacía concernidos o las referidas comunicaciones se hayan realizado con la advertencia expresa y explícita de poder ser utilizadas en juicio."

Además, señala el art. 23 del Real Decreto 135/2021, de 2 de marzo, por el que se aprueba el Estatuto General de la Abogacía Española, que lleva por rúbrica Confidencialidad de las comunicaciones entre los profesionales de la Abogacía que:

"El profesional de la Abogacía no podrá aportar a los Tribunales, ni facilitar a su cliente, las cartas, documentos y notas que, como comunicación entre profesionales de la Abogacía, mantenga con el profesional de la Abogacía de la otra parte,salvo que este lo autorice expresamente. Esta prohibición no alcanzará a las cartas, documentos y notas en que intervenga con mandato representativo de su cliente y así lo haga constar expresamente."

En las presentes diligencias se aportan las siguientes comunicaciones que nos cursamos quien este escrito firma y el letrado/a [COMPLETAR] respecto a [COMPLETAR], constando en el correo electrónico que se adjunta como doc. nº 1 la expresa autorización mutua que nos cursamos para que se pudiera hacer uso de ellas en vía judicial.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-.

Con ello, ha habido expresa autorización por ambas partes para que se presenten o utilicen documentos o comunicaciones privadas entre profesionales conforme señala el art. 16.3 antes citado y el art. 23 del Estatuto de la abogacía, por lo que interesa sean admitidos, aunque haciendo la advertencia de la admisibilidad legal de los mismos en base a los preceptos citados.

La interpretación que debe otorgarse al art. 16.2 y 3 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa es la del carácter "utilizable" de estos documentos y comunicaciones por expresa autorización existente por ambas partes.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y sean admitidos los documentos y comunicaciones que se han citado en el presente escrito, para que puedan tener eficacia probatoria en la presente causa por su carácter "utilizable".

Es Justicia que pido en [LUGAR].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
