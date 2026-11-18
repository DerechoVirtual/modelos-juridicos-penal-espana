---
name: infraccion-normas-riesgos-laborales-defensa-466
description: "Redacta el escrito «Infracción de normas de riesgos laborales: defensa» (formulario 466 de delitos contra los derechos de los trabajadores, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infracción de normas de riesgos laborales: defensa

> Formulario 0466 del plugin **Delitos contra los derechos de los trabajadores** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELE…
- - D./Dña. [NOMBRE Y APELLIDOS], que presenció los hechos.…
- - D./Dña. [NOMBRE Y APELLIDOS], trabajador/a presente en el lugar de los hechos que cumplió el plan de prevenc…
- .- Documental.- Plan de prevención de riesgos laborales y acreditación documental de su implementación en la e…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 316 CP
- artículo 316 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 318 del CP
- art. 73 CP
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

### Formulario 0466 · Infracción de normas de riesgos laborales: defensa

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 2 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que los acusados por un delito contra los derechos de los trabajadores por infracción de las normas de prevención de riesgos laborales del art. 316 CP en un procedimiento abreviado presenta sus conclusiones provisionales alegando que se implantó debidamente un plan de prevención de riesgos laborales.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], acusados/as en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del artículo 316 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mis representados/as no hicieron exactamente lo que se les imputa, ya que fue el/la trabajador/a el/la que incumplió las medidas de seguridad que habían sido informadas a tal efecto por el/la directivo/a D./Dña. [NOMBRE Y APELLIDOS], quien aplicó debidamente el plan de prevención de riesgos laborales con concreción y detalle. Además, el resto de trabajadores/as sí que llevaban puestas las medidas de seguridad, tratándose de una actuación aislada del/de la trabajador/a y culpa del/de la mismo/a.

SEGUNDA.- Los hechos no son constitutivos de un delito del art 316 CP. (2)

TERCERA.- Niego las correlativas. Mis representados/as no son los/las autores/as del delito por el que se procede ni de ningún otro.

CUARTA- Disconforme con las correlativas. Procede absolver a mis representados/as con todos los pronunciamientos favorables, por no existir responsabilidad penal.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que presenció los hechos.

- D./Dña. [NOMBRE Y APELLIDOS], técnico encargado/a de implantación de medidas de prevención con explicación del protocolo puesto en marcha y su incumplimiento por el/la trabajador/a.

- D./Dña. [NOMBRE Y APELLIDOS], oficial superior que testificará acerca del cumplimiento de las medidas.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], trabajador/a presente en el lugar de los hechos que cumplió el plan de prevención.

[OPCIONAL — incluir si procede]

.- Documental.- Plan de prevención de riesgos laborales y acreditación documental de su implementación en la empresa.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Se trata de un tipo penal de estructura omisiva o más propiamente de infracción de un deber que protege la seguridad en el trabajo entendido como la ausencia de riesgos para la vida y la salud del trabajador dimanante de las condiciones materiales de la prestación del trabajo, bien jurídico autónomo y por tanto independiente de la efectiva lesión que en todo caso merecería calificación independiente, en el que el sujeto activo, los legalmente obligados, ocupan una posición semejante a la de garante y al respecto se recuerda que el art. 14.2 de la Ley 31/95 de 8 de noviembre, de Prevención de Riesgos Laborales impone al empresario el deber de protección frente a los trabajadores para garantizar su seguridad y la salud en todos los aspectos relacionados con el trabajo.

Resulta incontestable que los empresarios o titulares de la empresa son los posibles sujetos activos del delito, pero no sólo ellos, sino también, desde una perspectiva penal los administradores y encargados del servicio a los que se refiere el art. 318 del CP.

El elemento normativo del tipo que se refiere a: "infracción de las normas de prevención de riesgos laborales" calificar al delito como tipo penal en blanco, de manera que es la infracción de la normativa laboral la que completa el tipo, exigiendo, además, el adecuado nexo de causalidad que la norma de seguridad infringidas debe poner en peligro grave su vida, salud o integridad física (de los trabajadores), y es la que envía a infracciones más graves de la normativa laboral que lleven consigo la creación de grave riesgo. (STS 1233/2002, de 29 de julio, rec. 3551/2000).

La normativa infringida en materia de prevención de riesgos laborales suele referirse a los artículos 3 ,14, 15, 17.1 de la Ley 31/95, de 8 de noviembre, Prevención de Riesgos Laborales. Estos incumplimientos deben ser puestos en relación con la normativa específica de equipos de trabajo establecida en el artículo 3.5 y anexo II 1. 14 del Real Decreto 1215/97, por el que se establecen las disposiciones mínimas de seguridad y salud para la utilización de equipos de trabajo por los trabajadores.

Constituye un delito de peligro, en el que no es necesario que el peligro se concrete en una lesión efectiva. Si el resultado lesivo se produce deberá acudirse al concurso real del art. 73 CP.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
