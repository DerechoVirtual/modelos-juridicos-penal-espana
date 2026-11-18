---
name: denuncia-falsa-acusacion-843
description: "Redacta el escrito «Denuncia falsa: acusación» (formulario 843 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Denuncia falsa: acusación

> Formulario 0843 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (4 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO (2 veces)
- [ ] DELITO (2 veces)
- [ ] FECHA DEL AUTO
- [ ] PENA
- [ ] IMPORTE (4 veces)
- [ ] LUGAR
- [ ] DESCRIBIR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…se presentó denuncia por parte de»; «…, ya que el delito atribuido es»; «… se demuestra con las pruebas siguientes»; «…nción psicológica recibida del psicólogo»; «….-Testifical-Pericial del psicólogo»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto
- la sentencia absolutoria / el auto de archivo

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS] testigo que intervino en el juicio oral del que dimana ahora este procedimiento…
- - D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre el daño moral padecido por el/la querellante.…
- .-Testifical-Pericial del psicólogo [COMPLETAR] a efectos de acreditar el daño moral sufrido por el/la querell…
- .- Documental: teniendo por reproducido el testimonio de la sentencia dictada por la Sección de lo Penal de Tr…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 456 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- artículo 456 CP
- art. 22 CP
- art. 456.1 CP
- art. 13 CP
- art. 33.2 CP
- art. 777.2 LECr
- arts. 370 y 380 LEC

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

### Formulario 0843 · Denuncia falsa: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (4); 4 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 bloques de alternativas señalados; 4 párrafos opcionales señalados; 31 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos de delito de denuncia falsa del art. 456 CP, y se reclama el daño moral producido, así como los perjuicios económicos objetivables derivados de la falsa denuncia.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante este órgano judicial por la vía del art. 781 LECRIM y en plazo (1) escrito de acusación por la vía del art. 780 LECRIM en relación con el art. 650 LECRIM contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

Conclusiones

PRIMERA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Con fecha [FECHA] se dictó sentencia firme en el procedimiento abreviado nº [Nº DE PROCEDIMIENTO] ante la Sección de lo Penal de Tribunal de Instancia de [SEDE] nº [NÚMERO] por delito de [DELITO] a raíz de denuncia interpuesta por el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] contra el/la querellante D./Dña. [NOMBRE Y APELLIDOS]. En la sentencia dictada, ya firme por no haberse interpuesto recurso contra la misma, se hace constar por el juzgador la posible existencia de fundamento para entender que el contenido de la denuncia era falso, lo que motivó que, incluso, la sentencia absolutoria se dictara in voce y recogiendo el/la juez/a en la misma la insostenibilidad de los hechos de la denuncia y la posibilidad de que fueran falsos a tenor de las pruebas practicadas.

Con fecha [FECHA] se presentó denuncia por parte de [COMPLETAR] contra el/la querellante siendo archivada por la sección de instrucción por auto de archivo haciendo constar el juez a instancia de esta parte en el auto, tras diligencias practicadas, el carácter insostenible de la denuncia y la existencia de indicios o clara apariencia de falsedad de la misma, al no ser ciertos los hechos denunciados y el dolo inherente al conocimiento del carácter falsario de los hechos denunciados. Y cuyo auto de fecha [FECHA DEL AUTO] ha devenido firme.

SEGUNDA.- Tales hechos son constitutivos del delito de denuncia falsa del artículo 456 CP.

Concurren los requisitos de la acusación y denuncia falsa:

1.- La imputación de hechos falsos de forma clara en la denuncia inicial.
2.- Los hechos denunciados, si fueran ciertos, serían constitutivos de delito de [DELITO].
3.- La denuncia se formuló ante la autoridad judicial.

4. Existe dolo y mala fe de presentar la denuncia con dolo y conciencia de su falsedad.

TERCERA.- Es responsable del delito de denuncia falsa, en concepto de autor/a, el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la agravante de del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de denuncia falsa la pena de [PENA], ya que el delito atribuido es [COMPLETAR]. (2)

SEXTA.- Existe derecho a recibir una indemnización por falso testimonio o por el daño moral sufrido por el perjudicado, ahora acusación particular, y que se fija, sin perjuicio de posterior determinación final en el escrito de acusación, en la suma de [IMPORTE] euros, por el sufrimiento psicológico y el perjuicio económico objetivable en base al daño moral, y con fundamento en la doctrina fijada por la Sala Segunda del Tribunal Supremo en las SSTS 535/2025 de 11 junio, 776/2024 de 18 septiembre y, sobre todo, STS 437/2022 de 4 mayo, a la hora de fijar los criterios en base a la reclamación del daño moral basado en las tesis del daño moral irreversible, tesis del antes y el después y la tesis de la declaración de impacto de la víctima en base a un daño moral consistente en:

1.- Zozobra y ansiedad sufrida por el perjudicado ante una denuncia falsa.

2. La publicidad que se dio a la denuncia que se demuestra con las pruebas siguientes [COMPLETAR].

3. Atención psicológica recibida del psicólogo [COMPLETAR].

Además del daño moral existente, se acreditan los siguientes gastos como perjuicios económicos objetivables tenidos como consecuencia de la falsa denuncia:

a.- Gastos económicos por pérdidas económicas provocadas por la falsa denuncia y el desprestigio derivado de estar sometido a un proceso judicial que se cuantifican en [IMPORTE] euros.

b.- Gastos judiciales que ascienden a [IMPORTE] euros.

Por ello, en concepto de responsabilidad civil se reclama, en principio, la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el juicio oral, intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] testigo que intervino en el juicio oral del que dimana ahora este procedimiento, a efectos de acreditar la falsedad de la denuncia y que fue determinante para [ELEGIR: la sentencia absolutoria / el auto de archivo]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre el daño moral padecido por el/la querellante.

[OPCIONAL — incluir si procede]

.-Testifical-Pericial del psicólogo [COMPLETAR] a efectos de acreditar el daño moral sufrido por el/la querellante. (4)

[OPCIONAL — incluir si procede]

.- Documental: teniendo por reproducido el testimonio de la sentencia dictada por la Sección de lo Penal de Tribunal de Instancia de [SEDE] nº [NÚMERO] y de la denuncia falsa presentada en su día.

.- Se aportan los siguientes documentos que ya fueron aportados en sede de la Sección de Instrucción del Tribunal de Instancia de [SEDE], a efectos de acreditar la falsedad de la denuncia y que fueron determinantes para [ELEGIR: la sentencia absolutoria / el auto de archivo].

-Se incluye [ELEGIR: la sentencia absolutoria / el auto de archivo].

.- Documentos relativos a los daños y perjuicios objetivables sufridos consistentes en [DESCRIBIR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) La pena a imponer en este caso depende del tipo de delito que se haya atribuido en la denuncia que se reputa falsa ya que así lo prevé el art. 456.1 CP. En este caso, presumiendo que el delito imputado fuera grave, la pena sería de prisión de seis meses a dos años y multa de doce a veinticuatro meses [NOTA DE REVISIÓN: Art. 456.1.1.º CP: si se imputa un delito grave, prisión y multa son conjuntas. Fuente: Código Penal, BOE-A-1995-25444, art. 456.1.1.º.]. Los delitos graves en el art. 13 CP son los que están sancionados con pena grave, es decir, pena superior a 5 años de prisión (art. 33.2 CP).

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

(4) En estos casos es posible que la declaración de un profesional se articule en calidad de testigo- perito de los arts. 370 y 380 LEC en razón a que puede declarar de lo que conoce, por lo que ha visto en cuanto a la atención que ha dispensado a la víctima, pero también es su condición de perito por la noción de la afectación de ser víctimas del delito, en cuanto a la reclamación por daño moral. De esta manera, el psicólogo podría declarar como testigo en razón a las asistencias que ha hecho al perjudicado y el coste que eso le produce a este, así como en razón a una pericial para declarar, conforme a sus conocimientos, el grado de afectación que le ha provocado al perjudicado para la reclamación de daño moral.

================================================================================
