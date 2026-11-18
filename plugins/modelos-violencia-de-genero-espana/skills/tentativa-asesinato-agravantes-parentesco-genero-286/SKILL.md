---
name: tentativa-asesinato-agravantes-parentesco-genero-286
description: "Redacta el escrito «Tentativa de asesinato con agravantes de parentesco y de género: querella» (formulario 286 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tentativa de asesinato con agravantes de parentesco y de género: querella

> Formulario 0286 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ACTO O RESOLUCIÓN
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…mente en SEGUNDO.- La querellante es Dña»; «…ctivos son los siguientes: El querellado»; «…ra hacer nada para evitarlo y defenderse»; «…re de un vecino, donde salió en su ayuda»; «…como secuelas las de»; «….- Testifical: -Declaración de»

## Elecciones que hay que hacer

- casado / convivendo

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del querellado.…
- .- Testifical:…
- .-Pericial: que se cite a la querellante Dña. [NOMBRE Y APELLIDOS] para ser reconocida por el médico forense.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 16 CP
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 544 bis LECRIM
- artículo 57 CP
- art. 281 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0286 · Tentativa de asesinato con agravantes de parentesco y de género: querella

- Año del modelo: 2021
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, contra [ACTO O RESOLUCIÓN] por un delito tentativa de asesinato del art. 139.1.1º y art. 16 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- La querellante es Dña [COMPLETAR], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El querellado es D. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El querellado [COMPLETAR], el día [FECHA] estaba esperando a que llegara a casa de trabajar mi representada [NOMBRE DEL REPRESENTADO/A], con la que llevaba [ELEGIR: casado / convivendo] años, cuando sobre las [Nº] horas apareció y, de modo sorpresivo, sin que pudiera hacer nada para evitarlo y defenderse [COMPLETAR] le asestó una puñalada en el cuello con un cuchillo de cocina de 15 cm y acto seguido otra en el estómago, todo ello con la intención de causarle la muerte, porque lo hizo en órganos y zonas donde sabía que acabaría con su vida, al tiempo que le decía:

"¡Te dije que no quería verte con tu compañero de trabajo! ¡Eres una zorra porque me engañas! ¡Eres solo mía y de nadie más y, como no quieres quedarte en casa para atenderme y obdecerme, es por lo que te mato!"

Sin embargo, mi representada le dio un fuerte empujón al querellado, abrió rápidamente la puerta de la calle y bajó como pudo las escaleras. Tocó el timbre de un vecino, donde salió en su ayuda [COMPLETAR], quien llamó a una ambulancia que, a los pocos minutos, le llevó al hospital, aún con vida, donde pudieron salvarle la vida.

De tales hechos le han quedado a Dña. [NOMBRE Y APELLIDOS] como secuelas las de [COMPLETAR], estando incapacitada [Nº]. días.

QUINTO.- Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de asesinato del art. 139.1.1º CP, en grado de tentativa conforme al art. 16 CP.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de [COMPLETAR] vecino que auxilió a la querellante.
-D./Dña [NOMBRE Y APELLIDOS] y D/Dña [NOMBRE Y APELLIDOS] agentes de las Fuerzas y Cuerpos de Seguridad del Estado que comparecieron en los hechos requerida su presencia por el/la vecino/a que ayudó.

[OPCIONAL — incluir si procede]

.-Pericial: que se cite a la querellante Dña. [NOMBRE Y APELLIDOS] para ser reconocida por el médico forense.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del querellado, disponiendo se proceda a la detención y prisión provisional del mismo, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros, y otra fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

Es Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa, asimismo, que en base al art. 544 bis LECRIM, dado que el delito objeto de querella está entre los incluidos en el artículo 57 CP, se dicte una orden de alejamiento que le impida acercarse a la víctima y a sus familiares a menos de 500 metros, así como, sobre todo, una orden de prohibición de comunicación por cualquier tipo de medio, así como se adopten las medidas cautelares enunciadas para asegurar las responsabilidades civiles.

SUPLICO A LA SECCIÓN: Que acuerde las medidas cautelares solicitadas.

SEGUNDO OTROSÍ DIGO: Que conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
