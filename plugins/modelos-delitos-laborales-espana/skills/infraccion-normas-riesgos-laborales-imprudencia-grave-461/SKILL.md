---
name: infraccion-normas-riesgos-laborales-imprudencia-grave-461
description: "Redacta el escrito «Infracción de normas de riesgos laborales por imprudencia grave: acusación» (formulario 461 de delitos contra los derechos de los trabajadores, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infracción de normas de riesgos laborales por imprudencia grave: acusación

> Formulario 0461 del plugin **Delitos contra los derechos de los trabajadores** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

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
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…programó la ejecución de una obra en»; «…t. 3 del RD 1627/1997, de 24 de octubre,»; «…la pena de [PENA] de prisión y»; «…, cuya declaración obra al folio»; «… que elaboró el informe obrante al folio»; «…os siguientes folios de las actuaciones:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical, a cuyo fin deberán ser citados/as los/as siguientes testigos:…
- - D./Dña. [NOMBRE Y APELLIDOS], cuya declaración obra al folio [COMPLETAR].…
- .- Pericial de técnico experto en prevención de riesgos laborales acerca de la no viabilidad de las medidas ad…
- .- Documental, por lectura de los siguientes folios de las actuaciones: [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 317 CP
- artículo 781.1 de la LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 317 del CP
- arts. 4.2.d) y 19.1 del Estatuto de los Trabajadores
- art. 14 de la Ley 31/1995
- art. 3 del RD 1627/1997
- art. 22 del CP
- art. 780 LECRIM
- art. 316 CP
- artículo 14.2 Ley 31/1995
- artículo 8.3 CP
- artículo 316 CP
- artículo 77 CP
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

### Formulario 0461 · Infracción de normas de riesgos laborales por imprudencia grave: acusación

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito en el que el acusador particular presenta sus conclusiones provisionales en procedimiento abreviado calificando los hechos de delito contra los derechos de los trabajadores por imprudencia grave del art. 317 CP, por no supervisión de normas de prevención de riesgos laborales.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL (1) ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El/La empresario/a D./Dña. [NOMBRE Y APELLIDOS] programó la ejecución de una obra en [COMPLETAR], en la que estaba trabajando D./Dña. [NOMBRE Y APELLIDOS], aunque con una absoluta falta de vigilancia de la ejecución de las medidas que se habían previsto, en base a las normas de prevención de riesgos laborales, no supervisándose que se tomaron aquellas medidas que estaban previstas conforme a la normativa laboral.

SEGUNDA.- Los hechos narrados son constitutivos de un delito contra los derechos de los trabajadores, por infracción de las normas de prevención de riesgos laborales por imprudencia grave del art. 317 del CP, en relación con los arts. 4.2.d) y 19.1 del Estatuto de los Trabajadores y el art. 14 de la Ley 31/1995 de Prevención de Riesgos Laborales, apartados 1 a 3, así como el Anexo IV del Real Decreto 1627/97, de 24 de octubre, parte C, apartados 3.a) y b) y apartados 5.a) y b) y el art. 3 del RD 1627/1997, de 24 de octubre, [COMPLETAR]. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] de prisión y [COMPLETAR] de multa a razón de [IMPORTE] euros/día con responsabilidad personal subsidiaria de 1 día por cada dos cuotas no satisfechas.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, a cuyo fin deberán ser citados/as los/as siguientes testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], cuya declaración obra al folio [COMPLETAR].

- Testigo-perito de la Inspección de Trabajo D./Dña. [NOMBRE Y APELLIDOS], que elaboró el informe obrante al folio [COMPLETAR] y ss. de la causa.

[OPCIONAL — incluir si procede]

.- Pericial de técnico experto en prevención de riesgos laborales acerca de la no viabilidad de las medidas adoptadas.

[OPCIONAL — incluir si procede]

.- Documental, por lectura de los siguientes folios de las actuaciones: [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Una cosa es la falta de prevención del riesgo equivalente a la omisión de las medidas necesarias y adecuadas exigidas conforme a la legislación laboral y otra distinta su insuficiencia o defectuosidad, lo que debe dar lugar a los dos tipos de comisión previstos, el art. 316 CP doloso y el art. 317 CP imprudente, radicando su diferencia en el elemento subjetivo: conciencia del peligro cuando se trata del tipo doloso, y a pesar de ello se omiten las medidas adecuadas y necesarias, e infracción del deber del cuidado por ausencia de todas las previsibles exigibles al garante de la seguridad y salud de los trabajadores (artículo 14.2 Ley 31/1995). Debe tenerse en cuenta que el ámbito ordinario e intenso de la protección corresponde sustancialmente al derecho laboral y que su trascendencia penal debe constituir remedio extremo. (STS 1355/2000, de 26 de julio, rec. 4716/1998).

El elemento normativo recogido en el art. 316 CP como «infracción de las normas de prevención de riesgos laborales» ha llevado a calificar a este delito como un tipo penal en blanco y, en consecuencia, el art. 317 CP constituye la incriminación de la realización imprudente de un tipo penal en blanco. Para proceder a la interpretación del art. 317 CP, por tanto, es necesario precisar qué contenido tiene ese elemento normativo en la configuración típica del tipo doloso (art. 316 CP) y, tras ello, comprobar si ese mismo contenido debe o no dársele en la interpretación del tipo imprudente.

La normativa infringida en materia de prevención de riesgos laborales suele referirse a los artículos 3 ,14, 15, 17.1 de la Ley 31/95, de 8 de noviembre, Prevención de Riesgos Laborales. Estos incumplimientos deben ser puestos en relación con la normativa específica de equipos de trabajo establecida en el artículo 3.5 y anexo II 1. 14 del Real Decreto 1215/97, por el que se establecen las disposiciones mínimas de seguridad y salud para la utilización de equipos de trabajo por los trabajadores.

Se ha señalado que el art. 316 CP refleja la imprudencia consciente, es comisión por omisión dolosa y el art. 317 CP la imprudencia inconsciente, la comisión por omisión imprudente o por culpa.

Cuando concurra el art. 317 CP con un tipo de imprudencia de resultado de muerte o lesiones se castiga conforme al principio de consunción ( artículo 8.3 CP ) absorbiendo el delito de resultado, por progresión delictiva, al de peligro que describe el artículo 316 CP, aunque habrá supuestos en los que resultaría de aplicación el concurso ideal ( artículo 77 CP ) "... cuando el resultado producido constituye solamente uno de los posibles resultados de la conducta omisiva del responsable de las medidas de seguridad ..." (STS 1036/2002, de 4 de junio, rec. 3307/2000 y STS 2445/2001, de 22 de diciembre, rec. 279/2000).

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
