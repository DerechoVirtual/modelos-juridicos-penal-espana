---
name: abogado-intervenir-videoconferencia-juicio-penal-422
description: "Redacta el escrito «Abogado: intervenir por videoconferencia en juicio penal telemático (hasta el 19 de marzo de 2024)» (formulario 422 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abogado: intervenir por videoconferencia en juicio penal telemático (hasta el 19 de marzo de 2024)

> Formulario 0422 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- La intervención telemática del acusado se rige por el art. 258 bis.2 LECrim (desde el 20-3-2024) y no por el art. 14.2 Ley 3/2020: es necesaria su presencia física en juicios por delito grave y de jurado, y si reside en la demarcación del órgano debe comparecer físicamente salvo causa justificada o fuerza mayor.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (3 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- acusación particular / defensa
- Juzgado / Sala
- el Tribunal / la Sala

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Aplicable hasta el 20 de junio de 2021 y si el que presenta el escrito es el defensor del acusado)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 731 bis LECRIM
- art. 229 LOPJ
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

### Formulario 0422 · Abogado: intervenir por videoconferencia en juicio penal telemático (hasta el 19 de marzo de 2024)

- Año del modelo: 2020
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (1); 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Avisos de la revisión: La intervención telemática del acusado se rige por el art. 258 bis.2 LECrim (desde el 20-3-2024) y no por el art. 14.2 Ley 3/2020: es necesaria su presencia física en juicios por delito grave y de jurado, y si reside en la demarcación del órgano debe comparecer físicamente salvo causa justificada o fuerza mayor.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el abogado de la acusación particular o de la defensa, solicita intervenir en el juicio oral por videoconferencia desde su despacho profesional, solicitando se habilite la conexión personalizada y llevar a cabo una prueba técnica previa

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la sección penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la [ELEGIR: acusación particular / defensa] en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] en el procedimiento nº [Nº DE PROCEDIMIENTO] que se sigue en este [ELEGIR: Juzgado / Sala] por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS], ante [ELEGIR: el Tribunal / la Sala] comparezco y, como más procedente sea en derecho, DIGO:

El día [FECHA] va a tener lugar el juicio señalado por dicho delito en el que somos parte.

La petición que se insta por medio del presente escrito va dirigida a postular que la presencia en el juicio telemático se lleve a cabo por este letrado/a desde su despacho profesional y no desde la sede donde se seguirá el juicio, en base a las siguientes

ALEGACIONES

PRIMERA.- En la GUÍA PARA LA CELEBRACIÓN DE ACTUACIONES JUDICIALES TELEMÁTICAS del CGPJ en el punto 1.2.2 se recoge, bajo la rúbrica Actuaciones externas con intervención de ciudadanos que:

"Dentro de esta categoría se incluiría la celebración de juicios en los que deban practicarse pruebas con intervención personal -interrogatorios de parte, testificales, intervención de peritos-, práctica de pruebas en procedimientos que no impongan la unidad de acto y otros actos procesales similares.

Cuando, por razones derivadas de la situación de emergencia sanitaria, se estime conveniente la celebración telemática de actos procesales, se considera que lo más adecuado sería intercalar, en la agenda del órgano jurisdiccional y en la medida de lo posible, actuaciones presenciales y telemáticas, reservando las actuaciones telemáticas a los actos procesales que se considere adecuado, en atención a las circunstancias que concurran, como el número limitado de intervinientes, corta duración previsible de la vista o juicio, menor complejidad previsible de los interrogatorios o la ubicación distante de los domicilios de las personas que hubiesen de intervenir.

La decisión de celebración de un juicio de manera presencial no excluye la posibilidad de que determinadas actuaciones procesales en el contexto de ese juicio se lleven a cabo de manera telemática, para evitar traslados inconvenientes o para mejor aprovechamiento de los recursos públicos -declaración de peritos de organismos públicos (Instituto Nacional de Toxicología, clínicas médico forenses), miembros de cuerpos policiales trasladados de localidad, testigos enfermos...-, como se ha venido haciendo hasta ahora en la práctica diaria de juzgados y tribunales, pero respetando las pautas establecidas en la presente guía en cuanto a la forma de celebración de esos concretos actos procesales telemáticos."

Y, sobre todo, el punto nº 49 de esta guía nos habilita para la petición que deducimos, en tanto en cuanto que:

"49. Los miembros del Ministerio Fiscal, abogados, procuradores y graduados sociales podrían intervenir desde sus dependencias oficiales o despachos profesionales cuando no sea requerida su presencia física por el órgano judicial. Podrán hacerse acompañar de las partes que no hayan de intervenir en el acto o cuya intervención se limite a prestar un consentimiento o cualquier otro acto personalísimo diferente a su participación en la práctica de la prueba."

Este punto nos habilita para la viabilidad de la medida que estamos solicitando en tanto en cuanto, a la vista de la celebración telemática, esta parte entiende que no hay inconveniente en que su presencia se habilite en el despacho de quien suscribe. (1)

[OPCIONAL — incluir si procede]

(Aplicable hasta el 20 de junio de 2021 y si el que presenta el escrito es el defensor del acusado)

Dado que el/la acusado/a va a intervenir también telemáticamente por ser la pena instada inferior a dos años, conforme al artículo 14.2 de la L 3/2020, de 18 de septiembre [NOTA DE REVISIÓN: El art. 14 Ley 3/2020 solo rigió hasta el 20-6-2021. Desde el 20-3-2024 se aplica el art. 258 bis.2 LECrim: presencia física del acusado en juicios por delito grave y de jurado y, en delito menos grave con pena superior a dos años de prisión, cuando lo pidan él o su letrado o lo estime necesario el tribunal. Fuente: Ley 3/2020, BOE-A-2020-10923, art. 14; LECrim, BOE-A-1882-6036, art. 258 bis.2.], de medidas procesales y organizativas para hacer frente al COVID-19 en el ámbito de la Administración de Justicia, se solicita que, en cualquier momento en el que interese hablar con el/la acusado/a por ser su letrado defensor, se pueda suspender puntualmente el juicio para realizar cualquier consulta para un mejor ejercicio del derecho de defensa.

SEGUNDA.- Es cierto que en la guía antes citada se expone que la declaración telemática puede llevarse a cabo en las dependencias judiciales en otra sede distinta al lugar donde se sigue el juicio, pero el riesgo de contagio del virus y el buen funcionamiento técnico de los sistemas informáticos nos permite instar que nuestra intervención lo sea desde nuestra sede profesional en nuestro despacho, por lo que se interesa se habilite la conexión personalizada para que desde el ordenador de nuestro despacho pueda llevarse a cabo la conexión con clave habilitada.

En su caso, se rogaría si se puede llevar a efecto una prueba técnica de contacto el día antes para verificar el funcionamiento del sistema.

TERCERA.- Se interesa, de igual modo, a ser posible, que mi cliente pueda declarar también desde este punto para evitar problemas con otra conexión adicional, garantizando que entrará en mi despacho cuando sea llamado a comparecer por la autoridad judicial, permaneciendo fuera del mismo mientras tanto.

Es por ello, por lo que se interesa que, en nuestra asistencia e intervención como letrado/a para el juicio señalado para el día [FECHA], se habilite la forma de acceso al juicio telemático facilitando la clave de acceso al sistema informático por plataforma digital para poder intervenir.

Por todo ello,

SUPLICO AL TRIBUNAL

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Véase la STS 331/2019 de 27 de junio 2019, Rec. 1376/2018 que ha validado el uso de la videoconferencia en juicios.

Véanse también arts. 731 bis LECRIM Y 777.2 LECRIM, art. 229 LOPJ, y el Estatuto de la Corte Penal Internacional aprobado en Roma el 17 de julio de 1998 e Instrucción 3/2002 de la Fiscalía General del Estado.

Señala la doctrina que la videoconferencia no es más que un instrumento técnico que permite que la prueba acceda al proceso, una modalidad de práctica de la prueba, de modo que será el medio de prueba de que se trate, y de acuerdo con sus propias reglas, el que deberá ser analizado en cuanto a las garantías que deben concurrir en su práctica. Y puede asegurarse que la utilización de la videoconferencia y de los demás medios técnicos que establece el art. 230 de la LOPJ no es una posibilidad facultativa o discrecional a disposición del juez o tribunal, sino un medio exigible ante el Tribunal y constitucionalmente digno de protección.

Además, incide la doctrina en que se respetan los principios del proceso penal de inmediación, publicidad, oralidad, concentración y contradicción.

================================================================================
