---
name: insolvencia-punible-querella-394
description: "Redacta el escrito «Insolvencia punible: querella» (formulario 394 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Insolvencia punible: querella

> Formulario 0394 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE (4 veces)
- [ ] Nº DE DOCUMENTO (4 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…a»; «…, que acreditará que se ha cometido»; «….- Documental: - Facturas siguientes:»; «…euros con otros acreedores que se citan»; «…. - Actas notariales de requerimientos»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de insolvencia no causal / En caso de insolvencia causal — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- - D./Dña. [NOMBRE Y APELLIDOS]…
- 1.- Declaración del/de la querellado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], acreedor del/de la acusado/a.…
- - D./Dña. [NOMBRE Y APELLIDOS], que acreditará que se ha cometido [COMPLETAR].…
- - D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre [DESCRIBIR].…
- .- Pericial:…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 259 del CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 5 del RDLeg. 1/2020
- art. 259.1 CP
- art. 259 CP
- art. 4 del Real Decreto Legislativo 1/2020
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 259.2 CP

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

### Formulario 0394 · Insolvencia punible: querella

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 4 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de un delito de insolvencia punible del art. 259 del CP, ya que el querellado ha realizado una serie de actuaciones que imposibilitan el cobro de deudas al querellante y a otros acreedores, sin haber solicitado concurso voluntario.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes por un delito de insolvencia punible del art 259.1 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]. (2)

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes (3):

El/La querellante es acreedor/a de el/la querellado/a en base a una serie de operaciones mercantiles por las que se le debía el importe de [IMPORTE] euros.

Las operaciones fueron las siguientes:

Se acreditan las mismas con los documentos nº [Nº DE DOCUMENTO] a [COMPLETAR].

Tras varios requerimientos de pago que se acreditan con los documentos nº [Nº DE DOCUMENTO], el/la querellado/a vino haciendo caso omiso a los mismos alegando que estaba en una situación de insolvencia, o próxima a ella, al comunicarnos con el documento nº [Nº DE DOCUMENTO], que no disponía de patrimonio alguno con el que afrontar las deudas existentes.

Además, el/la querellado/a es deudor/a de los/as siguientes acreedores/as:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

Por otro lado, el/la querellado/a no ha instado concurso voluntario, aun siendo consciente de su situación patrimonial y de sus deudas con acreedores, conforme al artículo 5 del RDLeg. 1/2020, de 5 de mayo, por el que se aprueba la Ley Concursal, y

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de insolvencia no causal / En caso de insolvencia causal — el texto de cada opción no venía en el formulario original]

Los elementos indiciarios sobre los comportamientos en que consiste el catálogo de acciones perpetradas de las que constan en el art. 259.1 CP son los siguientes:

QUINTO.- Los hechos expuestos revisten los caracteres de un delito del art. 259 CP.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], acreedor del/de la acusado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que acreditará que se ha cometido [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre [DESCRIBIR].

[OPCIONAL — incluir si procede]

.- Pericial:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

- Pericial de parte del/de la perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación del/de la deudor/a.

- Solicitud de designación de perito judicial que lleve a cabo examen de la situación económica del/de la deudor/a con los parámetros expuestos en la querella y los que posteriormente se puedan ampliar para evaluar el estado de insolvencia del/de la querellado/a y las operaciones llevadas a cabo en base al análisis de la documental.

[OPCIONAL — incluir si procede]

.- Documental:

- Facturas siguientes: [COMPLETAR].
- Fijación por documental del importe total de la deuda con el/la querellante que asciende a la suma de [IMPORTE] euros y de [IMPORTE] euros con otros acreedores que se citan [COMPLETAR].
- Actas notariales de requerimientos [COMPLETAR]:
- Contestaciones a los requerimientos:
- Documentos nº [Nº DE DOCUMENTO] de actuaciones que han agravado la situación de insolvencia del/de la deudor/a.
- Solicitudes de petición judicial de documental al registro mercantil respecto a si consta que se ha declarado o no en concurso y/o envío de documentación a que está obligado por legislación mercantil.
- Que se le requiera al/a la querellado/a para que aporte libros de contabilidad, y formalización, en su caso, del concurso.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a, disponiendo se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias, así como el traslado a los acreedores conocidos, o que se conozcan en la tramitación que se insta por Otrosí a tenor del art. 4 del Real Decreto Legislativo 1/2020, de 5 de mayo, por el que se aprueba el texto refundido de la Ley Concursal.

Es Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: A tenor del antes citado artículo se ruega se dé traslado al Ministerio Fiscal para que pueda instar del juez que conozca de esta causa la comunicación de aquellos hechos a los acreedores cuya identidad resulte de las actuaciones penales en curso, a fin de que, en su caso, puedan solicitar la declaración de concurso o ejercitar las acciones que les correspondan.

Por ello,

SUPLICO A LA SECCIÓN: se dé traslado a los acreedores que resulten del informe pericial, al objeto de que conozcan la pendencia de la causa penal.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(3) El delito del art. 259 CP debe identificarse con un pronóstico razonable que, en sede penal, ya incluso para la admisión a trámite de la querella o para dar curso a la denuncia, debe estar amparado por un elenco de indicios de suficiente solidez.

La acreditación indiciaria inicial puede llevarse a cabo mediante la aportación al juez instructor de datos que pongan de manifiesto claramente la crisis o déficit patrimonial del deudor a quien se imputa la comisión del delito (por ejemplo: relación de acreedores en caso de multiplicidad, inventarios del deudor que reflejen la situación deficitaria, y especialmente, relación de impagos).

Los requisitos de la persona contra quien se dirige la acción penal son dos:

a.- Situación de insolvencia actual o inminente.

La Insolvencia penal es sólo la definitiva «de naturaleza estructural». No coincide completamente con la insolvencia concursal, es más exigente en el carácter del incumplimiento de los pagos. (STS 652/2018, de 14 de diciembre, Rec. 45/2018)

b.- Realizar alguna de las conductas que se citan en el art. 259.1 CP.

• Que supongan una disminución del patrimonio (1ª a 4ª) o la asunción de un riesgo de perdidas injustificadas (5ª).

• Que infrinjan deberes legales contables («insolvencia documental») (6ª a 8ª)

• Cláusula de cierre (9ª) que introduce dos requisitos cumulativos (infracción grave y disminución patrimonial/ocultación) que parte de la jurisprudencia y de la doctrina consideran extensivos al resto de conductas del art. 259.1 CP.

El apartado 1º del art. 259 CP es definido como la insolvencia no causal y el apartado 2º como la insolvencia causal.

Así, cabe, en segundo lugar, (art. 259.2 CP) que mediante alguna de las conductas a que se refiere el apartado anterior, cause su situación de insolvencia, con lo que si en el apartado 1º se exige que se encuentre el querellado en situación de insolvencia y lleve a cabo alguna de estas conductas, en el apartado 2º se admite que "con una de esas conductas" provoque su insolvencia.

================================================================================
