---
name: conduccion-temeraria-escrito-acusacion-369
description: "Redacta el escrito «Conducción temeraria: escrito de acusación» (formulario 369 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción temeraria: escrito de acusación

> Formulario 0369 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] IMPORTE (6 veces)
- [ ] DESCRIBIR
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] ...
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dora del vehículo del/de la acusado/a es»; «… caso, en función de la lesión producida»; «…de»; «…ecta la Compañía de Seguros que al folio»; «…las cantidades por responsabilidad civil»; «…ral se requiera a la Compañía de Seguros»; «…édico forense con el siguiente resultado»

## Elecciones que hay que hacer

- conducción temeraria / lesiones
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- (Si la aseguradora aún no ha consignado las cantidades por responsabilidad civil [COMPLETAR])…
- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- — D./Dña. [NOMBRE Y APELLIDOS] que presenció el accidente.…
- .- Pericial médico forense con el siguiente resultado [COMPLETAR].…
- .- Documental siguiente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 380 CP
- art. 152.1 CP
- art. 382 CP
- artículo 781.1 de la LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- art. 650 LECRIM
- artículo 14 de la LECrim
- art. 22 del CP
- art. 7.6 RDLeg. 8/2004
- arts. 764 y 765 LECrim
- art. 7.2 RDLeg. 8/2004
- art. 20.3 Ley 50/1980
- art. 780 LECRIM
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

### Formulario 0369 · Conducción temeraria: escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 24 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 5 huecos del original que se habían perdido sin marca, marcados (IMPORTE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento abreviado presenta sus conclusiones provisionales calificando los hechos de delito de conducción temeraria del art. 380 CP, con resultado de lesiones del art. 152.1 CP, por lo que se aplicará la pena del delito más grave en su mitad superior, conforme al art. 382 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL (1) ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, en relación con el art. 650 LECRIM, con arreglo a lo dispuesto en el artículo 14 de la LECrim y con base en las siguientes

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] es propietario del vehículo matrícula asegurado en la compañía de seguros y el día circulaba por la avenida cuando detrás del mismo lo hacía el vehículo con matrícula conducido por D./Dña. [NOMBRE Y APELLIDOS], quien, de una forma claramente temeraria, comenzó a darle la luz larga con la intención de que acelerara la velocidad, al mismo tiempo que hacía gestos ostensibles de que fuera más rápido como pudo detectar por el espejo retrovisor. Tras esta presión que ejercía poniéndose, incluso, detrás del vehículo a escasos cm para presionarle más, le adelantó en una curva con grave riesgo para su integridad y, cuando estaba justo a su lado, le dio un volantazo y golpeó con su vehículo el conducido por mi mandante colisionando y saliendo de la carretera, éste último, colisionando con la pared de un edificio.

Del accidente resultaron daños causados en el vehículo por importe de [IMPORTE] y lesiones en mi representado/a consistentes en [DESCRIBIR], faltando al centro de trabajo desde el día siguiente al siniestro y sigue de baja en la actualidad.

La aseguradora del vehículo del/de la acusado/a es [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos del delito de conducción temeraria del art. 380 CP con resultado de lesiones por imprudencia grave del art. 152.1 CP, en relación con el art. 382 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias modificativas de la responsabilidad penal.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al acusado, en aplicación del art. 382 CP, la pena para el delito más grave en su mitad superior. En este caso, en función de la lesión producida [COMPLETAR], la pena debe ser la del delito de [ELEGIR: conducción temeraria / lesiones] de [COMPLETAR] de prisión y privación del permiso de conducir por tiempo de [Nº] años. (2)

SEXTA.- Como responsabilidad civil se postula se abone por los perjuicios causados la cantidad de [IMPORTE] euros, a cuyo pago deberá ser compelida como responsable civil directa la Compañía de Seguros que al folio [COMPLETAR] de la pieza de responsabilidad civil ya consta salió fiadora por las responsabilidades de este orden, por los siguientes conceptos:

- [IMPORTE] euros por daños en el vehículo matrícula:

Las siguientes cantidades han sido calculadas con arreglo al baremo del Anexo del RDLeg. 8/2004, de 29 de octubre, en cuanto a:

[IMPORTE] euros por lesiones causadas.

 [IMPORTE] euros por las secuelas.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

[OPCIONAL — incluir si procede]

(Si la aseguradora aún no ha consignado las cantidades por responsabilidad civil [COMPLETAR])

Igualmente, intereso que en el auto de apertura del juicio oral se requiera a la Compañía de Seguros [COMPLETAR], en base al art. 7.6 RDLeg. 8/2004, de 29 de octubre y arts. 764 y 765 LECrim., como responsable civil directa para que consigne judicialmente la cantidad de [IMPORTE] euros para hacer frente a las responsabilidades civiles que se deriven de los hechos que han dado lugar a las presentes actuaciones.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

— D./Dña. [NOMBRE Y APELLIDOS] que presenció el accidente.

— D./Dña. [NOMBRE Y APELLIDOS], representante del taller donde se efectuó la reparación o se efectuará

— D./Dña. [NOMBRE Y APELLIDOS] representante del centro de trabajo donde está de baja.

[OPCIONAL — incluir si procede]

.- Pericial médico forense con el siguiente resultado [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Documental siguiente:

-Atestado elaborado por la guardia civil.

-Fotografías del estado del vehículo y el lugar del accidente y el resultado de cómo quedó la casa.

-Facturas del vehículo y reparación.

-Facturas de los gastos médicos.

-Reclamación del perjudicado a la aseguradora de el/la denunciado/a del art. 7.2 RDLeg. 8/2004 y al objeto del devengo de los intereses de demora desde la fecha del siniestro ex art. 20.3 Ley 50/1980 de Contrato de Seguro.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica Y se mantenga el abono de la pensión provisional acordada por este órgano judicial en auto de fecha [FECHA] hasta el día de la firmeza de la sentencia.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) En este caso los hechos son constitutivos del delito de conducción temeraria del art. 380 CP, pero nótese que generalmente cuando se formule denuncia por la víctima será porque el conductor responsable ha causado un accidente con su temeraria conducción, lo que determinará que entre en juego el art. 382 CP que prevé que cuando con los actos sancionados en el art. 380 CP se ocasionase, además del riesgo prevenido, un resultado lesivo constitutivo de delito, bien de homicidio imprudente, bien de lesiones, cualquiera que sea su gravedad, se apreciará tan sólo la infracción más gravemente penada, aplicando la pena en su mitad superior y condenando, en todo caso, al resarcimiento de la responsabilidad civil que se hubiera originado. (STS 350/2020 de 25 de junio, Rec. 3491/2018).

Con ello, el delito de conducción temeraria es un delito de riesgo concreto pero, salvo que sea la policía la que levante atestado por un hecho como tal de conducción temeraria, en cuyo caso no hay perjudicado, al no existir daño, habría denuncia si alguien lo fuera, como en este ejemplo.

El Tribunal Supremo (SSTS 2251/2001, de 29 de noviembre, y 1039/2001, de 29 de mayo) ha precisado que «la simple conducción temeraria, creadora por sí misma de un peligro abstracto no sería suficiente, debiendo quedar acreditada la existencia de un peligro concreto [...] peligro que ha de ser efectivo, constatable para la vida o integridad física de personas concretas, distintas del sujeto pasivo».

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

================================================================================
