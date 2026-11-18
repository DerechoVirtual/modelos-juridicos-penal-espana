---
name: delito-contable-tributario-aplazar-renta-local-covid-19-432
description: "Redacta el escrito «Delito contable tributario para aplazar renta del local (COVID-19): apelación contra la condena» (formulario 432 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contable tributario para aplazar renta del local (COVID-19): apelación contra la condena

> Formulario 0432 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (5 veces)
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… que el objeto social del local es el de»; «… aportada, que la facturación del mes de»; «…sea de»; «…sea de [COMPLETAR], del mes de»; «…, del mes de [COMPLETAR] de»; «…de [COMPLETAR], del mes de»; «…e [COMPLETAR], del mes de [COMPLETAR] de»; «…de [COMPLETAR] y de»; «…e [COMPLETAR] y de [COMPLETAR] el mes de»; «…gico descenso, llegando al porcentaje de»; «…DOCUMENTAL consistente en aportación de:»; «…a reducción de la facturación mensual en»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR…
- 1.- TESTIFICAL: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- PERICIAL: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- DOCUMENTAL consistente en aportación de: [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 310 CP
- artículo 310 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 1.1 RDL 15/2020
- art. 3 RDL 15/2020
- art. 390 CP
- art. 5 RDL 15/2020
- artículo 3 RDL 15/2020
- art. 1 RDL 15/2020
- art. 2 RDL 15/2020

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

### Formulario 0432 · Delito contable tributario para aplazar renta del local (COVID-19): apelación contra la condena

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 4 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Avisos de la revisión: El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la sentencia que condena a un arrendatario de local de negocio por delito contable tributario del art. 310 CP, alegando error en la valoración de la pericial que acredita que la contabilidad presentada es cierta, y la bajada de ventas se debe a la pandemia por coronavirus.

Todas las referencias a Juzgados contenidas en este documento se entenderán sustituidas por las Secciones correspondientes de los Tribunales de Instancia cuando estos se constituyan, conforme al régimen transitorio que prevé la DT 1ª LO 1/2025.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito del artículo 310 CP, ante el Tribunal (1) comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (3)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba, como se explica a continuación:

Es conocido que es jurisprudencia reiterada y consolidada la que establece que solo al juzgador le compete apreciar y valorar las pruebas practicadas en el proceso bajo los principios de oralidad e inmediación, de suerte que, cuando se interpone un motivo de impugnación de esta naturaleza, al Tribunal de segunda instancia no le compete realizar una nueva valoración de la prueba practicada, sino simplemente comprobar si existe un absoluto vacío probatorio o si, por el contrario, hay un mínimo de actividad probatoria racional de cargo, practicada con todas las formalidades legales, que haya podido servir de base para formar la convicción del juzgador en ejercicio de la facultad soberana que le asiste para valorar las pruebas en conciencia, solo estando permitida la revisión de dicha valoración cuando, del examen de lo actuado, se evidencie con total claridad el error del juzgador al fijar el resultado probatorio de la sentencia recurrida o bien cuando se haya prescindido de alguna prueba de trascendencia manifiesta que aparezca reflejada con claridad o cuando se haya declarado probado un hecho importante a través de una interpretación ilógica.

Y en este caso esto ocurre, ya que en el juicio oral quedó acreditado que el/la condenado/a ahora recurrente no hizo exactamente aquello por lo que se condena por el delito del art. 310 CP (4), ya que el objeto social del local es el de [COMPLETAR]. pero la inexistencia de clientes por la pandemia del COVI-19 provocó, como se ha acreditado con la testifical y documental aportada, que la facturación del mes de [COMPLETAR] sea de [COMPLETAR], del mes de [COMPLETAR] de [COMPLETAR], del mes de [COMPLETAR] de [COMPLETAR] y de [COMPLETAR] el mes de [COMPLETAR]. Ello se comunicó en fecha [FECHA] al/a la arrendador/a, como se ha acreditado, aportando la facturación citada y la del trimestre del año anterior, sin que sea cierto que ello sea falso, sino ajustado al lógico descenso, llegando al porcentaje de [COMPLETAR] de reducción de ventas respecto al mismo periodo anterior, tal y como entendemos que quedó acreditado por pericial.

El juzgador ha llevado a cabo una valoración de la pericial contra el/la reo/a, vulnerando la presunción de inocencia y no teniendo en cuenta la prueba de descargo practicada y tomando por falso el contenido de la documental sin una debida motivación.

En su virtud,

SUPLICO AL TRIBUNAL:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante]. Y ello con independencia de que se alegue el error valorativo con respecto a la prueba que se ha practicado en el plenario. No obstante, manteniendo ese error respecto de las que se practicaron, se citan como no practicadas las que a continuación se relacionan y que se postula su práctica en esa instancia para llevar a cabo una valoración conjunta con las que se practicaron en el plenario y cuya validez se cuestiona en este recurso, como se ha expuesto:

[OPCIONAL — incluir si procede]

1.- TESTIFICAL: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- PERICIAL: A cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- DOCUMENTAL consistente en aportación de: [COMPLETAR].

SUPLICO AL TRIBUNAL: Que tenga por solicitadas las pruebas propuestas.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO AL TRIBUNAL: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

La persona jurídica debería interponer su propio recurso de apelación en caso de condena respecto a la indebida valoración de la prueba pericial en relación a la suficiencia del modelo de compliance.

(2) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(4) Este supuesto se refiere a los casos de arrendatarios de locales que han podido abrir desde el 15 de Marzo de 2020, fecha de declaración del estado de alarma por Coronavirus por RD 463/2020, de 14 de marzo, pero su facturación ha sido baja, aunque no lo suficiente para ampararse en la previsión del art. 1.1 RDL 15/2020, de 21 de abril, que da derecho a empresas, o entidades públicas o grandes tenedores y PYMES y autónomos a un aplazamiento temporal y extraordinario en el pago de la renta del local, arts. 3.1.c) y 3.2.c) RDL 15/2020, de 21 de abril.

El art. 3 RDL 15/2020, de 21 de abril, recoge los requisitos para tener derecho al aplazamiento en el pago de la renta de local. En este sentido, no podría tratarse de un hecho delictivo la circunstancia de que se redactaran documentos por los particulares alterando la verdad en los hechos, ya que la única forma de entender ilícito penal en las falsedades es la de la falsedad documental por la vía de los nº 1, 2 o 3 del art. 390 CP; pero no la de alteración de la verdad en la narración de los hechos, ya que ello iría como falsedad ideológica al ser no punible.

El art. 5 RDL 15/2020, de 21 de abril, regula las consecuencias para los arrendatarios que se hayan beneficiado del aplazamiento sin reunir los requisitos establecidos en el artículo 3 RDL 15/2020, de 21 de abril.

Sí que constituiría un ilícito penal, en concreto un delito de falsedad contable del art. 310 CP, si el arrendatario alterara la contabilidad del negocio para ofrecer al arrendador unos datos que permitan "acreditarle" una minoración de ingresos, es decir, para acreditar la reducción de la facturación mensual en [COMPLETAR], al menos, un 75 por ciento, en relación con la facturación media mensual del mismo trimestre del año anterior. (Art. 4 RDL 15/2020, de 21 de abril).

Nótese que la obligatoriedad en la aceptación del aplazamiento en el pago de la deuda lo es solo respecto al supuesto del art. 1 RDL 15/2020, de 21 de abril, con lo que este delito tiene una mayor relevancia en estos casos donde, si el arrendatario lo insta, es obligatoria la moratoria, lo que no ocurre en el caso de los supuestos del art. 2 RDL 15/2020, de 21 de abril, en donde es voluntario para el arrendador aceptar, o no, la propuesta del arrendatario.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012, de 25 de enero, rec. 932/2011.

================================================================================
