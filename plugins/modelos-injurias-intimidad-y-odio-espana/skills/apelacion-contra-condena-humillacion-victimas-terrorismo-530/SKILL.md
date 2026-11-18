---
name: apelacion-contra-condena-humillacion-victimas-terrorismo-530
description: "Redacta el escrito «Apelación contra la condena por humillación a víctimas del terrorismo por internet» (formulario 530 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por humillación a víctimas del terrorismo por internet

> Formulario 0530 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] FECHA (3 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (6), que [ELEGIR…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental consistente en aportación de:.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 578 CP
- artículo 578 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- artículos 572 a 577 CP

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

### Formulario 0530 · Apelación contra la condena por humillación a víctimas del terrorismo por internet

- Año del modelo: 2018
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (6); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la condena por delito de humillación de víctimas del terrorismo por internet, del art. 578 CP, alegando que no ha quedado acreditada la autoría del recurrente y que no ha existido tal humillación y solicitando la práctica de nuevas pruebas.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito del artículo 578 CP (2), ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (3) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (4)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se le condena, ya que los hechos descritos son absolutamente inciertos en cuanto a la autoría del/de la recurrente, ya que no consta acreditado que ese acceso al ordenador fuera por el/la acusado/a, ya que se trata de un piso compartido por varias personas y, por ello, la autoría del delito no está acreditada. Al mismo tiempo, se pone en duda que haya sido el ordenador de su inmueble el lugar de acceso, ya que es posible técnicamente la derivación a éste desde otro inmueble, no habiéndose llevado a cabo labor investigadora alguna que pudiera descubrir si la IP del ordenador fue pirateada desde otro punto. De suyo, de la pericial propuesta por la defensa se puso en duda la de la acusación y ello evidencia que no existe prueba de cargo que permita enervar la presunción de inocencia. (5)

Por otro lado, en cualquier caso, el tipo penal del art. 578 CP exige un acto objetivable de humillación a las víctimas y las expresiones que constan probadas no lo constituyen. Al examinar los mensajes que ahora se enjuician destaca, en primer lugar, que no contienen ningún comentario ácido contra la/s víctima/s del atentado ni expresan frases o comentarios hirientes, lacerantes o ultrajantes contra su persona o cualquier aspecto concreto de su vida pública o privada. Simplemente es objeto de mofa o de sarcasmo la forma en que se produjo el atentado (Tribunal Supremo, Sala Segunda, de lo Penal, Sentencia 334/2018, de 4 de Julio, Rec. 2193/2017).

En su virtud,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias y por interpuesto en tiempo y forma el presente RECURSO DE APELACIÓN contra la sentencia recaída en los precitados autos, lo admita, y tras los trámites procesales correspondientes, remita las actuaciones a la Audiencia Provincial para que, tras la celebración de la vista, resuelva con arreglo a las pretensiones de esta parte.

Es justicia que pido en [LUGAR], a [FECHA].

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (6), que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental consistente en aportación de:.

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

SEGUNDOOTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(2) En el art. 578 CP se prevén dos tipos de conductas:

1.- Enaltecimiento o la justificación públicos de los delitos comprendidos en los artículos 572 a 577 CP o de quienes hayan participado en su ejecución.
2.- La realización de actos que entrañen descrédito, menosprecio o humillación de las víctimas de los delitos terroristas o de sus familiares.

Y al objeto del ciberdelito, una agravación en el apartado segundo si se lleva a cabo por Internet. Sobre esta modalidad de delito cometido por redes sociales existe una importante doctrina de la Sala Segunda del Tribunal Supremo que trata de delimitar claramente el delito.

STS 378/2017, de 25 de Mayo, rec. 8/2017: el tipo exige formalmente una actuación del sujeto que suponga justificar delitos de terrorismo o enaltecer a los que hayan participado en ellos.

STS 706/2017, de 21 de Octubre, rec. 514/2017: la mera reproducción de imágenes y el "retuiteo" con difusión pública, aunque hubieran sido tomadas por un tercero, constituyen delito del art. 578 CP. El tipo penal no exige que el acusado asuma como propio, razone o argumente la imagen y su mensaje, o que los haya creado, sino que basta que disponga de ellos y les de publicidad. La expansión del mensaje posibilita que terceras personas se percaten de que están enalteciendo la trayectoria personal y los "méritos" de alguien cuya fama procede de los actos terroristas ejecutados.

STS 812/2011, de 21 de Julio, rec. 46/2011: distinción con la apología del terrorismo.

STS 334/2018, de 4 de Julio, rec. 2193/2017: el conjunto de los mensajes analizados no traspasan los límites para ser calificados como delito de humillación a las víctimas del terrorismo. Límites fronterizos entre la vía penal y la civil. Necesidad de que se adopten medidas organizativas en los prestadores de servicio para cortar la difusión inmediata de tales expresiones.

STS 95/2018, de 26 de Febrero, Rec. 979/2017.

STS 4/2017, de 18 de Enero, rec. 1619/2016: "Tuits" publicados en la cuenta de famoso cantante-letrista de rap metal.

(3) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(4) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(5) Es importante la pericial informática en estos casos, dado que puede el querellado impugnar la prueba digital. En casos de impugnación de prueba digital es carga de la prueba del denunciante/querellante comprobar la veracidad de su contenido por pericial informática, por lo que o bien se acompaña a la querella la misma, o se propone la pericial judicial, o bien una vez se haya impugnado por el denunciado/querellado es cuando puede proponerse la práctica de la pericial informática, ya que sin esta carece de valor probatorio su aportación, si es impugnada por el investigado.

(6) Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013, de 31 de enero, rec. 22/2013 y STS 32/2012, de 25 de enero, rec. 932/2011.

================================================================================
