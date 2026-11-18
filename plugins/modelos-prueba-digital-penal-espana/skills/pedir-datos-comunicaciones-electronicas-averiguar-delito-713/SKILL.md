---
name: pedir-datos-comunicaciones-electronicas-averiguar-delito-713
description: "Redacta el escrito «Pedir datos de comunicaciones electrónicas para averiguar un delito» (formulario 713 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir datos de comunicaciones electrónicas para averiguar un delito

> Formulario 0713 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tipificado en el artículo»; «…des públicas de comunicaciones en España»; «…o móvil) 1. El número o números marcados»; «…el tipo de comunicación) Tipo de llamada»; «…, servicios suplementarios»; «…ios de mensajería o multimedia empleados»; «…l servicio y la etiqueta de localización»; «…ón móvil) 1. La etiqueta de localización»

## Elecciones que hay que hacer

- doloso castigado con pena con límite máximo de [COMPLETAR], al menos, 3 años de prisión / cometido por grupo u organización criminal, de terrorismo / cometido a través de instrumentos informáticos o de cualquier otra tecnología de la información o la comunicación o servicio de comunicación

## Párrafos opcionales (11)

Inclúyelos solo si encajan en los hechos:

- (Datos necesarios para rastrear e identificar el origen de una comunicación telefónica fija o móvil)…
- (Datos necesarios para rastrear e identificar el origen de una comunicación por internet, correo electrónico y…
- (Datos necesarios para identificar el destino de una comunicación telefónica fija o móvil)…
- (Datos necesarios para rastrear e identificar el destino de una comunicación por internet, correo electrónico …
- (Datos necesarios para determinar la fecha, hora y duración de una comunicación telefónica fija o móvil)…
- (Datos necesarios para determinar la fecha, hora y duración del acceso a internet, al correo electrónico y a l…
- (Datos necesarios para identificar el tipo de comunicación)…
- (Datos necesarios para identificar el equipo de comunicación de los usuarios o lo que se considera ser el equi…
- (Datos necesarios para identificar el equipo de comunicación de acceso a internet, correo electrónico y telefo…
- (Datos necesarios para identificar la localización del equipo de comunicación móvil)…
- (Datos necesarios para identificar al titular de una tarjeta telefónica prepago)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 311 y 776.3 LECRIM
- artículos 311 y 776.3 LECRIM
- artículo 7.3 de la Ley 25/2007

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

### Formulario 0713 · Pedir datos de comunicaciones electrónicas para averiguar un delito

- Año del modelo: 2017
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (1); 1 desplegables y casillas convertidos en elección en blanco; 11 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se solicita al juez instructor que dicte auto pidiendo a los operadores que presten servicios de comunicaciones electrónicas la aportación de datos necesarios para la identificación de los autores del delito, conforme al art. 311 y 776.3 LECRIM, de conformidad con su deber de colaboración recogido en el art. 588 ter e LECRIM y lo dispuesto en los arts. 588 ter j a m LECRIM y la L 25/2007, de 18 de octubre, de conservación de datos relativos a las comunicaciones electrónicas y a las redes públicas de comunicaciones.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese órgano judicial por D./Dña. [NOMBRE Y APELLIDOS], por la comisión de un delito de [DELITO] tipificado en el artículo [COMPLETAR] CP, habiéndonos personado en las actuaciones por escrito de fecha [FECHA], aunque desconociendo la autoría de los hechos por haberse cometido por medios tecnológicos.

Que por esta parte se consideró imprescindible para el esclarecimiento de los hechos el que se trasladara al equipo de investigación de la policía judicial que realizara las investigaciones oportunas.

ALEGACIONES

PRIMERA.- Tras la investigación policial, en base a los artículos 311 y 776.3 LECRIM(Para el procedimiento abreviado) se hace preciso acreditar la identidad de la persona o personas autoras del delito objeto del presente procedimiento penal. (1)

SEGUNDA.- Dado que el delito que se investiga es [ELEGIR: doloso castigado con pena con límite máximo de [COMPLETAR], al menos, 3 años de prisión / cometido por grupo u organización criminal, de terrorismo / cometido a través de instrumentos informáticos o de cualquier otra tecnología de la información o la comunicación o servicio de comunicación], conforme al art. 588 ter a LECRIM, se interesa se requiera de los operadores que presten servicios de comunicaciones electrónicas disponibles al público o exploten redes públicas de comunicaciones en España [COMPLETAR], según el deber de colaboración del artículo 588 ter e LECRIM, de conformidad con lo dispuesto en la Ley 25/2007, de 18 de octubre, de conservación de datos relativos a las comunicaciones electrónicas y a las redes públicas de comunicaciones y a los arts. 588 ter j a m LECRIM, la aportación de la siguiente información:

[OPCIONAL — incluir si procede]

(Datos necesarios para rastrear e identificar el origen de una comunicación telefónica fija o móvil)

1. Número de teléfono de llamada.

2. Nombre y dirección del abonado o usuario registrado.

[OPCIONAL — incluir si procede]

(Datos necesarios para rastrear e identificar el origen de una comunicación por internet, correo electrónico y telefonía por internet)

1. La identificación de usuario asignada.

2. La identificación de usuario y el número de teléfono asignados a toda comunicación que acceda a la red pública de telefonía.

3. El nombre y dirección del abonado o del usuario registrado al que se le ha asignado en el momento de la comunicación una dirección de Protocolo de Internet (IP), una identificación de usuario o un número de teléfono.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar el destino de una comunicación telefónica fija o móvil)

1. El número o números marcados [COMPLETAR] y, en aquellos casos en que intervengan otros servicios, como el desvío o la transferencia de llamadas, el número o números hacia los que se transfieren las llamadas.

2. Los nombres y las direcciones de los abonados o usuarios registrados.

[OPCIONAL — incluir si procede]

(Datos necesarios para rastrear e identificar el destino de una comunicación por internet, correo electrónico y telefonía por internet)

1. La identificación de usuario o el número de teléfono del destinatario o de los destinatarios de una llamada telefónica por Internet.

2. Los nombres y direcciones de los abonados o usuarios registrados y la identificación de usuario del destinatario de la comunicación.

[OPCIONAL — incluir si procede]

(Datos necesarios para determinar la fecha, hora y duración de una comunicación telefónica fija o móvil)

La fecha y hora del comienzo y fin de la llamada o, en su caso, del servicio de mensajería o del servicio multimedia.

[OPCIONAL — incluir si procede]

(Datos necesarios para determinar la fecha, hora y duración del acceso a internet, al correo electrónico y a la telefonía por internet)

1. La fecha y hora de la conexión y desconexión del servicio de acceso a Internet registradas, basadas en un determinado huso horario, así como la dirección del Protocolo Internet, ya sea dinámica o estática, asignada por el proveedor de acceso a Internet a una comunicación, y la identificación de usuario o del abonado o del usuario registrado.

2. La fecha y hora de la conexión y desconexión del servicio de correo electrónico por Internet o del servicio de telefonía por Internet, basadas en un determinado huso horario.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar el tipo de comunicación)

Tipo de llamada [COMPLETAR], servicios suplementarios [COMPLETAR] o servicios de mensajería o multimedia empleados [COMPLETAR] o servicio de internet utilizado.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar el equipo de comunicación de los usuarios o lo que se considera ser el equipo de comunicación telefónica fija o móvil)

1. Los números de teléfono de origen y destino.

2. La identidad internacional del abonado móvil (IMSI) de la parte que efectúa la llamada.

3. La identidad internacional del equipo móvil (IMEI) de la parte que efectúa la llamada.

4. La IMSI de la parte que recibe la llamada.

5. La IMEI de la parte que recibe la llamada.

6. En el caso de los servicios anónimos de pago por adelantado, tales como los servicios con tarjetas prepago, fecha y hora de la primera activación del servicio y la etiqueta de localización [COMPLETAR] desde la que se haya activado el servicio.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar el equipo de comunicación de acceso a internet, correo electrónico y telefonía por internet)

1. El número de teléfono de origen en caso de acceso mediante marcado de números.

2. La línea digital de abonado (DSL) u otro punto terminal identificador del autor de la comunicación.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar la localización del equipo de comunicación móvil)

1. La etiqueta de localización [COMPLETAR] al inicio de la comunicación.

2. Los datos que permiten fijar la localización geográfica de la celda, mediante referencia a la etiqueta de localización, durante el período en el que se conservan los datos de las comunicaciones.

[OPCIONAL — incluir si procede]

(Datos necesarios para identificar al titular de una tarjeta telefónica prepago)

1. Nombre, apellidos y nacionalidad del comprador.

2. Número correspondiente al documento identificativo utilizado en la compra de la tarjeta telefónica de prepago, y la naturaleza o denominación de dicho documento.

3. El número de tarjeta de identificación fiscal, así como su denominación social y su código de identificación fiscal

Por todo ello, esta representación interesa de este órgano judicial que, de conformidad con lo dispuesto en el artículo 7.3 de la Ley 25/2007 [NOTA DE REVISIÓN: Desde el 11-5-2014 (Ley 9/2014) el plazo supletorio del art. 7.3 es de siete días naturales desde las 8:00 horas del día natural siguiente a la recepción de la orden; el plazo de 72 horas solo rige si lo fija expresamente la resolución judicial. Fuente: Ley 25/2007, BOE-A-2007-18243, art. 7.3 (redacción Ley 9/2014, BOE-A-2014-4950).], de 18 de octubre, se comisione a dos funcionarios de Policía Judicial para que requieran de los mencionados operadores la entrega de la información solicitada en un plazo de 72 horas, contadas a partir de las 8:00 horas del día laborable siguiente a aquél en que el operador reciba la copia del Auto judicial.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y acuerde la práctica de las diligencias interesadas, dándose al procedimiento el curso legal que corresponda.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del Procurador

Firma del Abogado

NOTAS DEL FORMULARIO

(1) Requiere autorización judicial previa. El artículo 588 bis b LECRIM establece que esta medida puede adoptarse de oficio, a instancia del fiscal o de la policía judicial. Ello no impide que una acusación particular pueda instarlo al juez si de esa manera puede conseguir avanzar en las diligencias de investigación. El juez daría traslado al Fiscal para informe y con este informe el juez resolvería a favor o en contra sobre esta petición, pero no puede privarse a la parte de ese derecho al menos de instar medidas de averiguación.

================================================================================
