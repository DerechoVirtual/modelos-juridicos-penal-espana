---
name: prevaricacion-judicial-querella-838
description: "Redacta el escrito «Prevaricación judicial: querella» (formulario 838 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prevaricación judicial: querella

> Formulario 0838 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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

- [ ] LOCALIDAD (7 veces)
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] ESTADO CIVIL
- [ ] NÚMERO (3 veces)
- [ ] FECHA (2 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…ituación personal del/de la querellado/a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella nº [NÚMERO] relativos a…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 446 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 277 LECrim
- artículos 73.3.b) LOPJ
- art. 728 LEC
- artículo 446 del Código Penal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 73 LOPJ
- art. 447 CP
- art. 448 CP
- art. 449 CP

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

### Formulario 0838 · Prevaricación judicial: querella

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 33 campos de relleno marcados en blanco; 1 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de querella contra un juez por presunto delito de prevaricación del art. 446 CP, por haber solicitado el embargo de unos bienes en un procedimiento civil sin cumplirse los requisitos legalmente establecidos.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sala de lo Civil y Penal del TSJ de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de prevaricación judicial del art. 446 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sala de lo civil y penal del TSJ de [LOCALIDAD] de esta capital por ser la competente para su instrucción, a tenor de los artículos 73.3.b) LOPJ y 272 de la Ley de Enjuiciamiento Criminal (2), al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil con D./Dña. [NOMBRE Y APELLIDOS], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD]. (3)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a D./Dña. [NOMBRE Y APELLIDOS] es juez/a de la Sección Civil plaza nº [NÚMERO] del Tribunal de Instancia de esta ciudad. Con fecha [FECHA] se ha dictado en el procedimiento de juicio ordinario nº [Nº DE PROCEDIMIENTO], que se tramita en su órgano judicial, auto ordenando la adopción de la medida cautelar de embargo de bienes del/de la querellante sin que se cumplan los requisitos del art. 728 LEC, al no haberse aportado con la solicitud de las mismas ninguno de los requisitos que se citan en el citado precepto, ni haberse adoptado por el/la querellado/a caución alguna en previsión de que el resultado final del pleito fuese desestimatorio y se causen al/a la ahora querellante daños y perjuicios. En concreto se ha embargado el bien inmueble sito en [LOCALIDAD], con referencia registral nº [NÚMERO] que estaba en disposición de ser vendido en la actualidad, siendo imposible la venta en tal estado de traba por este órgano judicial. La resolución se dicta a sabiendas de su injusticia, por cuanto no se han aportado por el/la demandante ninguno de los presupuestos del art. 728 LEC ni aportado ni exigido caución suficiente.

Se han provocado daños y perjuicios derivados de la no adquisición del bien inmueble por el/la posible comprador/a D./Dña. [NOMBRE Y APELLIDOS] tasados en [IMPORTE] euros.

QUINTO.- Los hechos expuestos, sin perjuicio de una mejor calificación jurídica posterior, revisten los caracteres de un delito de prevaricación judicial que define el artículo 446 del Código Penal, del que presuntamente es culpable el/la querellado/a. (4)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

- D./Dña. [NOMBRE Y APELLIDOS], demandante del procedimiento civil y posible comprador/a del bien inmueble ahora embargado.

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella nº [NÚMERO] relativos al procedimiento civil nº [Nº DE PROCEDIMIENTO].

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a [COMPLETAR], disponiendo se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) La competencia para la instrucción es de la Sala de lo Civil y penal del TSJ correspondiente a tenor del art. 73 LOPJ.

(3) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(4) Este es un delito esencialmente doloso que impide la comisión por imprudencia al exigirse en el art. 446 CP que se cometa a sabiendas de la injusticia de la resolución o sentencia, lo que podrá deducirse del desarrollo de los hechos, al colegirse rápidamente la injusticia manifiesta de la resolución o sentencia.

Cabe la comisión por imprudencia grave o ignorancia inexcusable en el art. 447 CP.

En el art. 448 CP se sanciona a quien se negase a juzgar, sin alegar causa legal, o so pretexto de oscuridad, insuficiencia o silencio de la Ley

Y en el art. 449 CP al Juez, Magistrado o Letrado/a de la Administración de Justicia culpable de retardo malicioso en la Administración de Justicia.

================================================================================
