---
name: lesiones-esterilizacion-discapacitada-calificacion-385
description: "Redacta el escrito «Lesiones por esterilización de discapacitada: calificación provisional de la defensa» (formulario 385 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones por esterilización de discapacitada: calificación provisional de la defensa

> Formulario 0385 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] PENA
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- el padre / la madre

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de los/as acusados/as que declararán en último lugar tras la práctica de la prueba.…
- .- Testifical de:…
- D./Dña. [NOMBRE Y APELLIDOS] profesional del centro hospitalario que tuvo conocimiento de lo ocurrido.…
- D./Dña. [NOMBRE Y APELLIDOS] familiar de la persona discapacitada.…
- .- Informe pericial médico acerca de la intervención llevada a cabo y sus consecuencias para la persona someti…
- .- Documental:…
- - Documental judicial por testimonio de particulares acerca de delitos de agresiones sexuales sufridos por la …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 149 del CP
- art. 149 CP
- artículo 652 de la Ley de Enjuiciamiento Criminal
- art. 14.3 CP
- art. 156 CP
- Ley Orgánica 2/2020

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

### Formulario 0385 · Lesiones por esterilización de discapacitada: calificación provisional de la defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 5 párrafos opcionales señalados; 10 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales en procedimiento común u ordinario negando que los hechos constituyan delito de lesiones del art. 149 del CP y, en su defecto, alegando error vencible de desconocimiento de que ya no era posible la esterilización de discapacitada por autorización judicial.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el procedimiento de sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], por el supuesto delito del art. 149 CP, comparezco ante la Sala y como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 652 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de calificación provisional del Fiscal y de la acusación particular y formulo escrito (1) con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que, por un lado, se entregó un escrito por [ELEGIR: el padre / la madre] de la discapacitada en la que existía una autorización judicial, o, al menos era su apariencia. Y, en su caso, se alega el error invencible de que se desconocía que ya no estaba permitido llevarlo a cabo ni por trámite judicial. Además, toda la situación fue promovida por [ELEGIR: el padre / la madre] de la discapacitada y con entrega de documentación de hechos de ataques sexuales sufridos por la víctima y la necesidad de evitar embarazados no deseados, lo cual dio pie a esa intervención en evitación de esas situaciones no deseadas.

SEGUNDA.- Niego las correlativas. Los hechos no son constitutivos de un delito del art. 149 CP. (2)

En su defecto, solicito se aplique el error vencible del art. 14.3 CP y la pena de [PENA] de prisión.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede, ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, sin declaración de responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio de los/as acusados/as que declararán en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical de:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] profesional del centro hospitalario que tuvo conocimiento de lo ocurrido.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] familiar de la persona discapacitada.

[OPCIONAL — incluir si procede]

.- Informe pericial médico acerca de la intervención llevada a cabo y sus consecuencias para la persona sometida a discapacidad.

[OPCIONAL — incluir si procede]

.- Documental:

-Respecto a escrito entregado para instar la intervención de esterilización, así como la solicitud de autorización judicial que entregó [ELEGIR: el padre / la madre] al autor de la intervención.
-Documental acreditativa de la discapacidad de la víctima.

[OPCIONAL — incluir si procede]

- Documental judicial por testimonio de particulares acerca de delitos de agresiones sexuales sufridos por la menor.

Por lo expuesto,

SUPLICO A LA SALA: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días hábiles desde que se recibe traslado de la causa.

(2) La Ley Orgánica 2/2020, de 16 de diciembre, de modificación del Código Penal para la erradicación de la esterilización forzada o no consentida de personas con discapacidad incapacitadas judicialmente reforma el art. 156 CP, prohibiendo el supuesto de que la esterilización de personas con discapacidad permanente o incapacitadas judicialmente pueda ser acordada por un Juez, por la vía que permitía el párrafo 2º del art. 156 CP, ya derogado.

Con ello, a partir de ahora, la consecuencia será que las operaciones de esterilización practicadas a incapaces constituirán, en todo caso, delito de lesiones, ya que no cabe llevarlas a cabo ni con autorización judicial.

Jurisprudencia de referencia (STS 145/2002 de 1 de febrero, Rec. 2091/2000) (STC 215/1994 de 14 de julio, Rec. 1415/1992) (SAP Madrid, 63/2000 de 4 de abril, Rec. 315/1998) (SAP Girona 235/2009 de 19 de junio, Rec. 14/2009) (Auto AP Álava, 21/2004 de 30 de marzo, Rec. 33/2004)

================================================================================
