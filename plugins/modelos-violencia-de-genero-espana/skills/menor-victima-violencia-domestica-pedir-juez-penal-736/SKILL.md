---
name: menor-victima-violencia-domestica-pedir-juez-penal-736
description: "Redacta el escrito «Menor víctima de violencia doméstica: pedir al juez penal suspender las visitas del progenitor» (formulario 736 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Menor víctima de violencia doméstica: pedir al juez penal suspender las visitas del progenitor

> Formulario 0736 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…víctima del presente procedimiento penal»; «…contra D.»; «…donde resulta como acusado D.»

## Elecciones que hay que hacer

- testigo / víctima

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 153.2 CP
- artículo 57 del Código Penal
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

### Formulario 0736 · Menor víctima de violencia doméstica: pedir al juez penal suspender las visitas del progenitor

- Año del modelo: 2016
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 13 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un menor víctima de violencia doméstica solicita al juez penal que se suspenda el régimen de visitas de su progenitor, en base al artículo 544 1 quinquies de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular en nombre y representación de el/la menor víctima del presente procedimiento penal [COMPLETAR] en las diligencias previas nº [Nº DE PROCEDIMIENTO]/[AÑO] que se sigue en este órgano judicial por delito de [DELITO] contra D. [COMPLETAR], ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Con fecha [FECHA] se ha citado a mi representado/a para que comparezca en su calidad de [ELEGIR: testigo / víctima] donde resulta como acusado D. [COMPLETAR].

Que, al tratarse de un procedimiento por delito de lesiones del artículo 153.2 CP (maltrato de violencia doméstica), se interesa se proceda al dictado de la medida cautelar de suspensión del régimen de visitas para el acusado al tratarse de un delito cometido sobre el/la propio/a menor. Los padres de la víctima D. acusado en el procedimiento penal y Dña. [NOMBRE Y APELLIDOS], madre de el/la menor, se encuentran separados judicialmente en la actualidad, existiendo una medida de régimen de visitas adoptada por la Sección de Familia, Infancia y Capacidad del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO].

En el artículo 544 quinquies LECRIM se recoge que:

En los casos en los que se investigue un delito de los mencionados en el artículo 57 del Código Penal, el Juez o Tribunal, cuando resulte necesario al fin de protección de la víctima menor de edad o con la capacidad judicialmente modificada, en su caso, adoptará motivadamente alguna de las siguientes medidas:

a) Suspender la patria potestad de alguno de los progenitores. En este caso podrá fijar un régimen de visitas o comunicación en interés del menor o persona con capacidad judicialmente modificada y, en su caso, las condiciones y garantías con que debe desarrollarse.
b) Suspender la tutela, curatela, guarda o acogimiento.
c) Establecer un régimen de supervisión del ejercicio de la patria potestad, tutela o de cualquier otra función tutelar o de protección o apoyo sobre el menor o persona con la capacidad judicialmente modificada, sin perjuicio de las competencias propias del Ministerio Fiscal y de las entidades públicas competentes.
d) Suspender o modificar el régimen de visitas o comunicación con el no conviviente o con otro familiar que se encontrara en vigor, cuando resulte necesario para garantizar la protección del menor o de la persona con capacidad judicialmente modificada.

En este caso el objeto de las diligencias es un delito del artículo 153.2 CP, por cuanto se considera procedente y proporcionado a la gravedad de lo ocurrido, al tratarse de un delito de maltrato a menores y debe entenderse procedente que se adopte esta medida que se enraíza en esencia en el propio delito cometido, ya que debe suspenderse el régimen de visitas para evitar la reiteración en el delito.

La gravedad de los hechos aconsejan el dictado de esta medida que le permite al menor disponer de la tranquilidad que exige la filosofía de la Ley 4/2015, de 27 de abril, de estatuto de la víctima en el proceso penal, ya que el artículo 19 de esta Ley señala, bajo la rúbrica "Derecho de las víctimas a la protección", que: "Las autoridades y funcionarios encargados de la investigación, persecución y enjuiciamiento de los delitos adoptarán las medidas necesarias, de acuerdo con lo establecido en la Ley de Enjuiciamiento Criminal, para garantizar la vida de la víctima y de sus familiares, su integridad física y psíquica, libertad, seguridad, libertad e indemnidad sexuales, así como para proteger adecuadamente su intimidad y su dignidad, particularmente cuando se les reciba declaración o deban testificar en juicio, y para evitar el riesgo de su victimización secundaria o reiterada."

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita el presente escrito y se acuerde la medida de suspensión del régimen de visitas y se comunique a tal fin al acusado.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
