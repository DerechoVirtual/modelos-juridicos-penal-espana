---
name: narcotrafico-salud-publica-defensa-conformidad-abreviado-791
description: "Redacta el escrito «Narcotráfico (salud pública): defensa con conformidad en el abreviado» (formulario 791 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Narcotráfico (salud pública): defensa con conformidad en el abreviado

> Formulario 0791 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] PENA
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…n de dependientes a consumo de drogas de»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es igual o inferior a 2 años)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 368 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 785 LECRIM
- art. 20 CP
- art. 80 CP
- art. 80.5 CP

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

### Formulario 0791 · Narcotráfico (salud pública): defensa con conformidad en el abreviado

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en un procedimiento abreviado se conforma con la pena solicitada por la acusación por delito de tráfico de drogas del art. 368 CP y solicita al mismo tiempo la suspensión de la ejecución de la pena en base a los arts. 80 y ss del CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a (1) del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento abreviado / por el supuesto delito contra la salud pública del art. 368 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (2) y al art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con la calificación de los hechos como delito contra la salud pública del art. 368 CP.

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] de prisión, a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025), al concurrir la circunstancia del párrafo 2º del art. 368 CP en relación a la escasa entidad del hecho y la absoluta dependencia del/de la acusado/a a las drogas que, aunque no constituya eximente plena del art. 20 CP, sí que constituye atenuante reconocida en la petición fiscal y debe valorarse para rebajar la pena en un grado según el párrafo segundo del art. 368 CP [NOTA DE REVISIÓN: El art. 368 CP no tiene apartados numerados; la rebaja en grado por escasa entidad está en su párrafo segundo. Fuente: Código Penal, BOE-A-1995-25444, art. 368.].

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es igual o inferior a 2 años)

Se solicita se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se interesa con ocasión del presente escrito, por concurrir los requisitos legales. Y, además, aplicarse el art. 80.5 CP aportando con este escrito certificado del centro de deshabituación de dependientes a consumo de drogas de [COMPLETAR] para iniciar tratamiento de deshabituación. (3)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral, incluso después de evacuado el trámite de calificación.

(2) La defensa puede llegar a pactar una conformidad con la fiscalía y acusación y bajar la pena de 3 años a 1 año y 6 meses de prisión, por concurrir las circunstancias del párrafo 2º del art. 368 CP a las que la defensa puede apelar para conseguir una rebaja de la citada pena mínima de tres años del tipo penal que daría con el acusado en prisión por ser superior a 2 años. Además, para la suspensión de la ejecución de la pena para estos casos se aplicaría el art. 80.5 CP.

(3) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
