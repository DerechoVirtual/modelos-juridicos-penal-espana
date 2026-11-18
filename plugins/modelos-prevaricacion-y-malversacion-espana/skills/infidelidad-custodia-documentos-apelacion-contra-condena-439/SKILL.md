---
name: infidelidad-custodia-documentos-apelacion-contra-condena-439
description: "Redacta el escrito «Infidelidad en la custodia de documentos: apelación contra la condena» (formulario 439 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infidelidad en la custodia de documentos: apelación contra la condena

> Formulario 0439 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] FECHA (5 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…esan como hechos probados los siguientes»; «…laración de culpabilidad los siguientes:»; «… de la sentencia es del tenor siguiente:»; «…l, ya que tratándose de un expediente de»; «…s preciso la incorporación del documento»; «…, ya que la norma»

## Elecciones que hay que hacer

- favorable / desfavorable

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 413 CP
- artículo 413 CP
- art. 24 CE

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

### Formulario 0439 · Infidelidad en la custodia de documentos: apelación contra la condena

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 16 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la sentencia de condena a un funcionario por delito de infidelidad en la custodia de documentos del art. 413 CP, alegando que no es obligatorio que el documento reclamado conste en un expediente concreto.

Al/A la Magistrado/a Presidente/a del Tribunal del Jurado de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio de la LOTJ número [NÚMERO] sobre delito del artículo 413 CP, comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (1) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 846 bis a de la Ley de Enjuiciamiento Criminal,

ANTECEDENTES

PRIMERO.- En el acta de la votación de los/as Jurados de fecha [FECHA] se contiene el veredicto donde se expresan como hechos probados los siguientes [COMPLETAR].

SEGUNDO.- El veredicto considera al/a la acusado/a culpable del delito de [DELITO], expresando su criterio [ELEGIR: favorable / desfavorable] a la remisión condicional de la pena que se impusiese y también sobre la petición del indulto en la sentencia.

TERCERO.- En el veredicto los/as Jurados han expresado como elementos de convicción para hacer dicha declaración de culpabilidad los siguientes: [COMPLETAR].

CUARTO.- El fallo de la sentencia es del tenor siguiente: [COMPLETAR].

MOTIVOS

ÚNICO.-

Al amparo del artículo 846 bis c de la Ley de Enjuiciamiento Criminal, letra b), la sentencia ha incurrido en infracción de precepto legal en la calificación jurídica de los hechos.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no ha cometido un ilícito penal, ya que tratándose de un expediente de [COMPLETAR] no es preciso la incorporación del documento [COMPLETAR], ya que la norma [COMPLETAR] no exige su constancia e incorporación. Por otro lado, este tipo penal exige una comisión estrictamente dolosa, y no culposa por lo que, incluso en el caso de que se tratara de una imprudencia el hecho quedaría impune y no sería delictivo, quedando su tratamiento en el ámbito puramente disciplinario.

Además, no se ha valorado la prueba de descargo expuesta y se ha hecho omisión absoluta en la sentencia con una absoluta falta de motivación de la prueba de descargo que se ha silenciado y provoca una auténtica indefensión material y una vulneración de la tutela judicial efectiva ex art. 24 CE. (2)

Se interesa, pues, la absolución.

En su virtud,

SUPLICO AL/A LA MAGISTRADO/A PRESIDENTE DEL TRIBUNAL DEL JURADO:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Sala de lo Civil y Penal del TSJ, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Plazo de interposición: dentro de los 10 días siguientes a la última notificación de la sentencia.

Si no se apela en dicho plazo, puede hacerse en el trámite de impugnación, pero queda supeditado a que el apelante principal mantenga el suyo.

(2) Los verbos típicos de la acción ilícita del art. 413 CP son: sustraer, destruir, inutilizar u ocultar. Habrá que valorar a la hora de interponer la querella cuál es la acción que va a ser objeto de acusación y redactarla.

Se trata de un delito eminentemente doloso al usar la expresión a sabiendas. Si lo que ha ocurrido es que el documento se ha extraviado no habrá delito, o si ha habido imprudencia en su custodia tampoco lo hay, porque las acciones de los verbos descritos exigen una actuación con dolo.

La actuación de defecto en la custodia podría dar lugar a responsabilidad disciplinaria, pero no penal. El principio de intervención mínima del derecho penal impide acudir a la vía penal si el hecho se debe a imprudencia o defecto de custodia.

Debe tratarse de documento sobre el que exista deber de conservar. Nótese que el tipo exige que se trate de documento "cuya custodia tenga encomendada", por lo que si no concurre este elemento tampoco se podrá acudir a la vía penal. Si el documento en cuestión no era preciso que se debiera conservar o custodiar, o fuera prescindible por poder ser sustituido por otro u otros que consten tampoco habrá delito, podría ser disciplinario, pero no penal.

Doctrina jurisprudencial: (STS 167/2018, de 11 de abril, rec. 1087/2017) (STS 542/2016, de 20 de junio, rec. 4/2016) (STS 941/2009, de 29 de septiembre, rec. 635/2008) (STS 497/2012, de 4 de junio, rec. 250/2011)

================================================================================
