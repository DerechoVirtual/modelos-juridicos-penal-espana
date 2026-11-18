---
name: insolvencia-punible-apelacion-contra-condena-391
description: "Redacta el escrito «Insolvencia punible: apelación contra la condena» (formulario 391 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Insolvencia punible: apelación contra la condena

> Formulario 0391 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…oral con los siguientes medios de prueba»; «…, habida cuenta que:»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental consistente en aportación de:.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 259 CP
- artículo 259 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 259.1 CP
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 259.2 CP

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

### Formulario 0391 · Insolvencia punible: apelación contra la condena

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la sentencia de condena por delito de insolvencia punible del art. 259 CP, alegando que ha habido error en la apreciación de la prueba porque ha quedado acreditado que el condenado no estaba en situación de insolvencia ni cometió ninguna de las actuaciones que se enumeran en el apartado 1 de art. 259 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito del artículo 259 CP, ante este órgano judicial (1) comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (3)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que cuando se interpone un motivo de impugnación de esta naturaleza al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando del examen de lo actuado se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se le condena, ya que no se encontraba en situación de insolvencia patrimonial, sino ante dificultades de pago propias del momento de crisis en el que nos encontramos, y llevando a cabo actuaciones para poder hacer frente al pago de las deudas, por lo que se rompe el primero de los requisitos del art. 259 CP acerca de que la situación del/de la condenado/a no es de insolvencia patrimonial actual o inminente, sino, tan solo, de estar pasando por dificultades económicas sobre las que se llevaron a cabo esfuerzos para asumir y hacer frente a las deudas en el menor tiempo posible. (4)

Con respecto a la/s conducta/s que se citan del art. 259.1 CP no es cierta la misma, y así se ha acreditado en el juicio oral con los siguientes medios de prueba [COMPLETAR], habida cuenta que: [COMPLETAR].

Faltando ambos presupuestos del art. 259 CP el/la condenado/a no puede ser autor/a del delito del art. 259 CP.(Si se tratara de la conducta del art. 260 CPse alegaría que no hay acto de favorecimiento doloso a acreedores ficticios, sino que los pagos son correctos y amparados en deuda existente y real y no creada de propósito)

El juzgador, además, ha llevado a cabo una valoración de la pericial contra el/la reo/a, vulnerando la presunción de inocencia y no teniendo en cuenta la prueba de descargo practicada y tomando por falso el contenido de la documental sin una debida motivación, ya que, además, la pericial aportada evidenció que no se encontraba en situación de insolvencia patrimonial actual o inminente y ello impide la comisión del delito del art. 259 CP.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental consistente en aportación de:.

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(2) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(4) El delito del art. 259 CP debe identificarse con un pronóstico razonable que, en sede penal, ya incluso para la admisión a trámite de la querella o para dar curso a la denuncia, debe estar amparado por un elenco de indicios de suficiente solidez.

La acreditación indiciaria inicial puede llevarse a cabo mediante la aportación al Juez instructor de datos que pongan de manifiesto claramente la crisis o déficit patrimonial del deudor a quien se imputa la comisión del delito (por ejemplo: relación de acreedores en caso de multiplicidad, inventarios del deudor que reflejen la situación deficitaria, y especialmente, relación de impagos).

Los requisitos de la persona contra quien se dirige la acción penal son dos:

a.- Situación de insolvencia actual o inminente.

La Insolvencia penal es sólo la definitiva «de naturaleza estructural». No coincide completamente con la insolvencia concursal, es más exigente en el carácter del incumplimiento de los pagos. (STS 652/2018, de 14 de diciembre, Rec. 45/2018)

b.- Realizar alguna de las conductas que se citan en el art. 259.1 CP.

• Que supongan una disminución del patrimonio (1ª a 4ª) o la asunción de un riesgo de perdidas injustificadas (5ª).

• Que infrinjan deberes legales contables («insolvencia documental») (6ª a 8ª)

• Cláusula de cierre (9ª) que introduce dos requisitos cumulativos (infracción grave y disminución patrimonial/ocultación) que parte de la jurisprudencia y de la doctrina consideran extensivos al resto de conductas del 259.1 CP.

El apartado 1º del art. 259 CP es definido como la insolvencia no causal y el apartado 2º como la insolvencia causal.

Así, cabe, en segundo lugar, (art. 259.2 CP) que mediante alguna de las conductas a que se refiere el apartado anterior, cause su situación de insolvencia, con lo que si en el apartado 1º se exige que se encuentre el querellado en situación de insolvencia y lleve a cabo alguna de estas conductas, en el apartado 2º se admite que "con una de esas conductas" provoque su insolvencia.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013, de 31 de enero y STS 32/2012, de 25 de enero, Rec. 932/2011.

================================================================================
