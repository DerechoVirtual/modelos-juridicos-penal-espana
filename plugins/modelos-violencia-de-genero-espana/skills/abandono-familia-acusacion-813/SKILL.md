---
name: abandono-familia-acusacion-813
description: "Redacta el escrito «Abandono de familia: acusación» (formulario 813 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abandono de familia: acusación

> Formulario 0813 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] PENA
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dos hijos comunes habidos del matrimonio»; «…y»; «…ncontraba trabajo se iría a la ciudad de»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de Dña. [NOMBRE Y APELLIDOS].…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- -D./Dña. [NOMBRE Y APELLIDOS], amigo/a de la denunciante.…
- .- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 226 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- artículo 89.5 b) LOPJ
- art. 14.5 b) LECRIM
- art. 14.6 b) LECRIM
- art. 14.7 LECRIM
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

### Formulario 0813 · Abandono de familia: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de alternativas señalados; 3 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular en un procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos de delito de abandono de familia del art. 226 CP.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular Dña. [NOMBRE Y APELLIDOS], comparezco ante el Juez y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM contra D. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] se marchó del domicilio conyugal integrado por D./Dña. [NOMBRE Y APELLIDOS], y dos hijos comunes habidos del matrimonio [COMPLETAR] y [COMPLETAR], bajo el pretexto de que como no encontraba trabajo se iría a la ciudad de [COMPLETAR] a conseguir un puesto de trabajo que le habían ofrecido.

Pasados dos meses desde su marcha y ante la falta de comunicación le envió D./Dña. [NOMBRE Y APELLIDOS] correo electrónico solicitándole ayuda económica para mantener a la familia, al no contestar a sus llamadas ni mensajes por WhatsApp, constando como bloqueada por el/la acusado/a en este medio de comunicación para impedir el contacto. Ante la falta de respuesta un mes después volvió a intentarlo y de nuevo hasta cuatro veces más sin resultado alguno, habiendo pasado hasta el momento de la denuncia un año sin noticias del/de la acusado/a que ha dejado abandonada a su familia.

SEGUNDA.- Tales hechos son constitutivos del delito de abandono de familia del art. 226 CP. (2)

TERCERA.- Es responsable del delito de abandono de familia del art. 226 CP el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] en concepto de autor/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la agravante genérica de del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de abandono de familia la pena de [PENA] e inhabilitación especial para el ejercicio del derecho de patria potestad, tutela, guarda o acogimiento familiar por tiempo de [DURACIÓN].

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio de Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS], amigo/a de la denunciante.

[OPCIONAL — incluir si procede]

.- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

Conforme al artículo 89.5 b) LOPJ y al art. 14.5 b) LECRIM, las Secciones de Violencia sobre la Mujer conocen de la instrucción de los procesos por cualquier delito contra las relaciones familiares, siempre que se hubiesen cometido contra quien sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género.

Conforme al artículo 89 bis 5 b) LOPJ [NOTA DE REVISIÓN: La competencia de las Secciones de Violencia contra la Infancia y la Adolescencia está en el art. 89 bis.5 b) LOPJ (redacción LO 1/2025); su reflejo procesal es el art. 14.6 b) LECrim. Fuente: LOPJ, BOE-A-1985-12666, art. 89 bis.5 (redacción LO 1/2025, BOE-A-2025-76).] y art. 14.6 b) LECRIM las Secciones de Violencia contra la Infancia y la Adolescencia son competentes para la instrucción de los procesos por cualquier delito contra las relaciones familiares cuando la víctima sea niño, niña o adolescente. No obstante, en caso de que estos hechos pudieran ser conocidos por las Secciones de Violencia sobre la Mujer, la competencia corresponde a esta última (art. 14.7 LECRIM y art. 89 bis 7 LOPJ).

(2) Este es un delito esencialmente doloso que requiere que se lleve a cabo por medio de una situación de abandono por parte del acusado a sus obligaciones como progenitor.

Se castiga, así, el incumplimiento de los deberes legales de asistencia inherentes a la patria potestad, tutela, guarda o acogimiento familiar o de prestar la asistencia necesaria legalmente establecida para el sustento de sus descendientes, ascendientes o cónyuge.

Sólo se perseguirá previa denuncia de la persona agraviada o de su representante legal. Cuando aquélla sea menor de edad, persona con discapacidad necesitada de especial protección o una persona desvalida, también podrá denunciar el Ministerio Fiscal.

Se castiga también el abandono de un menor de edad o una persona con discapacidad necesitada de especial protección por parte de la persona encargada de su guarda.

Es una agravación cuando por las circunstancias del abandono se haya puesto en concreto peligro la vida, salud, integridad física o libertad sexual del menor de edad o de la persona con discapacidad necesitada de especial protección.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
