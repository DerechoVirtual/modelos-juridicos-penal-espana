---
name: padres-victima-mayor-edad-personacion-como-acusacion-747
description: "Redacta el escrito «Padres de víctima mayor de edad: personación como acusación particular» (formulario 747 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Padres de víctima mayor de edad: personación como acusación particular

> Formulario 0747 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE DOCUMENTO
- [ ] AÑO (2 veces)
- [ ] FECHA (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…s de delito de malos tratos del artículo»

## Elecciones que hay que hacer

- ella / los padres / terceros
- niega los hechos / se niega a declarar / declara exculpando al denunciado

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 101, 110 y 761.2 de la Ley de Enjuiciamiento Criminal
- Ley 4/2015

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

### Formulario 0747 · Padres de víctima mayor de edad: personación como acusación particular

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (Nº, Nº DE DOCUMENTO, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que los padres de una víctima de un delito mayor de edad se personan como acusación particular, sin necesidad de formular querella, por ser considerados como víctimas directas por daño emocional, en aplicación del artículo 2 de la L 4/15 del Estatuto de la Víctima del Delito.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en representación de D./Dña. [NOMBRE Y APELLIDOS],como consta en escritura de poder inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme, acompañando certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada, comparezco ante este órgano judicial y como mejor proceda en derecho (1), DIGO:

Que hemos tenido conocimiento de la incoación de unas diligencias previas en este órgano judicial con el nº [Nº]/[AÑO] en razón al atestado policial elaborado a raíz de la intervención de los agentes policiales en el domicilio de la hija mayor de edad de mi mandante, D./Dña. [NOMBRE Y APELLIDOS] el pasado día [FECHA] por hechos constitutivos de delito de malos tratos del artículo [COMPLETAR] del CP.

Que, en uso del derecho reconocido en los artículos 101, 110 y 761.2 de la Ley de Enjuiciamiento Criminal, y en virtud del ofrecimiento de acciones que ha sido hecho a mi representado/a como perjudicado/a (2), una vez acudimos a dependencias policiales, me persono en las diligencias previas número [Nº DE PROCEDIMIENTO]/[AÑO] por el presunto delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS], para ejercitar la acusación particular del referido delito.

El Artículo 109 bis LECRIM señala que:

"1. Las víctimas del delito que no hubieran renunciado a su derecho podrán ejercer la acción penal en cualquier momento antes del trámite de calificación del delito, si bien ello no permitirá retrotraer ni reiterar las actuaciones ya practicadas antes de su personación. Si se personasen una vez transcurrido el término para formular escrito de acusación podrán ejercitar la acción penal hasta el inicio del juicio oral adhiriéndose al escrito de acusación formulado por el Ministerio Fiscal o del resto de las acusaciones personadas "

Debe estimarse la intervención de los progenitores como acusación particular como víctimas directas por daño emocional, ya que en estos casos deben ser considerados como perjudicados al aplicar la Ley 4/2015, ya que el Artículo 2 de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito señala que:

"Las disposiciones de esta Ley serán aplicables:

a) Como víctima directa, a toda persona física que haya sufrido un daño o perjuicio sobre su propia persona o patrimonio, en especial lesiones físicas o psíquicas,daños emocionaleso perjuicios económicos directamente causados por la comisión de un delito."

Se debe admitir la personación como acusación particular de los padres de una víctima de maltrato que puede negarse a denunciar o, que una vez presentada la denuncia por [ELEGIR: ella / los padres / terceros], [ELEGIR: niega los hechos / se niega a declarar / declara exculpando al denunciado]. Los progenitores pueden llegar a sufrir un daño emocional que dimana de la situación que está sufriendo su propia hija en el contexto de su relación de pareja o noviazgo sin convivencia, por hecho constitutivo de violencia de género.

El daño directo puede ser soportado por la víctima de violencia de género, pero los progenitores están sufriendo un daño moral o emocional, al comprobar que su propia hija sigue siendo víctima de maltrato sin poder hacer nada por ella, si ella no quiere reconocer los hechos, y en base a ello postulan la acción penal para intentar la condena de quien estos sostienen ser autor de los hechos de los que es víctima directa su propia hija, con lo que no son terceros ajenos a los hechos, sobre todo dadas las características que concurren en los casos de violencia de género con la conducta de algunas víctimas que por las razones que fueran pretenden ocultar los hechos.

La admisión de la personación particular de sus padres constituye, así, una medida de protección a la que se puede estar negando la víctima sin ser consciente, o siéndolo, de las consecuencias de su negativa a reconocerlo.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito y documentos adjuntos, los admita, teniéndome por personado en la representación de D./Dña. [NOMBRE Y APELLIDOS], como acusador particular ejercitando las acciones penales y civiles que se deriven de los hechos, y acuerde se entiendan conmigo las sucesivas diligencias, dándome vista de lo actuado.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS]

Firma del cliente

D./Dña. [NOMBRE Y APELLIDOS]

	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito puede presentarse tanto en la Sección de Violencia sobre la Mujer del Tribunal de Instancia como en el de instrucción dependiendo de las relaciones entre las partes.

(2) El perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

Los perjudicados que no hubiesen renunciado a su derecho, pueden mostrarse parte en la causa si lo hacen antes del trámite de calificación del delito, y ejercitar las acciones penales que procedan, sin que por ello se retroceda en el curso de las actuaciones.

Aunque los perjudicados no se muestren parte en la causa, no debe entenderse que renuncian al derecho de restitución, reparación o indemnización que, a su favor puede acordarse en sentencia firme. La renuncia de este derecho debe hacerse de una manera expresa y terminante.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

================================================================================
