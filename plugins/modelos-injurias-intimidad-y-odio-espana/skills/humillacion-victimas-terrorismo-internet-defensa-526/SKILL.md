---
name: humillacion-victimas-terrorismo-internet-defensa-526
description: "Redacta el escrito «Humillación a víctimas del terrorismo por internet: defensa» (formulario 526 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Humillación a víctimas del terrorismo por internet: defensa

> Formulario 0526 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- (4)…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 578 CP
- art. 578.1,2 y 4 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- artículos 572 a 577 CP
- art. 777.2 LECr
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

### Formulario 0526 · Humillación a víctimas del terrorismo por internet: defensa

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 párrafos opcionales señalados; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado por un delito de humillación de víctimas del terrorismo por internet del art. 578 CP, en un procedimiento abreviado, presenta sus conclusiones provisionales presentando pericial informática contradictoria.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del art. 578.1,2 y 4 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que no consta acreditado que ese acceso al ordenador fuera por el/la acusado/a, ya que se trata de un piso compartido por varias personas y, por ello, la autoría del delito no está acreditada. Al mismo tiempo, se pone en duda que haya sido el ordenador de su inmueble el lugar de acceso, ya que es posible técnicamente la derivación a éste desde otro inmueble, no habiéndose llevado a cabo labor investigadora alguna que pudiera descubrir si la IP del ordenador fue pirateada desde otro punto.

En segundo lugar, los hechos de la acusación no integran el elemento de la humillación a las víctimas, ya que son simples comentarios reprochables moralmente, pero en ningún caso delictivos.

SEGUNDA.- Los hechos no son constitutivos de un delito del art. 578 CP. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], que declararán sobre la inexistencia de la conducta de la que se le acusa por su conocimiento personal.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- (4)

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la acusación presentó pericial informática acreditativa de la prueba digital aportada / Si la acusación no presentó pericial informática acreditativa de la prueba digital aportada — el texto de cada opción no venía en el formulario original]

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el/la Letrado/a de la Administración de Justicia.

(2) En el art. 578 CP se prevén dos tipos de conductas:

1.- Enaltecimiento o la justificación públicos de los delitos comprendidos en los artículos 572 a 577 CP [NOTA DE REVISIÓN: El art. 578.1 CP remite a los delitos de los arts. 572 a 577. Fuente: Código Penal, BOE-A-1995-25444, art. 578.1.] o de quienes hayan participado en su ejecución.
2.- La realización de actos que entrañen descrédito, menosprecio o humillación de las víctimas de los delitos terroristas o de sus familiares.

Y al objeto del ciberdelito, una agravación en el apartado segundo si se lleva a cabo por Internet. Sobre esta modalidad de delito cometido por redes sociales existe una importante doctrina de la Sala Segunda del Tribunal Supremo que trata de delimitar claramente el delito.

STS 378/2017, de 25 de Mayo, rec. 8/2017: el tipo exige formalmente una actuación del sujeto que suponga justificar delitos de terrorismo o enaltecer a los que hayan participado en ellos.

STS 706/2017, de 21 de Octubre, rec. 514/2017: la mera reproducción de imágenes y el "retuiteo" con difusión pública, aunque hubieran sido tomadas por un tercero, constituyen delito del art. 578 CP. El tipo penal no exige que el acusado asuma como propio, razone o argumente la imagen y su mensaje, o que los haya creado, sino que basta que disponga de ellos y les de publicidad. La expansión del mensaje posibilita que terceras personas se percaten de que están enalteciendo la trayectoria personal y los "méritos" de alguien cuya fama procede de los actos terroristas ejecutados.

STS 812/2011, de 21 de Julio, rec. 46/2011: distinción con la apología del terrorismo.

STS 334/2018, de 4 de Julio, rec. 2193/2017: el conjunto de los mensajes analizados no traspasan los límites para ser calificados como delito de humillación a las víctimas del terrorismo. Límites fronterizos entre la vía penal y la civil. Necesidad de que se adopten medidas organizativas en los prestadores de servicio para cortar la difusión inmediata de tales expresiones.

STS 95/2018, de 26 de Febrero, Rec. 979/2017.

STS 4/2017, de 18 de Enero, rec. 1619/2016: "Tuits" publicados en la cuenta de famoso cantante-letrista de rap metal.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

(4) Puede simplemente plantearse la impugnación de la prueba digital si se aportó pero no se acompañó de pericial informática. Se incluye esta mención puesto que el Tribunal Supremo tiene declarado con respecto a la aportación de una prueba digital que, de impugnarse esta prueba, es preciso proponer y aportar prueba pericial que acredite ese contenido. (STS 300/2015, de 19 de mayo, rec. 2387/2014)

Los informes periciales pueden aportarse por las partes personadas en el proceso durante la fase de instrucción, así como acompañarlos junto con el escrito de calificación provisional (en el proceso ordinario; artículo 656 LECRIM) o en el escrito de acusación y/o defensa (en el proceso abreviado; artículos 781 y 784 LECRIM). En el juicio de delito leve, las partes aportarán los informes periciales en el acto del juicio oral (artículos 966 y 969.2 LECRIM).

================================================================================
