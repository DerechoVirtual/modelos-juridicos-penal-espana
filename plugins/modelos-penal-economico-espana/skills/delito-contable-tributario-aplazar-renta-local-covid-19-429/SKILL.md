---
name: delito-contable-tributario-aplazar-renta-local-covid-19-429
description: "Redacta el escrito «Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025)» (formulario 429 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025)

> Formulario 0429 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…a reducción de la facturación mensual en»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es de prisión igual o inferior a 2 años)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 310 CP
- art. 784.3 LECrim
- art. 787 LECrim
- art. 310 CP
- art. 80 CP
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

### Formulario 0429 · Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025)

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Avisos de la revisión: El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un arrendatario de local de negocio, que alteró la contabilidad del negocio para solicitar un aplazamiento de la renta por COVID 19, se conforma con la calificación jurídica de los hechos como delito contable tributario del artículo 310 CP y con la pena solicitada por la fiscalía, con la posibilidad de instar la suspensión de la pena si es inferior a 2 años.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito contable tributario del artículo 310 CP, comparezco ante el Tribunal y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1) y art. 784.3 LECrim, en relación con el art. 787 LECrim, se formula escrito de conformidad de los hechos considerados delito contable tributario del art. 310 CP. (2)

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] (3).

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es de prisión igual o inferior a 2 años)

Al haberse abonado la responsabilidad civil reclamada y no existir antecedentes penales, se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales. (4)

Por lo expuesto,

SUPLICO AL TRIBUNAL:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) Este supuesto se refiere a los casos de arrendatarios de locales que han podido abrir desde el 15 de Marzo de 2020, fecha de declaración del estado de alarma por Coronavirus por RD 463/2020, de 14 de marzo, pero su facturación ha sido baja, aunque no lo suficiente para ampararse en la previsión del art. 1.1 RDL 15/2020, de 21 de abril, que da derecho a empresas, o entidades públicas o grandes tenedores y PYMES y autónomos a un aplazamiento temporal y extraordinario en el pago de la renta del local, arts. 3.1.c) y 3.2.c) RDL 15/2020, de 21 de abril.

El art. 3 RDL 15/2020, de 21 de abril, recoge los requisitos para tener derecho al aplazamiento en el pago de la renta de local. En este sentido, no podría tratarse de un hecho delictivo la circunstancia de que se redactaran documentos por los particulares alterando la verdad en los hechos, ya que la única forma de entender ilícito penal en las falsedades es la de la falsedad documental por la vía de los nº 1, 2 o 3 del art. 390 CP; pero no la de alteración de la verdad en la narración de los hechos, ya que ello iría como falsedad ideológica al ser no punible.

El art. 5 RDL 15/2020, de 21 de abril, regula las consecuencias para los arrendatarios que se hayan beneficiado del aplazamiento sin reunir los requisitos establecidos en el artículo 3 RDL 15/2020, de 21 de abril.

Sí que constituiría un ilícito penal, en concreto un delito de falsedad contable del art. 310 CP, si el arrendatario alterara la contabilidad del negocio para ofrecer al arrendador unos datos que permitan "acreditarle" una minoración de ingresos, es decir, para acreditar la reducción de la facturación mensual en [COMPLETAR], al menos, un 75 por ciento, en relación con la facturación media mensual del mismo trimestre del año anterior. (Art. 4 RDL 15/2020, de 21 de abril).

Nótese que la obligatoriedad en la aceptación del aplazamiento en el pago de la deuda lo es solo respecto al supuesto del art. 1 RDL 15/2020, de 21 de abril, con lo que este delito tiene una mayor relevancia en estos casos donde, si el arrendatario lo insta, es obligatoria la moratoria, lo que no ocurre en el caso de los supuestos del art. 2 RDL 15/2020, de 21 de abril, en donde es voluntario para el arrendador aceptar, o no, la propuesta del arrendatario.

(3) En este caso podría pactarse la conformidad de los dos años o menos de prisión para conseguir la suspensión de la ejecución de la pena.

(4) Es importante instar ya la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
