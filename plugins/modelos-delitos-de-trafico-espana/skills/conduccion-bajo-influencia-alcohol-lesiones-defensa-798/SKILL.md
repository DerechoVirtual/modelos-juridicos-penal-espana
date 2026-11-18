---
name: conduccion-bajo-influencia-alcohol-lesiones-defensa-798
description: "Redacta el escrito «Conducción bajo la influencia del alcohol y lesiones: defensa con conformidad en el abreviado» (formulario 798 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción bajo la influencia del alcohol y lesiones: defensa con conformidad en el abreviado

> Formulario 0798 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- Califican las lesiones por el art. 147 CP (doloso); en un accidente por conducción etílica son lesiones imprudentes del art. 152.1 CP, que la LO 11/2022 reputa en todo caso imprudencia grave, y con esa pena debe hacerse la comparación del art. 382 CP.
- El art. 385 ter CP solo permite rebajar la pena de los delitos de los arts. 379, 383, 384 y 385; si por el art. 382 se impone la pena del delito de lesiones, su aplicación no está prevista en el texto legal.

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
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] FECHA

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 379 CP
- art. 382 y 147 CP
- art. 385 ter CP
- art. 382 CP
- art. 147 CP
- art. 784.3 LECrim
- art. 787 LECRIM
- art. 787 ter LECRIM
- arts. 147 CP
- art. 785 LECRIM
- art. 80 CP

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

### Formulario 0798 · Conducción bajo la influencia del alcohol y lesiones: defensa con conformidad en el abreviado

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Califican las lesiones por el art. 147 CP (doloso); en un accidente por conducción etílica son lesiones imprudentes del art. 152.1 CP, que la LO 11/2022 reputa en todo caso imprudencia grave, y con esa pena debe hacerse la comparación del art. 382 CP. · El art. 385 ter CP solo permite rebajar la pena de los delitos de los arts. 379, 383, 384 y 385; si por el art. 382 se impone la pena del delito de lesiones, su aplicación no está prevista en el texto legal.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la defensa en procedimiento abreviado por el que presenta su conformidad con la pena solicitada por la acusación por delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, en relación con el art. 382 y 147 CP (lesiones), aplicando el art. 385 ter CP, que permite rebajar la pena de prisión en un grado en atención a la menor entidad del riesgo causado, pudiendo así solicitar la suspensión de la ejecución de la pena por ser inferior a 2 años de prisión y cumplir el resto de requisitos legales de los arts. 80 y ss CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a del Ilustre Colegio de Procuradores de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD],, en representación del acusado/a, D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento / por el supuesto delito del art. 379 CP, en relación con el art. 382 CP y art. 147 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 y art. 784.3 LECrim (1), en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con la calificación de los hechos como el art. 379 CP, en relación con los arts. 147 CP y art. 382 CP, aplicando en esta conformidad el art. 385 ter CP, que permite rebajar la pena de prisión en un grado en atención a la menor entidad del riesgo causado.

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] de prisión y privación del derecho a conducir vehículos a motor y ciclomotores por tiempo de [DURACIÓN] a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

Se solicita se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss. que por la defensa se interesa, con ocasión del presente escrito, por concurrir los requisitos legales. (2)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma del acusado/a

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 y el art. 784.3 LECRIM se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) Con este escrito se aseguraría la suspensión de la ejecución de la pena y evitaría una pena superior que estaría sobre 1 año y 7 meses de prisión de no aplicarse el art. 385 ter CP o una mayor hasta tres años de prisión que sería el límite máximo a imponer al aplicarse el art. 147 CP en relación al art. 382 CP.

================================================================================
