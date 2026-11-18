---
name: prevaricacion-judicial-acusacion-839
description: "Redacta el escrito «Prevaricación judicial: acusación» (formulario 839 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prevaricación judicial: acusación

> Formulario 0839 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (4 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] COLEGIO
- [ ] SEDE
- [ ] NÚMERO (2 veces)
- [ ] FECHA (2 veces)
- [ ] Nº
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… en el procedimiento de juicio ordinario»; «…tuado hasta el momento de la vista oral.»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: a cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas: (Tener …
- .- Pericial del/de la perito que ha elaborado informe de daños causados.…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 446 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 728 LEC
- art. 446 del Código Penal
- art. 22 CP
- artículo 656 LECr
- art. 73 LOPJ
- art. 447 CP
- art. 448 CP
- art. 449 CP
- art. 777.2 LECr

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

### Formulario 0839 · Prevaricación judicial: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (4); 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la acusación particular en un procedimiento abreviado por el que se pide la apertura del juicio oral y se presentan conclusiones provisionales por delito de prevaricación del art. 446 CP contra un juez que en un procedimiento civil solicitó en embargo de unos bienes sin cumplir los requisitos legales.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sala de lo Civil y Penal del TSJ de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sala de lo civil y penal del TSJ de [LOCALIDAD] (1) por la vía del art. 781 LECRIM y en plazo (2) escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS] es juez/a de la Sección Civil del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO]. Con fecha [FECHA] se ha dictado en el procedimiento de juicio ordinario [COMPLETAR], que se tramita en este órgano judicial, auto ordenando la adopción de la medida cautelar de embargo de bienes del/de la demandado/a, ahora perjudicado/a D./Dña. [NOMBRE Y APELLIDOS] sin que se cumplan los requisitos del art. 728 LEC, al no haberse aportado con la solicitud de la misma ninguno de los requisitos que se citan en el citado precepto ni haberse adoptado por el/la acusado/a caución alguna en previsión de que el resultado final del pleito fuese desestimatorio y se causen al/a la ahora perjudicado/a daños y perjuicios. En concreto se ha embargado el bien inmueble sito en [LOCALIDAD], con referencia registral nº [NÚMERO] que estaba en disposición de ser vendido en la actualidad, siendo imposible la venta en tal estado de traba por este órgano judicial. La resolución se dicta a sabiendas de su injusticia, por cuanto no se aportaron por el/la demandante ninguno de los presupuestos del art. 728 LEC ni aportado ni exigido caución suficiente.

SEGUNDA.- Tales hechos son constitutivos del delito de prevaricación del art. 446 del Código Penal. (3)

TERCERA.- Es responsable del delito de prevaricación judicial del art. 446 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la agravante de del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de prevaricación judicial la pena de e inhabilitación especial para empleo o cargo público [NOTA DE REVISIÓN: El art. 446 CP no prevé inhabilitación para el sufragio pasivo; para cualquier otra resolución injusta (446.3.º) la pena es multa de doce a veinticuatro meses e inhabilitación especial de diez a veinte años. Fuente: Código Penal, BOE-A-1995-25444, art. 446.3.º.] por [Nº] años.

SEXTA.- Se han provocado daños y perjuicios derivados de la no adquisición del bien inmueble por el/la posible comprador/a D./Dña. [NOMBRE Y APELLIDOS] tasados en [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: a cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas: (Tener en cuenta lo dispuesto en el artículo 656 LECr, que dispone que hay que identificar bien a los testigos)

-D./Dña. [NOMBRE Y APELLIDOS], demandante del procedimiento civil y posible comprador/a del bien inmueble ahora embargado.

[OPCIONAL — incluir si procede]

.- Pericial del/de la perito que ha elaborado informe de daños causados.

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La competencia para la instrucción es de la Sala de lo Civil y penal del TSJ correspondiente a tenor del art. 73 LOPJ.

(2) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez instructor por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación

(3) Este es un delito esencialmente doloso que impide la comisión por imprudencia al exigirse en el art. 446 CP que se cometa a sabiendas de la injusticia de la resolución o sentencia, lo que podrá deducirse del desarrollo de los hechos, al colegirse rápidamente la injusticia manifiesta de la resolución o sentencia.

Cabe la comisión por imprudencia grave o ignorancia inexcusable en el art. 447 CP.

En el art. 448 CP se sanciona a quien se negase a juzgar, sin alegar causa legal, o so pretexto de oscuridad, insuficiencia o silencio de la Ley

Y en el art. 449 CP al Juez, Magistrado o Letrado/a de la Administración de Justicia culpable de retardo malicioso en la Administración de Justicia.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas, en su caso (art. 777.2 LECr.).

================================================================================
