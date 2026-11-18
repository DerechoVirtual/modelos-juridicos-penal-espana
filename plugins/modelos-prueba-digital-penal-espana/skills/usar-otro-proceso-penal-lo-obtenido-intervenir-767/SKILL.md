---
name: usar-otro-proceso-penal-lo-obtenido-intervenir-767
description: "Redacta el escrito «Usar en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones» (formulario 767 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Usar en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones

> Formulario 0767 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- [ ] SEDE (4 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] NÚMERO (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…scubrimiento de la siguiente información»; «…de las presentes diligencias, puesto que»; «…la medida de intervención con respecto a»; «…de»

## Elecciones que hay que hacer

- de la correspondencia / de las comunicaciones
- 579 bis / 588 bis i

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de intervención de la correspondencia / Si se trata de intervención de las comunicaciones — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 579 bis LECRIM

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

### Formulario 0767 · Usar en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular solicita que se pueda utilizar la información obtenida por la intervención de la correspondencia o de las comunicaciones telefónicas o telemáticas en otro proceso penal, por ser relevantes para el proceso presente, conforme al artículo 588 bis i LECRIM, en relación con el artículo 579 bis 1 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS] en el presente procedimiento nº [Nº DE PROCEDIMIENTO], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de intervención de la correspondencia / Si se trata de intervención de las comunicaciones — el texto de cada opción no venía en el formulario original]

CONCLUSIONES

ÚNICA.-

He tenido conocimiento del descubrimiento de la siguiente información [COMPLETAR] a raíz de una medida de intervención [ELEGIR: de la correspondencia / de las comunicaciones] en el procedimiento nº [Nº DE PROCEDIMIENTO], que se tramita ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO]. Esta es importantísima para la tramitación de las presentes diligencias, puesto que [COMPLETAR] por lo que se interesa se aplique el artículo [ELEGIR: 579 bis / 588 bis i] de la LECRIM ). (1)

En tal sentido, es por lo que se interesa que se solicite a la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] que se deduzca testimonio de la información obtenida a raíz de la medida de intervención con respecto a [COMPLETAR] y se remita a este órgano judicial para su incorporación a la causa por serme útil para la defensa de los intereses de mi representado.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN

que se acuerde reclamar de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] la deducción de testimonio de los particulares necesarios obtenidos en la medida de intervención [ELEGIR: de la correspondencia / de las comunicaciones] de [COMPLETAR], incluyendo entre los particulares los antecedentes indispensables, en todo caso, la solicitud inicial para la adopción, la resolución judicial que la acuerda y todas las peticiones y resoluciones judiciales de prórroga recaídas en el procedimiento de origen.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) El artículo 579 bis LECRIM (para intervención de la correspondencia) y el artículo 588 bis i LECRIM (para la intervención de las comunicaciones), introducidos ambos por la LO 13/2015, vigente a partir del 6 de diciembre de 2015, permiten dar solución procesal a los hallazgos causales en una investigación penal que pueda tener eficacia en otro proceso penal, bien porque este no se haya iniciado todavía y permita iniciarlo con el testimonio de particulares, o bien en procedimiento ya iniciado y en el que una parte considere de interés ese hallazgo para la investigación y aportación de diligencias que coadyuven a la investigación, siendo este último el objetivo del presente formulario.

================================================================================
