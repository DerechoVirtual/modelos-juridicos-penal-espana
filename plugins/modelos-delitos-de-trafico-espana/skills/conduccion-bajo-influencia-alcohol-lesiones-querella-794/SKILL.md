---
name: conduccion-bajo-influencia-alcohol-lesiones-querella-794
description: "Redacta el escrito «Conducción bajo la influencia del alcohol y lesiones: querella» (formulario 794 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción bajo la influencia del alcohol y lesiones: querella

> Formulario 0794 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Califican las lesiones por el art. 147 CP (doloso); en un accidente por conducción etílica son lesiones imprudentes del art. 152.1 CP, que la LO 11/2022 reputa en todo caso imprudencia grave, y con esa pena debe hacerse la comparación del art. 382 CP.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ACTO O RESOLUCIÓN
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (2 veces)
- [ ] MATRÍCULA (2 veces)
- [ ] Nº DE DOCUMENTO (5 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con domicilio en [LOCALIDAD],»; «…, con domicilio en [LOCALIDAD],»; «…, [COMPLETAR],»; «…y asegurado en la compañía»; «…por la vía interurbana»; «…con los ocupantes»; «…y asegurado en la compañía»; «…r trasladado/a al centro hospitalario de»; «…onde se aprecian las siguientes lesiones»; «…os agentes de la autoridad, se le hizo a»; «…, dando un resultado positivo al test de»; «…eron los siguientes daños en el vehículo»; …

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a [COMPLETAR].…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- - D./Dña. [NOMBRE Y APELLIDOS] amigo/a del querellante que iba como ocupante del vehículo siniestrado.…
- .- Pericial.…
- .- Documental, teniendo por reproducido los documentos aportados.…

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 147 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 379 CP
- art. 382 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 7 RDLeg. 8/2004
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- Ley 35/2015

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

### Formulario 0794 · Conducción bajo la influencia del alcohol y lesiones: querella

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 2 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 47 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)
- Avisos de la revisión: Califican las lesiones por el art. 147 CP (doloso); en un accidente por conducción etílica son lesiones imprudentes del art. 152.1 CP, que la LO 11/2022 reputa en todo caso imprudencia grave, y con esa pena debe hacerse la comparación del art. 382 CP.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que pueden ser constitutivos de delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 y lesiones del art. 147 CP.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra [ACTO O RESOLUCIÓN] por el delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, en relación con los art. 382 CP y art. 147 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes [NOTA DE REVISIÓN: El art. 277 citado es el de la LECrim (requisitos de la querella), no el del Código Penal. Fuente: Ley de Enjuiciamiento Criminal, BOE-A-1882-6036, art. 277.],

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD], [COMPLETAR].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD], [COMPLETAR], [COMPLETAR] (2).

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] mi mandante iba circulando con su vehículo matrícula [MATRÍCULA] y asegurado en la compañía [COMPLETAR] por la vía interurbana [COMPLETAR] con los ocupantes [COMPLETAR] cuando, al ir a salir de la misma realizando la debida indicación, le golpeó por detrás el vehículo matrícula [MATRÍCULA] conducido por D./Dña. [NOMBRE Y APELLIDOS] y asegurado en la compañía [COMPLETAR].

Tras ocurrir el accidente, compareció una dotación policial que requirió los servicios de una ambulancia, ya que tras el golpe, y a consecuencia de la velocidad del vehículo que conducía a 70 Km/h por encima de la permitida en el tramo donde ocurrieron los hechos, como consta en el atestado policial, mi mandante tuvo que ser trasladado/a al centro hospitalario de [COMPLETAR] en el que permaneció [Nº] días ingresado/a y, tras lo cual, se emitió informe médico que consta al documento nº [Nº DE DOCUMENTO] de la presente querella, donde se aprecian las siguientes lesiones [COMPLETAR] que integran las recogidas en el art. 147 CP.

Una vez comparecieron los agentes de la autoridad, se le hizo a [COMPLETAR] la prueba de alcoholemia, dando un resultado positivo al test de [COMPLETAR] como consta en el atestado al documento nº [Nº DE DOCUMENTO] aportado a la querella.

A raíz del hecho, se produjeron los siguientes daños en el vehículo [COMPLETAR] cuya reparación asciende a la suma de [IMPORTE] euros, según consta en presupuesto de valoración de daños que se adjunta como documento nº [Nº DE DOCUMENTO]. El resultado lesivo fue el siguiente [COMPLETAR] como consta en el informe del médico que se adjunta como documento nº [Nº DE DOCUMENTO].

Se acompaña como documento nº [Nº DE DOCUMENTO] la reclamación del perjudicado efectuada a la aseguradora del querellado, a los efectos del art. 7 RDLeg. 8/2004, de 29 de octubre, modificado por la Ley 35/2015 a los efectos del devengo de los intereses de demora, en su caso.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, en relación con el art. 382 CP y el delito de lesiones del art. 147 Código penal, del que presuntamente es culpable el/la querellado/a (3).

QUINTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto],

- Declaración del/de la querellante sobre los hechos de la querella.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] amigo/a del querellante que iba como ocupante del vehículo siniestrado.

[OPCIONAL — incluir si procede]

.- Pericial.

- Que D./Dña. [NOMBRE Y APELLIDOS] sea reconocido/a por el médico forense D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del querellado, disponiendo se proceda a la detención y prisión provisional del querellado, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros, que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Este es un delito esencialmente doloso en el que los perjudicados u ofendidos son las víctimas del accidente. Es un delito de riesgo que puede concurrir con un accidente del que se causen lesiones a terceros.

En este caso concurriría un delito del art. 379 CP y otro del art. 147 CP, pero se aplicaría el art. 382 CP que nos remitiría a la penalidad del art. 147 CP [NOTA DE REVISIÓN (comprobar): Las lesiones causadas al conducir bajo los efectos del alcohol son imprudentes: art. 152.1 CP en relación con el 147.1 (la LO 11/2022 reputa en todo caso imprudencia grave la conducción del art. 379 que determine el hecho); la comparación del art. 382 debe hacerse con esa pena. Fuente: Código Penal, BOE-A-1995-25444, arts. 152.1 y 382 (LO 11/2022, BOE-A-2022-14965).], ya que la infracción más gravemente penada es la del art. 147 CP, puesto que el del art. 379 CP lo es con pena de prisión de tres a seis meses y el del art. 147 CP de tres meses a tres años, con lo que se aplica la pena más grave en su mitad superior, que en este caso sería la de 16 meses y 15 días mínimo [NOTA DE REVISIÓN: Cálculo erróneo incluso con el art. 147.1 CP: la mitad superior de tres meses a tres años empieza en un año, siete meses y quince días. Fuente: Código Penal, BOE-A-1995-25444, arts. 147.1 y 382.].

En estos casos el perjudicado puede exigir por querella o denuncia la responsabilidad civil causada. Y los hechos podrían tramitarse por la vía penal al ser las lesiones causadas constitutivas de delito del art. 147 CP.

================================================================================
