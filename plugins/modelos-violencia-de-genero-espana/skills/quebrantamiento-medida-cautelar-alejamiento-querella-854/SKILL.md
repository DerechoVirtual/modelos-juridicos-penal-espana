---
name: quebrantamiento-medida-cautelar-alejamiento-querella-854
description: "Redacta el escrito «Quebrantamiento de medida cautelar de alejamiento: querella» (formulario 854 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Quebrantamiento de medida cautelar de alejamiento: querella

> Formulario 0854 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (3 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] CALLE
- [ ] NÚMERO (3 veces)
- [ ] FECHA (4 veces)
- [ ] Nº (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…mayor de edad, de estado civil con D.»; «…, vecino de [LOCALIDAD], con domicilio»; «…de»

## Elecciones que hay que hacer

- cónyuges / excónyuges / pareja de hecho / ex pareja de hecho

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del querellado sobre los hechos de la querella.…
- .- Testifical: a cuyo fin deberá ser citada a través de la oficina judicial la siguiente persona:…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña copia de l…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468.2 del CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 468.2 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 468.2 del Código Penal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 89.5 h) LOPJ
- art. 89.5 g) LOPJ
- art. 468.1 CP
- art. 48 CP
- art. 173.2 CP

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

### Formulario 0854 · Quebrantamiento de medida cautelar de alejamiento: querella

- Año del modelo: 2016
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 4 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Querella contra su pareja por haber incumplido una orden de alejamiento, lo que puede ser constitutivo de un delito de quebrantamiento de condena del art. 468.2 del CP.

Actualizado conforme a la LO 1/2025

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

A la Sección de Violencia sobre la Mujer que por turno de reparto corresponda

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal, contra D. por el delito de quebrantamiento de medida cautelar del art. 468.2 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante el Tribunal de Instancia de esta ciudad para su reparto a la Sección de Violencia sobre la Mujer que por turno corresponda, por ser competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal y artículo 89.5 h LOPJ, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR]. (2)

SEGUNDO.- La querellante es Dña. [NOMBRE Y APELLIDOS] mayor de edad, de estado civil con D. [COMPLETAR], de profesión [PROFESIÓN], vecina de [LOCALIDAD], con domicilio en la calle [CALLE] número [NÚMERO].

TERCERO.- El querellado es D. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil con Dña. [NOMBRE Y APELLIDOS] de profesión [PROFESIÓN], vecino de [LOCALIDAD], con domicilio [COMPLETAR]. (3)

CUARTO.- Los hechos objeto de la querella son los siguientes:

Con fecha [FECHA] y en las diligencias previas / se dictó por la Sección de Violencia sobre la mujer nº [NÚMERO] de [LOCALIDAD] una orden de alejamiento por la que el querellado D. no podía acercarse a menos de 500 metros a la querellante Dña. durante [Nº] meses. Esta resolución fue notificada al querellado en fecha [FECHA] requiriéndole para que acatara la orden con los apercibimientos legales correspondientes, teniendo con ello conocimiento el querellado de la existencia de la citada orden.

Estando vigente la orden de alejamiento, el querellado se personó en el domicilio de la querellante el día [FECHA] a las [Nº] horas, exigiéndole ver a los dos hijos comunes habidos en el matrimonio entre ellos, cerrando la puerta inmediatamente la querellante. En ese instante se encontraba la querellante con su madre Dña. [NOMBRE Y APELLIDOS].

La querellante y el querellado son [ELEGIR: cónyuges / excónyuges / pareja de hecho / ex pareja de hecho].

Sin perjuicio de una calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de quebrantamiento de medida cautelar, que define el artículo 468.2 del Código Penal, del que presuntamente es culpable el querellado. (4)

Como señala el Tribunal Supremo, Sala Segunda, de lo Penal, Sentencia 778/2010, de 1 Diciembre, Rec. 10469/2010 el tipo objetivo del delito del art. 468.2 CP sólo requiere que el autor sepa que era el destinatario de un mandato judicial por el que le es impuesta la prohibición de acercarse a la víctima. Ante cualquier alegación del querellado dirigida a alegar que tenía motivos para acercarse, otra interpretación del tipo objetivo contenido en el art. 468.2 CP sería claramente contraria a la finalidad de la norma, cuya función es proteger a la víctima del peligro que el posible autor representa para su integridad física y su vida. Consecuentemente, el tipo subjetivo, es decir el dolo, sólo presupone el conocimiento del mandato judicial que le incumbe y que el autor sepa que con su conducta lo incumple.

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: a cuyo fin deberá ser citada a través de la oficina judicial la siguiente persona:

- Ratificación de la querellante.

- Dña. [NOMBRE Y APELLIDOS] mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD], madre de la querellante que se encontraba en el domicilio en el momento de los hechos.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella. Se acompaña copia de la orden de alejamiento dictada por el Juez de Violencia sobre la Mujer nº [NÚMERO] de [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas, y se tomen las pertinentes medidas cautelares sobre los bienes del querellado, disponiendo se le exija fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Juez de Instrucción.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(2) La competencia para la instrucción del delito de quebrantamiento de condena, cuando la persona ofendida sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por una análoga relación de afectividad aun sin convivencia, así como los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad con medidas de apoyo que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, así como cuando la persona ofendida lo sea por alguno de los delitos señalados en el art. 89.5 h) LOPJ, es de la Sección de Violencia sobre la Mujer (art. 89.5 g) LOPJ). Si no se tratase de estas víctimas, la instrucción correspondería a una Sección de instrucción y se aplicaría el art. 468.1 CP.

(3) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(4) Debe tenerse en cuenta que en estos casos la circunstancia de ser cónyuge o excónyuge, pareja o expareja de hecho querellante y querellado hace aplicable el art. 468.2 CP que impone pena de prisión de seis meses a un año cuando se quebrantase un pena del art. 48 CP o una medida cautelar impuesta en procesos en los que el ofendido sea una de las personas del art. 173.2 CP.

Si no se tratase de estas víctimas del art. 173.2 CP, se aplicaría el art. 468.1 CP.

================================================================================
