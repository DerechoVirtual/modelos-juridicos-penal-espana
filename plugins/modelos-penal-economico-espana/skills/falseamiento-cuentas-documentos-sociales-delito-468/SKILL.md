---
name: falseamiento-cuentas-documentos-sociales-delito-468
description: "Redacta el escrito «Falseamiento de cuentas o documentos sociales (delito societario): acusación» (formulario 468 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falseamiento de cuentas o documentos sociales (delito societario): acusación

> Formulario 0468 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (12 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…r del % del capital social de la empresa»; «…de fecha [FECHA] en el que se recogía»; «…, datos todos ellos falsos, puesto que»; «… responsabilidad personal subsidiaria de»; «…ivas. — Documentos objeto de la falsedad»; «…e gestión presentado por el/la acusado/a»

## Elecciones que hay que hacer

- las cuentas anuales / un informe de gestión
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- D./Dña. [NOMBRE Y APELLIDOS], empleado/a.…
- .- Pericial:…
- .- Documental: fotocopia de la inscripción de dicha sociedad en el Registro Mercantil, así como del el Libro R…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 290 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 del CP
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

### Formulario 0468 · Falseamiento de cuentas o documentos sociales (delito societario): acusación

- Año del modelo: 2019
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular presenta sus conclusiones provisionales en procedimiento abreviado, calificando los hechos como delito de societario del art. 290 CP, por parte del administrador de la misma, al presentar las cuentas anuales o un informe con datos falsos de la empresa.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] y contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] es socio/a constituyente y titular del % del capital social de la empresa [COMPLETAR], como resulta de la fotocopia de la inscripción de dicha sociedad en el Registro Mercantil, así como del el Libro Registro de Acciones Nominativas.

El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS], administrador/a de la compañía, presentó [ELEGIR: las cuentas anuales / un informe de gestión] de fecha [FECHA] en el que se recogía [COMPLETAR], datos todos ellos falsos, puesto que [COMPLETAR].

El/La acusado/a ha falseado con ello documentos esenciales que muestren la imagen fiel del patrimonio, de la situación financiera y de los resultados de la sociedad.

Los hechos descritos han causado un perjuicio consistente en [IMPORTE] euros.

SEGUNDA.- Tales hechos son constitutivos del delito societario del art. 290 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 290 CP la pena de [PENA] de prisión y multa de [Nº] meses a razón de [IMPORTE] euros/día con responsabilidad personal subsidiaria de [COMPLETAR] día por cada dos cuotas diarias no satisfechas [NOTA DE REVISIÓN: Art. 53.1 CP: un día de privación de libertad por cada dos cuotas diarias no satisfechas. Fuente: Código Penal, BOE-A-1995-25444, art. 53.1.].

SEXTA.- Procede condenar al/a la acusado/a a que indemnice a la víctima por el importe de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- D./Dña. [NOMBRE Y APELLIDOS], gerente.

- D./Dña. [NOMBRE Y APELLIDOS], apoderado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], empleado/a.

[OPCIONAL — incluir si procede]

.- Pericial:

— Pericial de valoración del perjuicio económico causado al socio.
— Pericial de parte sobre la valoración de la falsedad del informe.

[OPCIONAL — incluir si procede]

.- Documental: fotocopia de la inscripción de dicha sociedad en el Registro Mercantil, así como del el Libro Registro de Acciones Nominativas.

— Documentos objeto de la falsedad [COMPLETAR].

— Informe de gestión presentado por el/la acusado/a [COMPLETAR].

— Documento que acredita la condición de socio/a de D./Dña. [NOMBRE Y APELLIDOS].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que solicito en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) El delito del art. 290 CP exige la concurrencia de dos tipos de autores: los administradores de derecho con cargo inscrito en el registro mercantil, o los de hecho, a fin de ampliar la acción penal al auténtico autor con cargo no inscrito en el registro, pero con poder fáctico y funcional en la sociedad. No es preciso que la sociedad tenga personalidad jurídica por su inscripción registral, ya que los hechos pueden haberse cometido en una sociedad en formación.

El objeto del delito es el falseamiento de las cuentas o documentos que reflejen el estado económico. Se exige que se trate de una actuación falsaria idónea para causar un perjuicio económico a la empresa. El perjuicio puede ser triple para que concurra la tipicidad del hecho en el art. 290 CP: a la sociedad, un socio o tercero. Se trata de un acto falsario cometido de modo exclusivo en documentos referidos a cuentas anuales o cualquier otro documento que se refiera a la situación económica de la empresa. La inidoneidad, o la referencia a otros documentos, así como la inexistencia del perjuicio en su idoneidad, no en su materialización, que no se exige, harán atípico el hecho.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
