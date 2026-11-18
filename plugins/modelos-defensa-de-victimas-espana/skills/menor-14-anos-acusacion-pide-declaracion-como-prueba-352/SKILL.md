---
name: menor-14-anos-acusacion-pide-declaracion-como-prueba-352
description: "Redacta el escrito «Menor de 14 años: la acusación pide su declaración como prueba preconstituida» (formulario 352 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Menor de 14 años: la acusación pide su declaración como prueba preconstituida

> Formulario 0352 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] NÚMERO
- [ ] DELITO (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… que comparezca en ese órgano judicial a»; «…r LECRIM. Señala el art. 449 bis LECRIM:»; «…enor, y que son las siguientes, a saber:»

## Elecciones que hay que hacer

- madre / padre
- acusación / calificación provisional

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 449 bis LECRIM
- art. 449 ter LECRIM
- artículo 777.3 LECRIM

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

### Formulario 0352 · Menor de 14 años: la acusación pide su declaración como prueba preconstituida

- Año del modelo: 2021
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 13 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusación particular en las DP número [NÚMERO], instruido por este órgano judicial, por el presunto delito de [DELITO], contra D./Dña. [NOMBRE Y APELLIDOS], como mejor proceda en derecho, DIGO:

Que se ha citado para que comparezca en ese órgano judicial a [COMPLETAR], de [Nº] años de edad, que acudirá acompañado por su [ELEGIR: madre / padre] D./Dña. [NOMBRE Y APELLIDOS], como representante legal.

En base a lo dispuesto en el art. 449 bis LECRIM y, sobre todo, del art. 449 ter LECRIM conforme a la redacción dada por la Ley Orgánica de protección de la infancia y adolescencia contra la violencia, solicito que la declaración del/de la menor sea grabada como prueba preconstituida y se guarde la misma para su conservación, de cara a ser reproducida en el juicio oral, a lo que ya haremos mención en nuestro escrito de [ELEGIR: acusación / calificación provisional]. Todo ello al tratarse de un delito de [DELITO] contemplado en el art. 449 ter LECRIM.

Señala el art. 449 bis LECRIM: [COMPLETAR]

"Cuando, en los casos legalmente previstos, la autoridad judicial acuerde la práctica de la declaración del testigo como prueba preconstituida, la misma deberá desarrollarse de conformidad con los requisitos establecidos en este artículo.

La autoridad judicial garantizará el principio de contradicción en la práctica de la declaración. La ausencia de la persona investigada debidamente citada no impedirá la práctica de la prueba preconstituida, si bien su defensa letrada, en todo caso, deberá estar presente. En caso de incomparecencia injustificada del defensor de la persona investigada o cuando haya razones de urgencia para proceder inmediatamente, el acto se sustanciará con el abogado de oficio expresamente designado al efecto.

La autoridad judicial asegurará la documentación de la declaración en soporte apto para la grabación del sonido y la imagen, debiendo el Letrado de la Administración de Justicia, de forma inmediata, comprobar la calidad de la grabación audiovisual. Se acompañará acta sucinta autorizada por el Letrado de la Administración de Justicia, que contendrá la identificación y firma de todas las personas intervinientes en la prueba preconstituida.

Para la valoración de la prueba preconstituida obtenida conforme a lo previsto en los párrafos anteriores, se estará a lo dispuesto en el artículo 730.2."

Además, el art. 449 ter LECRIM añade:

"Cuando una persona menor de catorce años o una persona con discapacidad necesitada de especial protección deba intervenir en condición de testigo en un procedimiento judicial que tenga por objeto la instrucción de un delito de homicidio, lesiones, contra la libertad, contra la integridad moral, trata de seres humanos, contra la libertad e indemnidad sexuales, contra la intimidad, contra las relaciones familiares, relativos al ejercicio de derechos fundamentales y libertades públicas, de organizaciones y grupos criminales y terroristas y de terrorismo, la autoridad judicial acordará, en todo caso, practicar la audiencia del menor como prueba preconstituida, con todas las garantías de la práctica de prueba en el juicio oral y de conformidad con lo establecido en el artículo anterior.

Este proceso se realizará con todas las garantías de accesibilidad y apoyos necesarios.

La autoridad judicial podrá acordar que la audiencia del menor de catorce años se practique a través de equipos psicosociales que apoyarán al tribunal de manera interdisciplinar e interinstitucional, recogiendo el trabajo de los profesionales que hayan intervenido anteriormente y estudiando las circunstancias personales, familiares y sociales de la persona menor o con discapacidad, para mejorar el tratamiento de los mismos y el rendimiento de la prueba. En este caso, las partes trasladarán a la autoridad judicial las preguntas que estimen oportunas quien, previo control de su pertinencia y utilidad, se las facilitará a las personas expertas. Una vez realizada la audiencia del menor, las partes podrán interesar, en los mismos términos, aclaraciones al testigo.

La declaración siempre será grabada y el juez, previa audiencia de las partes, podrá recabar del perito un informe dando cuenta del desarrollo y resultado de la audiencia del menor.

Para el supuesto de que la persona investigada estuviere presente en la audiencia del menor se evitará su confrontación visual con el testigo, utilizando para ello, si fuese necesario, cualquier medio técnico.

Las medidas previstas en este artículo podrán ser aplicables cuando el delito tenga la consideración de leve."

También en el artículo 777.3 LECRIM se añade:

«3. Cuando una persona menor de catorce años o una persona con discapacidad necesitada de especial protección deba intervenir en condición de testigo, será de aplicación lo dispuesto en el artículo 449 ter, debiendo la autoridad judicial practicar prueba preconstituida, siempre que el objeto del procedimiento sea la instrucción de alguno de los delitos relacionados en tal artículo. A efectos de su valoración como prueba en sentencia, la parte a quien interese deberá instar en el juicio oral la reproducción de la grabación audiovisual, en los términos del artículo 730.2.»

Por cumplirse en el presente caso con todos los requisitos legales, es viable instar que se proceda a la grabación de la declaración del/de la menor, y a fin de dar cumplimiento a lo preceptuado en el art. 449 ter LECRIM, transcribo las preguntas que se interesa sean leídas en la exploración al menor, y que son las siguientes, a saber:

[COMPLETAR]

Se interesa que. en el caso de comparecer el investigado, se garantice que no exista contacto físico y/o visual con el menor para evitar su victimización.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, se sirva admitirlo y se proceda a realizar la exploración del/de la menor como prueba preconstituida, grabada de cara a su conservación, para ser reproducida el día del juicio oral, realizándose las preguntas que se relacionan en el presente escrito.

Es Justicia que pido en [LUGAR]

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
