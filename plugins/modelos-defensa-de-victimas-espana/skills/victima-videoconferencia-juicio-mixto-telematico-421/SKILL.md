---
name: victima-videoconferencia-juicio-mixto-telematico-421
description: "Redacta el escrito «Víctima: videoconferencia en juicio mixto telemático-presencial (hasta el 19 de marzo de 2024)» (formulario 421 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima: videoconferencia en juicio mixto telemático-presencial (hasta el 19 de marzo de 2024)

> Formulario 0421 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- La fundamentación en el art. 14 Ley 3/2020 está agotada desde el 21-6-2021; la declaración telemática de víctimas de violencia de género o sexual, trata, menores o con discapacidad se garantiza hoy por el art. 258 bis.3.a) LECrim y el art. 137 bis.3 LEC (RDL 6/2023, desde el 20-3-2024).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…entado/a. Dada la gravedad de los hechos»

## Elecciones que hay que hacer

- el Tribunal / la Sala

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Aplicable hasta el 20 de junio de 2021 inclusive)…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 5 de la Ley 4/2015
- art. 25.2 Ley 4/2015
- art. 229 LOPJ
- art. 731 bis LECRIM
- art. 777.2 LECRIM
- art. 230 de la LOPJ

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

### Formulario 0421 · Víctima: videoconferencia en juicio mixto telemático-presencial (hasta el 19 de marzo de 2024)

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (1); 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Avisos de la revisión: La fundamentación en el art. 14 Ley 3/2020 está agotada desde el 21-6-2021; la declaración telemática de víctimas de violencia de género o sexual, trata, menores o con discapacidad se garantiza hoy por el art. 258 bis.3.a) LECrim y el art. 137 bis.3 LEC (RDL 6/2023, desde el 20-3-2024).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular solicita que la víctima, llamada a declarar, pueda hacer su declaración por videoconferencia desde su domicilio o, en su defecto, desde el lugar en el que intervenga la acusación particular por medio telemático, solicitando se habilite conexión personalizada.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la sección penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de ejercitando la acusación particular en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] en el procedimiento nº [Nº DE PROCEDIMIENTO] que se sigue en este juzgado por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS] ante [ELEGIR: el Tribunal / la Sala] comparezco y, como más procedente sea en derecho, DIGO:

El día [FECHA] va a tener lugar el juicio señalado por dicho delito en el que aparece citado/a a declarar mi representado/a.

Dada la gravedad de los hechos [COMPLETAR] y el derecho de mi representado/a a no sufrir una victimización secundaria, es por lo que se presenta este escrito por el que dado que el juicio se desarrollará por vía telemática mixto presencial con presencia de el/la acusado/a en la sede del órgano judicial, se interesa que la declaración de mi representado/a lo sea por conexión en plataforma digital que se utilice en el juicio telemático, basado en los siguientes

ALEGACIONES

PRIMERA.- Señala la Ley 4/2015, de 27 de abril, del Estatuto de la víctima:

En el art. 5 de la Ley 4/2015, de 27 de abril:

"1. Toda víctima tiene derecho, desde el primer contacto con las autoridades y funcionarios, incluyendo el momento previo a la presentación de la denuncia, a recibir, sin retrasos innecesarios, información adaptada a sus circunstancias y condiciones personales y a la naturaleza del delito cometido y de los daños y perjuicios sufridos, sobre los siguientes extremos:
a) Medidas de asistencia y apoyo disponibles, sean médicas, psicológicas o materiales"

En el art. 25.2 Ley 4/2015, de 27 de abril:

"Durante la fase de enjuiciamiento podrán ser adoptadas, conforme a lo dispuesto en la Ley de Enjuiciamiento Criminal, las siguientes medidas para la protección de las víctimas:

a) Medidas que eviten el contacto visual entre la víctima y el supuesto autor de los hechos, incluso durante la práctica de la prueba, para lo cual podrá hacerse uso de tecnologías de la comunicación.
b) Medidas para garantizar que la víctima pueda ser oída sin estar presente en la sala de vistas, mediante la utilización de tecnologías de la comunicación adecuadas."

SEGUNDA.- El art. 229 LOPJ prevé, desde su reforma operada por la LO 19/2003, de 23 de diciembre [NOTA DE REVISIÓN: La LO 19/2003, de modificación de la LOPJ, es de 23 de diciembre de 2003 (BOE de 26-12-2003). El art. 229.3 LOPJ tiene hoy la redacción de la LO 1/2025. Fuente: LO 19/2003, BOE-A-2003-23644; LOPJ, BOE-A-1985-12666, art. 229.], la posibilidad de realización telemática de actuaciones procesales -concretamente alude a declaraciones, interrogatorios, testimonios, careos, exploraciones, informes, ratificación de los periciales y vistas-. Escasos días antes -BOE de 3 de octubre- se había publicado la Declaración de aplicación provisional del convenio de asistencia judicial en materia penal entre los Estados miembros de la UE de 29 de mayo de 2000, cuyo artículo 10 prevé la denominada «audición por videoconferencia» de testigos y peritos que se encuentren en el territorio de un Estado miembro.

[OPCIONAL — incluir si procede]

(Aplicable hasta el 20 de junio de 2021 inclusive)

Más recientemente, el artículo 14 de la L 3/2020, de 18 de septiembre [NOTA DE REVISIÓN: Precepto temporal que solo rigió hasta el 20-6-2021. Hoy la presencia telemática se rige por el art. 258 bis LECrim (RDL 6/2023, vigente desde el 20-3-2024). Fuente: Ley 3/2020, BOE-A-2020-10923, art. 14; LECrim, BOE-A-1882-6036, art. 258 bis.], ha previsto que la forma telemática sea el modo preferente de celebración de las actuaciones judiciales hasta el 20 de junio de 2021.

TERCERA.- El art. 731 bis LECRIM señala que:

"El Tribunal, de oficio o a instancia de parte, por razones de utilidad, seguridad o de orden público, así como en aquellos supuestos en que la comparecencia de quien haya de intervenir en cualquier tipo de procedimiento penal como imputado, testigo, perito, o en otra condición resulte gravosa o perjudicial, podrá acordar que su actuación se realice a través de videoconferencia u otro sistema similar que permita la comunicación bidireccional y simultánea de la imagen y sonido, de acuerdo con lo dispuesto en el apartado 3 del art. 229 LOPJ ".

CUARTA.- En la GUÍA PARA LA CELEBRACIÓN DE ACTUACIONES JUDICIALES TELEMÁTICAS del CGPJ en el punto 1.2.2 se recoge, bajo la rúbrica Actuaciones externas con intervención de ciudadanos que:

"Dentro de esta categoría se incluiría la celebración de juicios en los que deban practicarse pruebas con intervención personal -interrogatorios de parte, testificales, intervención de peritos-, práctica de pruebas en procedimientos que no impongan la unidad de acto y otros actos procesales similares.

Cuando, por razones derivadas de la situación de emergencia sanitaria, se estime conveniente la celebración telemática de actos procesales, se considera que lo más adecuado sería intercalar, en la agenda del órgano jurisdiccional y en la medida de lo posible, actuaciones presenciales y telemáticas, reservando las actuaciones telemáticas a los actos procesales que se considere adecuado, en atención a las circunstancias que concurran, como el número limitado de intervinientes, corta duración previsible de la vista o juicio, menor complejidad previsible de los interrogatorios o la ubicación distante de los domicilios de las personas que hubiesen de intervenir.

La decisión de celebración de un juicio de manera presencial no excluye la posibilidad de que determinadas actuaciones procesales en el contexto de ese juicio se lleven a cabo de manera telemática, para evitar traslados inconvenientes o para mejor aprovechamiento de los recursos públicos -declaración de peritos de organismos públicos (Instituto Nacional de Toxicología, clínicas médico forenses), miembros de cuerpos policiales trasladados de localidad, testigos enfermos...-, como se ha venido haciendo hasta ahora en la práctica diaria de juzgados y tribunales, pero respetando las pautas establecidas en la presente guía en cuanto a la forma de celebración de esos concretos actos procesales telemáticos."

QUINTA.- La declaración telemática es cierto que en la guía antes citada se expone que puede llevarse a cabo en las dependencias judiciales en otra sede distinta al lugar donde se sigue el juicio, pero la victimización secundaria seguiría existiendo, por el riesgo de contagio de COVID-19 y por el regreso de la víctima a la sede judicial, por lo que se interesa se habilite la conexión personalizada para que, desde el ordenador del domicilio de la víctima, pueda llevarse a cabo la conexión con clave habilitada.

En su defecto, se interesa que la víctima pueda declarar desde el lugar en el que intervenga la acusación particular por medio telemático.

SEXTA.- La STS 331/2019 de 27 de junio 2019, Rec. 1376/2018 ha validado el uso de la videoconferencia en juicios para las víctimas. (1)

Es por ello, por lo que se interesa que en la declaración prevista como testigo de mi representado/a para el juicio señalado para el día [FECHA], a realizar de forma mixta telemática- presencial, se habilite la forma de acceso al juicio telemático, facilitando la clave de acceso al sistema informático por plataforma digital para poder intervenir en la declaración como testigo.

Por todo ello,

SUPLICO AL TRIBUNAL

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Véase también art. 777.2 LECRIM y el Estatuto de la Corte Penal Internacional aprobado en Roma el 17 de julio de 1998 e Instrucción 3/2002 de la Fiscalía General del Estado.

Señala la doctrina que la videoconferencia no es más que un instrumento técnico que permite que la prueba acceda al proceso, una modalidad de práctica de la prueba, de modo que será el medio de prueba de que se trate, y de acuerdo con sus propias reglas, el que deberá ser analizado en cuanto a las garantías que deben concurrir en su práctica. Y puede asegurarse que la utilización de la videoconferencia y de los demás medios técnicos que establece el art. 230 de la LOPJ no es una posibilidad facultativa o discrecional a disposición del juez o tribunal, sino un medio exigible ante el Tribunal y constitucionalmente digno de protección.

Además, incide la doctrina en que se respetan los principios del proceso penal de inmediación, publicidad, oralidad, concentración y contradicción.

================================================================================
