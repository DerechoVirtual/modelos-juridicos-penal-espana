---
name: prueba-ilicita-acusado-pide-audiencia-preliminar-antes-60
description: "Redacta el escrito «Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025)» (formulario 60 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025)

> Formulario 0060 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…que tiene acreditada del/de la acusado/a»

## Elecciones que hay que hacer

- abreviado / ordinario
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 785 de la Ley de Enjuiciamiento Criminal
- artículo 785 de la LECRIM

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

### Formulario 0060 · Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025)

- Año del modelo: 2025
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 55) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito que puede presentarse tanto en el p. abreviado como en el ordinario, por el que la defensa del acusado solicita que se celebre una audiencia preliminar al juicio oral para resolver sobre si la prueba presentada es ilícita. Aunque esta audiencia se prevé en el art. 785 LECRIM, conforme a la redacción dada por la LO 1/2025, que entra en vigor a partir del 3 de abril de 2025, no hay inconveniente para pedir una comparecencia previa al juicio oral antes de dicha fecha de entrada en vigor, para resolver la prueba ilícita.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala de lo Penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tiene acreditada del/de la acusado/a [COMPLETAR] en Procedimiento [ELEGIR: abreviado / ordinario] nº [NÚMERO] por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 785 de la Ley de Enjuiciamiento Criminal, según redacción dada por LO 1/2025, solicito la celebración de una audiencia preliminar al juicio oral en base a las siguientes

ALEGACIONES

PRIMERA.- En el presente procedimiento no se ha señalado todavía la fecha de la celebración del juicio oral.

SEGUNDA.- Con fecha [FECHA] se presentó escrito de conclusiones provisionales en la que se solicitaba la declaración de prueba ilícita consistente en [DESCRIBIR].

TERCERA.- Que, además de la existencia de la prueba ilícita anteriormente citada, concurre la conexión de antijuridicidad con los siguientes medios de prueba que se han planteado y propuesto por la fiscalía y por la acusación particular, en cuanto a su directa relación con la prueba planteada como ilícita por esta representación procesal:

CUARTA.- Que al objeto de que no se practique la citada prueba en el juicio oral, por considerarla ilícita esta representación procesal, así como las pruebas derivadas en conexión de antijuridicidad con la anteriormente citada, se solicita que se proceda al señalamiento y celebración de una audiencia preliminar, en donde, al modo previsto en el artículo 785 de la LECRIM, conforme a la redacción dada por LO 1/2025, se proceda a celebrar esta audiencia preliminar para que por este órgano de enjuiciamiento resuelva sobre las citadas pruebas, al objeto de evitar la posible contaminación psicológica del tribunal en el caso de que se practique prueba que luego sea declarada ilícita en la sentencia.

Es por ello por lo que se solicita el señalamiento y celebración de esta audiencia preliminar para que, en la misma y de forma oral, o posteriormente por auto, se resuelva sobre el alegato anteriormente expuesto de prueba ilícita y se proceda después al señalamiento del juicio oral, habiendo resuelto ya esta cuestión, al objeto de una mas adecuada higienización del proceso penal, evitando que la resolución de este alegato efectuado en el escrito de defensa se formule en sentencia y permitiendo con ello, incluso, la posible existencia de una conformidad por esta representación procesal, en el caso de que así fuera posible, lo que se nos impide si no se ha resuelto todavía la alegación de la prueba ilícita expuesta por esta defensa. antes del inicio del juicio oral.

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]

Que tenga por presentado este escrito con sus copias, los admita y por solicitada la celebración de una audiencia preliminar al juicio oral para la resolución previa de la prueba ilícita y prueba derivada en conexión de antijuridicidad ya expuesta en el presente escrito.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Esta comparecencia cabe tanto en procedimiento abreviado como para el sumario para resolver en estos casos el alegato de prueba ilícita planteado por la defensa con carácter previo al juicio oral. Así, la doctrina jurisprudencial del Tribunal Supremo defiende la extensión al ámbito del procedimiento de sumario de aquellas cuestiones beneficiosas que permitan un mejor ejercicio del derecho de defensa. (STS 199/2023 de 21 de marzo, Rec. 1762/2021 y STS. 94/2007 de 14 de febrero)

(2) Este escrito es válido para procedimientos incoados después del 3 de abril de 2025, fecha de entrada en vigor de la LO 1/2025, que modifica el art. 785 LECRIM, a tenor de la DT 9ª LO 1/2025. No obstante, para procedimientos ya incoados antes del 3 de abril de 2025 no debe haber inconveniente para que la defensa pida una comparecencia previa al juicio para resolver la prueba ilícita planteada antes del inicio del juicio oral
