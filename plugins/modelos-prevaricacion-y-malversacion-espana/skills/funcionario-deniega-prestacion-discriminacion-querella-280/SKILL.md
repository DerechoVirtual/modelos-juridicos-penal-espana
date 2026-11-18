---
name: funcionario-deniega-prestacion-discriminacion-querella-280
description: "Redacta el escrito «Funcionario que deniega una prestación por discriminación: querella» (formulario 280 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Funcionario que deniega una prestación por discriminación: querella

> Formulario 0280 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La LO 8/2021 añadió el art. 511.4 CP: en todos los casos se impone además inhabilitación especial para profesión u oficio educativos, deportivos y de tiempo libre (BOE-A-2021-9347).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, funcionario público de»; «…acudió a la»; «…sita en [LOCALIDAD] a tramitar»; «…, el/la funcionario/a»; «…fueron testigos las siguientes personas:»; «… insistir en que tenía derecho a obtener»; «…s comentarios denigrantes y centrados en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a…
- .- Testifical. Declaración de los siguientes testigos:…
- D./Dña. [NOMBRE Y APELLIDOS] que presenció los hechos.…
- D./Dña. [NOMBRE Y APELLIDOS] a quien el/la querellante contó lo ocurrido al instante de haber sucedido los hec…
- .- Pericial psicológica de afectación por los hechos ocurridos.…
- .- Documental:…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 511 CP
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0280 · Funcionario que deniega una prestación por discriminación: querella

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 3 llamadas a nota sin texto retiradas; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 24 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)
- Avisos de la revisión: La LO 8/2021 añadió el art. 511.4 CP: en todos los casos se impone además inhabilitación especial para profesión u oficio educativos, deportivos y de tiempo libre (BOE-A-2021-9347).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, por un delito del art. 511 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- El/la querellante es D./Dña [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El/la querellado/a es D/Dña [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD], funcionario público de [COMPLETAR]

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El día [FECHA] cuando D./Dña. [NOMBRE Y APELLIDOS] acudió a la [COMPLETAR] sita en [LOCALIDAD] a tramitar [COMPLETAR], el/la funcionario/a [COMPLETAR] le negó el derecho a tramitarlo, señalándole que

De los hechos fueron testigos las siguientes personas: [COMPLETAR]. Pese a insistir en que tenía derecho a obtener [COMPLETAR] el funcionario se mantuvo en su negativa reiterando sus comentarios denigrantes y centrados en [COMPLETAR].

Esta situación ha provocado en el/la querellante trastorno del sueño y ansiedad ante la discriminación de que fue objeto.

QUINTO.- Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 511 CP.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a

[OPCIONAL — incluir si procede]

.- Testifical. Declaración de los siguientes testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] que presenció los hechos.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] a quien el/la querellante contó lo ocurrido al instante de haber sucedido los hechos.

[OPCIONAL — incluir si procede]

.- Pericial psicológica de afectación por los hechos ocurridos.

[OPCIONAL — incluir si procede]

.- Documental:

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita y se practiquen las diligencias interesadas.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa como medida urgente que se suspenda cautelarmente de sus funciones al/a la querellado/a para evitar que vuelva a cometer el delito, dado que, además, la pena que lleva aparejada es la de inhabilitación especial para empleo o cargo público por tiempo de dos a cuatro años, junto con prisión y multa en su mitad superior [NOTA DE REVISIÓN: Al funcionario público se le aplica el art. 511.3 CP; la inhabilitación de uno a tres años del art. 511.1 es la del particular encargado de un servicio público. Fuente: Código Penal, BOE-A-1995-25444, art. 511.3.].

Se postula también que se adopten las medidas cautelares necesarias para garantizar las responsabilidades civiles y las costas.

SUPLICO A LA SECCIÓN: Que acuerde las medidas cautelares solicitadas.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
