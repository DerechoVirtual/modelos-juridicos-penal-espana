---
name: ciberbullying-conformidad-letrado-menor-acusacion-fiscal-673
description: "Redacta el escrito «Ciberbullying: conformidad del letrado del menor con la acusación del fiscal» (formulario 673 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ciberbullying: conformidad del letrado del menor con la acusación del fiscal

> Formulario 0673 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Letrado/a del/de la menor»; «…dida propuesta por el/la Fiscal es la de»; «…de la letra»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 169 CP
- art. 7 de la LO 5/2000
- art. 32 de la LO 5/2000
- art. 7.1 de la LO 5/2000

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

### Formulario 0673 · Ciberbullying: conformidad del letrado del menor con la acusación del fiscal

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el menor encausado en un proceso de menores y su letrado se conforman con la calificación de los hechos del fiscal de delito de amenazas por ciberbullying del art. 169 CP y a la pena solicitada.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Menores del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Letrado/a del/de la menor [COMPLETAR], inculpado/a en el procedimiento nº [Nº DE PROCEDIMIENTO] por delito de amenazas por ciberbullying, comparezco ante este órgano judicial y, como mejor proceda en Derecho, DIGO:

Que con fecha [FECHA] se me dio traslado del escrito de alegaciones del/de la Fiscal y del testimonio del expediente a efectos de formular escrito de alegaciones. La medida propuesta por el/la Fiscal es la de [COMPLETAR] de la letra [COMPLETAR] del art. 7 de la LO 5/2000 de la Responsabilidad Penal de los Menores (1) y esta defensa y el/la menor encausado/a nos hallamos conformes tanto con los hechos atribuidos en el citado escrito por la comisión de un delito de amenazas del art. 169 CP, en la modalidad de ciberbullying, como con la medida solicitada (2), por lo que, de acuerdo a lo dispuesto en el art. 32 de la LO 5/2000, se solicita el señalamiento de la comparecencia a efectos de conformidad que prevé este precepto.

Señala, así, el art. 32 de la LO 5/2000 de la Responsabilidad Penal de los Menores: "Si el escrito de alegaciones de la acusación solicitara la imposición de alguna o algunas de las medidas previstas en las letras e) a ñ) del apartado 1 del artículo 7, y hubiere conformidad del menor y de su letrado, así como de los responsables civiles, la cual se expresará en comparecencia ante el Juez de Menores en los términos del artículo 36, éste dictará sentencia sin más trámite."

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y señale día y hora para la celebración de comparecencia a efectos de conformidad con la medida solicitada por el/la Fiscal, con citación de mi defendido/a y de este/a Letrado/a.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma del/de la representante del/de la menor:

NOTAS DEL FORMULARIO

(1) Para que el menor y su Letrado puedan prestar su conformidad con la medida solicitada por el Fiscal, ésta debe ser alguna o algunas de las previstas en las letras e) a ñ) del art. 7.1 de la LO 5/2000.

(2) Este escrito es válido si no se ha personado la acusación particular en el procedimiento. En otro caso, habrá que entender que debe haber conformidad con la medida de mayor gravedad, por aplicación supletoria de las normas reguladoras del procedimiento abreviado.

El ciberbullying es el uso de los medios telemáticos (Internet, telefonía móvil y videojuegos online principalmente) para ejercer el acoso psicológico entre iguales. Un elemento exigente es que tiene que haber menores en ambos extremos del ataque para que se considere ciberbullying: si hay algún adulto, entonces estamos ante algún otro tipo de ciberacoso.

Las formas que adopta son muy variadas. (www.ciberbullying.com)

Según Álvaro ÉCIJA BERNAL (2017) es posible identificar siete categorías de acoso verbal y escrito a través de las nuevas tecnologías:

1. Flaming: Envío de mensajes violentos o que muestran enfado sobre una persona a un grupo o a esa persona vía email o SMS.
2. Acoso online: Envío continuado de mensajes ofensivos vía email o SMS a una persona.
3. Ciberstalking: Acoso online a través de amenazas de daño o intimidación físicas.
4. Denigración: Envío de información perjudicial, falsa y cruel sobre una persona a otra o publicación de la información en foros o redes sociales.
5. Suplantación de la persona: Simulación de la identidad de una persona y envío de información o subida de imágenes, videos o textos que agredan y hagan quedar mal a la víctima.
6. Outing: Subida de imágenes, videos o texto sobre una persona que contenga información privada o embarazosa.
7. Exclusión: Expulsión de un usuario de un grupo online formado en alguna plataforma.

================================================================================
