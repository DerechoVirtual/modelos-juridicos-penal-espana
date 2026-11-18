---
name: insolvencia-punible-escrito-acusacion-390
description: "Redacta el escrito «Insolvencia punible: escrito de acusación» (formulario 390 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Insolvencia punible: escrito de acusación

> Formulario 0390 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] NÚMERO
- [ ] IMPORTE (4 veces)
- [ ] Nº DE DOCUMENTO (4 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] DESCRIBIR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a»; «… en el art. 259.1 CP son los siguientes:»; «…, que acreditará que se ha cometido»; «….- Documental: - Facturas siguientes:»; «… con otros/as acreedores/as que se citan»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de insolvencia no causal / En caso de insolvencia causal — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- - D./Dña. [NOMBRE Y APELLIDOS]…
- 1.- Declaración del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], acreedor/a del/de la acusado/a.…
- - D./Dña. [NOMBRE Y APELLIDOS], que acreditará que se ha cometido [COMPLETAR].…
- - D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre [DESCRIBIR].…
- .- Informe pericial judicial de la situación del/de la deudor/a donde consta el examen de la situación económi…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 259 del CP
- artículo 781.1 de la LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- art. 650 LECRIM
- artículo 14 de la LECrim
- artículo 5 del RDLeg. 1/2020
- art. 259.1 CP
- art. 259 CP
- art. 22 del CP
- art. 259.5 CP
- art. 780 LECRIM
- art. 259.2 CP
- art. 777.2 LECrim

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

### Formulario 0390 · Insolvencia punible: escrito de acusación

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 4 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 29 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en el procedimiento abreviado calificando los hechos de delito de insolvencia punible del art. 259 del CP, ya que el acusado ha realizado una serie de actuaciones que imposibilitan el cobro de deudas a la acusación y a otros acreedores, sin haber solicitado concurso voluntario.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL (1) ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, en relación con el art. 650 LECRIM, con arreglo a lo dispuesto en el artículo 14 de la LECrim y con base en las siguientes

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] es acreedor/a del/de la acusado/a en base a una serie de operaciones mercantiles por las que se le debía el importe de [IMPORTE] euros.

Las operaciones fueron las siguientes:

Se acreditan las mismas con los documentos nº [Nº DE DOCUMENTO] a [COMPLETAR].

Tras varios requerimientos de pago que se acreditan con los documentos nº [Nº DE DOCUMENTO], el/la acusado/a vino haciendo caso omiso a los mismos alegando que estaba en una situación de insolvencia, o próxima a ella, al comunicarnos con el documento nº [Nº DE DOCUMENTO], que no disponía de patrimonio alguno con el que afrontar las deudas existentes.

Además, el/la acusado/a es deudor/a de los siguientes acreedores:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

Por otro lado, el/la acusado/a no ha instado concurso voluntario, aun siendo consciente de su situación patrimonial y de las deudas con acreedores, conforme al artículo 5 del RDLeg. 1/2020, de 5 de mayo, por el que se aprueba la Ley Concursal, y

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de insolvencia no causal / En caso de insolvencia causal — el texto de cada opción no venía en el formulario original]

Los elementos indiciarios sobre los comportamientos en que consiste el catálogo de acciones perpetradas de las que constan en el art. 259.1 CP son los siguientes: [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos del delito de insolvencia punible del art. 259 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS], por el delito del art. 259 CP la pena de [PENA] de prisión.

SEXTA.- El importe de la responsabilidad civil derivada de dicho delito deberá incorporarse, en su caso, a la masa en la suma de [IMPORTE] euros (art. 259.5 CP).

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por realizado el trámite de traslado para acusación y solicitada la apertura de juicio oral.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], acreedor/a del/de la acusado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que acreditará que se ha cometido [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre [DESCRIBIR].

[OPCIONAL — incluir si procede]

.- Informe pericial judicial de la situación del/de la deudor/a donde consta el examen de la situación económica del/de la deudor/a y las operaciones llevadas a cabo en base al análisis de la documental.

[OPCIONAL — incluir si procede]

.- Documental:

- Facturas siguientes: [COMPLETAR].
- Fijación por documental del importe total de la deuda con el/la perjudicado/a que asciende a la suma de [IMPORTE] euros y de [IMPORTE] euros con otros/as acreedores/as que se citan [COMPLETAR].
- Actas notariales de requerimientos:
- Documentos nº [Nº DE DOCUMENTO] de actuaciones que han agravado la situación de insolvencia del/de la deudor/a.
- Documental remitida por el Registro Mercantil respecto a carencia de cuentas anuales y documentación a que está obligado/a por legislación mercantil.
- Copia de los libros de contabilidad, y formalización, en su caso, del concurso.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) El delito del art. 259 CP debe identificarse con un pronóstico razonable que, en sede penal, ya incluso para la admisión a trámite de la querella o para dar curso a la denuncia, debe estar amparado por un elenco de indicios de suficiente solidez.

La acreditación indiciaria inicial puede llevarse a cabo mediante la aportación a este órgano judicial de datos que pongan de manifiesto claramente la crisis o déficit patrimonial del deudor a quien se imputa la comisión del delito (por ejemplo: relación de acreedores en caso de multiplicidad, inventarios del deudor que reflejen la situación deficitaria, y especialmente, relación de impagos).

Los requisitos de la persona contra quien se dirige la acción penal son dos:

a.- Situación de insolvencia actual o inminente.

La Insolvencia penal es sólo la definitiva «de naturaleza estructural». No coincide completamente con la insolvencia concursal, es más exigente en el carácter del incumplimiento de los pagos. (STS 652/2018, de 14 de diciembre, Rec. 45/2018)

b.- Realizar alguna de las conductas que se citan en el art. 259.1 CP.

• Que supongan una disminución del patrimonio (1ª a 4ª) o la asunción de un riesgo de perdidas injustificadas (5ª).

• Que infrinjan deberes legales contables («insolvencia documental») (6ª a 8ª)

• Cláusula de cierre (9ª) que introduce dos requisitos cumulativos (infracción grave y disminución patrimonial/ocultación) que parte de la jurisprudencia y de la doctrina consideran extensivos al resto de conductas del art. 259.1 CP.

El apartado 1º del art. 259 CP es definido como la insolvencia no causal y el apartado 2º como la insolvencia causal.

Así, cabe, en segundo lugar (art. 259.2 CP), que mediante alguna de las conductas a que se refiere el apartado anterior, cause su situación de insolvencia, con lo que si en el apartado 1º se exige que se encuentre el querellado en situación de insolvencia y lleve a cabo alguna de estas conductas, en el apartado 2º se admite que "con una de esas conductas" provoque su insolvencia.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
