---
name: abandono-lugar-accidente-lesiones-imprudentes-trafico-505
description: "Redacta el escrito «Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa con conformidad» (formulario 505 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa con conformidad

> Formulario 0505 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…cir vehículos a motor y ciclomotores por»

## Elecciones que hay que hacer

- 152.1 / 152.2

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es de prisión inferior a 2 años)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 382 bis CP
- art. 152 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 382 bis del CP
- art. 785 LECRIM
- art. 80 CP
- art. 195 CP
- arts. 147.1, 149 y 150 CP
- art. 152.2 CP
- artículo 382 bis CP

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

### Formulario 0505 · Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa con conformidad

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la calificación de los hechos como delito de abandono del lugar del accidente del art. 382 bis CP y de lesiones imprudentes del art. 152 CP y con la petición de la pena solicitada por la fiscalía. Si se pacta una pena de prisión por debajo de los 2 años se solicitará también la suspensión de la ejecución de la pena.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D/Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1) y el art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con la calificación de los hechos como delito de abandono del lugar del accidente del art. 382 bis CP y de lesiones imprudentes del art. 152 CP. (2)

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] de prisión y privación del derecho a conducir vehículos a motor y ciclomotores por [COMPLETAR] por el delito de abandono del lugar del accidente del art. 382 bis del CP y por el delito del art. [ELEGIR: 152.1 / 152.2] CP con resultado de lesiones de los arts. 147.1, 149 o 150 CP la pena de multa de [IMPORTE] a razón de [IMPORTE] euros/día y responsabilidad personal subsidiaria de 1 día de prisión por cada dos cuotas impagadas (3) a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

Y ello en cuanto se ha procedido a la indemnización del perjuicio causado consistente en el pago de [IMPORTE] euros, que era el importe reclamado.

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es de prisión inferior a 2 años)

Se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales. (4)

Se procede a la entrega del permiso de conducir para el cumplimiento de la pena de privación del derecho a conducir vehículos de motor.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR]

Firma de Abogado/a	Firma del acusado/a

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) El art. 382 bis CP será el que atraiga ahora las conductas de "fuga del lugar" cuando el accidente sea causado por el conductor, ya que la omisión del 195 CP no lo exige. En este caso fue el conductor el que se marchó y fue el causante de los hechos. Es un delito de mayor gravedad penológica porque lleva aparejado pena de privación del permiso de conducir. Se aplica el art. 195 CP si la persona se halla desamparada y en peligro manifiesto y grave.

Existirá delito de fuga tanto si el accidente se produce por imprudencia grave, menos grave o leve del conductor, o, incluso, por caso fortuito sin culpa de éste y no se baja del vehículo para auxiliar al herido. Lo que se sanciona es la huida en realidad con independencia de la causa del accidente.

Debe causarse un siniestro del que se derivan muertes o lesiones de los arts. 147.1, 149 y 150 CP.

Existirá delito de fuga tanto si el accidente se produce por imprudencia grave, menos grave o leve del conductor, o, incluso, por caso fortuito sin culpa de éste y no se baja del vehículo para auxiliar al herido., eso sí, debe causarse un siniestro del que se derivan muertes o lesiones de los arts. 147.1, 149 o 150 CP.

La LO 11/2022, vigente desde el 15 de septiembre de 2022, modifica la redacción del delito de abandono del lugar del accidente del art. 382 bis CP. En vez de remitirse a las lesiones del art. 152.2 CP que, a su vez, reenviaba a las de los arts. 147.1, 149 y 150 CP, el propio artículo 382 bis CP se refiere concretamente a estos 3 últimos artículos. La diferencia es que esas lesiones ya no tienen que producirse sólo por imprudencia menos grave, requisito que prevé el art. 152.2 CP, al que ya no hay remisión.

Es posible el concurso real del delito del art. 382 bis CP con otro delito de tráfico que se haya cometido, en este caso con el de lesiones imprudentes del art. 152 CP.

(3) En este caso podría pactarse la conformidad por debajo de los dos años de prisión para conseguir la suspensión de la ejecución de la pena.

(4) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
