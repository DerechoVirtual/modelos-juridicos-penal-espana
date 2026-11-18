---
name: apelacion-contra-condena-amenazas-informaticas-533
description: "Redacta el escrito «Apelación contra la condena por amenazas informáticas» (formulario 533 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por amenazas informáticas

> Formulario 0533 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…esan como hechos probados los siguientes»; «…laración de culpabilidad los siguientes:»; «… de la sentencia es del tenor siguiente:»; «… el apelante principal mantenga el suyo.»

## Elecciones que hay que hacer

- favorable / desfavorable

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 846 bis a) de la Ley de Enjuiciamiento Criminal
- art. 169 CP

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

### Formulario 0533 · Apelación contra la condena por amenazas informáticas

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 13 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la condena en procedimiento ante el Tribunal del Jurado por delito de amenazas por email condicionales del art. 169.1º pfo. 2 CP, alegando que no ha quedado acreditado el envío del correo electrónico amenazante por el acusado.

Al Magistrado Presidente del Tribunal del Jurado de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio de la LOTJ número [NÚMERO] sobre delito del artículo 169.1º CP párrafo 2º (1), comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación, conforme a lo prevenido en el artículo 846 bis a) de la Ley de Enjuiciamiento Criminal,

ANTECEDENTES

PRIMERO.- En el acta de la votación de los/as Jurados de fecha [FECHA] se contiene el veredicto donde se expresan como hechos probados los siguientes [COMPLETAR].

SEGUNDO.- El veredicto considera al/a la acusado/a culpable del delito de [DELITO], expresando su criterio [ELEGIR: favorable / desfavorable] a la remisión condicional de la pena que se impusiese y también sobre la petición del indulto en la sentencia.

TERCERO.- En el veredicto los/as Jurados han expresado como elementos de convicción para hacer dicha declaración de culpabilidad los siguientes: [COMPLETAR].

CUARTO.- El fallo de la sentencia es del tenor siguiente: [COMPLETAR].

MOTIVOS

ÚNICO.-

Al amparo del artículo 846 bis c de la Ley de Enjuiciamiento Criminal, letra e), se ha vulnerado el derecho a la presunción de inocencia porque, atendida la prueba practicada en el juicio, carece de toda base razonable la condena impuesta.

Y en este caso esto ocurre, ya que en el juicio quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se le condena, ya que los hechos que describe el/la perjudicado/a son falsos, ya que en modo alguno se envió ese mensaje, como acredita la pericial informática (3) que se aportó por esta parte y declaró el/la perito que lo elaboró. De suyo, mi representado/a ofreció a los agentes policiales voluntariamente el acceso a su ordenador y el material que se ha localizado por los agentes policiales no contenía el mensaje.

En su virtud,

SUPLICO AL/A LA MAGISTRADO/A PRESIDENTE/A DEL TRIBUNAL DEL JURADO:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La modalidad comisiva del art. 169 CP puede cometerse por medios informáticos, pudiendo llevarse a cabo por Whatsapp, correo electrónico, o los medios previstos en redes sociales mediante comunicación directa por uno de los sistemas de comunicación informática direccional entre partes y no público.

La modalidad de la amenaza informática está prevista de forma expresa, pero solo en el supuesto de amenazas condicionales del art. 169.1º pfo 2 CP, en cuyo caso supone una agravaciónel método utilizado para realizar la amenaza, distinguiendo la pena a imponer según se consiga o no el propósito, no existiendo una previsión especial de agravación para la amenaza informática no condicional.

En cualquier caso, la agravación existe cuando con ese método de llevar a cabo la amenaza se busque el anonimato, no cuando el receptor de la amenaza lo puede identificar con facilidad. Así lo señala el Tribunal Supremo, en STS 838/2016 de 4 de Noviembre, Rec. 537/2016.

(2) Plazo de interposición: dentro de los 10 días siguientes a la última notificación de la sentencia.

Si no se apela en dicho plazo, puede hacerse en el trámite de impugnación, pero queda supeditado a que el apelante principal mantenga el suyo.

[COMPLETAR]

(3) Es importante la pericial informática en estos casos, dado que puede el querellado impugnar la prueba digital. En casos de impugnación de prueba digital es carga de la prueba del denunciante/querellante comprobar la veracidad de su contenido por pericial informática, por lo que o bien se acompaña a la querella la misma, o se propone la pericial judicial, o bien una vez se haya impugnado por el denunciado/querellado es cuando puede proponerse la práctica de la pericial informática, ya que sin esta carece de valor probatorio su aportación, si es impugnada por el investigado.

================================================================================
