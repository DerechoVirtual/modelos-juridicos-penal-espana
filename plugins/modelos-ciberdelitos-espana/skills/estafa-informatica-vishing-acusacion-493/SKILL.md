---
name: estafa-informatica-vishing-acusacion-493
description: "Redacta el escrito «Estafa informática (vishing): acusación» (formulario 493 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (vishing): acusación

> Formulario 0493 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (3 veces)
- [ ] IMPORTE (2 veces)
- [ ] TELÉFONO
- [ ] NÚMERO (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…: CONCLUSIONES PRIMERA.- El/La acusado/a»; «…por parte de»; «…ido a un acceso indebido en la cuenta de»; «…del banco»; «…del Grupo de delincuencia tecnológica de»; «…abo. Informe de la compañía de teléfonos»; «…sobre las»; «…, identificando como titular del mismo a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Interrogatorio del acusador particular.…
- . Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que …
- D/Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial.…
- .- Documental, consistente en los extractos bancarios de las operaciones llevadas a cabo.…
- OTROSÍ DIGO SEGUNDO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la medida…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 249.1 a) CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 249.1 a) CP
- art. 22 del CP
- art. 48.3 CP
- art. 48.2 CP
- art. 48.1 y 57 CP
- art. 48 CP
- art. 57 CP
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

### Formulario 0493 · Estafa informática (vishing): acusación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 6 párrafos opcionales señalados; 26 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en un procedimiento abreviado calificando los hechos de delito de estafa informática del artículo 249.1 a) CP en la modalidad de vishing, que consiste en que el atacante, utilizando el VoIP (Voice over IP) realiza una llamada a la víctima diciéndole que su tarjeta de crédito está siendo utilizada fraudulentamente y para solucionarlo debe llamar a un teléfono y comunicar sus datos bancarios.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a [COMPLETAR] diseñó un sistema operativo mediante el cual una centralita enviaba llamadas aleatorias para que una vez contestada por el perjudicado se le interesaran sus datos bancarios mediante un sistema de voz automatizada. De esta manera con fecha [FECHA] por parte de [COMPLETAR] se recibió una de estas llamadas de teléfono y una voz de un sistema de llamadas automatizado hizo constar que se había procedido a un acceso indebido en la cuenta de [COMPLETAR] y que por ello debería proceder a llamar al número de teléfono de la entidad bancaria para facilitar los datos personales de acceso en la cuenta para poder bloquearla. Acto seguido llamó D./Dña. [NOMBRE Y APELLIDOS] al citado número de teléfono, confiando en que era del banco, y otra voz automatizada le pidió los datos de la cuenta. Dado el temor a que fuera cierto, y la apariencia de legalidad del proceso por el sistema típico de la banca utilizado de voz automatizada, se le dieron las claves. Al día siguiente, y tras consultar la cuenta, el perjudicado detecta que se había realizado una transferencia no autorizada por importe de [IMPORTE]... euros por parte del/de la acusado/a mediante el sistema operativo diseñado. Para ello, utilizó los números de teléfono [TELÉFONO] y la cuenta corriente nº [NÚMERO] del banco [COMPLETAR] diseñando el sistema mediante un ordenador ubicado en la calle

SEGUNDA.- Tales hechos son constitutivos del delito de estafa informática (vishing) del art. 249.1 a) CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer a el/la acusado/a por el delito del art. 249.1 a) CP la pena de [PENA]
prisión de seis meses a tres años, en su mitad superior si concurre una o dos agravantes genéricas
la superior en grado en su mitad inferior si concurren más de dos agravantes genéricas

Además, procede imponer la pena de prohibición de comunicación con la víctima, o con aquellos de sus familiares u otras personas que determine el juez prevista en el art. 48.3 CP, la pena de prohibición de aproximarse a la víctima o familiares u otras personas que determine el juez prevista en el art. 48.2 CP y la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. (3)

SEXTA.- Procede condenar al/a la acusado/a a que indemnice a la víctima por el importe de [IMPORTE] euros como cantidad sustraída.

Las costas deberán ser satisfechas por el/la acusado/a

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Interrogatorio del acusador particular.

[OPCIONAL — incluir si procede]

. Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados
judicialmente
mediante exhorto

D./Dña. [NOMBRE Y APELLIDOS] agentes del Grupo de delincuencia tecnológica de [COMPLETAR] intervinientes en la investigación.

D./Dña. [NOMBRE Y APELLIDOS] responsable de la entidad bancaria del perjudicado para que testifique sobre el sistema llevado a cabo en la cuenta del querellante y sus conocimientos sobre este tipo delictivo del vishing.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D/Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial.

Pericial informática judicial del ordenador donde se describe la operativa llevada a cabo por el/la acusado/a al acceder a los datos bancarios de el/la perjudicado/a.

Pericial de la brigada de delitos tecnológicos de la Policía Nacional.

[OPCIONAL — incluir si procede]

.- Documental, consistente en los extractos bancarios de las operaciones llevadas a cabo.

Informe de la compañía de teléfonos [COMPLETAR] sobre la llamada recibida por el/la querellante el día [FECHA] sobre las [COMPLETAR] Y las realizadas por el mismo al número [NÚMERO], identificando como titular del mismo a [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir si procede]

OTROSÍ DIGO SEGUNDO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la medida cautelar de alejamiento y prohibición de comunicación de los arts. 13 y 544 bis LECRIM.

Se interesa, además, se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. (5)

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

SUPLICO A LA SECCIÓN: Que adopte las medidas cautelares solicitadas y se comunique a esta parte.

Es Justicia que reitero en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Dentro de las estafas informáticas nos encontramos con el delito de estafa denominado VISHING, regulado hasta el 11 de enero de 2023 en el art. 248.2 a) y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP. Se trata de la unión de dos palabras en inglés, voice y ‘phising’. En este ciberdelito el atacante ofrece a la víctima un número de teléfono al que comunicarse en vez de un enlace a través del correo electrónico, como ocurre en el caso del ‘pishing’. En este delito se utiliza el VoIP (Voice over IP). Esta modalidad de estafa combina teléfono e internet.

El método consiste en marcar números de teléfono y cuando la víctima descuelga aparece un mensaje del grupo delictivo que parece que procede de una entidad financiera, ya que hacen uso de una Voz IP o voz automatizada que resulta creíble porque es muy similar a las utilizadas por los bancos.

Generalmente se le dice que su tarjeta de crédito está siendo utilizada fraudulentamente y que, por ello, es preciso actualizar la información personal, resolver un problema con una cuenta, o cualquier otro engaño similar.

Para resolver todas estas cuestiones, se facilita un número de teléfono específico al que llamar. Cuando lo hacen vuelve a sonar otro mensaje similar al de las voces automatizadas de los bancos del servicio telefónico de atención al cliente. Así, se solicita el número de cuenta, de tarjetas de crédito, su fecha de expiración, claves o nombre de usuarios que se utilizarán después para sacar el dinero de la cuenta de la víctima.

(3) En este caso, ante la inexistencia de una previsión de esta pena se ha optado por acudir al mecanismo de la "prohibición de acudir al lugar del delito" que se configura en este caso por medio de identificar el "lugar" con "internet", en cuyo caso se acuerda esta pena por la vía del art. 48 CP, en relación con el art. 57 CP.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

(5) La cautelar que se solicita tiene su base y razón de ser, no solo en la protección de los derechos del perjudicado por el delito, sino en aras a una protección general para evitar la reiteración delictiva de la comisión del ilícito penal por medio de las tecnologías de la comunicación y especialmente por el uso de internet a cualquier futuro perjudicado mientras se tramita la causa y hasta sentencia y su posible transformación en pena.

================================================================================
