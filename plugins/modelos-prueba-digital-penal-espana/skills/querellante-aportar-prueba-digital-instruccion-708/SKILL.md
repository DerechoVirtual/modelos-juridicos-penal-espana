---
name: querellante-aportar-prueba-digital-instruccion-708
description: "Redacta el escrito «Querellante: aportar prueba digital en la instrucción» (formulario 708 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Querellante: aportar prueba digital en la instrucción

> Formulario 0708 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…/a a mi representado/a por medio del que»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 299.2 LEC
- arts. 383 a 384 LEC
- Ley 6/2020

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

### Formulario 0708 · Querellante: aportar prueba digital en la instrucción

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (2); 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el querellante aporta en la instrucción, después de la querella y antes del escrito de acusación, una prueba obtenida por medios tecnológicos, en base al artículo 299.2 LEC, aplicable supletoriamente al proceso penal.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS] querellante en las diligencias previas nº [Nº DE PROCEDIMIENTO], en las que aparece como investigado/a D./Dña. [NOMBRE Y APELLIDOS] por el supuesto delito de [DELITO] comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, por medio del presente escrito, procedemos a aportar una prueba digital consistente en (1) (2)

A diferencia del proceso civil donde se recoge en el artículo 299.2 LEC que "2. También se admitirán, conforme a lo dispuesto en esta Ley, los medios de reproducción de la palabra, el sonido y la imagen, así como los instrumentos que permiten archivar y conocer o reproducir palabras, datos, cifras y operaciones matemáticas llevadas a cabo con fines contables o de otra clase, relevantes para el proceso" en el proceso penal debe efectuarse una remisión a este precepto para la aportación de la prueba digital, que en este caso lo verificamos por medio de la presentación, junto con el presente escrito, del soporte papel de la transcripción del contenido de la conversación enviada por el/a querellado/a a mi representado/a por medio del que [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y se tenga por aportada la prueba digital consistente en [DESCRIBIR] y que por medio del letrado de la administración de justicia se designe día y hora para proceder a la adveración del teléfono móvil donde se recibió el mensaje. Se interesa, también, se admita la aportación de la prueba y se tenga por admitida para la proposición de prueba aportada en la fase de instrucción al formular el escrito de acusación particular.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Son tres las fases de la prueba digital (Joaquín DELGADO MARTÍN):

1. Obtención de la prueba: se refiere al acceso a las fuentes de la prueba electrónica, es decir, a la obtención de la información o datos por las partes (o por la autoridad pública en el proceso penal) antes de su aportación al proceso. Se trata de acceder a la información o datos producidos o almacenados en un dispositivo electrónico, o bien transmitidos en forma electrónica a través de redes de comunicación abiertas o restringidas como Internet, telefonía fija, móvil u otras.
2. Incorporación al proceso de la información o datos obtenidos que sean relevantes para la acreditación de hechos. Estos datos han de tener entrada en el proceso a través de un concreto medio probatorio admitido por el ordenamiento; y ha de ser respetado el procedimiento que, para el concreto medio de prueba, sea contemplado por la respectiva legislación procesal para ejercitar válidamente el derecho a la prueba.
3. Valoración de la información o datos por el Juez o Tribunal de enjuiciamiento. Si se cumplen los requisitos de obtención e incorporación de la prueba electrónica al proceso, ésta puede desplegar eficacia probatoria siendo objeto de valoración por parte del Juez o Tribunal de conformidad con las reglas de la sana crítica (sistema de libre valoración de la prueba).

(2) La aportación al proceso de la prueba digital.

Los datos contenidos en un dispositivo electrónico han de ser aportados al proceso en un soporte determinado, lo que determinará el medio de prueba utilizado. En principio, todos los medios probatorios previstos por la Ley son aptos para incorporar al proceso los datos electrónicos.

En primer lugar, su contenido puede ser impreso en formato papel y presentado al proceso como un documento en soporte papel, resultando de aplicación el régimen jurídico de la prueba documental.

En segundo término, pueden ser incorporados al proceso mediante la aportación del propio documento electrónico, es decir, a través de la incorporación de los datos contenidos en soporte electrónico; resultando de aplicación el régimen jurídico de la prueba de instrumentos electrónicos del artículo 299.2 LEC que se contiene en los arts. 383 a 384 LEC y en la Ley 6/2020, de 11 de noviembre, reguladora de determinados aspectos de los servicios electrónicos de confianza.

================================================================================
