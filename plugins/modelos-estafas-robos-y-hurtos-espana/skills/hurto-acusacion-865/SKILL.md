---
name: hurto-acusacion-865
description: "Redacta el escrito «Hurto: acusación» (formulario 865 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto: acusación

> Formulario 0865 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde el 10-4-2026, si lo sustraído es un teléfono móvil u otro dispositivo con datos personales (salvo los expuestos a la venta), el hurto es agravado del art. 235.1.10.º CP: prisión de uno a tres años (LO 1/2026, BOE-A-2026-7966).
- Desde la LO 1/2026 el hurto de hasta 400 euros se castiga como el del art. 234.1 CP (prisión de seis a dieciocho meses) cuando el autor tenga tres condenas ejecutorias de la misma naturaleza del Título XIII, al menos una leve.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] COLEGIO (2 veces)
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD (3 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…aba el/la perjudicado/a por el parque de»; «…si tenía su monedero, en el que guardaba»; «…l delito de hurto, la pena de prisión de»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte]…
- D./Dña. [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD] que acompañaba al/a la perjudicado/a del hurto.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 234.1 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECrim
- art. 780 LECrim
- art. 650 LECrim
- art. 234.1 del Código Penal
- art. 22 CP
- art. 777.2 LECrim

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

### Formulario 0865 · Hurto: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 2 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Desde el 10-4-2026, si lo sustraído es un teléfono móvil u otro dispositivo con datos personales (salvo los expuestos a la venta), el hurto es agravado del art. 235.1.10.º CP: prisión de uno a tres años (LO 1/2026, BOE-A-2026-7966). · Desde la LO 1/2026 el hurto de hasta 400 euros se castiga como el del art. 234.1 CP (prisión de seis a dieciocho meses) cuando el autor tenga tres condenas ejecutorias de la misma naturaleza del Título XIII, al menos una leve.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la acusación particular en procedimiento abreviado por el que se solicita la apertura del juicio oral y se presentan las conclusiones provisionales calificando los hechos de delito de hurto del art. 234.1 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a del Ilustre Colegio de Procuradores de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], dirigido/a por el/la Letrado/a abajo firmante D./Dña. [NOMBRE Y APELLIDOS], colegiado/a n.º [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO: (1)

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECrim y escrito de acusación por la vía del art. 780 LECrim, en relación con el art. 650 LECrim, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El día [FECHA], sobre las [Nº] horas, caminaba el/la perjudicado/a por el parque de [COMPLETAR] con D./Dña. [NOMBRE Y APELLIDOS], cuando el/la acusado/a chocó con D./Dña. [NOMBRE Y APELLIDOS] de frente y, después de pedirle perdón, se marchó aceleradamente. Este hecho provocó extrañeza en D./Dña. [NOMBRE Y APELLIDOS] porque había mucho espacio para caminar sin necesidad de chocarse una persona con otra. Sospechó entonces que podían haberle hurtado, por lo que rápidamente buscó en el bolsillo interior de su chaqueta para ver si tenía su monedero, en el que guardaba [COMPLETAR] y éste había desaparecido. Rápidamente dio la vuelta y salió corriendo para alcanzar al/a la sospechoso/a, quien se giró y, al verle, se dio a la fuga sin que pudiera alcanzarle.

SEGUNDA.- Tales hechos son constitutivos del delito de hurto del art. 234.1 del Código Penal.

TERCERA.- Es responsable del delito de hurto en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren con respecto al/a la acusado/a circunstancias modificativas de la responsabilidad criminal.

Concurre con respecto al/a la acusado/a la agravante genérica de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a, por el delito de hurto, la pena de prisión de [COMPLETAR]. (2)

SEXTA.- La cantidad sustraída asciende a [IMPORTE] euros que se reclaman en concepto de responsabilidad civil.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD] que acompañaba al/a la perjudicado/a del hurto.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que el Juez le emplaza para ello, por la vía del art. 780 LECrim.

(2) En cuanto a la pena debemos hacer notar que la pena a imponer se aplica en su mitad superior cuando en la comisión del hecho se hubieran neutralizado, eliminado o inutilizado, por cualquier medio, los dispositivos de alarma o seguridad instalados en las cosas sustraídas. Por lo tanto, al autor del hurto en establecimientos comerciales que utilicen estos dispositivos para evitar que sean sustraídos se le aplica la pena de 12 meses de prisión.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim).

================================================================================
