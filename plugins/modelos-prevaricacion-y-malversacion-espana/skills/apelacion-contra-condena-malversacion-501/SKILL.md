---
name: apelacion-contra-condena-malversacion-501
description: "Redacta el escrito «Apelación contra la condena por malversación» (formulario 501 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por malversación

> Formulario 0501 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Tras la LO 14/2022 el art. 432.3 CP es un tipo atenuado (perjuicio o valor inferior a 4.000 euros: prisión de uno a dos años, multa e inhabilitación de uno a cinco años) y la rebaja del art. 434 exige reparar antes del inicio del juicio oral (BOE-A-2022-21800).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (5 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…esan como hechos probados los siguientes»; «…laración de culpabilidad los siguientes:»; «… de la sentencia es del tenor siguiente:»

## Elecciones que hay que hacer

- 432 / 432 bis / 433
- favorable / desfavorable

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Malversación con ánimo de lucro del art. 432 CP / Malversación sin ánimo de apropiación del art. 432 bis CP / Malversación por desvío presupuestario del art. 433 CP — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 432 CP
- art. 433 CP
- art. 432 bis CP
- art. 432 CP
- artículo 432 bis CP
- art. 434 CP
- artículo 433 CP

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

### Formulario 0501 · Apelación contra la condena por malversación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 12 campos de relleno marcados en blanco
- Avisos de la revisión: Tras la LO 14/2022 el art. 432.3 CP es un tipo atenuado (perjuicio o valor inferior a 4.000 euros: prisión de uno a dos años, multa e inhabilitación de uno a cinco años) y la rebaja del art. 434 exige reparar antes del inicio del juicio oral (BOE-A-2022-21800).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la sentencia de condena dictada por el Tribunal del Jurado alegando que se ha vulnerado el derecho a la presunción de inocencia porque, atendida la prueba practicada en el juicio, carece de toda base razonable la condena impuesta, ya que sus actos no son constitutivos de malversación con ánimo de lucro del artículo 432 CP, o por desvío presupuestario del art. 433 CP o bien que se infringe un precepto legal en la calificación jurídica de los hechos porque no son constitutivos de malversación por uso privado de patrimonio público del art. 432 bis CP.

Actualizado conforme a la LO 14/2022, vigente desde el 12 de enero de 2023.

Al/A la Magistrado/a Presidente/a del Tribunal del Juradode

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito del artículo [ELEGIR: 432 / 432 bis / 433] CP (1), comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación, conforme a lo prevenido en el artículo 846 bis a de la Ley de Enjuiciamiento Criminal.

ANTECEDENTES

PRIMERO.- En el acta de la votación de los Jurados de fecha [FECHA] se contiene el veredicto donde se expresan como hechos probados los siguientes [COMPLETAR].

SEGUNDO.- El veredicto considera al/a la acusado/a culpable del delito de [DELITO], expresando su criterio [ELEGIR: favorable / desfavorable] a la remisión condicional de la pena que se impusiese y también sobre la petición del indulto en la sentencia.

TERCERO.- En el veredicto los Jurados han expresado como elementos de convicción para hacer dicha declaración de culpabilidad los siguientes: [COMPLETAR].

CUARTO.- El fallo de la sentencia es del tenor siguiente: [COMPLETAR].

MOTIVOS

ÚNICO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Malversación con ánimo de lucro del art. 432 CP / Malversación sin ánimo de apropiación del art. 432 bis CP / Malversación por desvío presupuestario del art. 433 CP — el texto de cada opción no venía en el formulario original]

Por lo expuesto,

SUPLICO AL/A LA MAGISTRADO/A PRESIDENTE/A DEL TRIBUNAL DEL JURADO:

Que tenga por presentado este escrito con sus copias y por interpuesto en tiempo y forma el presente RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita, y tras los trámites procesales correspondientes, remita las actuaciones a la Sala de lo Civil y Penal del TSJ para que resuelva con arreglo a las pretensiones de esta parte.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La LO 14/2022, vigente desde el 12 de enero de 2023, modifica la malversación, distinguiendo tres niveles:

1. La apropiación de patrimonio público por parte del autor o que éste consienta su apropiación por terceras personas (artículo 432 CP), que integra la conducta más grave y contiene diversas agravaciones. Destaca:
a.- Se introduce el ánimo de lucro
b.- Se añade que el patrimonio público lo tenga a su cargo por razón de sus funciones o con ocasión de las mismas.
2. El uso temporal de bienes públicos sin animus rem sibi habendi y con su posterior reintegro (artículo 432 bis CP).

Si el culpable no reintegrara los mismos elementos del patrimonio público distraídos dentro de los diez días siguientes al de la incoación del proceso, se le impondrán las penas del artículo 432 CP.

Existe, incluso, una posibilidad de rebaja de la pena en uno o dos grados si el reintegro de las sumas es posterior a los 10 días desde la incoación del proceso penal, y así lo señala el art. 434 CP.

3. Un desvío presupuestario o gastos de difícil justificación (artículo 433 CP).

En estos casos la actuación administrativa persigue un interés público pero distinto a aquel que señala el ordenamiento en el supuesto concreto. El acto o la disposición normativa así dictada incurre en lo que denominamos una desviación de poder sutil o relativa, pues a pesar de atender al interés general, la Administración ejercita una potestad concreta con finalidades distintas a las encomendadas por la ley.

(2) Plazo de interposición: dentro de los 10 días siguientes a la última notificación de la sentencia.

Si no se apela en dicho plazo, puede hacerse en el trámite de impugnación, pero queda supeditado a que el apelante principal mantenga el suyo.

================================================================================
