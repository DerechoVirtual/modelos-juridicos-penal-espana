---
name: intervenciones-telefonicas-negarse-dar-juez-patron-movil-61
description: "Redacta el escrito «Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado» (formulario 61 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado

> Formulario 0061 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…éfono móvil. Señala el art. 11 LOPJ que:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 18.3 CE
- art. 18.1 CE
- art. 11 LOPJ

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

### Formulario 0061 · Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado

- Año del modelo: 2024
- Revisión 17-11-2026: 6 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 56) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que se presenta oposición a la entrega al órgano judicial del patrón de un teléfono móvil sin existir la debida base previa de investigación suficiente que permita tal medida de injerencia, como diligencia derivada de prueba ilícita en la medida de intervención telefónica, ex art. 11 LOPJ.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], como consta acreditado en las diligencias número [NÚMERO], ante este órgano judicial comparezco y como mejor en derecho proceda,

DIGO:

Que con fecha [FECHA], se me ha interesado la entrega del patrón del teléfono móvil para el volcado de su contenido, en las presentes diligencias previas a raíz del auto de fecha [FECHA], por el que se acordaron las intervenciones telefónicas y, por medio de la presente, interesamos la nulidad del citado auto de intervención telefónica, en base a que se acordó la medida de injerencia sin una previa de investigación policial suficiente que habilitara la citada medida de intervención telefónica, siendo por ello meramente prospectiva y, como consecuencia de ello, la petición de entrega del teléfono móvil para el volcado del contenido del mismo como prueba derivada de la ilícita.

Como señala el Tribunal Supremo, STS 302/2024 de 10 de abril, Rec. 10428/2023: "la descripción de los indicios del oficio policial debe considerarse suficiente y habilitante para el dictado del auto. Lo que debe analizarse es, pues, la "suficiencia" de la investigación. El carácter prospectivo del oficio policial en el sentido de que lo que se pretende es que con poca base de investigación previa se pida la ayuda del juez para "comprobar" si, en efecto, el delito se está cometiendo daría lugar a la nulidad de las pruebas por ilicitud ante la insuficiencia del oficio y el corolario auto habilitante."

En este caso no ha habido base suficiente para la investigación, y ello ha determinado que se inste la intervención telefónica para comprobar si se está cometiendo algún delito, lo que da lugar al carácter prospectivo de la medida de injerencia adoptada judicialmente. De ahí que la petición de la entrega patrón del teléfono móvil deviene prueba ilícita al ser prueba derivada en conexión de antijuricidad con la medida de intervención telefónica acordada.

No existe tampoco la debida proporcionalidad de la medida de injerencia al tener que preservarse el secreto de las comunicaciones y suponer una vulneración constitucional ex art. 18.3 CE y el derecho a la intimidad personal del art. 18.1 CE, al interesar la entrega de un teléfono móvil sin existir la debida base previa de investigación suficiente que permita tal medida de injerencia en el carácter personal del contenido de un teléfono móvil.

Señala el art. 11 LOPJ que: [COMPLETAR]

"1. En todo tipo de procedimiento se respetarán las reglas de la buena fe. No surtirán efecto las pruebas obtenidas, directa o indirectamente, violentando los derechos o libertades fundamentales."

Con ello, deviene nula tanto la medida de intervención telefónica como la petición de entrega del teléfono móvil para su volcado, dada la ilicitud de la medida de injerencia adoptada sin soporte de investigación previo, por lo que la entrega del teléfono móvil se lleva a cabo con carácter prospectivo, que está prohibido ex art. 11 LOPJ.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y me tenga por opuesto a la medida de entrega del teléfono móvil como diligencia derivada de prueba ilícita en la medida de intervención telefónica, planteando desde este momento la nulidad de la citada medida y el carácter de prueba ilícita de la acordada y la presente petición a la que expresamos oposición formal.

Es Justicia que pido en [LUGAR].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
