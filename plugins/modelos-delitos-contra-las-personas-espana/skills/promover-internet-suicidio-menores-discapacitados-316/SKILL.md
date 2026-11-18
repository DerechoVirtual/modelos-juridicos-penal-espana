---
name: promover-internet-suicidio-menores-discapacitados-316
description: "Redacta el escrito «Promover por internet el suicidio de menores o discapacitados: denuncia» (formulario 316 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Promover por internet el suicidio de menores o discapacitados: denuncia

> Formulario 0316 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] DNI/NIE (2 veces)
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…D»; «… [COMPLETAR], con DNI nº [DNI/NIE] y Dª.»; «…hemos conocido que en»; «…siguientes expresiones que transcribimos»; «…visita con frecuencia»; «…a persona denunciada que se conocen son:»; «…igos que han visualizado los mensajes de»; «…a a la identidad del mismo que consta en»; «…n objeto de denuncia y los contenidos de»; «…idades judiciales ordenen la retirada de»

## Elecciones que hay que hacer

- menor / discapacitado/a
- menor de edad / discapacitado/a
- cierre o clausura de la página web / acceso a la red social

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la denunciado/a.…
- . Testifical…
- [OPCIONAL — incluir si procede]…
- .- Pericial…
- .- Documental:…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 259 a 269 de la LECRIM
- art. 143 bis CP
- art. 544 bis LECRIM
- art. 57 CP

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

### Formulario 0316 · Promover por internet el suicidio de menores o discapacitados: denuncia

- Año del modelo: 2021
- Revisión 17-11-2026: 1 rangos de artículos despegados («25 a31» → «25 a 31»); 2 llamadas a nota sin texto retiradas; 4 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (DNI/NIE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D [COMPLETAR], con DNI nº [DNI/NIE] y Dª. [COMPLETAR], con DNI nº [DNI/NIE], como padres del/de la [ELEGIR: menor / discapacitado/a], comparecen ante este órgano judicial y, como mejor proceda en derecho, DICEN:

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM formulamos denuncia y,

EXPONEMOS

PRIMERO.- Los hechos que motivan la denuncia y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] hemos conocido que en [COMPLETAR] que ha creado D./Dña. [NOMBRE Y APELLIDOS] ha subido contenidos claros y tendenciosos dirigidos a fomentar o incitar al suicidio de personas menores de edad o con discapacidad necesitadas de especial protección, como consta en las siguientes expresiones que transcribimos [COMPLETAR].

Este método conlleva un grave peligro al dirigirse a personas con problemas de autoestima y con claros déficits personales que pueden llevar a que quien los lea pueda aceptar las instrucciones, consejos o directrices que se indican y acabar con su vida.

En nuestro caso, nuestro/a hijo/a [ELEGIR: menor de edad / discapacitado/a] visita con frecuencia [COMPLETAR] y ha sido por ello por lo que hemos detectado, al comprobar los contenidos del ordenador, los mensajes que lee del/de la denunciado/a y la alta influencia que está ejerciendo sobre nuestro/a hijo/a y el elevado riesgo de que pueda llevar a cabo la conducta que le propone el/la denunciado/a.

Sin perjuicio de una mejor calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 143 bis CP.

SEGUNDO.- Los datos de la persona denunciada que se conocen son: [COMPLETAR].

TERCERO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la denunciado/a.

[OPCIONAL — incluir si procede]

. Testifical

-Declaración del/de la [ELEGIR: menor / discapacitado/a] que será grabada como prueba preconstituida para ser reproducida el día del juicio oral por la vía de los arts. 449 bis, 449 ter, 703 bis y 777.3 LECRIM.

-Declaración de los siguientes testigos que han visualizado los mensajes de [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

[OPCIONAL — incluir si procede]

.- Pericial

-Pericial psicológica de la situación de ansiedad y depresión provocada en el/la menor por visualizar los contenidos de internet.

[OPCIONAL — incluir si procede]

.- Documental:

- Se solicita que se dirija atento oficio a la brigada de delitos tecnológicos de las Fuerzas y cuerpos de seguridad del Estado para que se identifique al denunciado en virtud de la referencia a la identidad del mismo que consta en [COMPLETAR] y confirmación de autoría.
- Acta notarial del/de la Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Ilustre colegio de que ha redactado la misma en atención a haber comprobado personalmente los hechos que son objeto de denuncia y los contenidos de [COMPLETAR] durante los siguientes días.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de denuncia y documentos, se admita, se practiquen las diligencias interesadas y se acuerde como medida cautelar ex art. 143 bis CP que las autoridades judiciales ordenen la retirada de [COMPLETAR] y la interrupción de los servicios que ofrezcan dichos contenidos.

Con ello, se insta el [ELEGIR: cierre o clausura de la página web / acceso a la red social].

OTROSÍ DIGO: Se interesa se proceda a la inmediata detención del denunciado, dada la gravedad de los hechos denunciados y que en base al art. 544 bis LECRIM, dado que el delito denunciado está entre los incluidos en el art. 57 CP se dicte una orden de alejamiento que le impida acercarse a la víctima y sus familiares a menos de 500 metros, así como, sobre todo, una orden de prohibición de comunicación por cualquier tipo de medio, incluidos los tecnológicos.

Asimismo, se postula se acuerde como medida cautelar urgente, en base al párrafo 2º del art. 143 bis CP, la retirada de los contenidos distribuidos por internet y redes sociales por el/la querellado/a, la interrupción de los servicios que ofrezcan predominantemente dichos contenidos o el bloqueo de unos y otros cuando radiquen en el extranjero.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

SEGUNDO OTROSÍ DIGO: que para nuestra representación y defensa en esta causa designamos al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman con nosotros este escrito en prueba de aceptación y conformidad.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

================================================================================
