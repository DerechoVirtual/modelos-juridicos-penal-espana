---
name: entrega-menor-precio-alterar-filiacion-querella-807
description: "Redacta el escrito «Entrega de menor por precio para alterar la filiación: querella» (formulario 807 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Entrega de menor por precio para alterar la filiación: querella

> Formulario 0807 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (3 veces)
- [ ] PROFESIÓN (3 veces)
- [ ] LOCALIDAD (6 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…, director/a del centro hospitalario»; «…Dña. dio a luz en su centro a un niño el»; «…ue le había entregado el/la querellado/a»; «…fermero/a que presenció los hechos. - D.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración de los querellados sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Documental, teniendo por reproducidos los documentos aportados.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 221 del CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 221 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 57 CP
- art. 4 LEC
- art. 24.2 LEC
- art. 62 CP
- Ley 20/2011

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

### Formulario 0807 · Entrega de menor por precio para alterar la filiación: querella

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 3 huecos del original que se habían perdido sin marca, marcados (IMPORTE, NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que pueden ser constitutivos de un delito de entrega de menor para alterar la filiación del art. 221 del CP.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D. y Dña. por el delito de alteración de la paternidad, estado o condición del menor del art. 221 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

TERCERO.- Los querellados son D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD] y Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecina de [LOCALIDAD] con domicilio en [LOCALIDAD]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

D./Dña. [NOMBRE Y APELLIDOS], director/a del centro hospitalario [COMPLETAR] tuvo conocimiento de que la querellada Dña. dio a luz en su centro a un niño el [COMPLETAR], como consta en el certificado expedido por el/la médico D./Dña. [NOMBRE Y APELLIDOS] que se adjunta como documento nº 1. Al día siguiente, tuvo noticia de que el/la enfermero/a D./Dña. [NOMBRE Y APELLIDOS] presenció cómo el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] recibía al menor de manos de su progenitora gestante, la también querellada Dña. [NOMBRE Y APELLIDOS] en la misma habitación del hospital, comprobando como el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] le entregaba a cambio un sobre con dinero, que pudo ver el/la enfermero/a desde el pasillo al estar la puerta entreabierta. Acto seguido, el/la querellado/a salió de la habitación corriendo, dando aviso la enfermera al equipo de seguridad del hospital, siendo interceptado por el guarda de seguridad D. antes de salir del centro hospitalario. A la progenitora gestante del menor se le intervino un sobre que le había entregado el/la querellado/a [COMPLETAR], que contenía 3.000 euros.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de alteración de la paternidad, estado o condición del menor del art. 221 CP, en grado de tentativa, del que presuntamente son culpables los querellados. (3)

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración de los querellados sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

- D./Dña. [NOMBRE Y APELLIDOS], enfermero/a que presenció los hechos.

- D. [COMPLETAR], encargado de seguridad del hospital que detuvo al acusado saliendo del centro con el bebé en brazos.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos aportados.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal de los querellados, disponiendo se proceda a la detención y prisión provisional de los querellados, o se les exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias. Además, se interesa se acuerde la medida cautelar de alejamiento y prohibición de comunicación de los arts. 13 y 544 bis LECRIM, en relación con el art. 57 CP.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, en cumplimiento de lo previsto en el art. 280 de la Ley de Enjuiciamiento criminal, esta parte prestará la fianza que este órgano judicial estime conveniente para responder de las resultas del juicio.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Este es un delito esencialmente doloso. Se trata de un delito en el que, a cambio de precio, se provoca la alteración de la paternidad, estado o condición de un menor. Exige como elemento del tipo que "medie una compensación económica".

El objetivo real es alterar la filiación.

Se castiga tanto al que da al menor como al que lo recibe y al intermediario, aunque la entrega del menor se hubiese efectuado en país extranjero.

Se aplicaría la pena inferior en grado al tratarse de tentativa de delito (art. 62 CP).

En las parejas del mismo sexo registral, las referencias hechas a la madre se entenderán hechas a la madre o progenitor gestante y las referencias hechas al padre se entenderán referidas al padre o progenitor no gestante (DA 10ª Ley 20/2011, de 21 de julio, del Registro Civil, según redacción dada por L 4/2023, de 28 de febrero, para la igualdad y garantía de derechos de las personas trans y LGTBI).

================================================================================
