---
name: abandono-familia-defensa-810
description: "Redacta el escrito «Abandono de familia: defensa» (formulario 810 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abandono de familia: defensa

> Formulario 0810 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…contrar un trabajo, pero en la ciudad de»; «…, -D.»; «…, cayendo en una profunda depresión. -D.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y qu…
- .- Pericial: declaración del/de la perito que se menciona a continuación y que deberá ser citado/a [ELEGIR: ju…
- .- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 226 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECrim
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

### Formulario 0810 · Abandono de familia: defensa

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 10 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en un procedimiento abreviado presenta sus conclusiones provisionales frente a acusación de delito de abandono de familia del art. 226 CP alegando que falta el ánimus de dejar de atender sus obligaciones.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas / por el supuesto delito de abandono de familia del art. 226 CP, comparezco ante el Juez y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le atribuye, ya que se tuvo que marchar del domicilio ante la nula posibilidad de encontrar un trabajo, pero en la ciudad de [COMPLETAR] las circunstancias para encontrar un empleo fueron duras y se vino abajo, ya que se marchó a otra ciudad para ver si lo encontraba con el mismo resultado. Al ver que dependían de él dos hijos y su pareja y ver que no podía encontrar trabajo, entró en una profunda depresión que no le permitió contactar con su familia y se tuvo que ir a casa de su hermano, que le atendió, acudiendo a la consulta de un psicólogo, no existiendo ánimus alguno de dejar de atender sus obligaciones sino que el estado de ansiedad pudo con él/ella.

SEGUNDA.- Disconforme con la correlativa. Los hechos no son constitutivos de un delito de abandono de familia. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- Disconforme con las correlativas. Procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto],

-D. [COMPLETAR], amigo/a del/de la acusado/a a quien contó los hechos de la reacción que tuvo cuando vio que no encontraba trabajo, cayendo en una profunda depresión.

-D. [COMPLETAR], hermano/a del/de la acusado/a que le acogió.

[OPCIONAL — incluir si procede]

.- Pericial: declaración del/de la perito que se menciona a continuación y que deberá ser citado/a [ELEGIR: judicialmente / mediante exhorto],

D./Dña. [NOMBRE Y APELLIDOS] médico psiquiatra que le asistió en su proceso depresivo.

[OPCIONAL — incluir si procede]

.- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde el traslado de las actuaciones del art. 784 LECrim.

Conforme al artículo 89.5 b) LOPJ y al art. 14.5 b) LECRIM, las Secciones de Violencia sobre la Mujer conocen de la instrucción de los procesos por cualquier delito contra las relaciones familiares, siempre que se hubiesen cometido contra quien sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género.

Conforme al artículo 89 bis 5 b) LOPJ [NOTA DE REVISIÓN: La competencia de las Secciones de Violencia contra la Infancia y la Adolescencia está en el art. 89 bis.5 b) LOPJ (redacción LO 1/2025); su reflejo procesal es el art. 14.6 b) LECrim. Fuente: LOPJ, BOE-A-1985-12666, art. 89 bis.5 (redacción LO 1/2025, BOE-A-2025-76).] y art. 14.6 b) LECRIM las Secciones de Violencia contra la Infancia y la Adolescencia son competentes para la instrucción de los procesos por cualquier delito contra las relaciones familiares cuando la víctima sea niño, niña o adolescente. No obstante, en caso de que estos hechos pudieran ser conocidos por las Secciones de Violencia sobre la Mujer, la competencia corresponde a esta última (art. 14.7 LECRIM y art. 89 bis 7 LOPJ).

(2) Este es un delito esencialmente doloso que no requiere que se lleve a cabo por medio de una situación de abandono por parte del acusado a sus obligaciones como progenitor.

Se castiga, así, el incumplimiento de los deberes legales de asistencia inherentes a la patria potestad, tutela, guarda o acogimiento familiar o de prestar la asistencia necesaria legalmente establecida para el sustento de sus descendientes, ascendientes o cónyuge.

Sólo se perseguirá previa denuncia de la persona agraviada o de su representante legal. Cuando aquélla sea menor de edad, persona con discapacidad necesitada de especial protección o una persona desvalida, también podrá denunciar el Ministerio Fiscal.

Se castiga también el abandono de un menor de edad o una persona con discapacidad necesitada de especial protección por parte de la persona encargada de su guarda

Es una agravación cuando por las circunstancias del abandono se haya puesto en concreto peligro la vida, salud, integridad física o libertad sexual del menor de edad o de la persona con discapacidad necesitada de especial protección.

No concurrirá si se acreditan circunstancias que determinan la imposibilidad de actuar de alguna manera distinta.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
