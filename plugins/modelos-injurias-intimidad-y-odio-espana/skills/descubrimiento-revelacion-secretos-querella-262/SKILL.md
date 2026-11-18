---
name: descubrimiento-revelacion-secretos-querella-262
description: "Redacta el escrito «Descubrimiento y revelación de secretos: querella» (formulario 262 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Descubrimiento y revelación de secretos: querella

> Formulario 0262 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 197 CP está vigente en la redacción dada por la LO 10/2022 (desde el 7-10-2022). Su apartado 7 incluye hoy un segundo párrafo que castiga a quien, habiendo recibido imágenes o grabaciones íntimas, las difunde, revela o cede sin consentimiento. El art. 417 CP no ha cambiado.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] NÚMERO (2 veces)
- [ ] Nº DE DOCUMENTO (5 veces)
- [ ] LOCALIDAD (14 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ÓRGANO
- [ ] FECHA (5 veces)
- [ ] Otros 25 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dor/a de los Tribunales y de la sociedad»; «…ra de poder especial otorgado a mi favor»; «…te. SEGUNDO.- Es querellante la sociedad»; «…legalmente por su administrador único D.»; «…on domicilio en [LOCALIDAD] - La empresa»; «…presentada por su administrador único D.»; «… certificación del Registro Mercantil de»; «… colaboración y préstamo con la sociedad»; «…suscrito con la sociedad»; «… y el administrador único de la sociedad»; «…recieron en la notaría del querellado D.»; «…, de la sucursal bancaria de»; …

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1) Se cite a los querellados y se les reciba declaración en concepto de investigados.…
- 2) Se solicite del Registro Central de Penados hoja histórico-penal del querellados, uniéndose a los autos.…
- 3) Testifical, a fin de que se reciba declaración a:…
- 4) Documental, admitiendo los documentos acompañados con este escrito de querella.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 417 del Código Penal
- artículos 270 y 277 de la Ley de Enjuiciamiento Criminal
- art. 14.2 de la LECrim
- arts. 197 y 198 CP
- arts. 197 y 198 del CP
- art. 417 del CP
- art. 197.2 CP
- artículo 417.2 CP
- art. 417 CP
- artículo 197.2 del CP
- art. 24 CP
- art. 427 CP
- art. 198 del CP
- art. 277.5 de la LECrim

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

### Formulario 0262 · Descubrimiento y revelación de secretos: querella

- Año del modelo: 2022
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 63 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO, Nº DE DOCUMENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 146) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que se ponen en conocimiento del Juez unos hechos que presentan los caracteres de un delito de descubrimiento y revelación de secretos de los arts. 197 y ss CP o, alternativamente, del art. 417 CP. Recuerde que....

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de la sociedad [COMPLETAR], según consta en escritura de poder especial otorgado a mi favor [COMPLETAR],

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada.

Actuando bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [LOCALIDAD] colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que en nombre de mi mandante y siguiendo sus instrucciones por medio del presente escrito interpongo QUERELLA CRIMINAL por delito de descubrimiento y revelación de secretos, previsto y penado en los art. 197, 197 quinquies y 198 del Código Penal o, alternativamente, en el art. 417 del Código Penal, todo ello conforme a lo previsto en los artículos 270 y 277 de la Ley de Enjuiciamiento Criminal y

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente conforme al art. 14.2 de la LECrim., al haberse cometido los delitos en dicho partido judicial según se puede constatar de la descripción de hechos que se realizará posteriormente.

SEGUNDO.- Es querellante la sociedad [COMPLETAR], con domicilio en [LOCALIDAD], representada legalmente por su administrador único D. [COMPLETAR], mayor de edad, vecino de [LOCALIDAD], con domicilio en [LOCALIDAD], en su calidad de perjudicada por el delito objeto de querella como se relatará seguidamente.

TERCERO.- Se dirige la querella contra:

- D/Dª [NOMBRE Y APELLIDOS], de profesión notario/a, mayor de edad, vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD]
-D/Dª [NOMBRE Y APELLIDOS], de profesión abogado/a, mayor de edad, vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD]
- La empresa [COMPLETAR], con domicilio en [LOCALIDAD].

CUARTO.- La querella se interpone por un delito de descubrimiento y revelación de secretos previsto y penado en los arts. 197 y 198 CP o, alternativamente, en el art. 417 del Código Penal, según resulta de los siguientes hechos:

1) La sociedad querellante [ÓRGANO] está dedicada a realizar proyectos y obras de ingeniería civil, ostentando la condición de contratista pública en numerosos contratos en el ámbito de las Administraciones y entes públicos estatales, autonómicos y locales. La misma está representada por su administrador único D. [COMPLETAR], quien ostenta asimismo la titularidad del 90% de su capital social, según consta en la certificación del Registro Mercantil de [COMPLETAR] que acompaño como documento número [Nº DE DOCUMENTO].
En fecha [FECHA], la querellante, con motivo de sus necesidades contractuales y de financiación para concurrir a una licitación con el Ayuntamiento de [LOCALIDAD], para la construcción de un centro multiusos municipal, por importe de diez millones de euros, concertó un contrato privado de colaboración y préstamo con la sociedad [COMPLETAR], por importe de ochocientos mil euros, para la ejecución de las obras y hacer frente a los gastos necesarios para afrontar las inversiones derivadas del proyecto, en caso de ser adjudicada su licitación por el Ayuntamiento ( acompaño como documento número [Nº DE DOCUMENTO] contrato privado de fecha [FECHA] suscrito con la sociedad [COMPLETAR]).
A este efecto, y como quiera que en fecha [FECHA] se adjudicó el contrato a la sociedad que administra mi representado, el querellante y el administrador único de la sociedad [COMPLETAR], comparecieron en la notaría del querellado D. [COMPLETAR], sita en [LOCALIDAD], en la cual otorgaron escritura pública de contrato de ejecución de obras y de préstamo, de fecha [FECHA], autorizada por el querellado, por importe de ochocientos mil euros, los cuales se entregaron en ese mismo acto mediante ingreso en la cuenta corriente de la sociedad de mi representado número [NÚMERO], de la sucursal bancaria de [COMPLETAR] ( acompaño como documentos números 1 a 3, resolución de adjudicación del contrato, escritura pública de préstamo de fecha [FECHA] y resguardo de transferencia del importe total del préstamo).
2) A los pocos días de otorgarse dicha escritura de préstamo, el querellado D/Dª [NOMBRE Y APELLIDOS], actuando como abogado de la sociedad querellada [COMPLETAR], acudió a la sucursal bancaria donde se produjo el ingreso del préstamo, entrevistándose con el director de la sucursal D. [COMPLETAR], a quien le manifestó que tenía un reconocimiento notarial de deuda a favor de la sociedad cuya ejecución judicial se iba a instar de forma inmediata, conminándole a que bloqueara cualquier tipo de operación dineraria sobre la cuenta de la sociedad administrada por el querellante.
Ante la renuencia del director de la sucursal, el abogado querellado D/Dª [NOMBRE Y APELLIDOS] le exhibió un acta notarial de reclamación de deudas dinerarias no contradichas de tres años atrás, donde presuntamente se fijaba una cantidad adeudada por la sociedad querellante por importe de 230.000 euros, cuya validez y eficacia se niega rotundamente por esta parte, así como una copia de la escritura pública de ejecución de obras y préstamo que habían concertado mi representado y la sociedad prestamista [COMPLETAR].
En esta situación, el director de la sucursal D comunicó los hechos a mi representado, quien se puso de inmediato en contacto con la notaría, cuyos empleados negaron cualquier tipo de intervención en los hechos, sin que el notario querellado quisiera atender en ningún momento a los representantes de la sociedad querellante.
3) Ante ello, la querellante realizó diferentes gestiones con la sociedad prestamista, que desconocía absolutamente estos hechos. Asimismo, se puso en contacto con el abogado querellado a través de su defensa, quien omitió cualquier tipo de explicación.

Sin embargo, a través de los empleados de la notaría, así como por el conocimiento de numerosas personas que tienen relación con la sociedad querellada y con su abogado, esta parte ha podido conocer que el notario y abogado querellados tienen una relación de íntima amistad desde hace mucho tiempo atrás, y que incluso el notario es padrino de uno de los hijos del abogado querellado, lo cual es un primer sólido indicio de que el notario querellado, faltando a los deberes de su cargo, fue quien pudo entregar el contrato de ejecución de obras y de préstamo suscrito por la querellante al abogado querellado.

Ello concuerda con que el acta notarial de reclamaciones de deudas dinerarias fue autorizada por el mismo notario querellado D/Dª [NOMBRE Y APELLIDOS], aunque en aquel momento tenía su notaría en [COMPLETAR], tal como se acredita por la copia auténtica del acta que se acompaña como documento número
Junto a ello, tal como se acredita por la certificación del Registro Mercantil que se acompaña como documento número [Nº DE DOCUMENTO], tanto el notario como el abogado querellados son socios de la sociedad querellada [COMPLETAR] en un porcentaje del 40% del capital social cada uno de ellos, lo cual pone de manifiesto, indiciariamente, que ha existido una acción concertada para actuar en perjuicio de la querellante (acompaño como documento número [Nº DE DOCUMENTO] certificación del Registro Mercantil).
4) Esta parte entiende que, en principio y sin perjuicio de lo que resulte de la instrucción, los hechos relatados son susceptibles de ser calificados provisionalmente como un delito de descubrimiento y revelación de secretos de los arts. 197 y 198 del CP o, alternativamente, de violación de secretos del art. 417 del CP, de los que son responsables el abogado y notario querellados, así como la sociedad querellada [COMPLETAR], en este caso conforme a lo dispuesto en el art. 197 quinquies del Código Penal.

Se dan los requisitos de la conducta típica, puesto que hay sólidos indicios de que el notario querellado se apoderó y utilizó la información recabada en el ejercicio de su función, tanto cuando tramitó el procedimiento monitorio notarial, como cuando intervino como fedatario en el contrato de préstamo suscrito por la sociedad querellante, en beneficio del abogado y sociedad querelladas, y en perjuicio de la querellante. Resulta que el notario querellado se apoderó, utilizó y suministró la información y los datos de la querellante de un negocio privado concertado con otra sociedad, que era totalmente desconocido para terceros.

Como indican las SSTS 941/2005, de 18 de julio, y 1328/2009, de 30 de diciembre, el funcionario está autorizado para acceder a la información que conoce solo en lo relativo al desempeño de su función y, desde luego, nunca para hacer a aquella objeto de un apoderamiento ilícito, siendo típica la conducta tanto si es un acceso indebido a los datos por la vía del art. 197.2 CP, "sin estar autorizado", como por la vía artículo 417.2 CP, cuando el autor tiene un conocimiento propio de su cargo y obtenido por su intervención como fedatario público. En ambos casos se vulnera por el notario querellado su deber funcionarial de secreto.

Existen sólidos indicios de que el notario querellado violó el secreto en connivencia con el abogado querellado [COMPLETAR], con la finalidad de resarcirse de la presunta y negada deuda que tenía la querellante con la sociedad querellada [COMPLETAR] de la que forman parte como socios capitalistas, de manera que actuaron de consuno con ésta en perjuicio de la querellante, utilizando los datos personales recabados, entre ellos el número de cuenta bancaria, para presionar al director de la sucursal y obtener un beneficio económico en base a una supuesta deuda.

La actuación de los querellados se integra en todo caso en las conductas que tipifican tanto el art. 417 CP como el artículo 197.2 del CP, habiéndose apoderado y utilizado los datos de la querellante en perjuicio de la afectada, lo cual rellena los requisitos del tipo penal, de acuerdo a la interpretación reiterada en la STS núm. 525/2014, de 17 de junio, que sostiene que el término "perjuicio de tercero" incluye también al afectado, al titular de los datos, como ya se indicara en las SSTS 1084/2010 y 990/2012.

Como indica la STS 1084/2010, basta con que la acción se realice con la finalidad de perjudicar, sin que resulte necesaria para la consumación la producción del resultado lesivo, pues se trata de un delito de peligro que no requiere la ulterior producción de un resultado de lesión."

En el presente caso, los querellados actuaron con conocimiento del carácter reservado de los datos, a los que accedieron al margen de cualquier procedimiento o expediente, actuando conscientemente en perjuicio de la querellante titular de los datos personales, obtenidos ilegalmente, poniendo al descubierto los datos negociales y de titularidad de cuenta cuyo carácter reservado está fuera de toda duda, y con ello dañó el derecho de la querellante a preservarlos del conocimiento de tercero, En el caso del notario querellado, se prevalió claramente de su cargo, ostentando la condición de autoridad o funcionario ex art. 24 CP, por lo que su conducta se integra bien en el art. 427 CP, bien en el subtipo agravado del art. 198 del CP.

QUINTO.- Al derecho de esta parte interesa, de conformidad con lo dispuesto en el art. 277.5 de la LECrim., la práctica de las siguientes diligencias de investigación:

[OPCIONAL — incluir si procede]

1) Se cite a los querellados y se les reciba declaración en concepto de investigados.

[OPCIONAL — incluir si procede]

2) Se solicite del Registro Central de Penados hoja histórico-penal del querellados, uniéndose a los autos.

[OPCIONAL — incluir si procede]

3) Testifical, a fin de que se reciba declaración a:

- Mi representado D. [COMPLETAR], que comparecerá tan pronto sea citado por el Juez, interesándose su citación por medio de esta representación procesal.
-D/Dª [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], director de la sucursal bancaria de [COMPLETAR].
-D/Dª [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], administrador de la sociedad prestamista [COMPLETAR].
-D/Dª [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], empleado de la notaría de [COMPLETAR]

[OPCIONAL — incluir si procede]

4) Documental, admitiendo los documentos acompañados con este escrito de querella.

5) Las diligencias que V.I. considere oportunas y de interés para la causa, así como las derivadas de las anteriores.

SEXTO.- Esta parte, para garantizar las responsabilidades civiles derivadas del delito, interesa que se requiera a los querellados para que constituyan fianza por importe de 100.000 euros, procediendo, en otro caso, al embargo de bienes suficientes.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta querella, con su copia respectiva, se sirva en admitirla a trámite y, en su virtud, tenga por imputado al querellado, acuerde practicar las diligencias solicitadas, adoptando las medidas cautelares interesadas para garantizar la responsabilidad civil en que pudieren haber incurrido los querellados.

PRIMER OTROSÍ DIGO: que la querellante, en su calidad de perjudicada, por el hecho delictivo está exento de prestar fianza.

SUPLICO A LA SECCIÓN: que declare exenta a esta parte de la obligación de constituir fianza.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 197 CP está vigente en la redacción dada por la LO 10/2022 (desde el 7-10-2022). Su apartado 7 incluye hoy un segundo párrafo que castiga a quien, habiendo recibido imágenes o grabaciones íntimas, las difunde, revela o cede sin consentimiento. El art. 417 CP no ha cambiado.]
