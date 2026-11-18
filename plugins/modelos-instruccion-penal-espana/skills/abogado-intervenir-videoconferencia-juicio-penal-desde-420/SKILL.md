---
name: abogado-intervenir-videoconferencia-juicio-penal-desde-420
description: "Redacta el escrito «Abogado: intervenir por videoconferencia en el juicio penal (desde el 20 de marzo de 2024)» (formulario 420 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abogado: intervenir por videoconferencia en el juicio penal (desde el 20 de marzo de 2024)

> Formulario 0420 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La intervención por videoconferencia debe hacerse desde un punto de acceso seguro (art. 258 bis.1 LECrim y art. 62 RDL 6/2023) y solicitarse al menos diez días antes del acto (art. 137 bis.4 LEC, supletorio).
- Cuando se acuerde la presencia física del acusado será necesaria también la de su defensa; si se permite su declaración telemática, el abogado comparecerá junto a él o en la sede judicial (art. 258 bis.2 LECrim).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (3 veces)
- [ ] ...
- [ ] LUGAR

## Elecciones que hay que hacer

- acusación particular / defensa
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si es el abogado del acusado)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 258 bis LECRIM
- art. 258 bis.1 LECRIM
- art. 137 bis LEC
- arts. 731 bis LECRIM
- art. 229 LOPJ

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

### Formulario 0420 · Abogado: intervenir por videoconferencia en el juicio penal (desde el 20 de marzo de 2024)

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (1); 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La intervención por videoconferencia debe hacerse desde un punto de acceso seguro (art. 258 bis.1 LECrim y art. 62 RDL 6/2023) y solicitarse al menos diez días antes del acto (art. 137 bis.4 LEC, supletorio). · Cuando se acuerde la presencia física del acusado será necesaria también la de su defensa; si se permite su declaración telemática, el abogado comparecerá junto a él o en la sede judicial (art. 258 bis.2 LECrim).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el abogado de la acusación particular o de la defensa, solicita intervenir en el juicio oral por videoconferencia desde su despacho profesional, solicitando se habilite la conexión personalizada y llevar a cabo una prueba técnica previa, conforme a los arts. 258 bis LECRIM y 137 bis LEC [NOTA DE REVISIÓN: El precepto que el RDL 6/2023 introdujo en la LECrim sobre actos procesales por presencia telemática es el art. 258 bis (vigente desde el 20-3-2024); no existe art. 158 bis LECrim. Fuente: LECrim, BOE-A-1882-6036, art. 258 bis (añadido por art. 101.3 RDL 6/2023, BOE-A-2023-25758).], introducidos por RDL 6/2023, vigente desde el 20 de marzo de 2024

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincialde

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la [ELEGIR: acusación particular / defensa] en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] en el procedimiento nº [Nº DE PROCEDIMIENTO] por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS], ante este órgano jucial comparezco y, como más procedente sea en derecho, DIGO:

El día [FECHA] va a tener lugar el juicio señalado por dicho delito en el que somos parte.

La petición que se insta por medio del presente escrito va dirigida a postular que la presencia en el juicio se lleve a cabo por este/a letrado/a por videoconferencia desde su despacho profesional y no desde la sede donde se seguirá el juicio (1), en base a las siguientes

ALEGACIONES

PRIMERA.- En aplicación del art. 258 bis.1 LECRIM, que prevé que las actuaciones procesales se realicen preferentemente mediante presencia telemática, se permitió la comparecencia en juicio de mi mandante por videoconferencia.

[OPCIONAL — incluir si procede]

(Si es el abogado del acusado)

Señala el art. 258 bis.2.5º LECRIM que

"Cuando se disponga la presencia física del investigado o acusado, será también necesaria la presencia física de su defensa letrada. Cuando se permita su declaración telemática, el abogado del investigado o acusado comparecerá junto con este o en la sede del órgano judicial"

En este caso comunico que, en atención a lo expuesto, la intervención de la defensa letrada lo será también de forma telemática.

SEGUNDA.- Señala el art. 137 bis LEC, de aplicación supletoria conforme prevé el art. 258 bis.1 LECRIM que:

"2. Los y lasprofesionales,así como laspartes, peritos y testigos que deban intervenir en cualquier actuación porvideoconferencialo harán desdela oficina judicialcorrespondiente al partido judicial de sudomicilio o lugar de trabajo. En el caso de disponer de medios adecuados, dicha intervención también se podrá llevar a cabo desde el juzgado de paz de su domicilio o de su lugar de trabajo.
3. Cuando el juez o la jueza, en atención a las circunstancias concurrentes, lo estime oportuno, estas intervencionespodrán hacerse desde cualquier lugar, siempre que disponga de los medios que permitan asegurar la identidad del interviniente conforme a lo que se determine reglamentariamente. [...]"

En este caso solicito que la intervención de la defensa letrada por videoconferencia pueda realizarse desde su despacho, profesional, ya que cumple con los requisitos legales, en atención a las siguientes circunstancias

TERCERA.- Se interesa, a ser posible, que mi cliente pueda declarar también desde el despacho de D./Dña. [NOMBRE Y APELLIDOS] para evitar problemas con otra conexión adicional, garantizando que entrará cuando sea llamado a comparecer por la autoridad judicial, permaneciendo fuera del mismo mientras tanto.

Es por ello, por lo que se interesa que, en la asistencia e intervención como letrado/a de D./Dña. [NOMBRE Y APELLIDOS] para el juicio señalado para el día [FECHA], se habilite la forma de acceso al juicio telemático facilitando la clave de acceso al sistema informático por plataforma digital para poder intervenir.

Por todo ello,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Véase la STS 331/2019 de 27 de junio 2019, Rec. 1376/2018 que ha validado el uso de la videoconferencia en juicios.

Véanse también arts. 731 bis LECRIM y 777.2 LECRIM, art. 229 LOPJ, y el Estatuto de la Corte Penal Internacional aprobado en Roma el 17 de julio de 1998 e Instrucción 3/2002 de la Fiscalía General del Estado.

================================================================================
