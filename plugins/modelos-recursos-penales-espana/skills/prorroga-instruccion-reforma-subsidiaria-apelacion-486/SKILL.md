---
name: prorroga-instruccion-reforma-subsidiaria-apelacion-486
description: "Redacta el escrito «Prórroga de la instrucción: reforma y subsidiaria apelación» (formulario 486 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prórroga de la instrucción: reforma y subsidiaria apelación

> Formulario 0486 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NÚMERO (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (6 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tablecido en los artículos 216, 217, 222»; «…de doce meses, por las siguientes causas»; «…y por faltar las siguientes diligencias»; «…ia para la investigación se justifica en»; «…l auto de que se tenga que llevar a cabo»; «…ligencia para la instrucción de la causa»; «…, ya que»

## Elecciones que hay que hacer

- procedimiento abreviado / conclusión del sumario

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (En caso de recurso en procedimiento abreviado)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 324 LECRIM
- art. 324.1 LECRIM
- artículo 324 LECRIM
- art. 637 LECrim
- art. 641 LECrim
- art. 324.4 LECRIM
- art. 766.4 LECrim
- art. 766.3 LECrim

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

### Formulario 0486 · Prórroga de la instrucción: reforma y subsidiaria apelación

- Año del modelo: 2019
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de reforma de cualquiera de las partes en un proceso, y subsidiario de apelación, si no se admite el de reforma, contra auto por el que se acuerda la prórroga de una instrucción por 6 meses, conforme al art. 324 LECRIM, según regulación dada por L 2/2020, de 27 de julio, vigente a partir del 29 de julio de 2020.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales (col. nº [NÚMERO]), en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS] (col. nº [NÚMERO]), como ya tengo acreditado, ante el órgano judicial comparezco en el procedimiento nº [Nº DE PROCEDIMIENTO] por el delito de [DELITO] y, en términos de Derecho, DIGO:

Con fecha [FECHA] le ha sido notificado a esta parte el auto de fecha [FECHA] por el que se acordaba la prórroga de la instrucción por 6 meses y estimándolo perjudicial y gravoso para mi representado/a, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado interpongo en tiempo y forma recurso de reforma, y subsidiario de apelación, al amparo de lo establecido en los artículos 216, 217, 222 [COMPLETAR] y 766 LECRIM(El 766 en caso de recurso en el procedimiento abreviado), con base en los siguientes:

HECHOS

ÚNICO.-

Que, con fecha [FECHA] se dictó auto motivado de prórroga de la instrucción al cumplirse el día [FECHA] el plazo máximo de doce meses, por las siguientes causas [COMPLETAR] y por faltar las siguientes diligencias [COMPLETAR] cuya relevancia para la investigación se justifica en [COMPLETAR].

FUNDAMENTOS DE DERECHO

ÚNICO.-

Esta representación se opuso a la prórroga de la instrucción en la preceptiva audiencia de las partes:

Lo contemplado en el auto de que se tenga que llevar a cabo [COMPLETAR] no conlleva que se tenga que prorrogar la investigación, ya que no se ha justificado suficientemente la relevancia de dicha diligencia para la instrucción de la causa [COMPLETAR], ya que [COMPLETAR].

Por ello, se interpone el presente recurso de reforma postulando que debe cerrarse la fase previa de la investigación con el material practicado y, en su caso, procederse al dictado del archivo de las actuaciones, que es lo que se postula, o el dictado de continuación de las diligencias mediante el auto de transformación en [ELEGIR: procedimiento abreviado / conclusión del sumario], con los medios de investigación llevados hasta este momento, y sin que sea posible extender por mayor plazo esta fase previa, al haberse cumplido el plazo de 12 meses sin que concurran los presupuestos habidos en el art. 324.1 LECRIM, por cuanto lo contrario suponer ir en contra de un proceso sin dilaciones indebidas.

Está claro que en ningún caso el mero transcurso de los plazos máximos fijados en este artículo 324 LECRIM dará lugar al archivo de las actuaciones si no concurren las circunstancias que determinan legalmente el sobreseimiento libre (art. 637 LECrim) o el sobreseimiento provisional (art. 641 LECrim). Pero en este caso entendemos que sí concurren dado que

En caso subsidiario, el art. 324.4 LECRIM señala que «el juez concluirá la instrucción cuando entienda que ha cumplido su finalidad».

No cabe, en consecuencia, acordar la prórroga del plazo de la instrucción, ya que no concurren causas que lo justifican, suponiendo, nada más, que una petición de prórroga sin causa legal que lo ampare, dado que se han acabado los tiempos en donde la fase de investigación se podría eternizar con la configuración de una permanente consideración del imputado, por lo que la circunstancia de que en la actualidad se denomine investigado no permite mantener en esta situación a la persona contra la que se dirige la investigación, salvo causa justificada, y para diligencias relevantes, que no concurren en el presente caso.

Por todo lo anterior,

SUPLICO A LA SECCIÓN:

Que teniendo por presentado este recurso de reforma contra el auto de fecha [FECHA], con las copias que lo acompañan, lo admita y que se acuerde la reforma del auto dictado acordándose la no prórroga del plazo de instrucción, y procederse al archivo de las diligencias, o, en su defecto, a la conclusión de la instrucción.

[OPCIONAL — incluir si procede]

(En caso de recurso en procedimiento abreviado)

PRIMER OTROSÍ DIGO: Que, en caso de desestimarse total o parcialmente el recurso de reforma, solicito que se conceda nuevo traslado a esta parte por plazo de cinco días a los efectos prevenidos en el art. 766.4 LECrim.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que tenga por hecha la anterior manifestación.

SEGUNDO OTROSÍ DIGO: Que, en caso de tramitarse la apelación interpuesta con carácter subsidiario, designo los siguientes particulares para que sean remitidos a la Audiencia Provincial para la resolución del recurso, de acuerdo con lo establecido en el art. 766.3 LECrim:

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
