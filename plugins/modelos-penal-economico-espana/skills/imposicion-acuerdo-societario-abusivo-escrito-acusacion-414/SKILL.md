---
name: imposicion-acuerdo-societario-abusivo-escrito-acusacion-414
description: "Redacta el escrito «Imposición de acuerdo societario abusivo: escrito de acusación» (formulario 414 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Imposición de acuerdo societario abusivo: escrito de acusación

> Formulario 0414 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] NÚMERO (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de la sociedad»; «…disponía de un volumen de porcentaje del»; «…pero necesitaba la votación a favor de»; «…ros, en base a los siguientes parámetros»; «… SEXTA.- Deberá indemnizar a la sociedad»; «…, representante de la empresa»; «…donde se adoptó el acuerdo abusivo. —»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- — D./Dña. [NOMBRE Y APELLIDOS], socio/a presente el día de la junta.…
- — D./Dña. [NOMBRE Y APELLIDOS], miembro del Consejo de administración.…
- — D./Dña. [NOMBRE Y APELLIDOS], representante de la empresa [COMPLETAR] que, a raíz del acuerdo realizó activi…
- .- Pericial de parte del/de la perito D./Dña. [NOMBRE Y APELLIDOS] para la valoración del perjuicio económico …
- .- Documental, teniendo por reproducido los documentos aportados:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 291 del CP
- artículo 781.1 de la LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- art. 650 LECRIM
- artículo 14 de la LECrim
- art. 291 CP
- art. 22 del CP
- art. 780 LECRIM
- arts. 204 del Real Decreto Legislativo 1/2010
- artículo 291 CP
- art. 297 CP
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

### Formulario 0414 · Imposición de acuerdo societario abusivo: escrito de acusación

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en el procedimiento abreviado calificando los hechos de delito de imposición de acuerdos abusivos del art. 291 del CP, al haber impuesto un socio un acuerdo beneficioso para él y en perjuicio de los socios minoritarios y de la sociedad.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL (1) ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, en relación con el art. 650 LECRIM, con arreglo a lo dispuesto en el artículo 14 de la LECrim y con base en las siguientes

CONCLUSIONES

PRIMERA.- El/La socio/a D./Dña. [NOMBRE Y APELLIDOS] de la sociedad [COMPLETAR] se puso de acuerdo, por su liderazgo y capacidad de convencimiento, con otros socios, para darles traslado de la necesidad de que en la junta celebrada el día [FECHA] votaran a favor del punto del orden del día que él/ella mismo/a había instado al Consejo de administración para conseguir un beneficio concreto para él/ella, quien disponía de un volumen de porcentaje del [COMPLETAR] pero necesitaba la votación a favor de [COMPLETAR] y, a cambio de esa votación, prometió a una serie de socios darles una parte de los beneficios que obtuviera. Una vez celebrada la junta, D./Dña. [NOMBRE Y APELLIDOS], al aprovecharse de la situación dominante derivada de ostentar la mayoría en la junta, ejerció la mayoría de los votos que hacía falta obtener para la adopción del acuerdo.

Este acuerdo conllevó un perjuicio a la sociedad tasado en la suma de [IMPORTE] euros y un beneficio para el/la socio/a de [IMPORTE] euros, en base a los siguientes parámetros [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos del delito de imposición de acuerdos abusivos del art. 291 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS], por el delito del art. 291 CP la pena de [PENA] de prisión.

SEXTA.- Deberá indemnizar a la sociedad [COMPLETAR] en la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por realizado el trámite de traslado para acusación y solicitada la apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO].

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], socio/a presente el día de la junta.

— D./Dña. [NOMBRE Y APELLIDOS], secretario/a de la junta.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], miembro del Consejo de administración.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS], representante de la empresa [COMPLETAR] que, a raíz del acuerdo realizó actividades con el/la querellado/a en su propio beneficio y en perjuicio societario.

[OPCIONAL — incluir si procede]

.- Pericial de parte del/de la perito D./Dña. [NOMBRE Y APELLIDOS] para la valoración del perjuicio económico causado a la sociedad y el beneficio estimado al/a la socio/a D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados:

— Acta de la junta del día [FECHA] donde se adoptó el acuerdo abusivo.
— [COMPLETAR]

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

SEGUNDO OTROSÍ DIGO: Esta acusación particular interesa se acuerde la apertura inmediata de pieza separada de responsabilidad civil, requiriendo al/a la acusado/a para que preste fianza en cuantía suficiente para asegurar las responsabilidades pecuniarias que, en definitiva, puedan declararse procedentes.

SUPLICO A LA SECCIÓN: Que tenga por hecha la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Es un delito que puede estar en línea fronteriza con el derecho civil/mercantil, dado que se trata de acuerdos adoptados por mayoría en una junta de accionistas y que podrían ser impugnados con arreglo a los arts. 204 del Real Decreto Legislativo 1/2010, de 2 de julio, por el que se aprueba el texto refundido de la Ley de Sociedades de Capital y ss.

El artículo 291 CP parte de la adopción de un acuerdo obtenido lícitamente pero que debe calificarse de abusivo, y aquí radica la esencia del tipo, que conlleva necesariamente la existencia de un ánimo de lucro propio o ajeno (el de los socios que constituyen la mayoría) en perjuicio de la minoría y siempre que ello no reporte beneficios a la sociedad, es decir, es atípica la concurrencia del mencionado ánimo como compatible con un resultado beneficioso para los intereses societarios, con independencia de que la minoría se vea perjudicada. (STS 654/2002, de 17 de abril, Rec. 1051/2000 y STS 172/2010, de 4 de marzo, Rec. 1012/2009)

El precepto requiere una interpretación cautelosa tendente a delimitar taxativamente la prohibición penal y a legitimar la intervención del Derecho Penal conforme a criterios de lesividad.

El ámbito de aplicación de este delito se ubica en todo lo que se entienda por sociedad y, para ello, hay que acudir al art. 297 CP, donde por sociedad se entiende toda cooperativa, cajas de ahorro, mutua, entidad financiera o de crédito, fundación, sociedad mercantil o cualquier otra entidad de análoga naturaleza.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
