---
name: acoso-stalking-pedir-medida-cautelar-no-aproximacion-no-737
description: "Redacta el escrito «Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación» (formulario 737 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación

> Formulario 0737 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- testigo / víctima

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 172 ter CP
- art. 544 bis LECRIM
- artículo 57 del Código Penal
- artículo 19 de la Ley 4/2015
- art. 109.4 LECRIM

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

### Formulario 0737 · Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima de un delito de acoso o stalking del art. 172 ter CP, personada o no en el proceso, solicita que se adopte una medida cautelar de no aproximación, disponiendo así de la tranquilidad que exige la filosofía de la L 4/2015, del Estatuto de la Víctima del delito.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] (1) en las diligencias previas / que se siguen en este órgano judicial por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS] ante este órgano judicial (2) comparezco y, como más procedente sea en derecho, DIGO:

Con fecha [FECHA] se ha citado a mi representado/a para que comparezca en su calidad de [ELEGIR: testigo / víctima] donde resulta como acusado/a D./Dña. [NOMBRE Y APELLIDOS].

Que, al tratarse de un procedimiento por delito de acoso del art. 172 ter CP, incluido en el Título VI en los delitos contra la libertad, se interesa se proceda al dictado de una medida cautelar al/a la acusado/a de no aproximación al/a la denunciante D./Dña. [NOMBRE Y APELLIDOS] a menos de 500 metros de su domicilio, lugar de trabajo o lugares que frecuente.

En el art. 544 bis LECRIM se recoge que:

"En los casos en los que se investigue un delito de los mencionados en el artículo 57 del Código Penal, el Juez o Tribunal podrá, de forma motivada y cuando resulte estrictamente necesario al fin de protección de la víctima o evitar la reiteración delictiva, imponer cautelarmente al inculpado [NOTA DE REVISIÓN: Transcripción ajustada al art. 544 bis LECrim en la redacción de la LO 1/2026, de 8 de abril (vigente desde el 10-4-2026), que añade la finalidad de evitar la reiteración delictiva. Fuente: LO 1/2026, BOE-A-2026-7966, art. primero.tres (art. 544 bis LECrim).] la prohibición de residir en un determinado lugar, barrio, municipio, provincia u otra entidad local, o Comunidad Autónoma.

En las mismas condiciones podrá imponerle cautelarmente la prohibición de acudir a determinados lugares, barrios, municipios, provincias u otras entidades locales, o Comunidades Autónomas, o de aproximarse o comunicarse, con la graduación que sea precisa, a determinadas personas."

En este caso el objeto de las diligencias es un delito de acoso del art. 172 ter CP, por cuanto se considera procedente y proporcionado a la gravedad de lo ocurrido que se adopte esta medida que se enraiza en esencia en el propio delito cometido, ya que el/la denunciante no desea que el/la acusado/a siga acosándole y acercándose a su domicilio o lugar de trabajo o donde frecuente y que si lo hace a sabiendas cometa un delito de quebrantamiento de medida cautelar.

La gravedad del acoso sufrido por la víctima aconsejan el dictado de esta medida que solo restringe la libertad de movimientos sobre la víctima y le permite disponer de la tranquilidad que exige la filosofía de la Ley 4/2015 del Estatuto de la víctima en el proceso penal, ya que el artículo 19 de la Ley 4/2015, de 27 de abril, señala, bajo la rúbrica "Derecho de las víctimas a la protección" que: "Las autoridades y funcionarios encargados de la investigación, persecución y enjuiciamiento de los delitos adoptarán las medidas necesarias, de acuerdo con lo establecido en la Ley de Enjuiciamiento Criminal, para garantizar la vida de la víctima y de sus familiares, su integridad física y psíquica, libertad, seguridad, libertad e indemnidad sexuales, así como para proteger adecuadamente su intimidad y su dignidad, particularmente cuando se les reciba declaración o deban testificar en juicio, y para evitar el riesgo de su victimización secundaria o reiterada."

Por ello, intereso se acepte la petición y se acuerde la medida de alejamiento interesada y se requiera al/a la acusado/a para que no se aproxime a la víctima en los términos interesados.

Por todo ello,

SUPLICO A LA SECCIÓN:

Se admita el presente escrito y se acuerde la medida de alejamiento interesada y se requiera al/a la acusado/a para que no se aproxime a la víctima en los términos interesados.

En [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) No es obligatorio que la víctima se persone en el proceso penal para presentar este escrito. Puede hacerlo por sí misma y en base al art. 109.4 LECRIM este órgano judicial debería ofrecerle esta opción en la citación a juicio a fin de que pueda presentar, o no, este escrito.

(2) Este escrito puede presentarse tanto en la Sección de Instrucción o en la de Violencia sobre la Mujer si se tratara de acoso de pareja o ex pareja.

================================================================================
