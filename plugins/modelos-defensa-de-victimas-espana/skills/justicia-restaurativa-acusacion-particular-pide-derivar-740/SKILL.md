---
name: justicia-restaurativa-acusacion-particular-pide-derivar-740
description: "Redacta el escrito «Justicia restaurativa: la acusación particular pide derivar la causa penal» (formulario 740 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Justicia restaurativa: la acusación particular pide derivar la causa penal

> Formulario 0740 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, a [FECHA]. Firma de Procurador/a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 5.1 k) Ley 4/2015
- art. 15.1 de la Ley 4/2015

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

### Formulario 0740 · Justicia restaurativa: la acusación particular pide derivar la causa penal

- Año del modelo: 2016
- Revisión 17-11-2026: 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima en un proceso penal solicita al juez que suspenda el proceso penal y lo derive a un proceso de justicia restaurativa para llegar a un acuerdo que poder trasladar a un escrito de acusación conjunto entre la víctima, el investigado y el fiscal, puesto que el investigado ya ha reconocido los hechos en su declaración judicial y lo que constituye el interés de la víctima es reclamar el perdón y que sea satisfecha la indemnización económica a la que tiene derecho.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular de D./Dña. [NOMBRE Y APELLIDOS] y en su nombre y representación en las DP nº [Nº DE PROCEDIMIENTO]/[AÑO] por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS], ante el este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, tras conversaciones entre la víctima del presente procedimiento penal, representación que ejerzo, y el investigado se está de acuerdo para que se inste la vía de la mediación penal.

Ello tiene encaje en el art. 5.1 k) Ley 4/2015, de 27 de abril, del Estatuto de la Víctima del delito, en donde se reconoce a las víctimas: "... k) Servicios de justicia restaurativa disponibles, en los casos en que sea legalmente posible."

Por ello, y no tratándose de un caso de violencia de género ni de violencia sexual, donde no es posible, por vedarse por el art. 3 de la L 4/2015, de 27 de abril, es por lo que se interesa se inicien los trámites para la mediación penal, ya que el art. 15.1 de la Ley 4/2015, de 27 de abril, señala que:

"1. Las víctimas podrán acceder a servicios de justicia restaurativa, en los términos que reglamentariamente se determinen, con la finalidad de obtener una adecuada reparación material y moral de los perjuicios derivados del delito, cuando se cumplan los siguientes requisitos:
a) el infractor haya reconocido los hechos esenciales de los que deriva su responsabilidad;
b) la víctima haya prestado su consentimiento, después de haber recibido información exhaustiva e imparcial sobre su contenido, sus posibles resultados y los procedimientos existentes para hacer efectivo su cumplimiento;
c) el infractor haya prestado su consentimiento;
d) el procedimiento de mediación no entrañe un riesgo para la seguridad de la víctima, ni exista el peligro de que su desarrollo pueda causar nuevos perjuicios materiales o morales para la víctima; y
e) no esté prohibida por la ley para el delito cometido."

Se interesa se admita la petición de derivación del presente procedimiento a los servicios de justicia restaurativa, por el cauce previsto en la Disposición Adicional 9.6 de la LECRIM, en base a lo dispuesto en la Disposición Adicional 9.5 LECRIM, a cuyo tenor:

"El juez o el Tribunal, valorando las circunstancias del hecho, de la persona investigada, acusada o condenada y de la víctima, podrá, de oficio o a instancia de parte, remitir a las partes a un procedimiento restaurativo, salvo en los casos excluidos por ley. El inicio del procedimiento restaurativo en fase de instrucción no eximirá de la práctica de las diligencias indispensables para la comprobación de delito."

Se interesa esta derivación para la adopción, en su caso, de un acuerdo de reparación,te, siempre y cuando se indemnice a la víctima del delito en la suma de [IMPORTE] euros resultante de los daños y perjuicios causados, incluyendo el daño moral, como resultado del delito de [DELITO] del que fue víctima el/la denunciante.

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita la remisión a los servicios de justicia restaurativa de las presentes diligencias, a cuyo fin el mediador designado proceda a citar por separado a denunciante y denunciado, para poder conseguir un acuerdo de reparación, facilitándose el acceso al contenido del procedimiento por parte del equipo de justicia restaurativa para llevar a cabo el mismo y con el conocimiento del contenido de la denuncia y de la declaración de esta parte, al objeto de pactar un acuerdo de satisfacción con la parte denunciada.

OTROSÍ 1º: Según lo previsto en la Disposición Adicional 9.6 LECRIM, el inicio del procedimiento restaurativo en fase de instrucción no eximirá de la práctica de las diligencias indispensables para la comprobación de delito, pero se solicita que se suspenda en lo sucesivo hasta el informe que emita al respecto el equipo de justicia restaurativa.

OTROSÍ 2º: Se ruega se dé traslado al acusado/a de esta petición a los efectos de su aceptación y derivación a los servicios de justicia restaurativa.

En [LUGAR], a [FECHA].

Firma de Procurador/a [COMPLETAR]:

================================================================================
