---
name: delito-contra-relaciones-familiares-acusacion-particular-273
description: "Redacta el escrito «Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar» (formulario 273 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar

> Formulario 0273 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (3 veces)
- [ ] DELITO
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e fue turnada a ese órgano judicial, por»; «…e un delito de tipificado en el artículo»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 57 CP
- art. 544 ter LECRIM
- art. 173.2 CP
- art. 57.2 CP
- art. 544 ter.4 LECRIM

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

### Formulario 0273 · Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar

- Año del modelo: 2022
- Revisión 17-11-2026: 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia, que fue turnada a ese órgano judicial, por [COMPLETAR] por la comisión de un delito de tipificado en el artículo [COMPLETAR] CP habiéndonos personado en las DP por escrito de fecha

Que los hechos objeto de acusación se centran en el delito [DELITO] y el art. 57 CP, en virtud de la reforma operada por LO 8/2021, de 4 de junio, señala que:

"1. Las autoridades judiciales, en los delitos de homicidio, aborto, lesiones, contra la libertad, de torturas y contra la integridad moral, trata de seres humanos, contra la libertad e indemnidad sexuales, la intimidad, el derecho a la propia imagen y la inviolabilidad del domicilio, el honor, el patrimonio, el orden socioeconómicoy las relaciones familiares, atendiendo a la gravedad de los hechos o al peligro que el delincuente represente, podrán acordar en sus sentencias la imposición de una o varias de las prohibiciones contempladas en el artículo 48, por un tiempo que no excederá de diez años si el delito fuera grave, o de cinco si fuera menos grave

...2. En los supuestos de los delitos mencionados en el primer párrafo del apartado 1 de este artículo cometidos contra quien sea o haya sido el cónyuge, o sobre persona que esté o haya estado ligada al condenado por una análoga relación de afectividad aun sin convivencia, o sobre los descendientes, ascendientes o hermanos por naturaleza, adopción o afinidad, propios o del cónyuge o conviviente, o sobre los menores o personas con discapacidad necesitadas de especial protección que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho del cónyuge o conviviente, o sobre persona amparada en cualquier otra relación por la que se encuentre integrada en el núcleo de su convivencia familiar, así como sobre las personas que por su especial vulnerabilidad se encuentran sometidas a su custodia o guarda en centros públicos o privadosse acordará, en todo caso, la aplicación de la pena prevista en el apartado 2 del artículo 48por un tiempo que no excederá de diez años si el delito fuera grave, o de cinco si fuera menos grave, sin perjuicio de lo dispuesto en el párrafo segundo del apartado anterior."

Por otro lado, el art. 544 ter LECRIM prevé el dictado de la orden de protección donde se recojan, entre otras, las medidas cautelares que se fijen procedentes por el/la juez/a, y entre ellas la orden de alejamiento.

La LO 8/2021, de 4 de junio, ha incluido en la reforma del art. 57 CP que los delitos contra las relaciones familiares entre aquellos en los que se puede imponer la pena de alejamiento, siendo preceptiva cuando se trate ahora de delito contra las relaciones familiares si se dirige contra uno de los sujetos pasivos del art. 173.2 CP.

En el presente caso se trata de denuncia de [FECHA] contra [ACTO O RESOLUCIÓN] por lo que cumple el presupuesto del sujeto activo y pasivo al que se refiere el art. 57.2 CP, lo que permite que en fase de instrucción se pueda acudir a la vía del art. 544 ter LECRIM para instar la cautelar de alejamiento en aras a garantizar por adelantado la medida de protección que caracteriza a esta pena que ya es preceptiva en estos delitos tras la LO 8/2021, de 4 de junio.

Por todo ello, se solicita se tenga por cumplido el presupuesto del art. 544 ter.4 LECRIM y se tenga por instada la orden de protección, y en concreto la medida cautelar de alejamiento.

Por lo expuesto.

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizada la alegación de esta parte como acusación particular de que se tenga por instada la orden de protección y en concreto la medida cautelar de alejamiento, convocando a las partes a la audiencia pública previa al dictado de la citada orden de protección.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
