---
name: pedir-testigo-perito-declaren-persona-juicio-oral-desde-73
description: "Redacta el escrito «Pedir que testigo o perito declaren en persona en el juicio oral (desde el 20 de marzo de 2024)» (formulario 73 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que testigo o perito declaren en persona en el juicio oral (desde el 20 de marzo de 2024)

> Formulario 0073 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, según consta acreditado en»; «…O.- Como prevé el art. 258 bis.3 LECRIM:»

## Elecciones que hay que hacer

- testigo / perito
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En procedimiento abreviado / En procedimiento común u ordinario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 258 bis.3 LECRIM

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

### Formulario 0073 · Pedir que testigo o perito declaren en persona en el juicio oral (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 4 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 10 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 76) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito que puede presentar tanto la acusación como la defensa del acusado en cualquier proceso penal, solicitando declaración presencial del testigo o perito, en lugar de por videoconferencia, que es la regla general, en los casos previstos en el art. 258 bis 3 LECRIM, conforme a la redacción dada por RDL 6/2023, de 19 de diciembre, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA OPCIÓN Y REDACTARLA: En procedimiento abreviado / En procedimiento común u ordinario — el texto de cada opción no venía en el formulario original]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en [COMPLETAR] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.- Que en fecha [FECHA] se ha señalado el juicio oral en el procedimiento antes indicado donde consta admitida la declaración como [ELEGIR: testigo / perito] D./Dña. [NOMBRE Y APELLIDOS].

SEGUNDA.- Que por medio del presente intereso que la comparecencia en sede judicial como [ELEGIR: testigo / perito] de D./Dña. [NOMBRE Y APELLIDOS] se haga presencialmente.

FUNDAMENTOS JURÍDICOS

ÚNICO.-

Como prevé el art. 258 bis.3 LECRIM: [COMPLETAR]

"3. Se garantizará especialmente que las declaraciones o interrogatorios de las partes acusadoras, testigos o peritos se realicen de forma telemática en los siguientes supuestos, salvo que el Juez o Tribunal, mediante resolución motivada, en atención a las circunstancias del caso concreto, estime necesaria su presencia física:
a) Cuando sean víctimas de violencia de género, de violencia sexual, de trata de seres humanos o cuando sean víctimas menores de edad o con discapacidad. Todas ellas podrán intervenir desde los lugares donde se encuentren recibiendo oficialmente asistencia, atención, asesoramiento o protección, o desde cualquier otro lugar, siempre que dispongan de medios suficientes para asegurar su identidad y las adecuadas condiciones de la intervención.
b) Cuando el testigo o perito comparezca en su condición de Autoridad o funcionario público, realizando entonces su intervención desde un punto de acceso seguro."

En el caso presente concurren las condiciones para que la declaración de D./Dña. [NOMBRE Y APELLIDOS] se lleve a cabo de forma telemática, no obstante lo cual interesamos que, dada la importancia del juicio y la necesidad de que la inmediación en la práctica del interrogatorio sea máxima, para poder destacar el lenguaje gestual con la mayor precisión por parte del tribunal que observe las declaraciones, es por lo que se interesa que se lleve a cabo la comparecencia del testigo o perito de forma presencial, garantizando, en su caso, la evitación de la victimización secundaria en la forma que se estime procedente e, incluso, acordando la celebración del juicio de forma cerrada para evitar presencia de familiares del/de la acusado/a que puedan atemorizar al testigo o perito. Pero, en cualquier caso, consideramos primordial que se escuche de forma presencial a D./Dña. [NOMBRE Y APELLIDOS] y no de forma telemática.

Por todo ello,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración de D./Dña. [NOMBRE Y APELLIDOS] como [ELEGIR: testigo / perito] se lleve a cabo presencialmente el día señalado para el juicio en la sede física del órgano judicial.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
