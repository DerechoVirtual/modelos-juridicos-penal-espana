---
name: estafa-informatica-vishing-defensa-489
description: "Redacta el escrito «Estafa informática (vishing): defensa» (formulario 489 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (vishing): defensa

> Formulario 0489 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- judicialmente / mediante exhorto
- - / D. / Dña.

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1. Testifical: declaración de los testigos que se mencionan a continuación y que deberán ser citados [ELEGIR: …
- [ELEGIR: - / D. / Dña.].…
- .- (4)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) del CP
- artículo 249.1 a) CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 249.1 a) CP
- art. 784 LECRIM
- art. 777.2 LECrim
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

### Formulario 0489 · Estafa informática (vishing): defensa

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 párrafos opcionales señalados; 4 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado/a por un delito de estafa informática del art. 249.1 a) del CP en un procedimiento abreviado presenta sus conclusiones provisionales alegando que no ha quedado demostrado que sea él el autor de la estafa aportando pericial informática.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del artículo 249.1 a) CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa, ya que no consta acreditado que ese acceso a los datos bancarios de el/la querellante fuera por el/la acusado/a, ya que se trata de un piso compartido por varias personas y, por ello, la autoría del delito no está acreditada. Al mismo tiempo, se pone en duda que haya sido el ordenador de su inmueble el lugar de acceso, ya que es posible técnicamente la derivación a éste desde otro inmueble, no habiéndose llevado a cabo labor investigadora alguna que pudiera descubrir si la IP del ordenador fue pirateada desde otro punto.

SEGUNDA.- Los hechos no son constitutivos de un delito de estafa informática del art. 249.1 a) CP. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el/la acusado/ar particular y además los siguientes:

[OPCIONAL — incluir si procede]

1. Testifical: declaración de los testigos que se mencionan a continuación y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto], que declararán sobre la inexistencia de la conducta de la que se le acusa por su conocimiento personal.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

[ELEGIR: - / D. / Dña.].

[OPCIONAL — incluir si procede]

.- (4)

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original]

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Dentro de las estafas informáticas nos encontramos con el delito de estafa denominado VISHING, regulado hasta el 11 de enero de 2023 en el art. 248.2 a) y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP. Se trata de la unión de dos palabras en inglés, voice y ‘phising’. En este ciberdelito el atacante ofrece a la víctima un número de teléfono al que comunicarse en vez de un enlace a través del correo electrónico, como ocurre en el caso del ‘pishing’. En este delito se utiliza el VoIP (Voice over IP). Esta modalidad de estafa combina teléfono e internet.

El método consiste en marcar números de teléfono y cuando la víctima descuelga aparece un mensaje del grupo delictivo que parece que procede de una entidad financiera, ya que hacen uso de una Voz IP o voz automatizada que resulta creíble porque es muy similar a las utilizadas por los bancos.

Generalmente se le dice que su tarjeta de crédito está siendo utilizada fraudulentamente y que, por ello, es preciso actualizar la información personal, resolver un problema con una cuenta, o cualquier otro engaño similar.

Para resolver todas estas cuestiones, se facilita un número de teléfono específico al que llamar. Cuando lo hacen vuelve a sonar otro mensaje similar al de las voces automatizadas de los bancos del servicio telefónico de atención al cliente. Así, se solicita el número de cuenta, de tarjetas de crédito, su fecha de expiración, claves o nombre de usuarios que se utilizarán después para sacar el dinero de la cuenta de la víctima.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

(4) Puede simplemente plantearse la impugnación de la prueba digital si se aportó pero no se acompañó de pericial informática. Se incluye esta mención puesto que el Tribunal Supremo tiene declarado con respecto a la aportación de una prueba digital que, de impugnarse esta prueba, es preciso proponer y aportar prueba pericial que acredite ese contenido. (STS 300/2015, de 19 de mayo, Rec. 2387/2014)

Los informes periciales pueden aportarse por las partes personadas en el proceso durante la fase de instrucción, así como acompañarlos junto con el escrito de calificación provisional (en el proceso ordinario; artículo 656 LECRIM) o en el escrito de acusación y/o defensa (en el proceso abreviado; artículos 781 y 784 LECRIM). En el juicio de delito leve, las partes aportarán los informes periciales en el acto del juicio oral (artículos 966 y 969.2 LECRIM).

================================================================================
