---
name: delito-contable-tributario-aplazar-renta-local-covid-19-430
description: "Redacta el escrito «Delito contable tributario para aplazar renta del local (COVID-19): querella» (formulario 430 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contable tributario para aplazar renta del local (COVID-19): querella

> Formulario 0430 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (5 veces)
- [ ] FECHA (4 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a reducción de la facturación mensual en»; «…dentro de este partido, concretamente en»; «…ario en el pago de la renta de los meses»; «…del mes»; «…a reducción de la facturación mensual en»

## Elecciones que hay que hacer

- sin fianza / con fianza, que se fijará en la cantidad de [IMPORTE], exigiéndose fianza para cubrir las responsabilidades civiles, procediéndose, si no la prestara, a embargar sus bienes suficientes para atenderlas, fijándose su importe en [IMPORTE] euros

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- DECLARACIÓN del/de la querellado/a sobre los hechos de la querella.…
- .- TESTIFICAL, consistente en la declaración de los/as testigos que se enumeran a continuación, que deberán se…
- - D./Dña. [NOMBRE Y APELLIDOS], empleado/a del local de negocio arrendado.…
- - D./Dña. [NOMBRE Y APELLIDOS], cliente habitual del local de negocio arrendado.…
- .- PERICIAL judicial, para que, por el/la perito designado/a, experto/a en análisis de contabilidad, se haga u…
- .- DOCUMENTAL consistente en:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 310 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 de la LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 3.1.c) del RDL 15/2020
- art. 10.1 RD 463/2020
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 1.1 RDL 15/2020
- art. 3 RDL 15/2020
- art. 390 CP
- art. 5 RDL 15/2020
- artículo 3 RDL 15/2020
- art. 1 RDL 15/2020
- art. 2 RDL 15/2020

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

### Formulario 0430 · Delito contable tributario para aplazar renta del local (COVID-19): querella

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a juzgados penales actualizadas (LO 1/2025); 3 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)
- Avisos de la revisión: El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Querella de arrendador contra arrendatario por posible delito contable tributario del art. 310 CP, por alterar la contabilidad del negocio para acreditar una reducción de la facturación mensual en [COMPLETAR], al menos, un 75%, en relación con la facturación media mensual del mismo trimestre del año anterior, para solicitar un aplazamiento de la renta por COVID 19.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Todas las referencias a Juzgados contenidas en este documento se entenderán sustituidas por las Secciones correspondientes de los Tribunales de Instancia cuando estos se constituyan, conforme al régimen transitorio que prevé la DT 1ª LO 1/2025.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante el Tribunal comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo QUERELLA en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, contra D./Dña. [NOMBRE Y APELLIDOS], a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 de la LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante el Tribunal de Instancia (Sección de Instrucción) de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellante es arrendador/a del inmueble sito en [LOCALIDAD] del que es arrendatario/a el/la querellado/a. Con fecha [FECHA] el/la arrendatario/a presentó a mi mandante por correo electrónico una solicitud de aplazamiento y quita en la deuda existente en el pago de la renta mensual del inmueble, como consecuencia de la pandemia del COVID 19, en la que alegaba, en base al art. 3.1.c) del RDL 15/2020, de 21 de abril, el aplazamiento temporal y extraordinario en el pago de la renta de los meses [COMPLETAR], comenzando el pago aplazado desde el día [FECHA] del mes [COMPLETAR]. Para ello, envió a mi mandante en el correo electrónico antes citado la documentación contable relativa a la facturación que había tenido en las mensualidades en las que pudo abrir el local, por no estar incluido en los que tenían prohibición ex art. 10.1 RD 463/2020, de 14 de marzo, y ello comparado con la media mensual del trimestre al que pertenece dicho mes referido al año anterior, para cuyo fin se adjuntó la copia de la contabilidad relativa a la constancia en sus libros de contabilidad.

Conforme a esos datos contables, se pactó un aplazamiento de la renta firmado en fecha [FECHA] Sin embargo, según noticias que nos han llegado de los/as testigos que declararán, no son ciertos los datos adjuntos, ni la contabilidad relativa al periodo del estado de alarma, ni la precedente del año anterior, de tal forma que ha alterado los datos contables de ambos periodos para disfrazar las ganancias obtenidas y ampararse en una petición de aplazamiento en la renta, fuera de los cauces permitidos por el RDL 15/2020, de 21 de abril, mediante el ardid de la falsedad contable.

En base a esas alteraciones contables, se pactó un aplazamiento de la renta que se debe considerar nulo por haberse basado en la documentación falsa presentada. La renta que se debía pagar durante el periodo que se pactó el aplazamiento ascendía a la suma de [IMPORTE] euros; sin embargo, la renta actual que se debe pagar es la de [IMPORTE] euros.

QUINTO.- Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito contable tributario del art. 310 CP. (3)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- DECLARACIÓN del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- TESTIFICAL, consistente en la declaración de los/as testigos que se enumeran a continuación, que deberán ser citados/as en el día y hora que a tal fin se señale para su declaración ante el/la Juez/a instructor/a:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], empleado/a del local de negocio arrendado.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], cliente habitual del local de negocio arrendado.

[OPCIONAL — incluir si procede]

.- PERICIAL judicial, para que, por el/la perito designado/a, experto/a en análisis de contabilidad, se haga un informe de los libros de contabilidad del/de la querellado/a en consonancia con los informes de la Agencia Tributaria y la documental que se adjunta que fue la que envió el/la querellado/a al/a la querellante para conseguir la rebaja de la renta.

[OPCIONAL — incluir si procede]

.- DOCUMENTAL consistente en:

- Copia de la aportada por el/la querellado/a, que se considera falsa, y que se requiera a la Agencia Tributaria para que se remita la declaración fiscal del/de la querellado/a del ejercicio del año anterior.
- Copia del pacto firmado de aplazamiento del pago.
- Que se requiera al/a la querellado/a la exhibición de sus libros de contabilidad.

Por lo expuesto,

SUPLICO AL TRIBUNAL:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal y sobre los bienes del/de la querellado/a D./Dña. [NOMBRE Y APELLIDOS], acordando su detención y prisión provisional [ELEGIR: sin fianza / con fianza, que se fijará en la cantidad de [IMPORTE], exigiéndose fianza para cubrir las responsabilidades civiles, procediéndose, si no la prestara, a embargar sus bienes suficientes para atenderlas, fijándose su importe en [IMPORTE] euros].

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO AL TRIBUNAL: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a;	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Tribunal de Instancia (Sección de Instrucción).

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Este supuesto se refiere a los casos de arrendatarios de locales que han podido abrir desde el 15 de Marzo de 2020, fecha de declaración del estado de alarma por Coronavirus por RD 463/2020, de 14 de marzo, pero su facturación ha sido baja, aunque no lo suficiente para ampararse en la previsión del art. 1.1 RDL 15/2020, de 21 de abril, que da derecho a empresas, o entidades públicas o grandes tenedores y PYMES y autónomos a un aplazamiento temporal y extraordinario en el pago de la renta del local, arts. 3.1.c) y 3.2.c) RDL 15/2020, de 21 de abril.

El art. 3 RDL 15/2020, de 21 de abril, recoge los requisitos para tener derecho al aplazamiento en el pago de la renta de local. En este sentido, no podría tratarse de un hecho delictivo la circunstancia de que se redactaran documentos por los particulares alterando la verdad en los hechos, ya que la única forma de entender ilícito penal en las falsedades es la de la falsedad documental por la vía de los nº 1, 2 o 3 del art. 390 CP; pero no la de alteración de la verdad en la narración de los hechos, ya que ello iría como falsedad ideológica al ser no punible.

El art. 5 RDL 15/2020, de 21 de abril, regula las consecuencias para los arrendatarios que se hayan beneficiado del aplazamiento sin reunir los requisitos establecidos en el artículo 3 RDL 15/2020, de 21 de abril.

Sí que constituiría un ilícito penal, en concreto un delito de falsedad contable del art. 310 CP, si el arrendatario alterara la contabilidad del negocio para ofrecer al arrendador unos datos que permitan "acreditarle" una minoración de ingresos, es decir, para acreditar la reducción de la facturación mensual en [COMPLETAR], al menos, un 75 por ciento, en relación con la facturación media mensual del mismo trimestre del año anterior. (Art. 4 RDL 15/2020, de 21 de abril).

Nótese que la obligatoriedad en la aceptación del aplazamiento en el pago de la deuda lo es solo respecto al supuesto del art. 1 RDL 15/2020, de 21 de abril, con lo que este delito tiene una mayor relevancia en estos casos donde, si el arrendatario lo insta, es obligatoria la moratoria, lo que no ocurre en el caso de los supuestos del art. 2 RDL 15/2020, de 21 de abril, en donde es voluntario para el arrendador aceptar, o no, la propuesta del arrendatario.

================================================================================
