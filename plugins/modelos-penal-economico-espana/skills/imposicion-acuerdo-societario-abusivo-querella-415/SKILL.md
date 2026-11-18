---
name: imposicion-acuerdo-societario-abusivo-querella-415
description: "Redacta el escrito «Imposición de acuerdo societario abusivo: querella» (formulario 415 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Imposición de acuerdo societario abusivo: querella

> Formulario 0415 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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
- [ ] NOMBRE Y APELLIDOS (14 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] IMPORTE (4 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…de la sociedad»; «…umen de porcentaje de capital social del»; «…pero necesitaba la votación a favor de»; «…ros, en base a los siguientes parámetros»; «…, representante de la empresa»; «… la junta en que se adoptó el acuerdo. —»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- — D./Dña. [NOMBRE Y APELLIDOS], socio/a presente el día de la junta en que se adoptó el acuerdo.…
- — D./Dña. [NOMBRE Y APELLIDOS], miembro del Consejo de administración.…
- — D./Dña. [NOMBRE Y APELLIDOS], representante de la empresa [COMPLETAR] que contrató con el/la querellado/a, a…
- .- Pericial de parte del/de la perito D./Dña. [NOMBRE Y APELLIDOS] sobre el perjuicio económico causado y el b…
- .- Documental, teniendo por reproducido los documentos aportados en cuanto a:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 291 del CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 291 CP
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- arts. 204 del Real Decreto Legislativo 1/2010
- artículo 291 CP
- art. 297 CP

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

### Formulario 0415 · Imposición de acuerdo societario abusivo: querella

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de un delito de imposición de acuerdos abusivos del art. 291 del CP, ya que un socio consiguió la adopción de un acuerdo que perjudica a la minoría y a la sociedad, en beneficio propio.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, contra D./Dña. [NOMBRE Y APELLIDOS] por un delito de imposición de acuerdos abusivos del art. 291 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en. (2)

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La socio/a D./Dña. [NOMBRE Y APELLIDOS] de la sociedad [COMPLETAR] se puso de acuerdo, por su liderazgo y capacidad de convencimiento con otros socios, dándoles traslado de la necesidad de que en la junta celebrada el día [FECHA] votaran a favor del punto del orden del día que él/ella mismo/a había instado al Consejo de administración para conseguir un beneficio concreto para él/ella, quien disponía de un volumen de porcentaje de capital social del [COMPLETAR] pero necesitaba la votación a favor de [COMPLETAR] y, a cambio de esa votación, prometió a una serie de socios darles una parte de los beneficios que obtuviera. Una vez celebrada la junta, D./Dña. [NOMBRE Y APELLIDOS], al aprovecharse de la situación dominante derivada de ostentar la mayoría en la junta, ejerció la mayoría de los votos que hacía falta obtener para la adopción del acuerdo.

Este acuerdo conllevó un perjuicio a la sociedad tasado en la suma de [IMPORTE] euros y un beneficio para el/la socio/a de [IMPORTE] euros, en base a los siguientes parámetros [COMPLETAR].

QUINTO.- Los hechos expuestos, salvo una mejor calificación posterior, revisten los caracteres de un delito de imposición de acuerdos abusivos del art. 291 CP. (3)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], socio/a presente el día de la junta en que se adoptó el acuerdo.

— D./Dña. [NOMBRE Y APELLIDOS], secretario/a de la junta

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], miembro del Consejo de administración.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], representante de la empresa [COMPLETAR] que contrató con el/la querellado/a, a raíz del acuerdo, en su propio beneficio y en perjuicio societario.

[OPCIONAL — incluir si procede]

.- Pericial de parte del/de la perito D./Dña. [NOMBRE Y APELLIDOS] sobre el perjuicio económico causado y el beneficio estimado al/a la socio/a D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados en cuanto a:

— Acta de la junta en que se adoptó el acuerdo.
— [COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a, disponiendo se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y otra fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Es Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(3) Es un delito que puede estar en línea fronteriza con el derecho civil/mercantil, dado que se trata de acuerdos adoptados por mayoría en una junta de accionistas y que podrían ser impugnados con arreglo a los arts. 204 del Real Decreto Legislativo 1/2010, de 2 de julio, por el que se aprueba el texto refundido de la Ley de Sociedades de Capital y ss

El artículo 291 CP parte de la adopción de un acuerdo obtenido lícitamente pero que debe calificarse de abusivo, y aquí radica la esencia del tipo, que conlleva necesariamente la existencia de un ánimo de lucro propio o ajeno (el de los socios que constituyen la mayoría) en perjuicio de la minoría y siempre que ello no reporte beneficios a la sociedad, es decir, es atípica la concurrencia del mencionado ánimo como compatible con un resultado beneficioso para los intereses societarios, con independencia de que la minoría se vea perjudicada. (STS 654/2002, de 17 de abril, Rec. 1051/2000 y STS 172/2010, de 4 de marzo, Rec. 1012/2009)

El precepto requiere una interpretación cautelosa tendente a delimitar taxativamente la prohibición penal y a legitimar la intervención del Derecho Penal conforme a criterios de lesividad.

El ámbito de aplicación de este delito se ubica en todo lo que se entienda por sociedad y, para ello, hay que acudir al art. 297 CP, donde por sociedad se entiende toda cooperativa, cajas de ahorro, mutua, entidad financiera o de crédito, fundación, sociedad mercantil o cualquier otra entidad de análoga naturaleza.

================================================================================
