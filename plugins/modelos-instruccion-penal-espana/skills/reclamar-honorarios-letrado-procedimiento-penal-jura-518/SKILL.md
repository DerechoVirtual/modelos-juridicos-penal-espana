---
name: reclamar-honorarios-letrado-procedimiento-penal-jura-518
description: "Redacta el escrito «Reclamar los honorarios del letrado en un procedimiento penal (jura de cuentas)» (formulario 518 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reclamar los honorarios del letrado en un procedimiento penal (jura de cuentas)

> Formulario 0518 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde el 20-3-2024 (RDL 6/2023) el art. 35.4 LEC exige, si el cliente es persona física, aportar con la cuenta el contrato suscrito con él para que el juez controle de oficio las cláusulas abusivas.
- La impugnación por excesivos da traslado al abogado por cinco días y el decreto que fija la cantidad admite recurso directo de revisión (art. 35.2 LEC, redacción RDL 6/2023).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] IMPORTE
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…s jura de cuentas (1), contra mi cliente»; «… impugnación Teniendo la parte requerida»; «…, solicito se expida exhorto a»; «… por formulada reclamación de honorarios»; «…stas, bajo apercibimiento de apremio. En»; «…. Firma de Abogado/a:»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 35 LEC
- arts. 25 a 29 del RD 135/2021
- artículo 6.2.e) de la LO 5/2024
- artículo 35 de la LEC

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

### Formulario 0518 · Reclamar los honorarios del letrado en un procedimiento penal (jura de cuentas)

- Año del modelo: 2019
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (1); 12 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: Desde el 20-3-2024 (RDL 6/2023) el art. 35.4 LEC exige, si el cliente es persona física, aportar con la cuenta el contrato suscrito con él para que el juez controle de oficio las cláusulas abusivas. · La impugnación por excesivos da traslado al abogado por cinco días y el decreto que fija la cantidad admite recurso directo de revisión (art. 35.2 LEC, redacción RDL 6/2023).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Modelo de escrito promoviendo reclamación de honorarios de abogado, de conformidad con los arts. 35 LEC y 25 a 29 del Estatuto General de la Abogacía [NOTA DE REVISIÓN: En el Estatuto General de la Abogacía aprobado por RD 135/2021 el art. 44 regula los registros colegiales; los honorarios se regulan en los arts. 25 a 29, que son los que cita el cuerpo del escrito. Fuente: RD 135/2021, BOE-A-2021-4568, arts. 25 a 29 y 44.]

Actualizado conforme al RD 135/2021, de 2 de marzo, que aprueba el Estatuto General de la Abogacía, con entrada en vigor el 1 de julio de 2021.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Letrado/a de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en la Ejecutoria [Nº DE PROCEDIMIENTO] antes Juicio Oral nº [NÚMERO], ante este órgano judicial comparezco y como mejor proceda en Derecho, DIGO:

Que al amparo de lo dispuesto en el artículo 35 de la Ley de Enjuiciamiento Civil, y los arts. 25 a 29 del RD 135/2021, de 2 de marzo por el que se aprueba el Estatuto General de la Abogacía, mediante el presente escrito formulo reclamación de honorarios Antes jura de cuentas (1), contra mi cliente [COMPLETAR], en reclamación de la cantidad de [IMPORTE] €, que me son debidas como pago de los honorarios que devengué en el asunto, acreditados en la minuta de Letrado/a que adjunto y calculados conforme a los criterios orientativos de honorarios publicados por el colegio de la abogacía de [COLEGIO], permitidos por el artículo 6.2.e) de la LO 5/2024, del Derecho de Defensa.

Por ello, solicito se requiera al deudor para que pague dicha suma o impugne la cuenta, en el plazo de diez días, bajo apercibimiento de apremio si no pagare ni formulare impugnación

Teniendo la parte requerida [COMPLETAR] domicilio en [LOCALIDAD], solicito se expida exhorto a [COMPLETAR] en los términos interesados.

En su virtud,

SUPLICO A LA SECCIÓN

Que teniendo por presentado este escrito con la minuta detallada que se acompaña y con copia simple de todo ello, tenga por formulada reclamación de honorarios [COMPLETAR] contra mi cliente, en reclamación de la cantidad antes indicada, y se le requiera para que dentro del término de diez días las pague con las costas, bajo apercibimiento de apremio.

En [COMPLETAR].

Firma de Abogado/a: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) El llamado procedimiento de jura de cuentas en la anterior LEC de 1881, ahora reclamación de honorarios conforme a la actual LEC, es un procedimiento especial y privilegiado, mediante el que un abogado o un procurador pueden reclamar sus honorarios o derechos profesionales. No es un privilegio por razón de la persona, sino otorgado a los letrados en atención a su intervención en el pleito concreto en que han actuado (STC de 25 de marzo de 1993). Pero como tal privilegio de estos profesionales, comporta una facultad o derecho que su titular puede ejercitar o no. Nadie puede ser obligado a usar de un privilegio. El artículo 35 de la LEC no impone al letrado que utilice ese cauce procesal para reclamar sus honorarios, sino que dice que los letrados "podrán". Es decir, que es potestativo del letrado decidir el procedimiento que le interesa utilizar. Además, la renuncia al procedimiento privilegiado ningún perjuicio causa al deudor que, por el contrario, resulta favorecido, pues al acudir el letrado a un proceso monitorio, la oposición del deudor le abre la vía de un proceso ordinario donde de manera plena y sin las restricciones del procedimiento de jura de cuentas podrá hacer alegaciones y defender sus intereses.

La no sujeción a tasas judiciales del procedimiento de jura de cuentas del procurador (Consulta Vinculante V1369-13 de la DGT, de 23 de abril), ha de entenderse aplicable por analogía a la jura de cuentas de abogado.

================================================================================
