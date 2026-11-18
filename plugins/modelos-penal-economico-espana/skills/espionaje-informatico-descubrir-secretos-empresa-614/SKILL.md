---
name: espionaje-informatico-descubrir-secretos-empresa-614
description: "Redacta el escrito «Espionaje informático para descubrir secretos de empresa: acusación» (formulario 614 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Espionaje informático para descubrir secretos de empresa: acusación

> Formulario 0614 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… de descubrir los secretos de la empresa»; «…me pericial de la empresa de informática»; «…s de una llamada telefónica recibida por»; «…de entrada por orden judicial en la nave»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se revelan los secretos descubiertos / Si se revelan los secretos descubiertos — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se revelan los secretos descubiertos / Si se revelan los secretos descubiertos — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- (Si se revelan los secretos descubiertos)…
- (Si no se hubiera adoptado aún la medida cautelar de entrada e incautación de datos)…
- 1.- Interrogatorio del/de la acusado/a.…
- .- Interrogatorio del acusador particular.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 del CP
- art. 278.2 CP
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

### Formulario 0614 · Espionaje informático para descubrir secretos de empresa: acusación

- Año del modelo: 2018
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 6 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales y califica los hechos de un delito contra el mercado y los consumidores del art. 278.1 o 2 CP al acceder al sistema de información de una empresa, vulnerando sus sistemas de protección, para descubrir sus secretos.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, con total intención de descubrir los secretos de la empresa [COMPLETAR], de los que es titular el/la querellante ha accedido intencionadamente, y por medios tecnológicos, a su sistema de información vulnerando los sistemas de protección que impiden ese acceso sin autorización alguna del/de la querellante. Esta información se ha obtenido mediante un informe pericial de la empresa de informática [COMPLETAR] con la que se tiene contratada la cobertura informática de la citada empresa, constando el apoderamiento de datos y su alteración. La medida de seguridad de acceso vulnerada fue implantada por la citada empresa, quien nos informó inmediatamente de haber detectado la vulneración del acceso a la información, a través de una llamada telefónica recibida por [COMPLETAR] el día [FECHA].

[OPCIONAL — incluir si procede]

(Si se revelan los secretos descubiertos)

Estos datos se han cedido a terceros, habida cuenta que por medio del/de la empresario/a D./Dña. [NOMBRE Y APELLIDOS] se nos ha facilitado información acerca de la oferta de estos datos a cambio de precio, a lo que se accedió para obtener pruebas por el/la citado/a empresario/a, a fin de comprobar cuáles eran los datos que se habían obtenido y que fueron entregados a su legítimo titular por el tercero.

Los daños y perjuicios causados a mi representado/a, titular de la empresa cuyos secretos se han descubierto, asciende a la suma de [IMPORTE] euros, en razón al contenido del informe pericial que se adjunta como doc. nº 1.

SEGUNDA.- (2)

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se revelan los secretos descubiertos / Si se revelan los secretos descubiertos — el texto de cada opción no venía en el formulario original]

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- (3)

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se revelan los secretos descubiertos / Si se revelan los secretos descubiertos — el texto de cada opción no venía en el formulario original]

SEXTA.- Los daños y perjuicios causados al/a la titular de la empresa asciende a la suma de [IMPORTE] euros en razón al contenido del informe pericial que se adjunta.

Las costas deberán ser satisfechas por el/la acusado/a.

[OPCIONAL — incluir si procede]

(Si no se hubiera adoptado aún la medida cautelar de entrada e incautación de datos)

SÉPTIMA.- Se interesa como medida cautelar la orden de entrada por orden judicial en la nave [COMPLETAR] sita en [LOCALIDAD] para la oportuna incautación de los datos obtenidos, a fin de comprobar dónde se hayan servido u ofrecido los mismos, previo control de los libros comerciales de clientes.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Interrogatorio del acusador particular.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

— D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes de la brigada de delitos tecnológicos que detectaron la IP del ordenador desde el que se llevó a cabo la comisión del ilícito penal.

— D./Dña. [NOMBRE Y APELLIDOS], empleado/a de la empresa atacada.

— D./Dña. [NOMBRE Y APELLIDOS], titular de la empresa informática que recibió los datos de la afectada.

[OPCIONAL — incluir si procede]

.- Pericial:

- Del/De la perito informático D./Dña. [NOMBRE Y APELLIDOS] que detectó el acceso a los sistemas de información de la empresa.
- Del/De la perito D./Dña. [NOMBRE Y APELLIDOS] que elaboró la pericial de daños.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Es un delito de consumación anticipada. Basta la acción de apoderamientodirigida a alcanzar ese descubrimiento. Conseguir el conocimiento del secreto pertenece a la fase posterior de agotamiento de la infracción. La estructura del tipo es la propia de los delitos mutilados de dos actos: una vez constatada la intención antijurídica de descubrir el secreto, el tipo se consuma con la conducta de apoderamiento, interceptación o utilización de artificios técnicos, sin necesidad de que concurra un efectivo descubrimiento. Su difusión, revelación o cesión a terceros constituye la figura agravada del art. 278.2 CP.

(3) Sin perjuicio de las penas que pudieran corresponder por el apoderamiento o destrucción de los soportes informáticos. Habría entonces concurso de delitos con el de hurto, robo, daños, incendio, etc.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
