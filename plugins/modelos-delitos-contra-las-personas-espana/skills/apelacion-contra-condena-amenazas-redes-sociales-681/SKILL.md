---
name: apelacion-contra-condena-amenazas-redes-sociales-681
description: "Redacta el escrito «Apelación contra la condena por amenazas en redes sociales» (formulario 681 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por amenazas en redes sociales

> Formulario 0681 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] DELITO
- [ ] FECHA DE LA SENTENCIA
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…esan como hechos probados los siguientes»; «… de la sentencia es del tenor siguiente:»; «…ar con el/la acusado/a por la red social»; «…versación que tuvieron por la red social»

## Elecciones que hay que hacer

- favorable / desfavorable

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Del/De la testigo D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 169 CP
- art. 169.1 del CP
- art. 173.1 del CP

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

### Formulario 0681 · Apelación contra la condena por amenazas en redes sociales

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 16 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (FECHA DE LA SENTENCIA)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso presentado por el condenado en un procedimiento ante el Tribunal del Jurado por delito de amenazas del art. 169 CP, agravadas por cometerse a través de mensajes enviados por alguna red social, en base a error en la apreciación de la prueba, por no haber valorado las pruebas presentadas por el acusado.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

Al/A la Magistrado/a Presidente/a del Tribunal del Jurado de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a, actuando en nombre y representación del/de la condenado/a D./Dña. [NOMBRE Y APELLIDOS] en el juicio de la LOTJ número [NÚMERO] sobre delito del art. 169 CP (1), ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en para ante la Sala de lo Civil y Penal del TSJ de [LOCALIDAD], conforme a lo prevenido en el artículo 846 bis a de la Ley de Enjuiciamiento Criminal.

ANTECEDENTES

PRIMERO.- En el acta de la votación de los/as Jurados de fecha [FECHA] se contiene el veredicto donde se expresan como hechos probados los siguientes [COMPLETAR].

SEGUNDO.- El veredicto considera al/a la acusado/a culpable del delito de [DELITO], expresando su criterio [ELEGIR: favorable / desfavorable] a la remisión condicional de la pena que se impusiese y también sobre la petición del indulto en la sentencia.

TERCERO.- En el veredicto los/as Jurados han expresado como elementos de convicción para hacer dicha declaración de culpabilidad los siguientes:

CUARTO.- El fallo de la sentencia es del tenor siguiente: [COMPLETAR].

MOTIVOS

ÚNICO.-

Al amparo del artículo 846 bis c de la Ley de Enjuiciamiento Criminal, letra e), se ha vulnerado el derecho a la presunción de inocencia porque, atendida la prueba practicada en el juicio, carece de toda base razonable la condena impuesta.

Y en este caso esto ocurre, ya que en el juicio quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se le condena, siendo errónea la declaración de hechos probados, ya que fue el/la querellante, quien insistió en iniciar la comunicación al contactar con el/la acusado/a por la red social [COMPLETAR] e incluso concertar una cita con él/ella, como consta en la transcripción de la conversación que tuvieron por la red social [COMPLETAR] siendo objetivo de el/la querellante contraer matrimonio con el/la acusado/a, a lo que se negaba éste/a de forma reiterada, llegando a manifestarle que si no dejaba de enviarle mensajes daría cuenta a la policía. Se ha tratado de una situación de acoso que ha sufrido el/la acusado/a por el/la querellante de la que no tenía otra forma de salir que enviándole un mensaje para que le dejara en paz y no prosiguiera con su acto de acoso. Y ello se ha acreditado por la declaración de el/la recurrente con plena convicción, rogando se proceda al visionado del CD de la grabación del juicio, ya que no se han valorado las siguientes declaraciones:

Del/De la acusado/a D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Del/De la testigo D./Dña. [NOMBRE Y APELLIDOS]

No existe en la sentencia motivación alguna acerca de las causas y alegaciones expuestas por el/la ahora recurrente, lo que evidencia la necesidad de la revocación de la sentencia condenatoria, ya que solo se han valorado las pruebas propuestas por la acusación y no por la defensa.

En su virtud,

SUPLICO AL/A LA MAGISTRADO/A PRESIDENTE/A DEL TRIBUNAL DEL JURADO:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación contra la sentencia de fecha [FECHA DE LA SENTENCIA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado al Tribunal Superior de Justicia, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

OTROSÍ DIGO: Que designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO AL/A LA MAGISTRADO/A PRESIDENTE/A DEL TRIBUNAL DEL JURADO: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) El delito de amenazas (STS 342/2013 de 17 de abril, rec. 1461/2012) conlleva:

a) Una conducta del agente constituida por expresiones o acto idóneos para violentar el ánimo del sujeto pasivo, intimidándole con la conminación de un mal injusto, determinado y posible,
b) Que la expresión de dicho propósito por parte del agente sea seria, firme y creíble, atendiendo a las circunstancias concurrentes; y
c) Que estas mismas circunstancias, subjetivas y objetivas, doten a la conducta de la entidad suficiente como para merecer una contundente repulsa social, que fundamente razonablemente el juicio de antijuridicidad de la acción y su calificación como delictiva (cfr. por todas, SSTS 264/2009, 12 de marzo, rec. 1018/2008, 259/2006, 6 de marzo, rec. 1566/2005, 557/2007, 21 de junio, rec. 171/2007 y 268/1999, 26 de febrero, rec. 613/1998).

Si, además de la amenaza, se atentara contra la integridad moral el TS apunta que la condena por un delito de amenazas graves del art. 169.1 del CP es perfectamente compatible con el delito contra la integridad moral del art. 173.1 del CP. Estaremos, en definitiva, ante un concurso real de delitos, no ante un concurso aparente de normas.

Según criterio jurisprudencial "el delito de amenazas se comete por el anuncio consciente de un mal futuro, injusto, determinado y posible, con el único propósito de crear una intranquilidad de ánimo, inquietud o zozobra en el amenazado, pero sin la intención de dañar materialmente al sujeto mismo" (STS. 593/2003, 16 de abril, rec. 483/2002).

(2) Plazo de interposición: dentro de los 10 días siguientes a la última notificación de la sentencia.

Si no se apela en dicho plazo, puede hacerse en el trámite de impugnación, pero queda supeditado a que el apelante principal mantenga el suyo.

================================================================================
