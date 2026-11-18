---
name: violencia-sobre-mujer-personacion-victima-diligencias-376
description: "Redacta el escrito «Violencia sobre la Mujer: personación de la víctima en diligencias previas» (formulario 376 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violencia sobre la Mujer: personación de la víctima en diligencias previas

> Formulario 0376 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…riodo de convivencia. 2) Pericial, de Dª»; «…usa el informe médico emitido por el Dr.»; «…, Médico del Centro Hospitalario de»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 311 y 761 de la LECrim
- art. 24 de la CE

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

### Formulario 0376 · Violencia sobre la Mujer: personación de la víctima en diligencias previas

- Año del modelo: 2021
- Revisión 17-11-2026: 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE DOCUMENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima de un delito de violencia de género se persona en las diligencias previas que se siguen ante la Sección de Violencia sobre la Mujer para ejercer la acusación particular, conforme a los arts. 109, 109 bis y 761 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A],como consta en escritura de poder inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme, acompañando certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada, comparezco y, como mejor proceda en derecho, DIGO:

Que en la representación de la víctima que ostento me persono como ACUSACIÓN PARTICULAR, de conformidad con lo dispuesto en el art. 109 y 109 bis de la LECrim, solicitando que se entiendan con esta parte las sucesivas actuaciones en el modo y forma previsto por la Ley y, a la vez, al amparo de lo dispuesto en los arts. 311 y 761 de la LECrim., esta parte PROPONE la práctica de las siguientes

DILIGENCIAS

PRIMERA.- Con carácter previo, y a efectos de proposición y práctica de diligencias de investigación en la fase de instrucción, invocamos el art. 24 de la CE por cuanto que nos encontramos ante un proceso de violencia de género, donde la doctrina constitucional expresada en la STC 87/2020, de 20 de julio, ha destacado que la investigación penal concretamente desplegada ha de satisfacer el derecho a la tutela judicial efectiva de quien se encuentra en posición de víctima en supuestos de violencia de género o cometida en un entorno familiar o afectivo, para lo que debe profundizar sobre los hechos denunciados. De ello se deriva un canon reforzado que exige que en casos como el de este procedimiento, donde existe la sospecha fundada de delito, se practiquen otras diligencias de investigación que, complementando esos testimonios enfrentados de las partes unidas por una relación de afectividad, presente o pasada, permitan ahondar en los hechos descartando o confirmando aquella sospecha inicial. De ahí que, según se expresa en la citada STC 87/2020, de 20 de julio, el deber de diligencia del órgano judicial requiere abundar en la investigación allí donde no se hayan agotado las posibilidades razonables de indagación sobre los hechos de apariencia delictiva.

En este caso, el investigado ha venido realizando de forma continuada y permanente una conducta de maltrato denunciada por mi representada, cuya ocultación en el tiempo se ha producido al desarrollarse en el ámbito de la convivencia marital, de ahí que nos encontremos con las dificultades que pone de manifiesto la doctrina constitucional, a cuyo efecto se proponen las diligencias instructoras que se dirán al ser imprescindibles para el esclarecimiento de los hechos.

SEGUNDA.- Atendido lo anterior, se proponen las siguientes diligencias de prueba, las cuales son necesarias para el total esclarecimiento de los hechos:

1) Testifical de D./Dña. [NOMBRE Y APELLIDOS] y de D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], quienes, como vecinos de la vivienda contigua a la de mi representada, han sido testigos presenciales y de referencia de las agresiones y amenazas de las que ha sido víctima mi representada. de forma constante durante el periodo de convivencia.
2) Pericial, de Dª [COMPLETAR], psicóloga especializada en casos de violencia de género, quien ha asistido a la víctima desde hace y ha emitido informe sobre su evolución, estado y secuelas, el cual se acompaña a este escrito como documento número [Nº DE DOCUMENTO], solicitando que comparezca ante el Juez, a fin de que ratifique y, en su caso, aclare y amplíe el informe emitido, para acreditar la situación que ha padecido la víctima y la que presenta en la actualidad.
3) Documental, a fin de que se incorpore a la causa el informe médico emitido por el Dr. [COMPLETAR], Médico del Centro Hospitalario de [COMPLETAR], donde se atendió a mi representada por las lesiones sufridas el día [FECHA], fecha de última de las agresiones denunciadas.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que acompaño, me tenga por personado y parte en la condición de acusación particular, entendiéndose con esta representación las sucesivas diligencias en el modo y forma prevenido por la Ley, y por propuestas las anteriores diligencias, acordando su admisión y práctica con citación de esta parte.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
