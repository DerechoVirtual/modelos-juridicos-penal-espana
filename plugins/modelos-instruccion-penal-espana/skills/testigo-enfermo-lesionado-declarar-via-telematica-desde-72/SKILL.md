---
name: testigo-enfermo-lesionado-declarar-via-telematica-desde-72
description: "Redacta el escrito «Testigo enfermo o lesionado: declarar por vía telemática desde casa (desde el 20 de marzo de 2024)» (formulario 72 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Testigo enfermo o lesionado: declarar por vía telemática desde casa (desde el 20 de marzo de 2024)

> Formulario 0072 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 62 LEC regula la apreciación de oficio de la competencia para conocer de los recursos y no tiene relación con este escrito. La cita parece referirse al art. 62 del RDL 6/2023 (puntos de acceso seguros y lugares seguros), vigente desde el 9-1-2024.
- Declarar desde el domicilio no es automático: el art. 137 bis.3 LEC solo permite intervenir «desde cualquier lugar» si el juez lo estima oportuno y se puede asegurar la identidad del declarante. Si el declarante es menor de edad, solo puede hacerlo desde una oficina judicial. La petición debe presentarse al menos diez días antes del señalamiento (art. 137 bis.4 LEC).
- La declaración en el domicilio por enfermedad del art. 364.2 LEC solo procede cuando no pueda hacerse por videoconferencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, según consta acreditado en»

## Elecciones que hay que hacer

- enfermo/a / con lesión impeditiva consistente en [DESCRIBIR] en concreto en la siguiente dirección [COMPLETAR], a cuyo fin solicito que se nos indique en tiempo y forma la plataforma que se puede utilizar para ello
- enfermedad / lesión impeditiva
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral procedimiento abreviado / En fase de juicio oral procedimiento común u ordinario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 364.2 LEC
- art. 258 bis.1 LECRIM
- artículo 137 bis de la Ley 1/2000
- art. 137 bis.4 LEC
- art. 62 del RDL 6/2023

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

### Formulario 0072 · Testigo enfermo o lesionado: declarar por vía telemática desde casa (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 8 campos de relleno marcados en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 75) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito que puede presentar tanto la acusación como la defensa del acusado en cualquier proceso penal, bien en fase de instrucción o en fase de juicio oral, solicitando que el testigo enfermo o con lesiones impeditivas pueda declarar por videoconferencia desde su domicilio, conforme al arts. 258 bis 1 LECRIM y arts. 137 bis.3 y 4 y 364.2 LEC (y art. 62 RDL 6/2023), en base a la redacción dada por RDL 6/2023, de 19 de diciembre, vigentes desde el 20 de marzo de 2024.

---

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral procedimiento abreviado / En fase de juicio oral procedimiento común u ordinario — el texto de cada opción no venía en el formulario original]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en [COMPLETAR] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Que por medio del presente escrito intereso que la comparecencia en sede judicial como testigo de D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo por vía telemática por encontrarse [ELEGIR: enfermo/a / con lesión impeditiva consistente en [DESCRIBIR] en concreto en la siguiente dirección [COMPLETAR], a cuyo fin solicito que se nos indique en tiempo y forma la plataforma que se puede utilizar para ello].

FUNDAMENTOS JURÍDICOS

ÚNICO.-

Como prevé el apartado 1º del artículo 364.2 LEC, de aplicación supletoria en el proceso penal:

"2.Cuando no pueda realizarse por videoconferenciay por enfermedad u otro motivo de los referidos en el apartado 4 del artículo 169, el tribunal considerare que algún testigo no puede comparecer en la sede de aquél, podrá tomársele declaración en su domicilio, bien directamente, bien a través de auxilio judicial, según que dicho domicilio se halle o no en la demarcación del tribunal.

A la declaración podrán asistir las partes y sus abogados, y, si no pudieren comparecer, se les autorizará a que presenten interrogatorio escrito previo con las preguntas que desean formular al testigo interrogado."

Además, el art. 258 bis.1 LECRIM añade que: 1. Constituido el órgano judicial en su sede, los actos de juicio, vistas, audiencias, comparecencias, declaraciones y, en general, todas las actuaciones procesales, se realizarán preferentemente, salvo que el juez o jueza o tribunal, en atención a las circunstancias, disponga otra cosa, mediante presencia telemática,siempre que las oficinas judiciales o fiscales tengan a su disposición los medios técnicos necesarios para ello, con las especialidades previstas en los artículos 325, 731 bis y 306 de la Ley de Enjuiciamiento Criminal, de conformidad con lo dispuesto en el apartado 3 del artículo 229 y artículo 230 de la Ley Orgánica del Poder Judicial, y supletoriamente por lo dispuesto en la el artículo 137 bis de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil. La intervención mediante presencia telemática se practicará siempre a través depunto de acceso seguro, de conformidad con la normativa que regule el uso de la tecnología en la Administración de Justicia."

Por ello, se interesa que, dada la [ELEGIR: enfermedad / lesión impeditiva] que tiene el testigo, y la imposibilidad de comparecer en sede judicial, se interesa que la declaración se lleve a cabo por la plataforma que se indique y desde el lugar de la residencia del testigo sito en habilitando el propio testigo una plataforma on line aceptada por el tribunal para efectuar la conexión desde su domicilio, garantizando la identidad del mismo, previa acreditación oportuna, o constituyéndose en el domicilio un Letrado de la AJ del partido judicial del lugar de residencia del testigo para dar fe de su identidad a la hora de declarar.

Además, se cumple el presupuesto contemplado en el art. 137 bis.4 LEC de que se presenta el escrito diez días antes del señalado para la actuación correspondiente.

Igualmente, se cumple el presupuesto del art. 62 del RDL 6/2023 de 19 de diciembre respecto de la característica de "punto de acceso seguro" por la aceptación previa del órgano judicial del sistema que se designe y la presencia del LAJ del órgano judicial correspondiente para que asista a la verificación de la identidad del declarante desde su domicilio.

Por todo ello

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración del testigo D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo por vía telemática desde su domicilio, designando y comunicándonos en forma la plataforma que se puede utilizar para este fin.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 62 LEC regula la apreciación de oficio de la competencia para conocer de los recursos y no tiene relación con este escrito. La cita parece referirse al art. 62 del RDL 6/2023 (puntos de acceso seguros y lugares seguros), vigente desde el 9-1-2024.]

[NOTA DE REVISIÓN: Declarar desde el domicilio no es automático: el art. 137 bis.3 LEC solo permite intervenir «desde cualquier lugar» si el juez lo estima oportuno y se puede asegurar la identidad del declarante. Si el declarante es menor de edad, solo puede hacerlo desde una oficina judicial. La petición debe presentarse al menos diez días antes del señalamiento (art. 137 bis.4 LEC).]

[NOTA DE REVISIÓN: La declaración en el domicilio por enfermedad del art. 364.2 LEC solo procede cuando no pueda hacerse por videoconferencia.]
