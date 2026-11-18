---
name: pedir-testigo-perito-declaren-via-telematica-desde-20-74
description: "Redacta el escrito «Pedir que testigo o perito declaren por vía telemática (desde el 20 de marzo de 2024)» (formulario 74 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que testigo o perito declaren por vía telemática (desde el 20 de marzo de 2024)

> Formulario 0074 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, según consta acreditado en»; «…o, en concreto en la siguiente dirección»; «…El art. 258 bis 1 LECRIM añade que:»

## Elecciones que hay que hacer

- sede judicial / juicio oral
- testigo / perito
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de declaración de testigo / En caso de declaración de perito — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 137 bis.2 LEC
- artículo 137 bis de la Ley 1/2000
- art. 137 bis.4 LEC

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

### Formulario 0074 · Pedir que testigo o perito declaren por vía telemática (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 77) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito tanto de la acusación como de la defensa del acusado por el que se solicita que la declaración de un testigo o un perito en la instrucción o en el juicio oral de un proceso penal se realice por videoconferencia, por residir fuera de la demarcación judicial correspondiente, conforme a los arts. 137 bis 2 y 364.1 LEC, de aplicación supletoria en base al art. 258 bis LECRIM, según redacción dada por RDL 6/2023, de 19 de diciembre, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en [COMPLETAR] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Que por medio del presente escrito intereso que la comparecencia en [ELEGIR: sede judicial / juicio oral] como [ELEGIR: testigo / perito] de D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo por videoconferencia por residir fuera del lugar donde se sigue el juicio, en concreto en la siguiente dirección [COMPLETAR], a cuyo fin solicitamos se nos indique en tiempo y forma el lugar donde se debe dirigir mi representado/a para la citada declaración.

FUNDAMENTOS JURÍDICOS

ÚNICO.-

Como prevé el art. 137 bis.2 LEC: "Las partes, peritos y testigos que deban intervenir en cualquier actuación por videoconferencia lo harán desde la oficina judicial correspondiente al partido judicial de su domicilio o lugar de trabajo."

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de declaración de testigo / En caso de declaración de perito — el texto de cada opción no venía en el formulario original]

El art. 258 bis 1 LECRIM añade que: [COMPLETAR]

"1. Constituido el órgano judicial en su sede, los actos de juicio, vistas, audiencias, comparecencias, declaraciones y, en general, todas las actuaciones procesales, se realizarán preferentemente, salvo que el juez o jueza o tribunal, en atención a las circunstancias, disponga otra cosa, mediante presencia telemática,siempre que las oficinas judiciales o fiscales tengan a su disposición los medios técnicos necesarios para ello, con las especialidades previstas en los artículos 325, 731 bis y 306 de la Ley de Enjuiciamiento Criminal, de conformidad con lo dispuesto en el apartado 3 del artículo 229 y artículo 230 de la Ley Orgánica del Poder Judicial, y supletoriamente por lo dispuesto en la el artículo 137 bis de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil. La intervención mediante presencia telemática se practicará siempre a través de punto de acceso seguro, de conformidad con la normativa que regule el uso de la tecnología en la Administración de Justicia."

Por ello, se interesa que el punto al que deba asistir a declarar por videoconferencia lo sea en el del lugar de la residencia del [ELEGIR: testigo / perito] sito en

Además, se cumple el presupuesto contemplado en el art. 137 bis.4 LEC de que se presenta el escrito diez días antes del señalado para la actuación correspondiente

Por todo ello, se ruega se me indique el lugar al que debe acudir [ELEGIR: testigo / perito] para declarar por videoconferencia.

Por todo ello

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración del [ELEGIR: testigo / perito] D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo por videoconferencia designando y comunicándonos en forma el lugar al que se debe acudir para esa declaración.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
