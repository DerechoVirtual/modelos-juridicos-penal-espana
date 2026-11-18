---
name: prueba-digital-pericial-informatica-propuesta-escrito-703
description: "Redacta el escrito «Prueba digital y pericial informática: propuesta en el escrito de acusación» (formulario 703 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prueba digital y pericial informática: propuesta en el escrito de acusación

> Formulario 0703 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO (2 veces)
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, Procurador/a»; «…n las siguientes: CONCLUSIONES Primera.-»; «…del artículo»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado/a D./Dña. [NOMBRE Y APELLIDOS]…
- 2.- Testifical, interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- -D./Dña. [NOMBRE Y APELLIDOS]…
- 3.- Pericial siguiente:…
- 4.- Documental:…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- artículo 780 LECRIM
- artículo 650 LECRIM
- artículo 781 LECRIM
- artículo 777.2 LECRIM
- artículos 763, 764 y 765 LECRIM
- artículo 459 LECRIM
- artículo 778.1 LECRIM
- artículo 656 LECRIM
- artículos 781 y 784 LECRIM
- artículos 966 y 969.2 LECRIM

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

### Formulario 0703 · Prueba digital y pericial informática: propuesta en el escrito de acusación

- Año del modelo: 2017
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 4 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular presenta sus conclusiones provisionales y solicita la apertura de juicio oral, proponiendo pericial informática que corrobore la prueba digital aportada (mensaje instantáneo de WhatsApp, email, etc.).

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a [COMPLETAR] de los Tribunales en la representación que tengo acreditada del acusador particular D./Dña. [NOMBRE Y APELLIDOS] en las diligencias previas número [Nº DE PROCEDIMIENTO] seguidas por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) escrito de acusación por la vía del artículo 780 LECRIM, en relación con el artículo 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] y solicito apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia, por la vía del artículo 781 LECRIM, con base en las siguientes:

CONCLUSIONES

Primera.- [COMPLETAR].

Segunda.- Tales hechos son constitutivos del delito de [DELITO] del artículo [COMPLETAR] del Código Penal.

Tercera.- Es responsable del delito en concepto de autor el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS]

Cuarta.- No concurren circunstancias modificativas de responsabilidad criminal.

Quinta.- Procede imponer a el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

Sexta.- El/la acusado/a deberá indemnizar a mi representado/a, por importe de [IMPORTE] euros en concepto de daño moral.

Las costas deberán ser satisfechas por el/la acusado/a, incluyendo las de esta acusación particular.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO

Que, para el juicio oral, intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (2)

Los propuestos por el Ministerio Fiscal y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado/a D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

2.- Testifical, interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

3.- Pericial siguiente:

Prueba pericial informática relativa a la prueba digital aportada consistente en la adveración realizada ante el letrado de la administración de justicia del contenido de los mensajes remitidos, para lo que se aportó pericial informática de parte sobre le veracidad de esta prueba digital, para lo que comparecerá al juicio oral el perito D./Dña. [NOMBRE Y APELLIDOS] para exponer el contenido de la pericia llevada a cabo. (3)

[OPCIONAL — incluir si procede]

4.- Documental:

1.- Acta del letrado de la administración de justicia de adveración de la prueba digital aportada que se propone en este acto consistente en transcripción de los mensajes recibidos cotejados con la pericial informática.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN

Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde que el Juez le emplaza para ello, por la vía del artículo 780 LECRIM.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (artículo 777.2 LECRIM) [NOTA DE REVISIÓN: La prueba anticipada en diligencias previas se regula en el art. 777.2 LECrim; el art. 797.2 se refiere a las diligencias urgentes ante el juzgado de guardia en el juicio rápido. Fuente: LECrim, BOE-A-1882-6036, arts. 777.2 y 797.2.].

En el escrito de acusación se podrá solicitar la práctica anticipada de aquellas pruebas que no puedan llevarse a cabo durante las sesiones del juicio oral, así como la adopción, modificación o suspensión de las medidas a que se refieren los artículos 763, 764 y 765 LECRIM, o cualesquiera otras que resulten procedentes o se hubieren adoptado, así como la cancelación de las tomadas frente a personas contra las que no se dirija acusación.

(3) En el proceso penal, el informe debe ser emitido por dos peritos (artículo 459 LECRIM), salvo en el procedimiento abreviado, que podrá ser emitido por uno solo de ellos, cuando el Juez lo considere suficiente (artículo 778.1 LECRIM).

Se incluye esta mención habida cuenta que el Tribunal Supremo tiene declarado, con respecto a la aportación de un WhatsApp o cualquier otra prueba digital que, de impugnarse, es preciso proponer y aportar prueba pericial que acredite ese contenido (STS 300/2015, de 19 de mayo).

Los informes periciales pueden aportarse por las partes personadas en el proceso durante la fase de instrucción, así como acompañarlos junto con el escrito de calificación provisional (en el proceso ordinario; artículo 656 LECRIM) o en el escrito de acusación y/o defensa (en el proceso abreviado; artículos 781 y 784 LECRIM). En el juicio de delito leve, las partes aportarán los informes periciales en el acto del juicio oral (artículos 966 y 969.2 LECRIM).

================================================================================
