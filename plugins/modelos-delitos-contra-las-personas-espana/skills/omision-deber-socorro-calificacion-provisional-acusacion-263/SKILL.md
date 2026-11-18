---
name: omision-deber-socorro-calificacion-provisional-acusacion-263
description: "Redacta el escrito «Omisión del deber de socorro: calificación provisional de la acusación» (formulario 263 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Omisión del deber de socorro: calificación provisional de la acusación

> Formulario 0263 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ún consta acreditado en el Procedimiento»; «…con DNI [DNI/NIE] y domicilio»; «… PROVISIONALES PRIMERA.- El/La acusado/a»; «…ción de asistencia al paciente, dado que»; «…la negativa a atenderle fue el siguiente»; «… agravantes. Concurre en el/la acusado/a»; «…o y el/la querellado/a se negó a actuar.»

## Elecciones que hay que hacer

- se negó a prestar asistencia médica / abandonó el servicio cuando debía prestarle asistencia médica
- de la negativa / del abandono del servicio
- esta negativa / este abandono
- más tarde le fue diagnosticado / de la denegación se derivó la agravación consistente en

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la acusado/a.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial siguiente:…
- .- Documental: respecto a la enfermedad del paciente, su historial clínico para acreditar el grave riesgo de s…
- (Si desea solicitar diligencias complementarias)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 27.4 LO 5/1995
- artículo 29 de la Ley Orgánica 5/1995
- art. 650 LECRIM
- art. 196 CP
- art. 22 del CP

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

### Formulario 0263 · Omisión del deber de socorro: calificación provisional de la acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 2 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 24 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento [COMPLETAR] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando en el plazo concedido por el traslado bajo el amparo del art. 27.4 LO 5/1995, que se ha verificado a los fines dispuestos en el artículo 29 de la Ley Orgánica 5/1995 del Tribunal del Jurado, en relación al art. 650 LECRIM, solicitamos la apertura de juicio oral y formulamos, por medio del presente escrito de calificación provisional, contra D./Dña. [NOMBRE Y APELLIDOS] con DNI [DNI/NIE] y domicilio [COMPLETAR] las siguientes,

CONCLUSIONES PROVISIONALES

PRIMERA.- El/La acusado/a [COMPLETAR], médico del hospital, estando de servicio el día [FECHA] en el citado hospital, [ELEGIR: se negó a prestar asistencia médica / abandonó el servicio cuando debía prestarle asistencia médica] al paciente, sin excusa ni razón alguna justificativa [ELEGIR: de la negativa / del abandono del servicio], derivándose de [ELEGIR: esta negativa / este abandono] grave riesgo para la salud del paciente, dado que [ELEGIR: más tarde le fue diagnosticado / de la denegación se derivó la agravación consistente en].

El/La acusado/a tenía obligación de asistencia al paciente, dado que [COMPLETAR]

El riesgo que se derivó de la negativa a atenderle fue el siguiente [COMPLETAR].

Por los hechos se ha derivado una gran intranquilidad, ansiedad y zozobra en el propio paciente y en sus familiares allí presentes durante.. días, habiéndose diagnosticado un cuadro de.

SEGUNDA.- Tales hechos son constitutivos del delito de omisión del deber de socorro del art. 196 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] de multa a razón de [IMPORTE] euros/día y con la de inhabilitación especial para empleo o cargo público, profesión u oficio, por tiempo de [Nº] años. Con responsabilidad personal subsidiaria de 1 día de prisión por dos cuotas impagadas.

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, evacuadas las conclusiones y se tenga por solicitada la apertura de juicio oral contra D./Dña. [NOMBRE Y APELLIDOS].

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Declaración del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración del paciente a quien no se atendió.

-Declaración de familiares, profesionales o amigos que vieron lo ocurrido.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Declaración de los testigos que puedan dar razón de los hechos por estar en ese momento en el centro médico, tales como:

a.- La persona o personas que lo llevaron al hospital o estaban allí con él/ella.

D./Dña. [NOMBRE Y APELLIDOS]

b.- Testigos como otros responsables del centro que le trasladaron lo que ocurría al médico y el/la querellado/a se negó a actuar. [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

c.- Testifical del director médico del centro para que declare acerca de la obligación de actuar del/de la querellado/a en ese momento y sus obligaciones como médico en ese centro respecto a lo que requería el/la paciente.

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

a.- Pericial médica acerca del estado del/de la paciente en ese momento y que a raíz de la negativa del/de la querellado/a se derivó un grave riesgo para la salud del paciente.

b.- Pericial psicológica del daño moral sufrido por el/la paciente y familiares por los hechos.

[OPCIONAL — incluir si procede]

.- Documental: respecto a la enfermedad del paciente, su historial clínico para acreditar el grave riesgo de su omisión por el querellado.

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias complementarias)

SEGUNDO OTROSÍ DIGO: Se proponen, además, como diligencias complementarias para su práctica en la audiencia preliminar, y que no son reiteración de las que han sido practicadas con anterioridad, las siguientes:

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
