---
name: intrusismo-profesional-escrito-acusacion-244
description: "Redacta el escrito «Intrusismo profesional: escrito de acusación» (formulario 244 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Intrusismo profesional: escrito de acusación

> Formulario 0244 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] NÚMERO
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…PRIMERA.- Por ello, desde»; «…a agravante específica del apartado 2 de»; «… agravantes. Concurre en el/la acusado/a»; «…otorga habilitación para el ejercicio de»; «… DIGO: Se interesa la medida cautelar de»

## Elecciones que hay que hacer

- académico / oficial

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el denunciado no tiene el título académico que exige su profesión / Si el denunciado no tiene el título oficial que se exige para el ejercicio de una profesión — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental consistente en:…
- (Si el acusado publicitó su actividad)…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 403 CP
- art. 22 del CP

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

### Formulario 0244 · Intrusismo profesional: escrito de acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 21 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el denunciado no tiene el título académico que exige su profesión / Si el denunciado no tiene el título oficial que se exige para el ejercicio de una profesión — el texto de cada opción no venía en el formulario original]

PRIMERA.- Por ello, desde [COMPLETAR] el/la acusado/a ha estado ejerciendo la actividad citada, recibiendo a clientes en la oficina antes citada, sin estar habilitado para el ejercicio de esta profesión.

Se requirió notarialmente desde el colegio de al/a la acusado/a para que cesase en el ejercicio de su actividad, sin resultado alguno.

SEGUNDA.- Tales hechos son constitutivos de un delito de intrusismo profesional del art. 403 CP, con la agravante específica del apartado 2 de [COMPLETAR].

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- Testifical:

—Declaración de D./Dña. [NOMBRE Y APELLIDOS] presidente del Colegio de de y de los siguientes miembros de la junta de gobierno conocedores de las actividades desarrolladas por el mismo.

—Declaración de D./Dña. [NOMBRE Y APELLIDOS] presidente de la comunidad de propietarios y administrador de fincas del edificio donde radica el local donde ejerce esta actividad el denunciado para que declaren sobre la actividad que despliega.

—Declaración de D./Dña. [NOMBRE Y APELLIDOS] conserje del inmueble sobre los mismos extremos.

—Declaración de los siguientes clientes del/de la denunciado/a conocidos para que declaren sobre la actividad y cómo conocieron el ejercicio de la profesión del querellado.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

—Declaración de D./Dña. [NOMBRE Y APELLIDOS] para que declare como técnico de la Administración competente en la entrega del título [ELEGIR: académico / oficial] que otorga habilitación para el ejercicio de [COMPLETAR] y las consecuencias de que se ejerza sin título.

[OPCIONAL — incluir si procede]

.- Documental consistente en:

—Facturas pagadas por clientes del/de la denunciado/a que han decidido colaborar con el denunciante.
—Exigencias de titulación requerida para el ejercicio de la actividad de.
—Requerimiento notarial al/a la denunciado/a para que cese en su actividad.

[OPCIONAL — incluir si procede]

(Si el acusado publicitó su actividad)

—

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa la medida cautelar de [COMPLETAR]

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
