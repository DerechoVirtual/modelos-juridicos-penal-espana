---
name: menor-afectado-proceso-penal-representante-pide-sea-oido-64
description: "Redacta el escrito «Menor afectado por un proceso penal: su representante pide que sea oído» (formulario 64 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Menor afectado por un proceso penal: su representante pide que sea oído

> Formulario 0064 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- El art. 234.2 LOPJ, en la redacción de la LO 1/2025 vigente desde el 23-1-2025, regula el acceso a la información y a los documentos del procedimiento de quien acredite un «interés legítimo y directo». El derecho a ser oído antes de la decisión lo reconoce el art. 7 LO 5/2024, que para los menores remite al art. 9 LO 1/1996.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS
- [ ] LOCALIDAD
- [ ] ÓRGANO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…resentante legal del/de la menor de edad»

## Elecciones que hay que hacer

- las diligencias previas / el sumario

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 234 de la Ley Orgánica 6/1985
- art. 7.1 de la Ley Orgánica 5/2024
- artículo 9 de la Ley Orgánica 1/1996
- artículo 302 LECrim
- art. 234 LOPJ
- art. 7 LO 5/2024

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

### Formulario 0064 · Menor afectado por un proceso penal: su representante pide que sea oído

- Año del modelo: 2024
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 58) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito mediante el que el representante de una persona menor de edad que tiene un interés legítimo en un procedimiento, solicita que se oiga al menor, antes de personarse en las actuaciones y obtener la condición de parte, conforme al art. 234 LOPJ, art. 7 LO 5/2024, del Derecho de Defensa y art. 9 LO 1/1996, de Protección Jurídica del Menor.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº con domicilio en [LOCALIDAD], actuando como representante legal del/de la menor de edad [COMPLETAR], en [ELEGIR: las diligencias previas / el sumario] número, comparezco ante este órgano jjudicial y por medio del presente escrito

DIGO:

Que mediante [ÓRGANO] he conocido que se tramitan las presentes diligencias y, en razón al interés legítimo que tengo en las mismas, en base a un interés jurídico específico y reforzado consistente en que, al haber conocido el contenido de la denuncia formulada por contra y determinadas cuestiones que han surgido y que afectan personalmente a mi hijo/a menor de edad, es por lo que entiendo que debe ser escuchado, asistido por quien suscribe, mediante la oportuna citación judicial, a fin de declarar sobre los hechos que se están tramitando, antes de que se dicte una resolución judicial, en la medida en que le afectan, así como para aportar documentos, lo que, mediante la invocación del artículo 234 de la Ley Orgánica 6/1985, de 1 de julio, del Poder Judicial, determina el acceso, previo a la personación en las actuaciones, a esa información.

El referido precepto dispone lo siguiente:

"1. Los Letrados de la Administración de Justicia y funcionarios competentes de la Oficina judicial facilitarán a los interesados cuanta información soliciten sobre el estado de las actuaciones judiciales, que podrán examinar y conocer, salvo que sean o hubieren sido declaradas secretas o reservadas conforme a la ley.
2. Las partes y cualquier persona que acredite un interés legítimo y directo tendrán derecho a acceder a la información existente en los procedimientos judiciales y a consultar, en la forma dispuesta en las leyes procesales y, en su caso, en la ley que regule el uso de las tecnologías en la Administración de Justicia, los escritos y documentos que consten en los autos, no declarados secretos ni reservados. También tendrán derecho a que se les expidan los testimonios y certificados en los casos y a través del cauce establecido en las leyes procesales.

Además, señala el párrafo 2º del art. 7.1 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa que:

"Cuando se trate de menores, tienen derecho a ser oídos en cualquier procedimiento administrativo, judicial o de mediación en que estén afectados en los términos y con las garantías del artículo 9 de la Ley Orgánica 1/1996, de 15 de enero, de Protección Jurídica del Menor, de modificación parcial del Código Civil y de la Ley de Enjuiciamiento Civil."

Es necesario, por ello, el acceso a ciertos contenidos de la causa con antelación a la adquisición de la condición de parte, en el caso de que así se considere, a la que la Ley de Enjuiciamiento Criminal vincula la obtención del pleno conocimiento de las actuaciones judiciales, con la excepción de las que se encuentren secretas, y a los solos efectos del procedimiento (artículo 302 LECrim.).

Hay que señalar, también, que el artículo 9 de la Ley Orgánica 1/1996, de 15 de enero, de Protección Jurídica del Menor, de modificación parcial del Código Civil y de la Ley de Enjuiciamiento Civil. que lleva por rúbrica Derecho a ser oído y escuchado dice lo siguiente:

"1. El menor tiene derecho a ser oído y escuchado sin discriminación alguna por edad, discapacidad o cualquier otra circunstancia, tanto en el ámbito familiar como en cualquier procedimiento administrativo, judicial o de mediación en que esté afectado y que conduzca a una decisión que incida en su esfera personal, familiar o social, teniéndose debidamente en cuenta sus opiniones, en función de su edad y madurez. Para ello, el menor deberá recibir la información que le permita el ejercicio de este derecho en un lenguaje comprensible, en formatos accesibles y adaptados a sus circunstancias.

En los procedimientos judiciales o administrativos, las comparecencias o audiencias del menor tendrán carácter preferente, y se realizarán de forma adecuada a su situación y desarrollo evolutivo, con la asistencia, si fuera necesario, de profesionales cualificados o expertos, cuidando preservar su intimidad y utilizando un lenguaje que sea comprensible para él, en formatos accesibles y adaptados a sus circunstancias informándole tanto de lo que se le pregunta como de las consecuencias de su opinión, con pleno respeto a todas las garantías del procedimiento.

2. Se garantizará que el menor, cuando tenga suficiente madurez, pueda ejercitar este derecho por sí mismo o a través de la persona que designe para que le represente. La madurez habrá de valorarse por personal especializado, teniendo en cuenta tanto el desarrollo evolutivo del menor como su capacidad para comprender y evaluar el asunto concreto a tratar en cada caso. Se considera, en todo caso, que tiene suficiente madurez cuando tenga doce años cumplidos.

Para garantizar que el menor pueda ejercitar este derecho por sí mismo será asistido, en su caso, por intérpretes. El menor podrá expresar su opinión verbalmente o a través de formas no verbales de comunicación.

No obstante, cuando ello no sea posible o no convenga al interés del menor se podrá conocer la opinión del menor por medio de sus representantes legales, siempre que no tengan intereses contrapuestos a los suyos, o a través de otras personas que, por su profesión o relación de especial confianza con él, puedan transmitirla objetivamente."

La existencia del "interés legítimo" invocado no se puede restringir a la exigencia de una personación como acusación particular, ya que la viabilidad del acceso a cierta información de la instrucción (como es el atestado o la denuncia y determinadas diligencias que se dirán en su momento una vez se acceda a la información) es un derecho reconocido en el art. 234 LOPJ y art. 7 LO 5/2024, por cuanto concurre el referido interés legítimo en base a las razones que a continuación se exponen:

Hay que recordar que el derecho del menor a ser «oído y escuchado» es norma de orden público, indisponible y por tanto, de inexcusable observancia para todos los poderes públicos (STC 141/2000, de 29 de mayo, FJ 5). Solamente podría impedirse en los casos en que resulte un "interés del menor" el hecho de que no se le implique en determinada investigación. Pero en este caso ocurre lo contrario, ya que es el menor por medio de su representación legal el que desea comparecer y que se le reciba declaración por las razones invocadas.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y se tenga por alegado el "interés legítimo" del menor al que represento en el acceso al conocimiento de las presentes diligencias interesando se le cite judicialmente para ser oído y aportar documentos, reservándome el derecho para personarme en la causa en su representación legal cuando tenga acceso a la información.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma del representante legal del menor

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 234.2 LOPJ, en la redacción de la LO 1/2025 vigente desde el 23-1-2025, regula el acceso a la información y a los documentos del procedimiento de quien acredite un «interés legítimo y directo». El derecho a ser oído antes de la decisión lo reconoce el art. 7 LO 5/2024, que para los menores remite al art. 9 LO 1/1996.]
