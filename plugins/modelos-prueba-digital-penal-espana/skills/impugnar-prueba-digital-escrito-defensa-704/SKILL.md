---
name: impugnar-prueba-digital-escrito-defensa-704
description: "Redacta el escrito «Impugnar una prueba digital en el escrito de defensa» (formulario 704 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impugnar una prueba digital en el escrito de defensa

> Formulario 0704 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, Procurador/a»; «…del artículo»; «…tos favorables, por no ser el/la autor/a»; «…del artículo»; «… del teléfono móvil de mi representado/a»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración de los siguientes testigos, que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]…
- - D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- artículo 777.2 LECRIM
- artículo 656 LECRIM
- artículos 781 y 784 LECRIM
- artículos 966 y 969.2 LECRIM

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

### Formulario 0704 · Impugnar una prueba digital en el escrito de defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 párrafos opcionales señalados; 15 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en un procedimiento abreviado presenta sus conclusiones provisionales. En los medios de prueba solicita la impugnación de una prueba digital presentada por la acusación (mensaje de WhatsApp, de mensajería instantánea, email, etc.), aportando pericial contradictoria.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a [COMPLETAR] de los Tribunales en la representación que tengo acreditada de el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

Primera.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo lo que se le imputa ya que en modo alguno cometió los hechos por los que se le acusa por la acusación particular y la fiscalía.

Segunda.- Los hechos no son constitutivos de delito alguno.

Tercera.- Niego las correlativas. Mi representado/a no es autor/a del delito por el que se procede ni de ningún otro.

Cuarta.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente. Subsidiariamente, para el caso de que no lo estime así este órgano judicial, concurre la circunstancia atenuante de [CIRCUNSTANCIA] del artículo [COMPLETAR] del Código Penal. (2)

Quinta.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a [COMPLETAR]. Subsidiariamente, para el caso de que no lo estime así este órgano judicial, procede la imposición a mi representado/a de la pena de [PENA] del artículo [COMPLETAR] del CP.

Sexta.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO

Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración de los siguientes testigos, que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

2.- Pericial siguiente:

Prueba pericial contradictoria con la pericial de parte propuesta por la acusación particular en cuanto a la prueba digital aportada de que desde este mismo instante se impugna por vulneración de derechos fundamentales, al haberse obtenido ilícitamente, al apoderarse el acusador particular del teléfono móvil de mi representado/a [COMPLETAR]. (4)

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde que se recibe el escrito de acusación.

(2) Es recomendable que se proponga alguna propuesta subsidiaria si existen dudas acerca de si se decreta la culpabilidad en el plenario proponiendo, de concurrir, la atenuante que se estime procedente.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (artículo 777.2 LECRIM).

Es importante citar a juicio oral a aquellos que han emitido facturas o informes médicos para que se ratifiquen en ellos.

(4) Puede también simplemente plantearse la impugnación de la prueba digital si se aportó pero no se acompañó de pericial informática. Se incluye esta mención habida cuenta que el Tribunal Supremo tiene declarado con respecto a la aportación de un WhatsApp (u otra prueba digital) que de impugnarse esta prueba digital es preciso proponer y aportar prueba pericial que acredite ese contenido. (STS 300/2015, de 19 de mayo)

Los informes periciales pueden aportarse por las partes personadas en el proceso durante la fase de instrucción, así como acompañarlos junto con el escrito de calificación provisional (en el proceso ordinario; artículo 656 LECRIM) o en el escrito de acusación y/o defensa (en el proceso abreviado; artículos 781 y 784 LECRIM). En el juicio de delito leve, las partes aportarán los informes periciales en el acto del juicio oral (artículos 966 y 969.2 LECRIM).

================================================================================
