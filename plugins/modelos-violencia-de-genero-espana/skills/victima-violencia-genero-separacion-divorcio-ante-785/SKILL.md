---
name: victima-violencia-genero-separacion-divorcio-ante-785
description: "Redacta el escrito «Víctima de violencia de género: separación o divorcio ante la Sección de Violencia sobre la Mujer» (formulario 785 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima de violencia de género: separación o divorcio ante la Sección de Violencia sobre la Mujer

> Formulario 0785 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ña. y D. contrajeron matrimonio civil en»; «…, el»; «…erido matrimonio nació un hijo de nombre»; «…bles deudas, que amenazan ese patrimonio»; «…- El demandado trabaja por cuenta propia»; «…o y el anterior, como documentos números»; «…y»; «…y [COMPLETAR] SEXTO.-»

## Elecciones que hay que hacer

- SEPARACIÓN / DIVORCIO
- el esposo / la esposa
- representado / representada
- separación / divorcio
- parcialmente / totalmente
- Sección de Instrucción del Tribunal de Instancia / Sección de Violencia sobre la Mujer del Tribunal de Instancia
- la separación / el divorcio

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Solo para el caso de no haber transcurrido tres meses desde la celebración del matrimonio / En otro caso — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Se adjunta, al objeto de demostrar las rentas de la unidad familiar, copias de la declaración —conjunta— del I…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 770 LEC
- artículo 544 ter de la Ley de Enjuiciamiento Criminal
- artículo 81 CCiv
- artículo 86 CCiv
- artículo 59 de la Ley Orgánica 1/2004
- artículo 753 LEC
- artículo 10.1 LEC
- artículo 91 CCiv
- artículo 774 LEC
- artículo 394 LEC
- artículo 773 de la LEC
- Ley 17/2021

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

### Formulario 0785 · Víctima de violencia de género: separación o divorcio ante la Sección de Violencia sobre la Mujer

- Año del modelo: 2016
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 3 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de víctima de violencia de género con hijos menores que promueve ante la sección de Violencia sobre la Mujer del Tribunal de Instancia demanda de separación o divorcio por la vía del artículo 770 LEC para que se modifiquen las medidas civiles adoptadas en la orden de protección.

Actualizado conforme a la Ley 17/2021, de 15 de diciembre, de modificación del Código Civil, la Ley Hipotecaria y la Ley de Enjuiciamiento Civil, sobre el régimen jurídico de los animales, vigente a partir del 5 de enero de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a, en representación de D./Dña. [NOMBRE Y APELLIDOS], en virtud de poder notarial que acompaño y cuya devolución solicito, una vez testimoniado en autos, por necesitarlo para otros usos, ante este órgano judicial, comparezco, y como mejor proceda en Derecho, DIGO:

Que con fecha [FECHA], por la Sección de Violencia sobre la Mujer del Tribunal de Instancia [SEDE] plaza nº [NÚMERO] se dictó Auto acordando la orden de protección prevista en el artículo 544 ter de la Ley de Enjuiciamiento Criminal adoptando las medidas civiles que constan en el mismo, el cual se acompaña como documento número 1 de la presente demanda.

Que, conforme al artículo 544 quinquies 3 de la LECr, por medio del presente escrito, promuevo DEMANDA DE [ELEGIR: SEPARACIÓN / DIVORCIO] contra [ELEGIR: el esposo / la esposa] de mi [ELEGIR: representado / representada], de conformidad con lo dispuesto en el artículo 81 CCiv o artículo 86 CCiv y en relación con el artículo 770 LEC.

Que desde este momento anunciamos la solicitud de MODIFICACIÓN DE LAS MEDIDAS CIVILES adoptadas en el mencionado auto, toda vez que las mismas, tal y como se va a pasar a razonar, son las más adecuadas para regir la nueva situación de [ELEGIR: separación / divorcio].

Todo ello de conformidad con los siguientes,

HECHOS

PRIMERO.- Dña. y D. contrajeron matrimonio civil en [COMPLETAR], el [COMPLETAR], a cuya acreditación se acompaña certificación expedida por el Registro Civil de [LOCALIDAD], como documento número [Nº DE DOCUMENTO].

SEGUNDO.- Del referido matrimonio nació un hijo de nombre [COMPLETAR], de [Nº] años, todavía menor de edad, como se demuestra con la certificación registral que se presenta como documento número [Nº DE DOCUMENTO].

TERCERO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Solo para el caso de no haber transcurrido tres meses desde la celebración del matrimonio / En otro caso — el texto de cada opción no venía en el formulario original]

CUARTO.- El régimen conyugal de bienes es el de sociedad de gananciales, por la vecindad de los consortes y no haberse otorgado nunca capitulaciones matrimoniales, siendo el domicilio conyugal herencia del demandado D./Dña. [NOMBRE Y APELLIDOS], y por lo tanto, bien privativo del mismo, teniendo conocimiento de que el demandado ha ido contrayendo innumerables deudas, que amenazan ese patrimonio [COMPLETAR].

QUINTO.- El demandado trabaja por cuenta propia [COMPLETAR]

Sin embargo, mi patrocinada carece de ingresos propios, y aún de cualificación profesional de cualquier tipo.

[OPCIONAL — incluir si procede]

Se adjunta, al objeto de demostrar las rentas de la unidad familiar, copias de la declaración —conjunta— del I.R.P.F. del año pasado y el anterior, como documentos números [COMPLETAR] y

[COMPLETAR]

SEXTO.- [COMPLETAR]

FUNDAMENTOS DE DERECHO

I.- Es competente la Sección de Violencia sobre la Mujer del Tribunal de Instancia del lugar del domicilio conyugal conforme al artículo 769.1, párrafo 1.º LEC (o en su caso, por ser el domicilio de la víctima de conformidad con lo establecido en el artículo 59 de la Ley Orgánica 1/2004, de 28 de diciembre)

II.- El proceso adecuado es el del juicio verbal (arts. 437 y ss. LEC), como se diseña especialmente por el artículo 753 LEC, y con las peculiaridades del artículo 770 LEC, para conocer de las demandas contenciosas de separación.

III.- Tiene la demandante legitimación activa ordinaria por hallarse en la situación jurídica de relación conyugal, como detenta la pasiva su marido demandado (artículo 81 CCiv y artículo 10.1 LEC), siendo el objeto del proceso principal la pretensión de separación conyugal y la adopción de medidas definitivas derivadas de la misma.

IV.- El fondo de la pretensión consiste en la declaración de separación conyugal (o divorcio) sin consenso de los cónyuges, a instancia de uno de ellos por existencia de un riesgo para la vida, la integridad física, la libertad, la integridad moral o libertad o indemnidad sexual del cónyuge demandante o de los hijos de ambos o de cualquiera de los miembros del matrimonio (o bien) por el mero transcurso de tres meses desde la celebración del matrimonio.

V.- Conforme al artículo 91 CCiv y artículo 774 LEC, el órgano judicial deberá pronunciarse en definitiva sobre las medidas que se solicitarán que se adopten con carácter de provisionales, acerca de los hijos, vivienda, el destino de los animales de compañía, alimentos, pensión compensatoria y régimen matrimonial de bienes, las cuales se pretenden igualmente como definitivas.

En tal sentido, esta parte pretende que sean [ELEGIR: parcialmente / totalmente] modificadas las medidas civiles adoptadas en la orden de protección dictada por la [ELEGIR: Sección de Instrucción del Tribunal de Instancia / Sección de Violencia sobre la Mujer del Tribunal de Instancia] con fecha [FECHA], y ello en base a lo dispuesto en el artículo 544 quinquies.3 LECRIM, por cuanto

VI.- Las costas procesales deben ser impuestas a la parte demandada, por criterio del íntegro vencimiento, en atención al artículo 394 LEC.

Y demás normas y jurisprudencia de general y pertinente aplicación.

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito de demanda y documentos que lo acompañan, los admita a trámite, y en su virtud, y previos los trámites legales, dicte sentencia por la que se declare [ELEGIR: la separación / el divorcio] del matrimonio formado por mi [ELEGIR: representado / representada] y D./Dña. [NOMBRE Y APELLIDOS], con la adopción de las siguientes medidas:

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO

Que esta parte interesa la adopción de medidas provisionales al amparo de lo dispuesto en el artículo 773 de la LEC, y de conformidad a lo previsto en el artículo 544 quinquies 3 de la Ley de Enjuiciamiento Criminal, se solicita la modificación de las adoptadas con carácter previo en sede penal en los siguientes términos:

SUPLICO A LA SECCIÓN

que acuerde como medidas provisionales las anteriormente relacionadas MODIFICANDO las adoptadas en sede penal en los términos que han quedado expuestos.

Es Justicia que reitero en el lugar y fecha ut supra indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
