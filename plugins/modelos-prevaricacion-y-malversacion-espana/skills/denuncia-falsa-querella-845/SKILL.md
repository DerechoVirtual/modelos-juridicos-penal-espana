---
name: denuncia-falsa-querella-845
description: "Redacta el escrito «Denuncia falsa: querella» (formulario 845 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Denuncia falsa: querella

> Formulario 0845 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

- [ ] SEDE (4 veces)
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO (2 veces)
- [ ] DELITO (2 veces)
- [ ] FECHA DEL AUTO
- [ ] DESCRIBIR
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…se presentó denuncia por parte de»; «… se demuestra con las pruebas siguientes»; «…nción psicológica recibida del psicólogo»; «…n proceso judicial que se cuantifican en»; «…. b.- Gastos judiciales que ascienden a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto
- la sentencia absolutoria / el auto de archivo

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Ratificación del/de la querellante.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS] testigo que intervino en el juicio oral del que dimana ahora este procedimiento…
- - D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre el daño moral padecido por el/la querellante.…
- .-Testifical-Pericial del psicólogo a efectos de acreditar el daño moral sufrido por el/la querellante. (4)…
- .- Documental: teniendo por reproducido el testimonio de la sentencia dictada por la Sección de lo Penal del T…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 456 del CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 456 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 456 del Código Penal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC

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

### Formulario 0845 · Denuncia falsa: querella

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 4 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 42 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que pueden ser constitutivos de un delito de denuncia falsa del art. 456 del CP, y se reclama el daño moral producido, así como los perjuicios económicos objetivables derivados de la falsa denuncia.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de denuncia falsa del art. 456 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil con D./Dña. [NOMBRE Y APELLIDOS], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS] (2), mayor de edad, de estado civil con D./Dña. [NOMBRE Y APELLIDOS], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Con fecha [FECHA] se dictó sentencia firme (3) en el procedimiento abreviado nº [Nº DE PROCEDIMIENTO] ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] por delito de [DELITO] a raíz de denuncia interpuesta por el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] contra el/la querellante D./Dña. [NOMBRE Y APELLIDOS]. En la sentencia dictada, ya firme por no haberse interpuesto recurso contra la misma, se hace constar por el juzgador la posible existencia de fundamento para entender que el contenido de la denuncia era falso, lo que motivó que, incluso, la sentencia absolutoria se dictara in voce y recogiendo el/la juez/a en la misma la insostenibilidad de los hechos de la denuncia y la posibilidad de que fueran falsos a tenor de las pruebas practicadas.

Con fecha [FECHA] se presentó denuncia por parte de [COMPLETAR] contra el/la querellante siendo archivada por la sección de instrucción por auto de archivo haciendo constar el juez a instancia de esta parte en el auto, tras diligencias practicadas, el carácter insostenible de la denuncia y la existencia de indicios o clara apariencia de falsedad de la misma, al no ser ciertos los hechos denunciados y el dolo inherente al conocimiento del carácter falsario de los hechos denunciados. Y cuyo auto de fecha [FECHA DEL AUTO] ha devenido firme.

QUINTO.- Los hechos expuestos revisten los caracteres de un delito de denuncia falsa que define el artículo 456 del Código Penal, del que presuntamente es culpable el/la querellado/a.

Concurren los requisitos de la acusación y denuncia falsa:

1.- La imputación de hechos falsos de forma clara en la denuncia inicial.
2.- Los hechos denunciados, si fueran ciertos, serían constitutivos de delito de [DELITO].
3.- La denuncia se formuló ante la autoridad judicial.

4. Existe dolo y mala fe de presentar la denuncia con dolo y conciencia de su falsedad.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Ratificación del/de la querellante.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] testigo que intervino en el juicio oral del que dimana ahora este procedimiento, a efectos de acreditar la falsedad de la denuncia y que fue determinante para [ELEGIR: la sentencia absolutoria / el auto de archivo]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre el daño moral padecido por el/la querellante.

[OPCIONAL — incluir si procede]

.-Testifical-Pericial del psicólogo a efectos de acreditar el daño moral sufrido por el/la querellante. (4)

[OPCIONAL — incluir si procede]

.- Documental: teniendo por reproducido el testimonio de la sentencia dictada por la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] y de la denuncia falsa presentada en su día.

- Se aportan los siguientes documentos que ya fueron aportados en sede de la Sección de Instrucción del Tribunal de Instancia de [SEDE], a efectos de acreditar la falsedad de la denuncia y que fueron determinantes para [ELEGIR: la sentencia absolutoria / el auto de archivo].

- Se incluye [ELEGIR: la sentencia absolutoria / el auto de archivo].

- Documentos relativos a los daños y perjuicios objetivables sufridos consistentes en [DESCRIBIR].

SÉPTIMO.- Existe derecho a recibir una indemnización por falso testimonio o por el daño moral sufrido por el perjudicado, ahora querellante, y que se fija, sin perjuicio de posterior determinación final en el escrito de acusación, en la suma de [IMPORTE] euros, por el sufrimiento psicológico y el perjuicio económico objetivable en base al daño moral, y con fundamento en la doctrina fijada por la Sala Segunda del Tribunal Supremo en las SSTS 535/2025 de 11 junio, 776/2024 de 18 septiembre y, sobre todo, STS 437/2022 de 4 mayo, a la hora de fijar los criterios en base a la reclamación del daño moral basado en las tesis del daño moral irreversible, tesis del antes y el después y la tesis de la declaración de impacto de la víctima en base a un daño moral consistente en:

1. Zozobra y ansiedad sufrida por el perjudicado ante una denuncia falsa.
2. La publicidad que se dio a la denuncia que se demuestra con las pruebas siguientes [COMPLETAR].
3. Atención psicológica recibida del psicólogo [COMPLETAR].

Además del daño moral existente, se acreditan los siguientes gastos como perjuicios económicos objetivables tenidos como consecuencia de la falsa denuncia:

a.- Gastos económicos por pérdidas económicas provocadas por la falsa denuncia y el desprestigio derivado de estar sometido a un proceso judicial que se cuantifican en [COMPLETAR].

b.- Gastos judiciales que ascienden a [COMPLETAR].

Por ello, en concepto de responsabilidad civil se reclama, en principio, la suma de [IMPORTE] euros.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a D./Dña. [NOMBRE Y APELLIDOS], disponiendo se proceda a la detención y prisión provisional del/de la querellado/a (5), o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Para proceder por el delito de denuncia falsa del art. 456 CP, es preciso hacer mención a su apartado 2 en donde se exige que, con carácter previo, haya recaído sentencia firme o auto de archivo firme. No podrá interponerse esta querella sin este requisito.

(4) En estos casos es posible que la declaración de un profesional se articule en calidad de testigo- perito de los arts 370 y 380 LEC en razón a que puede declarar de lo que conoce, por lo que ha visto en cuanto a la atención que ha dispensado a la víctima, pero también es su condición de perito por la noción de la afectación de ser víctimas del delito, en cuanto a la reclamación por daño moral. De esta manera, el psicólogo podría declarar como testigo en razón a las asistencias que ha hecho al perjudicado y el coste que eso le produce a este, así como en razón a una pericial para declarar, conforme a sus conocimientos, el grado de afectación que le ha provocado al perjudicado para la reclamación de daño moral.

(5) Téngase en cuenta que, para petición de prisión provisional o fianza por la libertad (art 503.1.1ª LECRIM) es necesario que conste en la causa la existencia de uno o varios hechos que presenten caracteres de delito sancionado con pena cuyo máximo sea igual o superior a dos años de prisión, o bien con pena privativa de libertad de duración inferior si el investigado o encausado tuviere antecedentes penales no cancelados ni susceptibles de cancelación, derivados de condena por delito doloso.

================================================================================
