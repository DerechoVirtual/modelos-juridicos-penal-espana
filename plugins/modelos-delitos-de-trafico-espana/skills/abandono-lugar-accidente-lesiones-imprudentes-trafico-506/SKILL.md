---
name: abandono-lugar-accidente-lesiones-imprudentes-trafico-506
description: "Redacta el escrito «Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella» (formulario 506 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella

> Formulario 0506 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] MATRÍCULA (2 veces)
- [ ] CALLE (2 veces)
- [ ] DESCRIBIR
- [ ] NÚMERO (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…. SEGUNDO.- El/la querellante es D./Dña.»; «…TERCERO.- El/La querellado/a es D./Dña.»; «…y asegurado en la compañía»; «…conducido por»; «… de Se comunica a la compañía de seguros»; «… médico forense, para que sea reconocido»; «…Se solicita se requiera a la aseguradora»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si las lesiones se deben a imprudencia grave / Si las lesiones se deben a imprudencia menos grave — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- .- Declaración de el/la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- — D./Dña. [NOMBRE Y APELLIDOS] testigo visual de los hechos.…
- .- Pericial del médico forense, para que sea reconocido [COMPLETAR] por el médico forense, a fin de que emita …
- .- Se aporta pericial médica de parte del médico D./Dña. acreditativa del resultado lesional, a fin de que sea…
- .- Documental.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 382 bis CP
- art. 152 CP
- artículos 270 LECRIM
- art. 382 bis CP
- artículos 277 LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 7 del RDLeg. 8/2004
- art. 7.1 RDLeg. 8/2004
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 24.1 LEC
- art. 4 LEC
- art. 24.2 LEC
- art. 77 RDL 6/2023
- art. 195 CP
- art. 152.2 CP
- arts. 147.1, 149 y 150 CP
- art. 20.3 Ley 50/1980
- art. 7 RDLeg. 8/2004
- Ley 20/2015

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

### Formulario 0506 · Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella

- Año del modelo: 2019
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (7); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 5 párrafos opcionales señalados; 33 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 4 huecos del original que se habían perdido sin marca, marcados (IMPORTE, NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de delito de abandono de lugar del accidente (fuga) del artículo 382 bis CP y de lesiones por imprudencia del art. 152 CP derivadas de un accidente de tráfico.

Actualizado conforme a la L 5/2025, de 24 de julio, por la que se modifican el texto refundido de la Ley sobre responsabilidad civil y seguro en la circulación de vehículos a motor y la Ley 20/2015, de 14 de julio, de ordenación, supervisión y solvencia de las entidades aseguradoras y reaseguradoras, vigente desde el 26 de julio de 2025.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 LECRIM y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de abandono del lugar del accidente del art. 382 bis CP, y de lesiones imprudentes del art. 152 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/la querellante es D./Dña. [COMPLETAR], como queda dicho, mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]

TERCERO.- El/La querellado/a es D./Dña. [COMPLETAR], mayor de edad, estado civil, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] y conduciendo el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] con su vehículo matrícula [MATRÍCULA] y asegurado en la compañía [COMPLETAR] por la calle [CALLE] infringió la señal de ceda el paso existente en la confluencia con la calle [CALLE] y colisionó con el vehículo matrícula [MATRÍCULA] conducido por [COMPLETAR]. Tras el accidente y al comprobar el estado lesivo de mi representado/a, conductor del citado vehículo, en lugar de ayudarle, se subió a su vehículo y se marchó del lugar dejando al accidentado abandonado. Del accidente resultó el perjudicado con lesiones consistentes en [DESCRIBIR] tardando en curar [Nº] días. (3) Los daños en el vehículo ascendieron a la suma de

Se comunica a la compañía de seguros [COMPLETAR] la presentación de la querella, lo que equivale a la reclamación extrajudicial de los daños para que proceda a realizar una oferta motivada, conforme al art. 7 del RDLeg. 8/2004, de 29 de octubre. (4)

QUINTO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si las lesiones se deben a imprudencia grave / Si las lesiones se deben a imprudencia menos grave — el texto de cada opción no venía en el formulario original]

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

.- Declaración de el/la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados
judicialmente
mediante exhorto

— D./Dña. agente de la policía local nº [NÚMERO] y D./Dña. agente de la policía local nº [NÚMERO] para que declaren sobre los hechos.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS] testigo visual de los hechos.

[OPCIONAL — incluir si procede]

.- Pericial del médico forense, para que sea reconocido [COMPLETAR] por el médico forense, a fin de que emita informe de sanidad sobre el resultado lesional.

[OPCIONAL — incluir si procede]

.- Se aporta pericial médica de parte del médico D./Dña. acreditativa del resultado lesional, a fin de que sea ratificado el día del juicio. (6)

[OPCIONAL — incluir si procede]

.- Documental.

— Atestado elaborado al efecto.

— Facturas de gastos médico farmacéuticos por importe de [IMPORTE] euros.

— Factura de daños en el vehículo que ascendieron a la suma de [IMPORTE] euros

— Copia de la comunicación del perjudicado a la entidad aseguradora del comienzo del proceso penal (art. 7.1 RDLeg. 8/2004, de 29 de octubre) de fecha [FECHA] (7)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal de el/la querellado/a.

Es de Justicia que pido en [LUGAR]

OTRO SÍ PRIMERO DIGO: Se solicita se requiera a la aseguradora [COMPLETAR] que proceda a la consignación de la suma de [IMPORTE] euros que son objeto de reclamación en base al informe forense y gastos aportados.

OTROSÍ SEGUNDO DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO].

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Este hecho está regulado en el art. 382 bis CP que será el que atraiga ahora las conductas de "fuga del lugar" cuando el accidente sea causado por el conductor, ya que la omisión del art. 195 CP no lo exige. En este caso fue el conductor el que se marchó y fue el causante de los hechos. Es un delito de mayor gravedad penológica porque lleva aparejado pena de privación del permiso de conducir. Se aplica el art. 195 CP si la persona se halla desamparada y en peligro manifiesto y grave.

Existirá delito de fuga tanto si el accidente se produce por imprudencia grave, menos grave o leve del conductor, o, incluso, por caso fortuito sin culpa de éste y no se baja del vehículo para auxiliar al herido, eso sí, debe causarse un siniestro del que se derivan muertes o lesiones de los arts. 147.1, 149 o 150 CP.

La LO 11/2022, vigente desde el 15 de septiembre de 2022, modifica la redacción del delito de abandono del lugar del accidente del art. 382 bis CP. En vez de remitirse a las lesiones del art. 152.2 CP que, a su vez, reenviaba a las de los arts. 147.1, 149 y 150 CP, el propio artículo 382 bis CP se refiere concretamente a estos 3 últimos artículos. La diferencia es que esas lesiones ya no tienen que producirse sólo por imprudencia menos grave, requisito que prevé el art. 152.2 CP, al que ya no hay remisión.

(4) Desde la reforma operada en el art. 7 del RDLeg. 8/2004, de 29 de octubre por la L 5/2025, de 24 de julio, si el perjudicado comunica a la aseguradora el inicio del procedimiento penal ello equivale a la reclamación extrajudicial de los daños y si ésta no consigna podrá reclamarle, luego, los intereses desde la fecha del siniestro por el art. 20.3 Ley 50/1980 de 8 de octubre, de Contrato de Seguro.

(5) Es posible el concurso real del delito del art. 382 bis CP con otro delito de tráfico que se haya cometido, en este caso con lesiones por imprudencia del art. 152 CP. Para la calificación de la imprudencia véase STS 421/2020, de 22 de julio, Rec. 1086/2018.

(6) Dado que en vía penal se contará con el informe del forense se evita el gasto del lesionado en un informe de parte previo a la denuncia para objetivar las lesiones. En cualquier caso puede obtener ese informe para llevarlo al reconocimiento forense si se quiere hacer hincapié en determinados extremos y para que se ese informe de parte pueda ser analizado por el forense. Será decisión del lesionado aportarlo o no, para una mejor información del forense.

(7) Desde la reforma de la L 5/2025, de 24 de julio, si el perjudicado desea presentar reclamación extrajudicial por los daños por la vía del art. 7 RDLeg. 8/2004, de 29 de octubre, debe comunicar al asegurador el inicio del proceso penal, lo que equivaldrá a la presentación de dicha reclamación.

No es preceptiva la reclamación extrajudicial del perjudicado si se va a la vía penal. Pero es recomendable para poder activar la obligación de presentar la oferta por la aseguradora y consignar para evitar los intereses de demora.

================================================================================
