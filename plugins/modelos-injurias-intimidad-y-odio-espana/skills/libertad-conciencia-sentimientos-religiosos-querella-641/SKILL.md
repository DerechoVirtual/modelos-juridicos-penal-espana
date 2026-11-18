---
name: libertad-conciencia-sentimientos-religiosos-querella-641
description: "Redacta el escrito «Libertad de conciencia y sentimientos religiosos: querella» (formulario 641 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Libertad de conciencia y sentimientos religiosos: querella

> Formulario 0641 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] LOCALIDAD (5 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] CALLE
- [ ] PROFESIÓN
- [ ] FECHA (3 veces)
- [ ] Nº
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «… de Justicia con la siguiente referencia»; «…terio de Justicia, porque, de no hacerlo»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Declaración del querellante.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], que se encontraba ese día en el templo religioso.…
- .- Documental, aportando las cintas de grabación del lugar que grabaron la secuencia ocurrida el día [FECHA] a…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 523 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 277 LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- artículo 523 CP

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

### Formulario 0641 · Libertad de conciencia y sentimientos religiosos: querella

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un párroco pone en conocimiento del juez unos hechos que presentan los caracteres de un delito contra los sentimientos religiosos del art. 523 CP, al haber entrado una persona en su iglesia amenazando y usando la fuerza para echar a los que allí estaban.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en representación de la parroquia sita en [LOCALIDAD], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS], por el delito del art. 523 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El querellante es D. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, con domicilio en [LOCALIDAD], calle [CALLE], y párroco de la iglesia sita en [LOCALIDAD]. (2)

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (3)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a, el día [FECHA] accedió a la iglesia sita en [LOCALIDAD] amenazando a los que se encontraban allí presentes para que se marcharan del templo religioso, e incluso empujó a dos señoras que se encontraban en la primera fila, agarrándolas con fuerza del brazo para que salieran del lugar, lo que obligó a suspender el acto religioso que en ese momento se estaba realizando, referido a la confesión religiosa inscrita en el Ministerio de Justicia con la siguiente referencia [COMPLETAR].

QUINTO.- Los hechos expuestos revisten los caracteres de un delito contra los sentimientos religiosos del art. 523 CP y del que presuntamente es culpable el/la querellado/a, que es quien irrumpe en lugar de culto religioso y atenta contra los sentimientos religiosos. (4)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Declaración del querellante.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que se encontraba ese día en el templo religioso.

[OPCIONAL — incluir si procede]

.- Documental, aportando las cintas de grabación del lugar que grabaron la secuencia ocurrida el día [FECHA] a las [Nº] horas.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se exija fianza en la cantidad de [IMPORTE] euros para hacer frente a las responsabilidades civiles que se deriven y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(2) El párroco es el único representante legal de la Parroquia y quien debe cuidar y responder por todos los bienes de la Parroquia y defender los intereses de la misma, y en este caso otorgar el poder para presentar la querella por haberse cometido el delito dentro de ella y atentar contra los sentimientos religiosos.

(3) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(4) En este tipo penal se exige la concurrencia de cualquiera de las vías de acción que constan en el tipo, es decir, violencia, amenaza, tumulto o vías de hecho y la acción consiste en impedir, interrumpir o perturbar actos, funciones, ceremonias o manifestaciones de confesiones religiosas, pero se exigen que consten inscritas en el Registro del Ministerio de Justicia, porque, de no hacerlo [COMPLETAR], no estaría incluido en el tipo y solo se sancionarían las conductas realizadas que fueran delictivas, pero fuera de este artículo 523 CP.

Si, además de los hechos descritos en el art. 523 CP se realizaran otros consistentes en daños en bienes muebles o lesiones a las personas presentes en el lugar, se aplicarían las reglas del concurso con el tipo del art. 523 CP.

La STS 835/2017, de 19 de diciembre, rec. 47/2017, por un lado, recuerda que la ley exige que se actué con violencia, amenaza, tumulto o vías de hecho, de manera que el impedimento, la interrupción o la perturbación ocasionada de cualquier otra forma no sería delictiva. Por otro, que la doctrina exige que cualquiera de esos resultados presente cierta relevancia, teniendo en cuenta el tiempo de duración, la forma en la que se ha causado y la forma en la que cesó.

En cuanto a la penalidad se impone la de 6 meses a 6 años si los actos se realizan en lugar de culto y la de multa de 4 a 10 meses si se hacen en otro lugar, es decir fuera del lugar de culto, tales como los templos religiosos.

================================================================================
