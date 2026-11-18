---
name: lesiones-escrito-acusacion-437
description: "Redacta el escrito «Lesiones: escrito de acusación» (formulario 437 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones: escrito de acusación

> Formulario 0437 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tomando unas copas en el Bar»; «…entado/a fue trasladado/a al hospital de»; «…édico emitido por el Centro Hospitalario»; «…con el art. 149 CP la pena de prisión de»; «…, propietario/a del bar»; «… delictivos, quien podrá ser citado/a en»; «…, cliente/a del bar»; «… los hechos, quien podrá ser citado/a en»; «…édico emitido por el Centro Hospitalario»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de el/la acusado/a.…
- .- Testifical, consistente en la declaración de los/as testigos que se enumeran a continuación, que deberán se…
- .- Pericial. Informe del/de la médico forense D./Dña. [NOMBRE Y APELLIDOS].…
- .- Documental consistente en:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 147 CP
- art. 149 CP
- artículo 781.1 de la LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- art. 650 LECrim
- artículo 14 de la LECrim
- artículo 147 del Código Penal
- artículo 149 del CP
- art. 22 del CP
- art. 780 LECRIM
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

### Formulario 0437 · Lesiones: escrito de acusación

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito del acusado presentando sus conclusiones provisionales en un procedimiento abreviado y calificando los hechos de delito de lesiones definido en el art. 147 CP, en relación con el art. 149 CP por producirse pérdida de visión.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL (1) ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, en relación con el art. 650 LECrim, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- A.- El pasado día [FECHA], sobre las [Nº] horas, se encontraba mi representado/a, junto con su amigo/a D./Dña. [NOMBRE Y APELLIDOS], mayor de edad y con domicilio en [LOCALIDAD] tomando unas copas en el Bar [COMPLETAR], sito en [LOCALIDAD].

Estando en esta situación, se aproximó a ellos quien luego reconoció mi representado/a como el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS], compañero/a de trabajo suyo y, alzando la voz, le dijo: ‘eres un maldito trepa’. Acto seguido cogió un vaso que estaba apoyado en la barra del bar y golpeó con él a mi representado/a en la cara, después de lo cual echó a correr hacia la salida y desapareció del lugar de los hechos rápidamente.

B.- Mi representado/a fue trasladado/a al hospital de [COMPLETAR], donde se le observó un desprendimiento de retina en su ojo derecho, por lo que tuvo que ser sometido/a con urgencia a una intervención quirúrgica, después de la cual se le ha diagnosticado una pérdida absoluta de visión en el citado ojo por no poder reponerle correctamente la retina que se encontraba partida. Se aporta como documento nº 1 parte médico emitido por el Centro Hospitalario [COMPLETAR].

C.- Actualmente mi representado/a continúa hospitalizado/a sin haber recibido respuesta por parte de los médicos acerca de cuándo será dado de alta.

SEGUNDA.- Los hechos expuestos revisten los caracteres de un delito de lesiones que define el artículo 147 del Código Penal, en relación con el artículo 149 del CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 147 CP, en relación con el art. 149 CP la pena de prisión de [COMPLETAR].

SEXTA.- Procede condenar al/a la acusado/a a que indemnice al/a la perjudicado/a con [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (2)

[OPCIONAL — incluir si procede]

1.- Interrogatorio de el/la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, consistente en la declaración de los/as testigos que se enumeran a continuación, que deberán ser citados/as en el día y hora que a tal fin se señale para su declaración ante el/la Juez/a instructor/a:

-D./Dña. [NOMBRE Y APELLIDOS], amigo/a de mi representado/a y que se encontraba con él/ella en el lugar de los hechos, con domicilio en [LOCALIDAD].
-D./Dña. [NOMBRE Y APELLIDOS], propietario/a del bar [COMPLETAR] donde ocurrieron los hechos delictivos, quien podrá ser citado/a en [COMPLETAR].
- D./Dña. [NOMBRE Y APELLIDOS], cliente/a del bar [COMPLETAR] y testigo presencial de los hechos, quien podrá ser citado/a en [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Pericial. Informe del/de la médico forense D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental consistente en:

-Parte médico emitido por el Centro Hospitalario [COMPLETAR].
-Historia clínica de D./Dña. [NOMBRE Y APELLIDOS] donde no se reflejan antecedentes por lesiones en el ojo de carácter previo a los hechos.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
