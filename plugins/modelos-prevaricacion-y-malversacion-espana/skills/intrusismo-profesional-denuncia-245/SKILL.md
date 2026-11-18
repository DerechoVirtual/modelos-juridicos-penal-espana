---
name: intrusismo-profesional-denuncia-245
description: "Redacta el escrito «Intrusismo profesional: denuncia» (formulario 245 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Intrusismo profesional: denuncia

> Formulario 0245 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] LUGAR (2 veces)
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] ÓRGANO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…SEGUNDO.- Por ello, desde»; «…otorga habilitación para el ejercicio de»

## Elecciones que hay que hacer

- académico / oficial

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima o su representante / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el denunciado no tiene el título académico que exige su profesión / Si el denunciado no tiene el título oficial que se exige para el ejercicio de una profesión — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la denunciado/a…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental consistente en:…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 259 a 269 de la LECRIM
- art. 403 CP

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

### Formulario 0245 · Intrusismo profesional: denuncia

- Año del modelo: 2022
- Revisión 17-11-2026: 1 rangos de artículos despegados («25 a31» → «25 a 31»); 2 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 13 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima o su representante / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original]

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia con base en los siguientes

HECHOS

PRIMERO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el denunciado no tiene el título académico que exige su profesión / Si el denunciado no tiene el título oficial que se exige para el ejercicio de una profesión — el texto de cada opción no venía en el formulario original]

SEGUNDO.- Por ello, desde [COMPLETAR] el/la denunciado/a ha estado ejerciendo la actividad citada, recibiendo a clientes en la oficina antes citada, lo que determina que esté cometiendo delito de intrusismo profesional del art. 403 CP al no estar habilitado para el ejercicio de esta profesión.

Se ha requerido notarialmente desde el colegio de al/a la denunciado/a para que cese en el ejercicio de su actividad, sin resultado alguno.

En su virtud,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta denuncia, se sirva admitirla y, en su virtud, de traslado de la presente, teniéndome por parte para cuantas acciones civiles y penales dimanen de los referidos hechos.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO: Que interesa a esta parte denunciante que se lleven a cabo las siguientes diligencias:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la denunciado/a

[OPCIONAL — incluir si procede]

.- Testifical:

— Declaración de D./Dña. [NOMBRE Y APELLIDOS] presidente del Colegio de de y de los siguientes miembros de la junta de gobierno conocedores de las actividades desarrolladas por el mismo.
— Declaración de D./Dña. [NOMBRE Y APELLIDOS] presidente de la comunidad de propietarios y administrador de fincas del edificio donde radica el local donde ejerce esta actividad el denunciado para que declaren sobre la actividad que despliega.
— Declaración de D./Dña. [NOMBRE Y APELLIDOS] conserje del inmueble sobre los mismos extremos.
— Declaración de los siguientes clientes del/de la denunciado/a conocidos para que declaren sobre la actividad y cómo conocieron el ejercicio de la profesión del querellado.
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

— Declaración de D./Dña. [NOMBRE Y APELLIDOS] para que declare como técnico de la Administración competente en la entrega del título [ELEGIR: académico / oficial] que otorga habilitación para el ejercicio de [COMPLETAR] y las consecuencias de que se ejerza sin título.

[OPCIONAL — incluir si procede]

.- Documental consistente en:

— Facturas pagadas por clientes del/de la denunciado/a que han decidido colaborar con el denunciante.
— Exigencias de titulación requerida para el ejercicio de la actividad de.
— Requerimiento notarial al/a la denunciado/a para que cese en su actividad.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que ordene la práctica de las diligencias probatorias interesadas en dicho Otrosí. Y que, además, se acuerde la medida cautelar de cese inmediato en la actividad que despliega el/la denunciado/a para evitar la causación de daños y perjuicios a clientes que desconozcan la ausencia de titulación del/de la denunciado/a para ejercer esa actividad y se eviten los daños que se están causando.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

SUPLICO A LA SECCIÓN: Que tenga por hecha la anterior manifestación.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

================================================================================
