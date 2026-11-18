---
name: apelacion-contra-condena-estafa-informatica-vishing-491
description: "Redacta el escrito «Apelación contra la condena por estafa informática (vishing)» (formulario 491 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por estafa informática (vishing)

> Formulario 0491 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- OTRO SÍ 1º DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR: n…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- -D./Dña. [NOMBRE Y APELLIDOS]…
- 2.- Pericial: A cuyo fin deberá ser citado a través de la oficina judicial el siguiente perito:…
- 3.- Documental consistente en aportación de:…
- OTROSÍ 2º DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, desi…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0491 · Apelación contra la condena por estafa informática (vishing)

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 5 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito del condenado por delito de estafa informática (vishing) del art. 249.1 a) CP recurriendo la sentencia por error en la apreciación de la prueba, argumentando que no se ha probado suficientemente que el ordenador a través del cual se cometió la estafa le petenecía.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a, actuando en nombre y representación del/de la condenado/a D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito del art. 249.1 a) CP (1) ante este órgano judicial (2) comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (3) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial, en base a las siguientes.

ALEGACIONES (4)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el condenado ahora recurrente no hizo exactamente aquello por lo que se le condena, ya que los hechos que describe el denunciante son absolutamente inciertos en cuanto a la autoría del recurrente, ya que no consta acreditado que ese acceso al ordenador del perjudicado fuera por el/la acusado/a, en orden a recabar sus datos, puesto que se trata de un piso compartido por varias personas y, por ello, la autoría del delito no está acreditada. Al mismo tiempo, se pone en duda que haya sido el ordenador de su inmueble el lugar de acceso, ya que es posible técnicamente la derivación este desde otro inmueble, no habiéndose llevado a cabo labor investigadora alguna que pudiera descubrir si la IP del ordenador fuera pirateada desde otro punto. De suyo, de la pericial propuesta por la defensa se puso en duda la de la acusación y ello evidencia que no existe prueba de cargo que permita enervar la presunción de inocencia.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA]. recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

[OPCIONAL — incluir si procede]

OTRO SÍ 1º DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

2.- Pericial: A cuyo fin deberá ser citado a través de la oficina judicial el siguiente perito:

-D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

3.- Documental consistente en aportación de:

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

[OPCIONAL — incluir si procede]

OTROSÍ 2º DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Dentro de las estafas informáticas nos encontramos con el delito de estafa denominado VISHING, regulado hasta el 11 de enero de 2023 en el art. 248.2 a) y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP. Se trata de la unión de dos palabras en inglés, voice y ‘phising’. En este ciberdelito el atacante ofrece a la víctima un número de teléfono al que comunicarse en vez de un enlace a través del correo electrónico, como ocurre en el caso del ‘pishing’. En este delito se utiliza el VoIP (Voice over IP). Esta modalidad de estafa combina teléfono e internet.

El método consiste en marcar números de teléfono y cuando la víctima descuelga aparece un mensaje del grupo delictivo que parece que procede de una entidad financiera, ya que hacen uso de una Voz IP o voz automatizada que resulta creíble porque es muy similar a las utilizadas por los bancos.

Generalmente se le dice que su tarjeta de crédito está siendo utilizada fraudulentamente y que, por ello, es preciso actualizar la información personal, resolver un problema con una cuenta, o cualquier otro engaño similar.

Para resolver todas estas cuestiones, se facilita un número de teléfono específico al que llamar. Cuando lo hacen vuelve a sonar otro mensaje similar al de las voces automatizadas de los bancos del servicio telefónico de atención al cliente. Así, se solicita el número de cuenta, de tarjetas de crédito, su fecha de expiración, claves o nombre de usuarios que se utilizarán después para sacar el dinero de la cuenta de la víctima.

(2) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(3) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(4) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012, de 25 de enero, Rec. 932/2011.

================================================================================
