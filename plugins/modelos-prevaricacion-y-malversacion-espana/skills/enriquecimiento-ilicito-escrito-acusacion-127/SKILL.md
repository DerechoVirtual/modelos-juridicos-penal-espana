---
name: enriquecimiento-ilicito-escrito-acusacion-127
description: "Redacta el escrito «Enriquecimiento ilícito: escrito de acusación» (formulario 127 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Enriquecimiento ilícito: escrito de acusación

> Formulario 0127 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] NÚMERO
- [ ] IMPORTE (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] PLAZO
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…la acusado/a D./Dña. cesó en su cargo de»; «… ejerció en la Administración Pública de»; «…e la citada autoridad, ya jubilada desde»; «…os acreditados, y tras ser requerido por»; «… agravantes. Concurre en el/la acusado/a»; «…los funcionarios de la Administración de»; «…do/a durante su ejercicio en el cargo de»; «…do/a durante su ejercicio en el cargo de»; «…responsable de la Administración»; «…zas y Cuerpos de seguridad del Estado de»; «…acusado/a por parte de la Administración»

## Elecciones que hay que hacer

- un incremento patrimonial / una cancelación de obligaciones o deudas

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- Es de Justicia que pido en [LUGAR], a [FECHA].…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Declaración de los miembros de las Fuerzas y Cuerpos de seguridad del Estado de [COMPLETAR], para que proce…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental consistente en requerimiento al/a la acusado/a por parte de la Administración [COMPLETAR] para q…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 438 bis CP
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

### Formulario 0127 · Enriquecimiento ilícito: escrito de acusación

- Año del modelo: 2023
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 29 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El/la acusado/a D./Dña. cesó en su cargo de [COMPLETAR] que ejerció en la Administración Pública de [COMPLETAR]. Es notorio que la citada autoridad, ya jubilada desde [COMPLETAR], ha obtenido [ELEGIR: un incremento patrimonial / una cancelación de obligaciones o deudas] por un valor de [IMPORTE] euros, con respecto a sus ingresos acreditados, y tras ser requerido por [COMPLETAR] no ha cumplimentado la razón de ser de ese incremento patrimonial, transcurrido el plazo que se le concedió para ello.

SEGUNDA.- Tales hechos son constitutivos de un delito de enriquecimiento ilícito del art. 438 bis CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] prisión, multa de [IMPORTE], e inhabilitación especial para empleo o cargo público y para el ejercicio del derecho de sufragio pasivo por tiempo de [DURACIÓN].

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

[OPCIONAL — incluir si procede]

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

1.- Declaración del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de los funcionarios de la Administración de [COMPLETAR] para que declaren sobre las circunstancias que pueden haber rodeado al incremento patrimonial del/de la acusado/a durante su ejercicio en el cargo de [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Declaración de los siguientes testigos (no funcionarios) para que declaren sobre las circunstancias que pueden haber rodeado al incremento patrimonial del/de la acusado/a durante su ejercicio en el cargo de [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

- Declaración de D./Dña. [NOMBRE Y APELLIDOS] responsable de la Administración [COMPLETAR] que efectuó el requerimiento al/a la acusado/a para que justificara, en el plazo de [PLAZO], el incremento patrimonial que tuvo en el ejercicio de su cargo.

[OPCIONAL — incluir si procede]

.- Declaración de los miembros de las Fuerzas y Cuerpos de seguridad del Estado de [COMPLETAR], para que procedan a dar cuenta de las diligencias de investigación llevadas a cabo para esclarecer las razones del incremento patrimonial.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental consistente en requerimiento al/a la acusado/a por parte de la Administración [COMPLETAR] para que facilitase la documentación que justificase el incremento patrimonial sin que lo haya respondido en el plazo concedido.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
