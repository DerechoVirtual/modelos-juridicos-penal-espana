---
name: humillacion-victimas-terrorismo-internet-ciberterrorismo-528
description: "Redacta el escrito «Humillación a víctimas del terrorismo por internet (ciberterrorismo): querella» (formulario 528 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Humillación a víctimas del terrorismo por internet (ciberterrorismo): querella

> Formulario 0528 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] PROFESIÓN (3 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ntes: El/La querellado/a ha publicado en»; «…diversos mensajes en fechas»; «…del terrorismo y que fue asesinado/a por»; «… del terrorismo, que fue asesinado/a por»; «…sobre la que expuso que»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (9)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D/Dña, que ha visto por internet los mensajes publicados.…
- .- Que se oficie a la brigada de delitos tecnológicos y se acceda a dictar auto de entrada y registro del orde…
- .- Pericial informática del ordenador del/de la querellado/a y los contenidos habidos en el mismo.…
- .- Documental, (prueba digital) teniendo por reproducidos los documentos aportados. Acta notarial del/de la Il…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Se oficie a los prestadores de servicio para la retirada de los mensajes publicados y cierre de los perfile…
- . Se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la libertad…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 578 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 578.1, 2 y 4 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- artículos 572 a 577 CP

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

### Formulario 0528 · Humillación a víctimas del terrorismo por internet (ciberterrorismo): querella

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 8 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito mediante el que se ponen en conocimiento del juez unos hechos que presentan los caracteres de un delito de humillación a las víctimas del terrorismo por internet del art. 578 CP, al haber vertido en redes sociales comentarios de menosprecio a víctimas del terrorismo.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que siguiendo las instrucciones de mis mandantes, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de humillación a las víctimas del terrorismo del art. 578.1, 2 y 4 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, y del Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005. (2)

SEGUNDO.- Los/as querellantes son, como queda dicho, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD] y D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (3)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a ha publicado en [COMPLETAR] diversos mensajes en fechas [COMPLETAR] en los que señala que: D./Dña. [NOMBRE Y APELLIDOS] víctima del terrorismo y que fue asesinado/a por [COMPLETAR] merecía morir y que debió hacerlo mucho antes. Lo mismo hizo constar con D./Dña. [NOMBRE Y APELLIDOS], víctima del terrorismo, que fue asesinado/a por [COMPLETAR] sobre la que expuso que [COMPLETAR]. En ambos casos con clara y demostrada intención de humillarlos/as.

Ambas víctimas son hijos/as de los/as querellantes.

QUINTO.- Los hechos expuestos revisten los caracteres de un delito de humillación a víctima del terrorismo del art. 578 CP y del que presuntamente es culpable el/la querellado/a. (4)

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D/Dña, que ha visto por internet los mensajes publicados.

[OPCIONAL — incluir si procede]

.- Que se oficie a la brigada de delitos tecnológicos y se acceda a dictar auto de entrada y registro del ordenador del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Pericial informática del ordenador del/de la querellado/a y los contenidos habidos en el mismo.

Por ello, que se ordene a la brigada de delitos tecnológicos de la policía para que lleven a cabo examen del ordenador del/de la querellado/a para constatación informática de los hechos de la querella. (5)

[OPCIONAL — incluir si procede]

.- Documental, (prueba digital) teniendo por reproducidos los documentos aportados. Acta notarial del/de la Ilmo/a. Sr./Sra. Notario/a D./Dña. [NOMBRE Y APELLIDOS] donde consta la constatación de ajustarse el documento anterior a la realidad al ser adverado notarialmente cada documento aportado en base al cotejo en el propio ordenador respecto a lo publicado en la red social.

SÉPTIMO.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE] euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Se oficie a los prestadores de servicio para la retirada de los mensajes publicados y cierre de los perfiles sociales del/de la querellado/a, de acuerdo con el art. 3 del Reglamento (UE) 2021/784 de 29 de abril de 2021, sobre la lucha contra la difusión de contenidos terroristas en línea.

[OPCIONAL — incluir si procede]

. Se proceda a la detención y prisión provisional del/de la querellado/a, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita y se practiquen las diligencias interesadas.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) El juez competente es aquel donde puedan encontrarse pruebas materiales del delito y donde se han iniciado las primeras investigaciones al respecto, que generalmente suele coincidir con el lugar del domicilio de la víctima por ser donde se han descubierto dichas pruebas.

(3) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(4) En el art. 578 CP se prevén dos tipos de conductas:

1.- Enaltecimiento o la justificación públicos de los delitos comprendidos en los artículos 572 a 577 CP [NOTA DE REVISIÓN: El art. 578.1 CP remite a los delitos de los arts. 572 a 577. Fuente: Código Penal, BOE-A-1995-25444, art. 578.1.] o de quienes hayan participado en su ejecución.
2.- La realización de actos que entrañen descrédito, menosprecio o humillación de las víctimas de los delitos terroristas o de sus familiares.

Y al objeto del ciberdelito, una agravación en el apartado segundo si se lleva a cabo por Internet. Sobre esta modalidad de delito cometido por redes sociales existe una importante doctrina de la Sala Segunda del Tribunal Supremo que trata de delimitar claramente el delito.

STS 378/2017, de 25 de Mayo, rec. 8/2017: el tipo exige formalmente una actuación del sujeto que suponga justificar delitos de terrorismo o enaltecer a los que hayan participado en ellos.

STS 706/2017, de 21 de Octubre, rec. 514/2017: la mera reproducción de imágenes y el "retuiteo" con difusión pública, aunque hubieran sido tomadas por un tercero, constituyen delito del art. 578 CP. El tipo penal no exige que el acusado asuma como propio, razone o argumente la imagen y su mensaje, o que los haya creado, sino que basta que disponga de ellos y les de publicidad. La expansión del mensaje posibilita que terceras personas se percaten de que están enalteciendo la trayectoria personal y los "méritos" de alguien cuya fama procede de los actos terroristas ejecutados.

STS 812/2011, de 21 de Julio, rec. 46/2011: distinción con la apología del terrorismo.

STS 334/2018, de 4 de Julio, rec. 2193/2017: el conjunto de los mensajes analizados no traspasan los límites para ser calificados como delito de humillación a las víctimas del terrorismo. Límites fronterizos entre la vía penal y la civil. Necesidad de que se adopten medidas organizativas en los prestadores de servicio para cortar la difusión inmediata de tales expresiones.

STS 95/2018, de 26 Febrero, Rec. 979/2017.

STS 4/2017, de 18 Enero, rec. 1619/2016: "Tuits" publicados en la cuenta de famoso cantante-letrista de rap metal.

(5) Es importante la pericial informática en estos casos, dado que puede el querellado impugnar la prueba digital. En casos de impugnación de prueba digital es carga de la prueba del denunciante/querellante comprobar la veracidad de su contenido por pericial informática, por lo que o bien se acompaña a la querella la misma, o se propone la pericial judicial, o bien una vez se haya impugnado por el denunciado/querellado es cuando puede proponerse la práctica de la pericial informática, ya que sin esta carece de valor probatorio su aportación, si es impugnada por el investigado.

================================================================================
