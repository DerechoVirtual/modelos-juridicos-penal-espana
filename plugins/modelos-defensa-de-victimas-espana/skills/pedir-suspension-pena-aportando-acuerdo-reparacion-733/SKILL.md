---
name: pedir-suspension-pena-aportando-acuerdo-reparacion-733
description: "Redacta el escrito «Pedir la suspensión de la pena aportando acuerdo de reparación (condenado)» (formulario 733 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la suspensión de la pena aportando acuerdo de reparación (condenado)

> Formulario 0733 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] COLEGIO
- [ ] DELITO
- [ ] FECHA (3 veces)
- [ ] PENA
- [ ] IMPORTE
- [ ] NOMBRE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…acusado/a en ejecutoria penal»; «…todo ello, SUPLICO A LA SECCIÓNA LA SALA»

## Elecciones que hay que hacer

- A la Sección de lo Penal del Tribunal de Instancia deplaza nºA la Audiencia Provincial de Sección

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

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

### Formulario 0733 · Pedir la suspensión de la pena aportando acuerdo de reparación (condenado)

- Año del modelo: 2017
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el condenado solicita que se le suspenda la ejecución de la pena al cumplirse los requisitos legales exigidos y haber firmado un acuerdo de reparación con la acusación.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR: A la Sección de lo Penal del Tribunal de Instancia deplaza nºA la Audiencia Provincial de Sección]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los tribunales del Ilustre Colegio de Procuradores de [COLEGIO] en su nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] acusado/a en ejecutoria penal [COMPLETAR] que se sigue en este órgano judicial por delito de [DELITO] comparezco y, como más procedente sea en derecho, DIGO:Que, con fecha [FECHA] se dictó sentencia en el presente procedimiento resultando mi representado/a condenado/a a la pena de [PENA] con declaración de responsabilidad civil por importe de [IMPORTE] a favor de D./Dña. [NOMBRE Y APELLIDOS]

Pues bien, tras el desarrollo del proceso restaurativo derivado del presente procedimiento, y con suspensión del trámite procedimental que se acordó por auto de fecha [FECHA] y ante la intervención del mediador D./Dña. [NOMBRE], Apellidosse firmó acuerdo de reparación entre las partes que se adjunta como documento nº 1.Por ello, y no tratándose de un caso de violencia de género ni de violencia sexual, en donde no es posible por tenerla vetada la LO 1/2004 [NOTA DE REVISIÓN: La prohibición figura hoy en el art. 89.9 LOPJ (LO 1/2025), que veda los medios adecuados de solución de controversias en los asuntos de las Secciones de Violencia sobre la Mujer (el art. 87 ter LOPJ, introducido por el art. 44 LO 1/2004, está suprimido), y en el art. 3.1 Ley 4/2015, que veda la mediación y la conciliación en violencia sexual y de género. Fuente: LOPJ, BOE-A-1985-12666, arts. 87 ter y 89.9; Ley 4/2015, BOE-A-2015-4606, art. 3.1.], es por lo que se interesa se admita y convalide el presente acuerdo y, en base a lo dispuesto en el art. 84.1.1º CP, y al concurrir los presupuestos para la suspensión de la ejecución de la pena, se acuerde la misma, al ser la pena impuesta inferior a los dos años, no concurrir antecedentes penales y haber satisfecho la responsabilidad civil como consta en el acuerdo de reparación.

Todo ello conforme a la Disposición Adicional 9.9 LECRIM que dice:"9. En caso de existir acuerdo, el órgano judicial, previa audiencia del Ministerio Fiscal, de las partes personadas y de la víctima del delito, por término de tres días, valorando los acuerdos a los que las partes hayan llegado, las circunstancias concurrentes y el estado del procedimiento, podrá:...e) Resolver sobre la suspensión de la ejecución de la pena privativa de libertad, valorando el resultado del procedimiento restaurativo para el establecimiento de las condiciones, medidas u obligaciones de la suspensión; o, en su caso, sobre el contenido de los trabajos en beneficio de la comunidad."Por todo ello,

SUPLICO A LA SECCIÓNA LA SALA [COMPLETAR]:Se admita el presente escrito y se tenga por efectuadas las alegaciones y se acuerde la suspensión de la ejecución de la pena dando por válido y eficaz el acuerdo de reparación adjunto.

En [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

================================================================================
