---
name: falsedad-documento-mercantil-concurso-medial-estafa-850
description: "Redacta el escrito «Falsedad en documento mercantil en concurso medial con estafa: acusación» (formulario 850 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falsedad en documento mercantil en concurso medial con estafa: acusación

> Formulario 0850 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] LOCALIDAD (3 veces)
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dente de la Comunidad de Propietarios de»; «…trador/a de la comunidad de propietarios»; «…en la junta de propietarios celebrada el»; «…d de propietarios en la entidad bancaria»; «…dos cualesquiera de los tres autorizados»; «…ne" o electrónica de la entidad bancaria»; «…entes folios de las actuaciones: folios,»; «…a»; «…a [COMPLETAR] y»

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical, interrogatorio de los/as testigos que se mencionan a continuación y que deberán ser citados/as …
- .- Pericial caligráfica siguiente:…
- .- Documental, de los siguientes folios de las actuaciones: folios, [COMPLETAR] a [COMPLETAR] y [COMPLETAR], c…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 392.1 CP
- art. 248 CP
- artículos 780.1 y 781.1 LECrim
- artículo 650 de la Ley de Enjuiciamiento Criminal
- artículo 392.1 del Código Penal
- artículo 248 del Código Penal
- art. 390 del Código Penal
- artículo 77 del Código Penal
- artículo 74.1 del Código Penal
- artículos 392 CP
- art. 390 CP
- art. 123 del Código Penal
- art. 780 LECrim

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

### Formulario 0850 · Falsedad en documento mercantil en concurso medial con estafa: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (2); 4 párrafos opcionales señalados; 26 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la acusación en procedimiento abreviado solicitando la apertura del juicio oral y presentando sus conclusiones provisionales por delito de falsedad en documento mercantil del art. 392.1 CP y estafa del art. 248 CP [NOTA DE REVISIÓN: Tras la LO 1/2026 el art. 248 CP no tiene apartados numerados: la definición de estafa está en su párrafo primero. Fuente: Código Penal, BOE-A-1995-25444, art. 248 (redacción de la LO 1/2026, BOE-A-2026-7966).].

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del acusador particular, D./Dña. [NOMBRE Y APELLIDOS], como Presidente de la Comunidad de Propietarios de [COMPLETAR], según tengo ya acreditado en los autos número [Nº DE PROCEDIMIENTO], ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación de los artículos 780.1 y 781.1 LECrim., en relación con el artículo 650 de la Ley de Enjuiciamiento Criminal, solicito en plazo (1) la apertura del juicio oral ante la Sección de lo Penal del Tribunal de Instancia y formulo escrito de acusación, con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusadpo/a D./Dña. [NOMBRE Y APELLIDOS], fue nombrado/a administrador/a de la comunidad de propietarios [COMPLETAR] en la junta de propietarios celebrada el [COMPLETAR], a cambio de una retribución mensual de 500 euros.

Según consta en el acta de dicha Junta, se acordó en ese momento, igualmente, incluirle/a, como autorizado/a, en la cuenta bancaria de la comunidad, junto con el/la presidente/a D./Dña. [NOMBRE Y APELLIDOS], y el/la secretario/a D./Dña. [NOMBRE Y APELLIDOS], ambos/as vecinos/as de la comunidad y también designados/as como autorizados/as.

Para disponer del saldo de la cuenta bancaria, como consta, además de en el acta mencionada de la junta de propietarios, en el contrato de apertura de cuenta corriente a nombre de la comunidad de propietarios en la entidad bancaria [COMPLETAR], era necesaria la firma, al menos, de dos cualesquiera de los tres autorizados [COMPLETAR].

El talonario de cheques, como es habitual, quedó en poder del/de la administrador/a de la comunidad y ahora acusado/a, lo que facilitó sus propósitos delictivos.

Como consta en el extracto de movimientos de la cuenta bancaria, la forma usual de disponer del saldo de la cuenta para atender los gastos de la comunidad era a través de transferencias ordenadas por medio de los servicios de banca "on line" o electrónica de la entidad bancaria [COMPLETAR], y, solo puntualmente, mediante la emisión de cheques, firmados, por lo general, por el/la presidente/a de la Comunidad D./Dña. [NOMBRE Y APELLIDOS] y por el/la acusado/a.

Esta forma de proceder no generó incidencias inicialmente. Sin embargo, llegó un momento en el que el/la presidente/a y el/la secretario/a de la comunidad de propietarios detectaron una operativa anormal en la cuenta bancaria abierta a nombre de la comunidad, pues, a pesar de que ninguno de ellos había autorizado operaciones en cualquiera de las formas admitidas por los usos bancarios, en la cuenta de la comunidad figuraban varios adeudos.

En concreto, se aprecian cuatro cargos en cuenta que se corresponden con el pago por ventanilla de sendos cheques:

Fecha	Importe
4-3-2016	1.225 euros
7-3-2016	2.222 euros
4-4-2016	575 euros
15-4-2016	865 euros

Estos reintegros totalizan un importe de 4.887 euros.

Solicitada información a la sucursal bancaria, fueron mostrados al/a la presidente/a y al/a la secretario/a de la comunidad los cuatro cheques mencionados, en los que se aprecia la firma del/de la administrador/a, junto con otras firmas que simulan, en cada cheque, la firma del presidente/a, quien en ningún momento suscribió dichos documentos mercantiles.

Asimismo, desde la sucursal bancaria se confirmó que la persona que realizó los reintegros por ventanilla de los cuatro cheques fue el/la administrador/ade la comunidad, el/la acusado/a.

Aunque es cierto que no se puede saber si fue el/la acusado/a quien falsificó por sí o por medio de otra persona la firma del/de la presidente/a de la comunidad de propietarios, no hay duda, como se puede acreditar por los empleados de la agencia bancaria, de que fue él/ella quien los presentó y cobró.

SEGUNDA.- Tales hechos son constitutivos del delito de falsedad en documento mercantil del artículo 392.1 del Código Penal, en concurso medial con un delito de estafa del artículo 248 del Código Penal.

En cuanto a la falsedad documental, conforme establece la STS, Sala 2ª, 287/2016, de 7 de abril, rec. 1179/2015, concurren en este caso todos los elementos que la doctrina jurisprudencial exige para definir y caracterizar la falsedad documental: "la mutación de la verdad por alguno de los procedimientos enumerados en el art. 390 del Código Penal que recaiga sobre elementos esenciales del documento, con suficiente entidad, para afectar los normales efectos de las relaciones jurídicas y, finalmente, el dolo consistente en la conciencia y voluntad de transmutar la realidad".

TERCERA.- Es responsable del delito de falsedad en documento mercantil, en concurso medial con un delito de estafa, el/la acusado/a, administrador/a de la comunidad de propietarios, en concepto de autor/a, quien, por sí o por un tercero, falsificó la firma del/de la presidente/a de la comunidad en cuatro cheques, permitiéndole esta firma, junto con la propia, realizar los cuatro reintegros ilegítimos que anteriormente se han indicado.

CUARTA.- No concurren circunstancias modificativas de la responsabilidad penal.

QUINTA.- En función del criterio del artículo 77 del Código Penal, apartado 3, y del carácter continuado de las infracciones, según el artículo 74.1 del Código Penal, en relación con los artículos 392 CP, apartado 1, y art. 390 CP, apartado 1, procede imponer al/a la acusado/a, como autor/a de un delito de falsedad en documento mercantil, en concurso medial con un delito de estafa, una pena de [PENA] de prisión y multa de [Nº] meses, con una cuota diaria de [IMPORTE] euros.

SEXTA.- De conformidad con lo dispuesto en los arts. 110 y siguientes del Código Penal, el/la acusado/a deberá indemnizar a la comunidad de propietarios por importe de 4.887 euros en concepto de responsabilidad civil, más los intereses legales correspondientes.

Las costas deberán ser satisfechas por el/la acusado/a de conformidad con lo dispuesto en el art. 123 del Código Penal.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por realizado el trámite de traslado para acusación y solicitada la apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes

MEDIOS DE PRUEBA (2)

Los propuestos por el Ministerio Fiscal en su escrito de calificación y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, interrogatorio de los/as testigos que se mencionan a continuación y que deberán ser citados/as judicialmente:

- D./Dña. [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD], director/a de la sucursal bancaria.
- D./Dña. [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD], empleado/a de caja de la sucursal bancaria.

[OPCIONAL — incluir si procede]

.- Pericial caligráfica siguiente:

- D./Dña. [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD], Perito calígrafo.

[OPCIONAL — incluir si procede]

.- Documental, de los siguientes folios de las actuaciones: folios, [COMPLETAR] a [COMPLETAR] y [COMPLETAR], comprensivos de los siguientes extremos: libro de actas de la Comunidad de Propietarios, contrato de cuenta corriente, cheques presentados por el/la acusado/a para su cobro en la sucursal bancaria.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que el Juez le emplaza para ello, por la vía del art. 780 LECrim.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

================================================================================
