---
name: alteracion-precios-mercado-defensa-conformidad-549
description: "Redacta el escrito «Alteración de precios en el mercado: defensa con conformidad» (formulario 549 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alteración de precios en el mercado: defensa con conformidad

> Formulario 0549 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La pena del art. 284.1 CP tras la LO 1/2019 es prisión de seis meses a seis años, multa de dos a cinco años (o del tanto al triplo del beneficio si es mayor) e inhabilitación especial de dos a cinco años, de imposición conjunta (BOE-A-2019-2363).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] ENTRE (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… la Abogacía de fecha 1 de abril de 2009»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 284.1 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 785 LECRIM
- art. 80 CP
- art. 284 CP

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

### Formulario 0549 · Alteración de precios en el mercado: defensa con conformidad

- Año del modelo: 2018
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 6 llamadas a nota sin texto retiradas; 8 campos de relleno marcados en blanco
- Avisos de la revisión: La pena del art. 284.1 CP tras la LO 1/2019 es prisión de seis meses a seis años, multa de dos a cinco años (o del tanto al triplo del beneficio si es mayor) e inhabilitación especial de dos a cinco años, de imposición conjunta (BOE-A-2019-2363).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la calificación de los hechos realizada por el fiscal como delito contra el mercado y los consumidores del art. 284.1 CP, al alterar los precios en el mercado mediante engaño.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia. A la Sección de Instrucción del Tribunal de Instancia deplaza nºD./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], acusados/as en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito del art. 284.1 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 [COMPLETAR] y el art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con la calificación de los hechos como alteración de precios en el mercado con engaño del art. 284.1 CP.En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [ENTRE] 6 meses y 6 años de prisión y multa de [NOTA DE REVISIÓN: Desde la LO 1/2019 el art. 284.1 CP castiga con prisión de seis meses a seis años, multa de dos a cinco años (o del tanto al triplo si es mayor) e inhabilitación especial de dos a cinco años; las penas son acumulativas. Fuente: Código Penal, BOE-A-1995-25444, art. 284.1 (LO 1/2019, BOE-A-2019-2363).] [ENTRE] 2 y 5 años a razón de [NOTA DE REVISIÓN: Multa de dos a cinco años del art. 284.1 CP vigente; procede añadir la inhabilitación especial para intervenir en el mercado financiero de dos a cinco años. Fuente: Código Penal, BOE-A-1995-25444, art. 284.1 (LO 1/2019, BOE-A-2019-2363).] [IMPORTE] euros por día y al pago de [IMPORTE] euros de indemnización a los/as querellantes, a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

Se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss. que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales. Por lo expuesto,

SUPLICO A LA SECCIÓN:Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:Firma del acusado/a: En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.
 Son tres las modalidades del delito del art. 284 CP, conforme a la redacción dada por LO 1/2019, de 20 de febrero, siendo la referida al presente formulario la del nº 1. Se puede referir a cualquier tipo de producto, pero exigiéndose que en el modus operandi de la acción se emplee violencia, amenaza o engaño, que es lo que en este caso se lleva a cabo con el fin de alterar los precios, en este caso para fijar uno igual pero con distinta calidad del producto ofertado a fin de conseguir distorsionar el mercado y causar pérdidas a los perjudicados por ofertar menos precio pero con rebajada calidad del producto, lo que distorsiona el mercado al perder éstos poder competitivo y con beneficio de los acusados.

No se exige como elemento objetivo la constatación del perjuicio, sino solo la alteración del precio que surge de la libre competencia.
 Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
