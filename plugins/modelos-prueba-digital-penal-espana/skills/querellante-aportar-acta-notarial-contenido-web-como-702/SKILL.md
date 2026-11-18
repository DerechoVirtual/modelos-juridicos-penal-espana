---
name: querellante-aportar-acta-notarial-contenido-web-como-702
description: "Redacta el escrito «Querellante: aportar acta notarial del contenido de una web como prueba preconstituida» (formulario 702 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Querellante: aportar acta notarial del contenido de una web como prueba preconstituida

> Formulario 0702 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, Procurador/a»; «…or medio de internet, y en la página web»; «…por el que nos dirigimos a la Notaría de»; «…l respecto al contenido de la página web»

## Elecciones que hay que hacer

- atentan contra su honor, su intimidad y su propia imagen / pueden ser constitutivas de un delito de odio

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

### Formulario 0702 · Querellante: aportar acta notarial del contenido de una web como prueba preconstituida

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el querellante aporta, después de la querella, acta notarial acreditativa del contenido de una página web, como prueba preconstituida ante la posibilidad de que desaparezca, al ser el instrumento a través del cual se puede haber cometido un delito contra el honor, la intimidad y la propia imagen o un delito de odio.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a [COMPLETAR] de los Tribunales en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], querellante en las diligencias previas nº [Nº DE PROCEDIMIENTO] en las que aparece como investigado/a D./Dña. [NOMBRE Y APELLIDOS] por el supuesto delito de D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, por medio de la presente, realizo las siguientes

ALEGACIONES

Con fecha [FECHA] mi representado/a comprobó que, por medio de internet, y en la página web [COMPLETAR], (1) utilizada por el/la querellado/a, se estaban divulgando afirmaciones y manifestaciones que [ELEGIR: atentan contra su honor, su intimidad y su propia imagen / pueden ser constitutivas de un delito de odio], motivo por el que nos dirigimos a la Notaría de [COMPLETAR] a fin de que levantara acta notarial del contenido de estas afirmaciones de el/la querellado/a y. sobre todo, a fin de preconstituir prueba sobre estos hechos ante la previsibilidad de que pudiera hacerlos desaparecer. (2)

Es por ello, por lo que se sirve aportar en este escrito el acta notarial que actúa como documental respecto a la prueba digital del uso de internet, que es el medio por el que se ha realizado la difusión de las manifestaciones del querellado, que quedan así probadas, no habiéndose aportado en su momento con el escrito de querella, y haciéndolo por medio de este escrito, a fin de evitar la destrucción de pruebas que podría llevar a efecto el querellado, lo que se articula por la vía del artículo 299.2 LEC, de aplicación supletoria en el proceso penal en materia de prueba tecnológica.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y se tenga por aportada acta notarial respecto al contenido de la página web [COMPLETAR] utilizada por el/la querellado/a y se una a las presentes diligencias previas como documental.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) La dificultad de aportar al proceso "el contenido de una página web" hace que el recurso a un acta notarial pueda permitir aportar al proceso penal lo que constaba en ella y que era el instrumento digital para cometer el delito denunciado.

Son tres las fases de la prueba digital (Joaquín DELGADO MARTÍN):

1. Obtención de la prueba: se refiere al acceso a las fuentes de la prueba electrónica, es decir, a la obtención de la información o datos por las partes (o por la autoridad pública en el proceso penal) antes de su aportación al proceso. Se trata de acceder a la información o datos producidos o almacenados en un dispositivo electrónico, o bien transmitidos en forma electrónica a través de redes de comunicación abiertas o restringidas como Internet, telefonía fija, móvil u otras.
2. Incorporación al proceso de la información o datos obtenidos que sean relevantes para la acreditación de hechos. Estos datos han de tener entrada en el proceso a través de un concreto medio probatorio admitido por el ordenamiento; y ha de ser respetado el procedimiento que, para el concreto medio de prueba, sea contemplado por la respectiva legislación procesal para ejercitar válidamente el derecho a la prueba.
3. Valoración de la información o datos por el Juez o Tribunal de enjuiciamiento. Si se cumplen los requisitos de obtención e incorporación de la prueba electrónica al proceso, ésta puede desplegar eficacia probatoria siendo objeto de valoración por parte del Juez o Tribunal de conformidad con las reglas de la sana crítica (sistema de libre valoración de la prueba).

(2) La aportación al proceso de la prueba digital.

Los datos contenidos en un dispositivo electrónico han de ser aportados al proceso en un soporte determinado, lo que determinará el medio de prueba utilizado. En principio, todos los medios probatorios previstos por la Ley son aptos para incorporar al proceso los datos electrónicos.

En primer lugar, su contenido puede ser impreso en formato papel y presentado al proceso como un documento en soporte papel, resultando de aplicación el régimen jurídico de la prueba documental.

En segundo término, pueden ser incorporados al proceso mediante la aportación del propio documento electrónico, es decir, a través de la incorporación de los datos contenidos en soporte electrónico; resultando de aplicación el régimen jurídico de la prueba de instrumentos electrónicos del artículo 299.2 LEC que se contiene en los arts. 383 a 384 LEC y en la Ley 6/2020, de 11 de noviembre, reguladora de determinados aspectos de los servicios electrónicos de confianza.

================================================================================
