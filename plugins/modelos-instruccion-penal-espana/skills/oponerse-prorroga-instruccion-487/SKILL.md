---
name: oponerse-prorroga-instruccion-487
description: "Redacta el escrito «Oponerse a la prórroga de la instrucción» (formulario 487 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Oponerse a la prórroga de la instrucción

> Formulario 0487 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] NÚMERO (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…otar que: Que se tenga que llevar a cabo»; «…estigación, ya que para ello se exigiría»

## Elecciones que hay que hacer

- transformación en procedimiento abreviado / conclusión del sumario

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- (Si la prórroga la insta el Juez de oficio)…
- (Si la prórroga la insta el Fiscal)…
- (Si la prórroga la insta la parte contraria)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 324 LECRIM
- art. 324.1 de la Ley de Enjuiciamiento Criminal
- artículo 324.1 de la Ley de Enjuiciamiento Criminal
- art. 324.1 LECRIM
- art. 637 LECrim
- art. 641 LECrim
- art. 324.4 LECRIM

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

### Formulario 0487 · Oponerse a la prórroga de la instrucción

- Año del modelo: 2019
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que una de las partes en un proceso penal se opone a que se prorrogue la instrucción de una causa, interesada por el Juez, el Fiscal o por la otra parte, conforme al art. 324 LECRIM, según regulación dada por L 2/2020, de 27 de julio, vigente a partir del 29 de julio de 2020.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales (col. nº [NÚMERO]), en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS] (col. nº [NÚMERO]), como ya tengo acreditado, ante este órgano judicial comparezco en el procedimiento nº [Nº DE PROCEDIMIENTO] por el delito de [DELITO] y, en términos de Derecho,

DIGO:

PRIMERO.-

[OPCIONAL — incluir si procede]

(Si la prórroga la insta el Juez de oficio)

Que, conforme a lo dispuesto en el art. 324.1 de la Ley de Enjuiciamiento Criminal, se ha instado por el Juez la prórroga de la instrucción por seis meses, al estar próximo a concluir el plazo máximo de doce meses de la fase de investigación, en virtud de los siguientes motivos:

[OPCIONAL — incluir si procede]

(Si la prórroga la insta el Fiscal)

Que, conforme a lo dispuesto en el artículo 324.1 de la Ley de Enjuiciamiento Criminal, se ha presentado escrito por el Ministerio Fiscal instando la prórroga de la instrucción por seis meses, al estar próximo a concluir el plazo máximo de doce meses de la fase de investigación, en virtud de los siguientes motivos:

[OPCIONAL — incluir si procede]

(Si la prórroga la insta la parte contraria)

Que, conforme a lo dispuesto en el artículo 324.1 de la Ley de Enjuiciamiento Criminal, se ha presentado escrito por la representación de D./Dña. [NOMBRE Y APELLIDOS] instando la prórroga de la instrucción por seis meses, al estar próximo a concluir el plazo máximo de doce meses de la fase de investigación, en virtud de los siguientes motivos:

SEGUNDO.- Se ha dado traslado a esta parte del escrito de la fiscalía, y/o de la otra parte dada la preceptiva audiencia a las partes, antes de resolver ante la petición de prórroga.

En este estado de cosas, resulta evidente que no es preciso la necesidad de que se prorrogue por el plazo para instruir, puesto que debemos hacer notar que:

Que se tenga que llevar a cabo [COMPLETAR] no conlleva que se tenga que prorrogar la investigación, ya que para ello se exigiría [COMPLETAR]. Por ello, debe cerrarse la fase previa de la investigación con el material practicado y, en su caso, procederse al dictado del archivo de las actuaciones, que es lo que se postula, o el dictado de continuación de las diligencias mediante el auto de [ELEGIR: transformación en procedimiento abreviado / conclusión del sumario], con los medios de investigación llevados hasta este momento, y sin que sea posible extender por mayor plazo esta fase previa, al haberse cumplido el plazo máximo de doce meses previsto en el art. 324.1 LECRIM.

Está claro que en ningún caso el mero transcurso de los plazos máximos fijados dará lugar al archivo de las actuaciones si no concurren las circunstancias que determinan legalmente el sobreseimiento libre (art. 637 LECrim) o el sobreseimiento provisional (art. 641 LECrim). Pero, en este caso entendemos que sí concurren, dado que

En caso subsidiario, el art. 324.4 LECRIM señala que «el juez concluirá la instrucción cuando entienda que ha cumplido su finalidad».

No cabe, en consecuencia, acordar la prórroga del plazo de la instrucción, ya que no concurren causas que lo justifican, suponiendo, nada más, que una petición de prórroga sin causa legal que lo ampare, dado que se han acabado los tiempos en donde la fase de investigación se podría eternizar con la configuración de una permanente consideración del imputado, por lo que la circunstancia de que en la actualidad se denomine investigado no permite mantener en esta situación a la persona contra la que se dirige la investigación, salvo causa justificada, y para diligencias relevantes, que no concurren en el presente caso.

Por todo lo anterior,

SUPLICO A LA SECCIÓN:

Que, teniendo por presentado este escrito, con las copias que lo acompañan, lo admita y que se acuerde la no prórroga del plazo de instrucción, denegándose la petición formulada y procederse al archivo de las diligencias o, en su defecto, a la conclusión de la instrucción.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
