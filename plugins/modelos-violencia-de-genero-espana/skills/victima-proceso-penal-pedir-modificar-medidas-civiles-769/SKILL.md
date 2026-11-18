---
name: victima-proceso-penal-pedir-modificar-medidas-civiles-769
description: "Redacta el escrito «Víctima en el proceso penal: pedir modificar las medidas civiles del proceso de familia» (formulario 769 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima en el proceso penal: pedir modificar las medidas civiles del proceso de familia

> Formulario 0769 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (4 veces)
- [ ] ÓRGANO O PERSONA
- [ ] NÚMERO (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] Nº DE DOCUMENTO
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ncia de género tipificado en el artículo»; «…nº [NÚMERO] de»; «… dicho matrimonio nacieron dos hijos: 1º»; «…de [Nº] años de edad y»; «…onde se adoptaron las siguientes medidas»; «…to de declaración de IRPF del último año»

## Elecciones que hay que hacer

- separación / divorcio
- de Familia, Infancia y Capacidad / Civil

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 57 del Código Penal
- artículo 48 CP
- artículo 57.2 CP
- artículo 65 LO 1/2004
- artículo 66 LO 1/2004

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

### Formulario 0769 · Víctima en el proceso penal: pedir modificar las medidas civiles del proceso de familia

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 28 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que una víctima de violencia de género con hijos menores de edad, solicita en el proceso penal que el juez penal modifique medidas de naturaleza civil previamente adoptadas por el juez de familia, por la vía del artículo 544 quinquies de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese órgano judicial por Dña. [NOMBRE Y APELLIDOS] contra D. por la comisión de un delito de violencia de género tipificado en el artículo [COMPLETAR] CP habiéndonos personado en las actuaciones por escrito de fecha [FECHA].

Que, antes del dictado del auto previsto en el artículo 544 ter 7 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de adopción de medidas cautelares del orden civil en el auto resolviendo sobre la orden de protección interesada, en base al citado precepto y en relación con los arts. 61 y ss. LO 1/2004 y que en este caso son modificativas de las adoptadas por [ÓRGANO O PERSONA] nº [NÚMERO] de [COMPLETAR] procedimiento nº [Nº DE PROCEDIMIENTO], en base al artículo 544 quinquies LECRIM:

PRIMERA.- Señala el artículo 544 quinquies LECRIM que: "1. En los casos en los que se investigue un delito de los mencionados en el artículo 57 del Código Penal, el Juez o Tribunal, cuando resulte necesario al fin de protección de la víctima menor de edad o con la capacidad judicialmente modificada, en su caso, adoptará motivadamente alguna de las siguientes medidas:

a) Suspender la patria potestad de alguno de los progenitores. En este caso podrá fijar un régimen de visitas o comunicación en interés del menor o persona con capacidad judicialmente modificada y, en su caso, las condiciones y garantías con que debe desarrollarse.
b) Suspender la tutela, curatela, guarda o acogimiento.
c) Establecer un régimen de supervisión del ejercicio de la patria potestad, tutela o de cualquier otra función tutelar o de protección o apoyo sobre el menor o persona con la capacidad judicialmente modificada, sin perjuicio de las competencias propias del Ministerio Fiscal y de las entidades públicas competentes.
d) Suspender o modificar el régimen de visitas o comunicación con el no conviviente o con otro familiar que se encontrara en vigor, cuando resulte necesario para garantizar la protección del menor o de la persona con capacidad judicialmente modificada." (1)

El artículo 544 ter 7 LECRIM, reformado por la LO 8/2021 de 4 de Junio, señala en el párrafo 3º que: "Cuando se dicte una orden de protección con medidas de contenido penal y existieran indicios fundados de que los hijos e hijas menores de edad hubieran presenciado, sufrido o convivido con la violencia a la que se refiere el apartado 1 de este artículo, la autoridad judicial, de oficio o a instancia de parte, suspenderá el régimen de visitas, estancia, relación o comunicación del inculpado respecto de los menores que dependan de él. No obstante, a instancia de parte, la autoridad judicial podrá no acordar la suspensión mediante resolución motivada en el interés superior del menor y previa evaluación de la situación de la relación paternofilial."

Quiere esto decir que la regla general ahora es la suspensión del régimen de visitas y la excepción la no suspensión, siempre que nos encontremos en un caso de los expuestos en el citado párrafo del art. 544 ter 7 LECRIM, ya que debe ser ahora el investigado el que postule la no suspensión acreditando las razones para ello.

SEGUNDA.- La peticionaria de las medidas Dña. contrajo matrimonio con el denunciado D. [NOMBRE Y APELLIDOS] en fecha [FECHA] como consta en el documento nº [Nº DE DOCUMENTO] aportado de la inscripción en el registro civil de [LOCALIDAD]. De dicho matrimonio nacieron dos hijos: 1º [COMPLETAR] de [Nº] años de edad y [COMPLETAR] de [Nº] años de edad. Por lo tanto menores de edad.

Hay un procedimiento civil previo abierto de [ELEGIR: separación / divorcio] nº [NÚMERO] de la Sección [ELEGIR: de Familia, Infancia y Capacidad / Civil] del Tribunal de Instancia donde se adoptaron las siguientes medidas [COMPLETAR].

Se ha solicitado en la denuncia la adopción de la medida cautelar penal de prohibición de aproximación del denunciado del artículo 48 CP en relación con el artículo 57.2 CP, por lo que se interesa en el presente escrito la adopción de la medida civil de atribución del uso de la vivienda familiar sita en [LOCALIDAD], al ser el interés de la denunciante y de los hijos el más necesitado de protección, dada la condición de menores de edad de estos y la carencia de actividad laboral de la denunciante.

Pese a que en el procedimiento de la Sección [ELEGIR: de Familia, Infancia y Capacidad / Civil] del Tribunal de Instancia se acordó el régimen de custodia compartida, habida cuenta que se ha cometido un delito grave de violencia de género por la agresión sufrida por la denunciante en presencia de los hijos se solicita la modificación de tal medida y la atribución del régimen de guarda y custodia de los menores a favor de Dña. privando al denunciado del régimen de visitas, en base a la nueva redacción del art. 544 ter 7 LECRIM (LO 8/2021, de 4 de Junio) al haberse cometido el delito en presencia de sus hijos, lo que denota la agresividad del denunciado y la negativa que debe otorgarse a poder estar con sus hijos, todo ello hasta que se dicte sentencia en el procedimiento civil de modificación de medidas que se va a instar, no obstante lo cual resulta procedente la modificación por el juez de violencia de esta medida con carácter cautelar, dados los hechos de carácter penal que motivan el presente procedimiento. (2)

Se solicita la modificación de la pensión compensatoria por importe de [IMPORTE] euros en favor de la denunciante al haberse quedado sin trabajo y en razón a los ingresos del denunciado que ahora ascienden a la suma de [IMPORTE] euros, como se acredita con copia del documento de declaración de IRPF del último año [COMPLETAR].

Se solicita también por ello la ampliación de la pensión por alimentos en favor de cada hijo de [IMPORTE] euros en razón al mismo documento.

Por lo expuesto,

SUPLICO A LA SECCIÓN

que tenga por presentado este escrito, lo admita y tenga por realizado el trámite para el dictado de la orden de protección incluyendo como cautelares las medidas civiles interesadas y sus modificaciones.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) El juez debe acordar en todo caso estas medidas civiles, no pudiendo dejar de hacerlo.

(2) En cuanto a la posibilidad de suspensión de la guarda y custodia véase el artículo 65 LO 1/2004 y en cuanto a la privación del régimen de visitas véase el artículo 66 LO 1/2004.

================================================================================
