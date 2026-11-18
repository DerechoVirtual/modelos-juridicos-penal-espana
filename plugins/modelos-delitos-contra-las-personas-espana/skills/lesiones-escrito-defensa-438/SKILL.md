---
name: lesiones-escrito-defensa-438
description: "Redacta el escrito «Lesiones: escrito de defensa» (formulario 438 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones: escrito de defensa

> Formulario 0438 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA
- [ ] IMPORTE

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa / Alegación de que se ha cometido el delito de lesiones del art. 149 CP pero se aplica la atenuante de reparación del daño — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa o atenuante de reparación del daño — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa o atenuante de reparación del daño — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa / Alegación de atenuante de reparación del daño — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia o legítima defensa / Alegación de atenuante de reparación del daño — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia o legítima defensa / Alegación de atenuante muy cualificada de reparación del daño total / Alegación de atenuante simple de reparación del daño parcial — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELE…
- D./Dña. [NOMBRE Y APELLIDOS]…
- (Si se alega que se ha reparado el daño)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 149 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 150 CP
- art. 784 LECRIM
- arts. 149 y 150 CP
- art. 21.5 CP
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

### Formulario 0438 · Lesiones: escrito de defensa

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 6 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado por un delito de lesiones del art. 149 CP en un procedimiento abreviado presenta sus conclusiones provisionales alegando que sus actos no son delictivos, o que deben calificarse como lesiones del art. 147 o 150 CP, o bien que concurre legítima defensa o atenuante de reparación del daño, muy cualificada o simple.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de lesiones del art. 149 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa, en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa / Alegación de que se ha cometido el delito de lesiones del art. 149 CP pero se aplica la atenuante de reparación del daño — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Niego las correlativas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa o atenuante de reparación del daño — el texto de cada opción no venía en el formulario original]

TERCERA.- Niego las correlativas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa o atenuante de reparación del daño — el texto de cada opción no venía en el formulario original]

CUARTA.- Disconforme con las correlativas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia / Alegación de legítima defensa / Alegación de atenuante de reparación del daño — el texto de cada opción no venía en el formulario original]

QUINTA.- Disconforme con las correlativas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia o legítima defensa / Alegación de atenuante de reparación del daño — el texto de cada opción no venía en el formulario original]

SEXTA.- Disconforme con las correlativas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Alegación de que la lesión causada no es la del art. 149 CP, sino del art. 147 o del art. 150 CP / Alegación de inocencia o legítima defensa / Alegación de atenuante muy cualificada de reparación del daño total / Alegación de atenuante simple de reparación del daño parcial — el texto de cada opción no venía en el formulario original]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y la acusación particular y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], que presenciaron los hechos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

(Si se alega que se ha reparado el daño)

.- Documental, consistente en justificante acreditativo del abono a la acusación de la cantidad de [IMPORTE] euros.

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) En los delitos de lesiones suele aconsejarse que, en el caso de existir prueba sobre los hechos, dado que los arts. 149 y 150 CP llevan penas de 6 a 12 años y 3 a 6 años respectivamente, se proceda a la reparación del daño causado mediante la indemnización correspondiente, dado que la reparación íntegra podría conllevar la alegación por la defensa de una atenuante del art. 21.5 CP como muy cualificada que, a tenor del art. 66.1.2ª CP [NOTA DE REVISIÓN: La rebaja en uno o dos grados por una atenuante muy cualificada está en la regla 2.ª del art. 66.1 CP; el art. 66.2 (redacción LO 1/2026) se refiere a los delitos leves e imprudentes. Fuente: Código Penal, BOE-A-1995-25444, art. 66 (redacción LO 1/2026, BOE-A-2026-7966).] podrá conllevar la rebaja en la pena de 1 o 2 grados.

No obstante, nótese que para que opere la atenuante citada como muy cualificada debería procederse a una reparación íntegra del daño, o bien a un pago relevante y el resto llegar a un acuerdo con el perjudicado de pago aplazado, dado que en su defecto solo operaría como atenuante simple, que a tenor del art. 66.1º CP solo llevaría a poner la pena en la mitad inferior de los citados arcos de pena, que al ser tan elevadas no podría conllevar la suspensión de la ejecución de la pena.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
