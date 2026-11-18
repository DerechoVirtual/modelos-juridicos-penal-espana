---
name: justicia-restaurativa-investigado-pide-derivar-causa-739
description: "Redacta el escrito «Justicia restaurativa: el investigado pide derivar la causa penal» (formulario 739 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Justicia restaurativa: el investigado pide derivar la causa penal

> Formulario 0739 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] LUGAR
- [ ] FECHA

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0739 · Justicia restaurativa: el investigado pide derivar la causa penal

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el investigado solicita al juez suspender el proceso penal y derivar el caso a proceso de justicia restaurativa, ya que ha reconocido los hechos en su declaración judicial y la víctima está de acuerdo, para luego poder presentar escrito de acusación junto con la fiscalía y solicita ya la suspensión de la ejecución de la pena por cumplir los requisitos del art. 84.1.1º CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la defensa de el/la investigado/a, D./Dña. [NOMBRE Y APELLIDOS], y en su nombre y representación en las DP nº [Nº DE PROCEDIMIENTO]/[AÑO] que se siguen por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS] ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Se interesa se derive el presente procedimiento a los servicios de justicia restaurativa, por el cauce previsto en el apartado 6 de la Disposición Adicional 9 de la LECRIM, en base a lo dispuesto en el apartado 5 de la misma, a cuyo tenor:

"El juez o el Tribunal, valorando las circunstancias del hecho, de la persona investigada, acusada o condenada y de la víctima, podrá, de oficio o a instancia de parte, remitir a las partes a un procedimiento restaurativo, salvo en los casos excluidos por ley. El inicio del procedimiento restaurativo en fase de instrucción no eximirá de la práctica de las diligencias indispensables para la comprobación de delito."

El procedimiento actual se sigue por delito de [DELITO], no estando excluido ex lege de la posibilidad de derivación a justicia restaurativa.

En este caso, mi representado/a ya ha reconocido los hechos en su declaración judicial y por ello intereso se nos cite a las partes ante los servicios de justicia restaurativa, dado que lo que constituye el interés de esta parte es pedir el debido perdón y satisfacer la indemnización económica a la que tiene derecho el perjudicado.

Igualmente, se interesa que, una vez sea firme el acuerdo de mediación, se pacte una conformidad con la fiscalía, solicitando ya la suspensión de la ejecución de la pena, conforme permite el art. 84.1.1º CP (1).

Por todo ello,

SUPLICO A LA SECCIÓN:

Se admita la remisión a los servicios de justicia restaurativa de las presentes diligencias, a cuyo fin el mediador designado proceda a citar por separado a denunciante y denunciado, para poder conseguir un acuerdo de reparación, facilitándose el acceso al contenido del procedimiento por parte del equipo de justicia restaurativa para llevar a cabo el mismo y con el conocimiento del contenido de la denuncia y de la declaración de esta parte, al objeto de pactar un acuerdo de satisfacción con la parte denunciante.

OTROSÍ 1º: Según lo previsto en la Disposición Adicional 9.6 LECRIM, el inicio del procedimiento restaurativo en fase de instrucción no eximirá de la práctica de las diligencias indispensables para la comprobación de delito, pero se solicita que se suspenda en lo sucesivo hasta el informe que emita al respecto el equipo de justicia restaurativa.

OTROSÍ 2º: Se ruega se dé traslado a la acusación particular de esta petición a los efectos de su aceptación y derivación a los servicios de justicia restaurativa.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito instado por el investigado será objeto de traslado a la víctima a fin de que manifieste su aceptación y de este proceso se derivaría una sentencia de conformidad, en su caso, de ser posible esta, atendiendo a la pena y aplicando el art. 84.1.1º CP para la suspensión de la ejecución de la pena.

================================================================================
