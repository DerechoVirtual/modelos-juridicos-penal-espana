---
name: investigado-acusado-pedir-declarar-via-telematica-desde-71
description: "Redacta el escrito «Investigado o acusado: pedir declarar por vía telemática (desde el 20 de marzo de 2024)» (formulario 71 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Investigado o acusado: pedir declarar por vía telemática (desde el 20 de marzo de 2024)

> Formulario 0071 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- El art. 258 bis LECrim está en vigor desde el 20-3-2024 (DF 9ª.2 RDL 6/2023). El RDL se publicó el 20-12-2023.
- La regla general de presencia telemática tiene excepciones (art. 258 bis.2 LECrim). La presencia física es obligatoria en los juicios por delito grave y en los del Jurado. En los juicios por delito menos grave con pena de prisión superior a 2 años, es física si lo pide el acusado o su letrado o si lo estima el órgano. Si el acusado reside en la misma demarcación del órgano, debe comparecer físicamente, salvo causa justificada o fuerza mayor.
- El acusado que decida no acudir a la sede debe comunicarlo con al menos 5 días de antelación, y su abogado estará con él o en la sede judicial (art. 258 bis.2). Las citaciones solo informan de la posibilidad de declarar telemáticamente (art. 258 bis.5).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, según consta acreditado en»; «… órgano judicial, deberá notificarlo con»

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA
- investigado/a / acusado/a
- la comparecencia ante el juez / el juicio oral

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral procedimiento abreviado / En fase de juicio oral procedimiento común u ordinario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 258 bis.1 LECRIM
- artículo 137 bis de la Ley 1/2000
- art. 258 bis.2 LECRIM

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

### Formulario 0071 · Investigado o acusado: pedir declarar por vía telemática (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 3 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 campos de relleno marcados en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 74) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el acusado en cualquier proceso penal solicita declarar por videoconferencia, tanto en la fase de instrucción como en la de juicio oral, por residir fuera del lugar donde se sigue el juicio y no tratarse de delito grave o ante el Tribunal del Jurado, conforme al art. 258 bis.2, párrafos 2.º y 3.º, LECRIM, según redacción dada por RDL 6/2023, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral procedimiento abreviado / En fase de juicio oral procedimiento común u ordinario — el texto de cada opción no venía en el formulario original]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en [COMPLETAR] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original]

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En fase de instrucción / En fase de juicio oral — el texto de cada opción no venía en el formulario original]

FUNDAMENTOS JURÍDICOS

PRIMERO.- Señala el art. 258 bis.1 LECRIM que:

"1. Constituido el órgano judicial en su sede, los actos de juicio, vistas, audiencias, comparecencias, declaraciones y, en general, todas las actuaciones procesales, se realizarán preferentemente, salvo que el juez o jueza o tribunal, en atención a las circunstancias, disponga otra cosa, mediante presencia telemática, siempre que las oficinas judiciales o fiscales tengan a su disposición los medios técnicos necesarios para ello, con las especialidades previstas en los artículos 325, 731 bis y 306 de la Ley de Enjuiciamiento Criminal, de conformidad con lo dispuesto en el apartado 3 del artículo 229 y artículo 230 de la Ley Orgánica del Poder Judicial, y supletoriamente por lo dispuesto en la el artículo 137 bis de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil. La intervención mediante presencia telemática se practicará siempre a través de punto de acceso seguro, de conformidad con la normativa que regule el uso de la tecnología en la Administración de Justicia."

Añade el art. 258 bis.2, 2º y 3º LECRIM que:

"En los juicios por delito menos grave, cuando la pena exceda de dos años de prisión o, si fuera de distinta naturaleza, cuando su duración no exceda de seis años, el acusado comparecerá físicamente ante la sede del órgano de enjuiciamiento si así lo solicita este o su letrado, o si el órgano judicial lo estima necesario. La decisión deberá adoptarse en auto motivado.

En todo caso, en los procesos y juicios, cuando el acusado resida en la misma demarcación del órgano judicial que conozca o deba conocer de la causa, su comparecencia en juicio deberá realizarse de manera física en la sede del órgano judicial o enjuiciamiento, salvo que concurran causas justificadas o de fuerza mayor."

Con ello, dado que el/la acusado/a reside en demarcación distinta a la del órgano judicial que conoce del asunto, y no se trata por juicio por delito grave ni del Tribunal del Jurado, se interesa que la declaración dese lleve a cabo por vía telemática y se nos designe el punto de acceso seguro donde asistir para la práctica de la videoconferencia.

SEGUNDO.- Dice el párrafo 5º del art. 258 bis.2 LECRIM que:

"Cuando se disponga la presencia física del investigado o acusado, será también necesaria la presencia física de su defensa letrada. Cuando se permita su declaración telemática, el abogado del investigado o acusado comparecerá junto con este o en la sede del órgano judicial."

Por ello, en este caso comparecerá presencialmente en el juicio la dirección técnica del acusado.

Se cumple lo dispuesto en el párrafo 6º del art. 258 bis.2 LECRIM de que Cuando el acusado decida no comparecer en la sede del órgano judicial, deberá notificarlo con [COMPLETAR], al menos, cinco días de antelación.

Por todo ello,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración de D./Dña. [NOMBRE Y APELLIDOS] como [ELEGIR: investigado/a / acusado/a] se lleve a cabo por videoconferencia el día señalado para [ELEGIR: la comparecencia ante el juez / el juicio oral] y se dicte auto motivado aceptando la declaración por vía telemática, así como que designándonos un punto de acceso seguro donde asistir para su práctica.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) A partir del 20 de marzo de 2024, fecha de entrada en vigor del art. 258 bis LECRIM introducido por el RDL 6/2023, la regla general es la declaración del investigado o acusado por videoconferencia, conforme al art. 258 bis LECRIM, lo que se adoptará de oficio y se comunicará en las citaciones, pero ponemos este formulario a su disposición por si esto no ocurriese, en cuyo caso sería necesario proceder a su solicitud

[NOTA DE REVISIÓN: El art. 258 bis LECrim está en vigor desde el 20-3-2024 (DF 9ª.2 RDL 6/2023). El RDL se publicó el 20-12-2023.]

[NOTA DE REVISIÓN: La regla general de presencia telemática tiene excepciones (art. 258 bis.2 LECrim). La presencia física es obligatoria en los juicios por delito grave y en los del Jurado. En los juicios por delito menos grave con pena de prisión superior a 2 años, es física si lo pide el acusado o su letrado o si lo estima el órgano. Si el acusado reside en la misma demarcación del órgano, debe comparecer físicamente, salvo causa justificada o fuerza mayor.]

[NOTA DE REVISIÓN: El acusado que decida no acudir a la sede debe comunicarlo con al menos 5 días de antelación, y su abogado estará con él o en la sede judicial (art. 258 bis.2). Las citaciones solo informan de la posibilidad de declarar telemáticamente (art. 258 bis.5).]
