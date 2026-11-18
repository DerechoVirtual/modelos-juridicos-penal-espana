---
name: alteracion-lindes-denuncia-235
description: "Redacta el escrito «Alteración de lindes: denuncia» (formulario 235 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alteración de lindes: denuncia

> Formulario 0235 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] ÓRGANO
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…iguiente definición, lindes y extensión:»; «…o al/a la denunciado/a una "utilidad" de»; «…a persona denunciada que se conocen son:»; «…leven a cabo las siguientes diligencias:»; «…e la alteración de lindes que se tasa en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima o su representante / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- .- Declaración del/de la denunciante.…
- .- Testifical de los siguientes testigos de los hechos que han visto la alteración de lindes y apropiación de …
- D./Dña…
- .- Pericial topográfico (Ingeniero Técnico en Topografía o Ingeniero Superior en Geodesia y Cartografía) sobre…
- .- Aportación de prueba como documental de:…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 259 a 269 de la LECRIM
- art. 246.1 CP
- art. 246 CP

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

### Formulario 0235 · Alteración de lindes: denuncia

- Año del modelo: 2022
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 14 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Al Juez en servicio de Guardia del Tribunal de Instancia de [SEDE]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la presenta directamente la víctima o su representante / Si la presenta con Procurador y Abogado — el texto de cada opción no venía en el formulario original]

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia con base en los siguientes

HECHOS

PRIMERO.- El/La denunciante D./Dña. [NOMBRE Y APELLIDOS] es titular de la finca sita en que tiene una extensión de. Está inscrita en el registro de la propiedad nº con la siguiente definición, lindes y extensión: [COMPLETAR]. Se adjunta como documento nº 1 copia de la escritura de propiedad inscrita en el registro de la propiedad nº [Nº] de

Como colindante tiene el/la denunciante a D./Dña. [NOMBRE Y APELLIDOS]

El antes citado y colindante del/de la denunciante en fecha no conocida pero reciente —habida cuenta que hace dos semanas estuvo el/la denunciante en la finca y no existía la alteración actual—, ha modificado los lindes existentes en la finca en la zona... al punto de que se ha apropiado aproximadamente de unos metros.

Tal circunstancia se puede acreditar mediante la fotografía que se adjunta como documento nº 2

La modificación operada de apropiación ha consistido, por ello, en la de los metros cuadrados en la zona de. Con la siguiente descripción que consta en el informe pericial topográfico que se acompaña.

La apropiación de terreno ha reportado al/a la denunciado/a una "utilidad" de [COMPLETAR] metros cuadrados, lo que con un valor en la zona de [IMPORTE] euros/por m2 le supone un importe de [IMPORTE] euros.

Sin perjuicio de una más exacta calificació jurídica posterior, los hechos denunciados son constitutivos de un delito de alteración de lindes del art. 246.1 CP(en base a la "utilidad reportada"), así como de cualquier otro ilícito penal que pudiera resultar "e los hechos enjui"iados.

SEGUNDO.- Los datos de la persona denunciada que se conocen son: [COMPLETAR]. Es el titular de la finca colindante.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentada esta denuncia, se sirva admitirla y, en su virtud, de traslado de la presente, teniéndome por parte para cuantas acciones civiles y penales dimanen de los referidos hechos.

OTROSÍ DIGO: Que interesa a esta parte denunciante que se lleven a cabo las siguientes diligencias:

[COMPLETAR]

[OPCIONAL — incluir si procede]

.- Declaración del/de la denunciante.

[OPCIONAL — incluir si procede]

.- Testifical de los siguientes testigos de los hechos que han visto la alteración de lindes y apropiación de terreno y que son vecinos de la zona y titulares de fincas próximas.

- Declaración del/de la denunciado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña

[OPCIONAL — incluir si procede]

.- Pericial topográfico (Ingeniero Técnico en Topografía o Ingeniero Superior en Geodesia y Cartografía) sobre la alteración de los lindes por perito D./Dña. [NOMBRE Y APELLIDOS] que hace constar al efecto que, comprobada la titularidad y extensión de la finca, existe una alteración de los lindes en la zona.

La pericial incluye "a "utilidad report"da" al denunciado de la alteración de lindes que se tasa en [COMPLETAR] a los efectos de incluirlo en el nº 1 o 2 del art. 246 CP.

[OPCIONAL — incluir si procede]

.- Aportación de prueba como documental de:

—Copia de la escritura de propiedad de la finca afectada y de las fotografías de la alteración de lindes.
—Requerimiento notarial al denunciado para que retire la alteración llevada a efecto concediendo un plazo para ello sin haberlo verificado.

Por ello,

SUPLICO A LA SECCIÓN: Que ordene la práctica de las diligencias probatorias interesadas en dicho Otrosí.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

En [LUGAR], a [FECHA].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

================================================================================
