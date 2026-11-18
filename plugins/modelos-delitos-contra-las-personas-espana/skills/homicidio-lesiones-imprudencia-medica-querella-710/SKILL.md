---
name: homicidio-lesiones-imprudencia-medica-querella-710
description: "Redacta el escrito «Homicidio o lesiones por imprudencia médica: querella» (formulario 710 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Homicidio o lesiones por imprudencia médica: querella

> Formulario 0710 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD
- [ ] FECHA (4 veces)
- [ ] DESCRIBIR
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…dad laboral en el centro hospitalario de»; «… atendido/a en el centro hospitalario de»; «…nas molestias que le habían aparecido en»; «…io lugar al siguiente resultado lesional»; «…blema médico que sufría, se debió actuar»; «…eció. ha sufrido las siguientes lesiones»; «…y las siguientes secuelas»; «…médico del hospital»; «…director/a del Hospital»; «…os. Se interesa se solicite del hospital»

## Elecciones que hay que hacer

- del art. 152 CP, / a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes
- homicidio / lesiones
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella y que manifieste en particular.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial consistente en que se efectúe reconocimiento por el forense del estado lesional, al que se aportar…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella, en concreto de los gas…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 142 CP
- art. 152 CP
- artículos 277 LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- artículo 142.2 del Código Penal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 147.2 CP
- art. 3 Ley 41/2002
- arts. 2.2, 3 y 8.1 Ley 41/2002
- arts. 4, 5, 6 y 10 Ley 41/2002
- art. 2.4 Ley 41/2002
- arts. 8, 9 y 10 Ley 41/2002

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

### Formulario 0710 · Homicidio o lesiones por imprudencia médica: querella

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 3 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 bloques de alternativas señalados; 4 párrafos opcionales señalados; 37 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que revisten los caracteres de delito de homicidio, si ha habido resultado de muerte, o lesiones, por imprudencia médica, grave o menos grave.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] (2) por el delito imprudente

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

del art. 142 CP, [ELEGIR: del art. 152 CP, / a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes],

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en la calle número [NÚMERO].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD], médico de profesión y con actividad laboral en el centro hospitalario de [COMPLETAR]. (3)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] mi mandante fue atendido/a en el centro hospitalario de [COMPLETAR] por el médico D./Dña. [NOMBRE Y APELLIDOS] a raíz de un problema de salud que le fue detectado en fecha [FECHA] en un examen médico tras una revisión que solicitó en el citado centro, debido a unas molestias que le habían aparecido en [COMPLETAR].

Se le realizaron dos revisiones para valorar el origen de las dolencias y con fecha [FECHA] se le comunicó que se le iba a intervenir, pero sin llevar a cabo ningún tipo de consentimiento informado (4).

Además, la intervención médica no fue la correcta y no se desarrolló con arreglo a la lex artis (5), habida cuenta que, como consta en el informe pericial que se adjunta, la imprudencia dio lugar al siguiente resultado lesional [COMPLETAR]. Lo es por la no realización de la actuación médica consistente en [DESCRIBIR] que ante el problema médico que sufría, se debió actuar [COMPLETAR].

Como consecuencia de la no adecuación a la lex artis mi mandante

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

falleció.

ha sufrido las siguientes lesiones [COMPLETAR] y las siguientes secuelas [COMPLETAR].

Los gastos producidos han ascendido a la cifra de [IMPORTE] euros.

Los hechos expuestos, sin perjuicio de una mejor calificación jurídica posterior, revisten los caracteres de un delito de [ELEGIR: homicidio / lesiones] por IMPRUDENCIA MÉDICA que define el

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Artículo 142.1 del Código Penal,

artículo 142.2 del Código Penal,

Artículo 152.1 del Código Penal,

Artículo 152.2 del Código Penal,

del que presuntamente es culpable el/la querellado/a.

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella y que manifieste en particular.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- D./Dña. [NOMBRE Y APELLIDOS] médico del hospital [COMPLETAR].

- D./Dña. [NOMBRE Y APELLIDOS] enfermero/a que asistió a mi mandante en su estancia hospitalaria.

- D./Dña. [NOMBRE Y APELLIDOS] director/a del Hospital [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Pericial consistente en que se efectúe reconocimiento por el forense del estado lesional, al que se aportará el informe pericial médico de especialista en valoración de daño corporal para que, con el mismo y con el historial médico, pueda elaborar una pericia acerca de lo ocurrido y la culpabilidad del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella, en concreto de los gastos habidos.

Se interesa se solicite del hospital [COMPLETAR] el historial médico del/de la querellante.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal y sobre los bienes del/de la querellado/a, disponiendo se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros, y, a su vez, se exija fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) IMPORTANTE EN LAS QUERELLAS POR IMPRUDENCIA MÉDICA: Una querella por imprudencia médica puede articularse según haya sido el resultado lesional o mortal causado al paciente y sobre el que se quiere hacer girar la querella.

-Si se trata de responsabilidad por imprudencia médica por caso de muerte puede ser por imprudencia grave o menos grave del art. 142 CP.

-Si se trata de responsabilidad por imprudencia médica por caso de lesiones puede ser por imprudencia grave o menos grave del art. 152 CP.

Es preciso, por tanto, identificar si el hecho es constitutivo de imprudencia grave o menos grave, ya que ello determinará la pena en cada caso y por último cuál ha sido el resultado lesional.

Por ello, habrá que comprobar:

- Si el resultado es muerte o lesiones.

- Si hay imprudencia grave o menos grave. En caso de imprudencia profesional grave, se impondrá la pena de inhabilitación profesional, además de la pena principal correspondiente, no así para el caso de la imprudencia menos grave.

- Si las lesiones son las del art. 147.1, 149 o 150 CP, en el caso de la imprudencia grave, o si son las del art. 149 o 150 CP, en el caso de la imprudencia menos grave.

Las lesiones del art. 147.2 CP solo son punibles si son causadas por dolo no por imprudencia porque no están incluidas en el art. 152 CP.

También habrá que definir qué es imprudencia grave o menos grave para poder ubicar la conducta bien en el caso del art. 142.1 o 2 CP o bien en el art. 152.1 o 2 CP según cada caso. Para ello véase la STS 421/2020, de 22 de julio, Rec. 1086/2018.

(4) La Ley 41/2002, de 14 de noviembre, básica reguladora de la autonomía del paciente y de derechos y obligaciones en materia de información y documentación clínica, en la Exposición de Motivos, subraya la importancia que tienen los derechos de los pacientes como eje básico en las relaciones clínico-asistenciales, y los regula en su articulado. Entre los cuales se encuentra el de recibir una información adecuada antes de prestar el consentimiento a la actuación médica. La Ley 41/2002 define el consentimiento informado como «la conformidad libre, voluntaria y consciente de un paciente, manifestada en el pleno uso de sus facultades, después de recibir la información adecuada, para que tenga lugar una actuación que afecta a su salud»; la información clínica, como «todo dato, cualquiera que sea su forma, clase o tipo, que permite adquirir o ampliar conocimientos sobre el estado físico y la salud de una persona, o la forma de preservarla, cuidarla, mejorarla o recuperarla», y la intervención en el ámbito de la salud, como «toda actuación realizada con fines preventivos, diagnósticos, terapéuticos, rehabilitadores o de investigación» (art. 3 Ley 41/2002, de 14 de noviembre).

En los arts. 2.2, 3 y 8.1 Ley 41/2002, de 14 de noviembre, establece la necesidad de obtener el consentimiento antes de toda actuación en el ámbito de la sanidad, después de recibir el paciente una información adecuada —regulada en los arts. 4, 5, 6 y 10 Ley 41/2002, de 14 de noviembre— que le permita decidir libremente entre las opciones clínicas disponibles.

Reconoce el art. 2.4 Ley 41/2002, de 14 de noviembre, el derecho del paciente a negarse al tratamiento, excepto en los casos determinados en la Ley, debiendo constar la negativa por escrito.

La regulación del consentimiento informado viene dada en los arts. 8, 9 y 10 Ley 41/2002, de 14 de noviembre, del Capítulo IV, titulado «El respeto a la autonomía del paciente».

(5) Para que una intervención médica sea correcta conviene recordar que es necesaria la concurrencia de tres requisitos:

1. Que la intervención sea médicamente indicada. Algo obvio que no necesita más comentarios.
2. Que se realice conforme a la lex artis ad hoc. Esto es, para la existencia de una negligencia profesional médica es necesario, pues, que el médico actúe en el desempeño de las funciones que son propias de su especialidad o titulación y que realice su intervención con olvido o menosprecio de las reglas técnicas o lex artis que presiden el desempeño de una actividad profesional.
3. Que se lleve a cabo con el consentimiento informado del paciente. Con carácter general, el art. 8 de la L 41/2002, de 14 de noviembre, previene que «toda actuación en el ámbito de la salud de un paciente necesita el consentimiento libre y voluntario del afectado, una vez que, recibida la información prevista en el art. 4 L 41/2002, de 14 de noviembre, haya valorado las opciones propias.

Ahora bien, sólo cabrá estimar la existencia de un consentimiento válido si el que consiente está perfectamente informado.

================================================================================
