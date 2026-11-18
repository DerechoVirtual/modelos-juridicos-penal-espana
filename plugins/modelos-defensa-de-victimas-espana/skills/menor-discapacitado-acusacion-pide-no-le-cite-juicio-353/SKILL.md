---
name: menor-discapacitado-acusacion-pide-no-le-cite-juicio-353
description: "Redacta el escrito «Menor o discapacitado: la acusación pide que no se le cite al juicio oral» (formulario 353 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Menor o discapacitado: la acusación pide que no se le cite al juicio oral

> Formulario 0353 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- La prueba preconstituida obligatoria del art. 449 ter LECrim solo se aplica en la instrucción de los delitos que enumera: homicidio, lesiones, contra la libertad, contra la integridad moral, trata, contra la libertad e indemnidad sexuales, contra la intimidad, contra las relaciones familiares, contra los derechos fundamentales, organizaciones y grupos criminales y terrorismo. Se aplica también cuando el delito es leve.
- Según el art. 703 bis LECrim, en esos casos el testigo solo puede ser llamado al juicio de forma excepcional, a petición de parte y por resolución motivada que lo considere necesario, o cuando la prueba preconstituida no cumpla los requisitos del art. 449 bis y cause indefensión.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NÚMERO (3 veces)
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… defensa. Señala el art. 703 bis LECRIM:»; «…las partes." Y el art. 730 LECRIM añade:»; «…ulo 730.2.» Y el art. 788.2 LECRIM dice:»; «…se acuerde la citación para el juicio de»

## Elecciones que hay que hacer

- este órgano judicial / esta sala
- menor de 14 años de edad / persona con discapacidad necesitada de especial protección
- menor / con discapacidad
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 703 bis y 730 LECRIM
- art. 703 bis LECRIM
- art. 730 LECRIM
- artículo 777.3 LECRIM
- art. 788.2 LECRIM

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

### Formulario 0353 · Menor o discapacitado: la acusación pide que no se le cite al juicio oral

- Año del modelo: 2021
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 5 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 15 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 161) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación particular, que actúa en representación de la víctima menor de 14 años o con discapacidad necesitada de especial protección, solicita que, aunque se haya pedido por la defensa la comparecencia de la víctima en el juicio oral, no sea aceptada, sino que se reproduzca su declaración grabada en instrucción como prueba preconstituida, conforme al art. 703 bis LECRIM, introducido por la LO 8/2021, de protección integral a la infancia y la adolescencia frente a la violencia, con entrada en vigor a partir del 25 de junio de 2021.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusación particular en las DP número [NÚMERO], instruidas por la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], y pendiente de señalamiento de juicio en [ELEGIR: este órgano judicial / esta sala] por el presunto delito de [DELITO], contra D./Dña. [NOMBRE Y APELLIDOS], como mejor proceda en derecho, DIGO:

Que la víctima del delito es [ELEGIR: menor de 14 años de edad / persona con discapacidad necesitada de especial protección] por quien actúa esta acusación particular como representante legal.

Que la persona [ELEGIR: menor / con discapacidad] ha declarado ya en fase de instrucción ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], el día [FECHA], habiéndose grabado la declaración en base al art. 449 bis y 449 ter LECRIM conforme a la redacción dada por la LO 8/2021 de protección de la infancia y la adolescencia frente a la violencia.

Que, estando pendiente de la celebración de juicio y en base a lo dispuesto en los arts. 703 bis y 730 LECRIM, modificados por la antes citada Ley, se interesa que el día del juicio se proceda a reproducir la grabación de la declaración de la persona [ELEGIR: menor / con discapacidad] que se llevó a cabo en sede de instrucción, no admitiéndose en modo alguno la solicitud de su comparecencia el día del juicio solicitada por la defensa.

Señala el art. 703 bis LECRIM: [COMPLETAR]

"Cuando en fase de instrucción, en aplicación de lo dispuesto en el artículo 449 bis y siguientes, se haya practicado como prueba preconstituida la declaración de un testigo, se procederá, a instancia de la parte interesada, a la reproducción en la vista de la grabación audiovisual, de conformidad con el artículo 730.2, sin que sea necesaria la presencia del testigo en la vista.

En los supuestos previstos en el artículo 449.ter, la autoridad judicial solo podrá acordar la intervención del testigo en el acto del juicio, con carácter excepcional, cuando sea interesada por alguna de las partes y considerada necesaria en resolución motivada, asegurando que la grabación audiovisual cuenta con los apoyos de accesibilidad cuando el testigo sea una persona con discapacidad.

En todo caso, la autoridad judicial encargada del enjuiciamiento, a instancia de parte, podrá acordar su intervención en la vista cuando la prueba preconstituida no reúna todos los requisitos previstos en el artículo 449 bis y cause indefensión a alguna de las partes."

Y el art. 730 LECRIM añade: [COMPLETAR]

1. Podrán también leerse o reproducirse a instancia de cualquiera de las partes las diligencias practicadas en el sumario, que, por causas independientes de la voluntad de aquellas, no puedan ser reproducidas en el juicio oral.
2. A instancia de cualquiera de las partes, se podrá reproducir la grabación audiovisual de la declaración de la víctima o testigo practicada como prueba preconstituida durante la fase de instrucción conforme a lo dispuesto en el artículo 449 bis."

También, para el procedimiento abreviado, en el artículo 777.3 LECRIM se añade:

«3. Cuando una persona menor de catorce años o una persona con discapacidad necesitada de especial protección deba intervenir en condición de testigo, será de aplicación lo dispuesto en el artículo 449 ter, debiendo la autoridad judicial practicar prueba preconstituida, siempre que el objeto del procedimiento sea la instrucción de alguno de los delitos relacionados en tal artículo.

A efectos de su valoración como prueba en sentencia, la parte a quien interese deberá instar en el juicio oral la reproducción de la grabación audiovisual, en los términos del artículo 730.2.»

Y el art. 788.2 LECRIM dice: [COMPLETAR]

«2.Será de aplicación lo dispuesto en el artículo 703 bis en cuanto a la no intervención en el acto del juicio del testigo, cuando se haya practicado prueba preconstituida de conformidad con lo dispuesto en los artículos 449 bis y siguientes.»

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]

Que tenga por presentado este escrito, se sirva admitirlo y no se acuerde la citación para el juicio de [COMPLETAR], sustituyéndose por la reproducción en el juicio de la exploración que se llevó a cabo como prueba preconstituida grabada, de cara a ser reproducida el día del juicio oral.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) A partir del 25 de junio de 2021, fecha de entrada en vigor de la LO 8/2021, se secuencia y disciplina cómo deberá procederse en los casos de declaración de menores de edad o discapacitados en fase sumarial evitando, con ello, su declaración en el plenario para evitar su victimización secundaria. Se grabará la declaración y luego se reproduce en el juicio oral porque la acusación deberá haber propuesto como prueba la reproducción de esa grabación en el plenario para darle rango de verdadera prueba de cargo, aunque la contradicción ya se ha asegurado con carácter previo al estar presente el letrado del investigado debidamente citado. Resulta importante verificar en el acto por el LAJ el control de calidad de la grabación para evitar retrasos o nulidades si la reproducción no puede llevarse a cabo por falta de calidad en la grabación. Además: 1. Se fija la edad en los menores de 14 años que deba intervenir como testigo el parámetro para medir cuándo el juez en el caso de los delitos que se citan acordará en todo caso, como se expresa de forma imperativa, practicar la exploración como prueba preconstituida para ser luego reproducida en el plenario. 2. Se faculta al juez («podrá») a acordar que a exploración se practique a través de personas expertas para ganar la confianza de los menores y evitar victimización, pudiendo las partes preguntar por su conducto. 3. Se incide en que con respecto al investigado y el menor se evitará su confrontación visual con el testigo, utilizando para ello, si fuese necesario, cualquier medio técnico, como la videoconferencia para cualquier de ambos para evitar su contacto o visualización. 4. La cuestión relativa a la edad de los menores para que se les grabe su declaración se fija en el art. 449 ter en la de menores de 14 años, para situar una edad que suponga una presunción de madurez. Sobre ello trató la STS 329/2021 de 22 de abril

[NOTA DE REVISIÓN: La prueba preconstituida obligatoria del art. 449 ter LECrim solo se aplica en la instrucción de los delitos que enumera: homicidio, lesiones, contra la libertad, contra la integridad moral, trata, contra la libertad e indemnidad sexuales, contra la intimidad, contra las relaciones familiares, contra los derechos fundamentales, organizaciones y grupos criminales y terrorismo. Se aplica también cuando el delito es leve.]

[NOTA DE REVISIÓN: Según el art. 703 bis LECrim, en esos casos el testigo solo puede ser llamado al juicio de forma excepcional, a petición de parte y por resolución motivada que lo considere necesario, o cuando la prueba preconstituida no cumpla los requisitos del art. 449 bis y cause indefensión.]
