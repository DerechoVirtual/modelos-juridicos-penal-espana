---
name: revenge-porn-alegaciones-letrado-menor-acusado-513
description: "Redacta el escrito «Revenge porn: alegaciones del letrado del menor acusado» (formulario 513 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revenge porn: alegaciones del letrado del menor acusado

> Formulario 0513 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] NÚMERO
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o/a que actúa en defensa del/de la menor»; «…ión penal no hay participación. CUARTA.-»; «… alguna. En virtud de ello, SE INTERESA:»; «…Director/a del centro escolar»; «…erde la no publicidad de los menores. En»

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Examen del/de la menor encausado/a.…
- .- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental mediante la lectura de los siguientes folios de expediente:…
- Y hace suya la prueba propuesta por las demás partes, con derecho de intervenirla aun cuando fuese renunciada.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 31 de la LO 5/2000
- artículo 31 de la LORPM
- art. 35.2 de la LORPM

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

### Formulario 0513 · Revenge porn: alegaciones del letrado del menor acusado

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el letrado del menor presenta sus alegaciones contra la acusación de delito de descubrimiento y revelación de secretos, concretamente de sexting, en su modalidad de "revenge porn" del art. 197.7 CP aduciendo que él no fue quien subió a redes sociales las imágenes sexuales.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Menores del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a que actúa en defensa del/de la menor [COMPLETAR], tal y como consta en el expediente nº [Nº DE EXPEDIENTE], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, dentro del plazo que para ello marca la Ley, y de acuerdo con lo establecido en el art. 31 de la LO 5/2000, Reguladora de la Responsabilidad Penal de los Menores, vengo a presentar las siguientes

ALEGACIONES

PRIMERA.- De las actuaciones practicadas no resulta la comisión de ilícito penal alguno, ya que como puede verse en las respuestas enviadas por el/la denunciante, que se adjuntan como documental, en el expediente incoado por la fiscalía de menores, todo se reduce a unas imágenes que fueron extraídas por otra persona del teléfono móvil de el/la menor, y no por éste, sin que en cualquier caso existan datos para acreditar que ha sido éste/a el/la que subió esas imágenes a internet. (1)

SEGUNDA.- Los hechos relatados no son constitutivos de delito alguno, sino que se debe resolver en el equipo de mediación del centro escolar.

TERCERA.- Sin infracción penal no hay participación.

CUARTA.- [COMPLETAR]

QUINTA.- Disconformes con la medida solicitada por el Fiscal y por el acusador particular, procediendo la libre y total absolución de mi representado/a.

SEXTA.- No procede indemnización alguna.

En virtud de ello,

SE INTERESA: [COMPLETAR]

Se acuerde la apertura de la correspondiente audiencia para la que se proponen los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Examen del/de la menor encausado/a.

[OPCIONAL — incluir si procede]

.- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:

-D./Dña. [NOMBRE Y APELLIDOS] Director/a del centro escolar [COMPLETAR]
-Equipo de Asesoramiento Técnico, a través de los responsables del informe que aparece en los folios nº [NÚMERO] del expediente y con el objeto de que declaren acerca del contenido del mismo.
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental mediante la lectura de los siguientes folios de expediente:

[OPCIONAL — incluir si procede]

Y hace suya la prueba propuesta por las demás partes, con derecho de intervenirla aun cuando fuese renunciada.

OTROSÍ PRIMERO DIGO: Que, en interés del/de la menor, y de conformidad con lo establecido en el artículo 31 de la LORPM, se presenta este escrito y se propone la participación en el acto de la audiencia de

OTROSÍ SEGUNDO DIGO: Que, en interés del/de la menor, y de conformidad con lo establecido en el art. 35.2 de la LORPM, se solicita se acuerde la no publicidad de los menores.

En [COMPLETAR].

Firma de Abogado/a

NOTAS DEL FORMULARIO

(1) El delito conocido como "Revenge Porn" (Porno de venganza) es una modalidad del "sexting" tipificado en el art. 197.7 CP y ésa es justo su finalidad: causar daños como respuesta a una decepción amorosa, pero también se ha convertido en una forma de humillación pública.

================================================================================
