---
name: diputado-senador-querella-ante-tribunal-supremo-97
description: "Redacta el escrito «Diputado o senador: querella ante el Tribunal Supremo» (formulario 97 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Diputado o senador: querella ante el Tribunal Supremo

> Formulario 0097 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 277 LECrim exige que la querella se presente por procurador con «poder bastante» y la firme un letrado. El poder especial no es imprescindible: si falta, basta con la firma del querellante o de otra persona a su ruego (art. 277.7.º).
- En las causas contra diputados ante la Sala Segunda, la instrucción corresponde a un magistrado instructor designado por turno entre los miembros de la Sala (art. 57.2 LOPJ). La mención de la nota a ratificarse «ante el Juez de Instrucción» debe adaptarse a ese instructor.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (21 veces)
- [ ] LOCALIDAD (6 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] FECHA (9 veces)
- [ ] IMPORTE (3 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…d, diputado/a, que puede ser citado/a en»; «…d, diputado/a, que puede ser citado/a en»; «…tido por las personas de los querellados»; «… volviendo a venderla un mes más tarde a»; «…3 certificado de la sucursal bancaria de»; «…del Colegio de Notarios de»; «…(B) por un precio de»; «…nmobiliaria, el cual puede ser citado en»; «…a vivienda), el cual puede ser citado en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 71.3 CE
- art. 251.2 del Código Penal
- art. 277.5 y 755 de la LECrim

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

### Formulario 0097 · Diputado o senador: querella ante el Tribunal Supremo

- Año del modelo: 2023
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 llamadas a nota sin texto retiradas; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 42 campos de relleno marcados en blanco; 9 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)
- Nota explicativa incorporada desde la colección Procesal (formulario 99) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Querella por unos hechos que presentan los caracteres de un delito de estafa del art. 251.2 CP, cometidos por personas que ostentan la condición de diputados del Congreso, dirigido directamente ante la Sala 2ª del Tribunal Supremo. Recuerde que....

---

A la Sala Segunda del Tribunal Supremo

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [LOCALIDAD] colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, al amparo de lo dispuesto en el art. 277 y concordantes de la LECrim, mediante el presente escrito formulo QUERELLA CRIMINAL por un delito de estafa contra D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], diputados/as del Congreso, y

EXPONGO

PRIMERO.- Es competente la Excma. Sala a la que me dirijo por ostentar el/la querellado/a la condición de diputado/a, conforme a lo dispuesto en el art. 71.3 CE y 57.1.2.º LOPJ [NOTA DE REVISIÓN (comprobar): La competencia de la Sala Segunda para causas contra diputados y senadores está en el art. 57.1.2.º LOPJ; el art. 57.2 regula la designación del instructor. Fuente: LO 6/1985 del Poder Judicial, BOE-A-1985-12666, art. 57.], tal como acredito mediante testimonio del BOP de fecha [FECHA] donde aparece la proclamación de su elección y que acompaño como documento número uno de la querella.

SEGUNDO.- Es querellante mi representado/a D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, vecino/a de [LOCALIDAD], C/, comprador/a de la vivienda sita en [LOCALIDAD] y en tal concepto perjudicado/a por la conducta de D./Dña. [NOMBRE Y APELLIDOS]

TERCERO.- Se dirige la querella contra:

– D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, diputado/a, que puede ser citado/a en [COMPLETAR]
– D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, diputado/a, que puede ser citado/a en [COMPLETAR].

CUARTO.- La querella se interpone por un delito de estafa del art. 251.2 del Código Penal cometido por las personas de los querellados [COMPLETAR].

La relación circunstanciada de hechos pone de manifiesto que los querellados vendieron la vivienda sita en [LOCALIDAD] a mi representado/a en documento privado de fecha [FECHA], quien satisfizo su íntegro precio, volviendo a venderla un mes más tarde a [COMPLETAR] en escritura pública de fecha [FECHA].

A) ADQUISICIÓN DE LA VIVIENDA SITA EN [LOCALIDAD] POR EL/LA QUERELLANTE

En fecha [FECHA] el/la querellante compró la vivienda sita en [LOCALIDAD] a los querellados por un importe de [IMPORTE], quienes la vendieron a mi representado/a sin reserva ni objeción alguna (acompaño como documento número 1 contrato privado de compraventa de fecha [FECHA] suscrito por querellante y querellados).

Tal como consta en dicho contrato, mi mandante satisfizo la cantidad de [IMPORTE] mediante cheque bancario que entregó en ese mismo acto, y que fue cargado a la cuenta de mi mandante el día posterior a la venta (acompaño como documento número 2 extracto de la cuenta donde consta el asiento y como documento número 3 certificado de la sucursal bancaria de [COMPLETAR] en el que se acredita que el asiento corresponde al pago del cheque número [NÚMERO]).

Los querellados no hicieron reserva alguna, percibiendo la totalidad del precio pactado, a lo que habían condicionado la venta, comprometiéndose a entregar la vivienda y otorgar escritura pública en el plazo de un mes, tal como consta en la estipulación quinta del contrato (documento número 1).

Dicha compraventa se concertó con la mediación del Agente de la Propiedad Sr. [NOMBRE Y APELLIDOS] (A), quien estuvo presente en las negociaciones y en la firma del contrato privado de compraventa.

B) SEGUNDA VENTA POR LOS QUERELLADOS DE LA MISMA VIVIENDA AL SR. (B)

En cumplimiento de lo pactado, el/la querellante se dirigió, en diferentes ocasiones, a los querellados para el otorgamiento de la escritura de venta, y como quiera que el/la querellante sólo recibía excusas por parte de los/las querellados/as sobre el otorgamiento de la escritura de venta, les requirió notarialmente para su otorgamiento (acompaño como documento número 4 acta de requerimiento notarial extendida por el Iltre. Sr. Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Colegio de Notarios de [COMPLETAR]).

Extrañado/a por la falta de respuesta de los querellados, acudió al Registro de la Propiedad solicitando nota simple de la hoja registral correspondiente a la finca de donde resulta que los querellados, el día [FECHA], es decir, un mes después de la compraventa con el/la querellante, habían otorgado escritura pública de venta de la misma vivienda a favor del Sr. [NOMBRE Y APELLIDOS] (B) por un precio de [COMPLETAR] (acompaño como documento número 5 copia simple de la inscripción registral de la finca).

Ante la sucesión de los hechos, el querellante encomendó el asunto a esta dirección letrada, quien requirió nuevamente a los querellados, recibiendo contestación escrita de los mismos de fecha [FECHA] por vía fax, donde manifiestan que han tenido problemas económicos y que su disposición a solucionar el asunto (acompaño como documento número 6 copia del fax remitido por los querellados).

QUINTO.- Los hechos relatados son constitutivos, en principio y sin perjuicio de lo que resulte de la instrucción, de un delito de estafa previsto y penado en el art. 251.2 del Código Penal, del que aparecen como responsables los/las querellados/as, quienes han dispuesto de la vivienda vendida a mi representado/a, y cuyo precio percibieron en su integridad, antes de su definitiva transmisión, con evidente perjuicio para el/la querellante, quien a día de hoy no ha podido recuperar nada de la cantidad entregada.

SEXTO.- Al derecho de esta parte interesa, de conformidad con lo dispuesto en el art. 277.5 y 755 de la LECrim, la práctica de las siguientes diligencias de investigación:

1.- Dada la condición de diputado/as de los/las querellados/as D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] interesamos que recabe la correspondiente certificación del Congreso y se solicite autorización para investigarle por estos hechos delictivos, a cuyo efecto deberá librarse el correspondiente suplicatorio.
2.- Testifical, a fin de que sobre los hechos recogidos en el escrito de querella testifiquen las siguientes personas:
– D. [NOMBRE Y APELLIDOS] (querellante), el cual puede ser citado a través de esta representación procesal.
– Sr. [NOMBRE Y APELLIDOS] (A), Agente de la Propiedad Inmobiliaria, el cual puede ser citado en [COMPLETAR]
– Sr. [NOMBRE Y APELLIDOS] (B) (comprador de la vivienda), el cual puede ser citado en [COMPLETAR]
4.- Documental, para que libre mandamiento al Iltre Sr. Notario D. [NOMBRE Y APELLIDOS] para que aporte copia auténtica de la escritura de compraventa de fecha [FECHA] otorgada por los querellantes a favor del Sr. [NOMBRE Y APELLIDOS] (B).
5.- Documental, dando por reproducidos los documentos acompañados a la querella.
6.- Las diligencias que la Sala considere oportunas y de interés para la causa, así como las derivadas de las anteriores.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentada esta querella, con sus copias respectivas, se sirva en admitirla a trámite, y, en su virtud, se sirva solicitar autorización para investigar a los querellados, librando el correspondiente suplicatorio, y, para en su momento, acuerde practicar las diligencias solicitadas.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa que se adopten las siguientes medidas cautelares:

Esta parte no interesa por el momento, y sin perjuicio de lo que resulte de la investigación y de la autorización para imputar postulada, la medida cautelar de prisión provisional de los/las querellados/as.

Para garantizar las responsabilidades civiles derivadas del delito esta parte interesa que se requiera al querellado/a D./Dña. [NOMBRE Y APELLIDOS]. para que constituyan fianza por importe de [IMPORTE], apercibiéndoles de que, de no constituirse en el plazo de veinticuatro horas, se procederá al embargo de sus bienes.

Igual medida cautelar interesamos del/de la querellado/a D./Dña. [NOMBRE Y APELLIDOS] tan pronto se obtenga la autorización para que pueda ser imputado.

SUPLICO A LA SALA: Que se adopten las medidas solicitadas.

SEGUNDO OTROSÍ DIGO: que el/la querellante, en su calidad de perjudicado por el hecho delictivo, está exento de prestar fianza.

SUPLICO A LA SALA; Declare exenta a esta parte de la obligación de constituir fianza.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante el Juez de Instrucción. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023). El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella

[NOTA DE REVISIÓN: El art. 277 LECrim exige que la querella se presente por procurador con «poder bastante» y la firme un letrado. El poder especial no es imprescindible: si falta, basta con la firma del querellante o de otra persona a su ruego (art. 277.7.º).]

[NOTA DE REVISIÓN: En las causas contra diputados ante la Sala Segunda, la instrucción corresponde a un magistrado instructor designado por turno entre los miembros de la Sala (art. 57.2 LOPJ). La mención de la nota a ratificarse «ante el Juez de Instrucción» debe adaptarse a ese instructor.]
