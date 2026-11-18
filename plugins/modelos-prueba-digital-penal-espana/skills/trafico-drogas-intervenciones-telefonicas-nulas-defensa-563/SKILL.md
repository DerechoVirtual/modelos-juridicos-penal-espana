---
name: trafico-drogas-intervenciones-telefonicas-nulas-defensa-563
description: "Redacta el escrito «Tráfico de drogas con intervenciones telefónicas nulas: defensa» (formulario 563 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tráfico de drogas con intervenciones telefónicas nulas: defensa

> Formulario 0563 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] LUGAR
- [ ] FECHA
- [ ] NÚMERO
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…castigados con pena con límite máximo de»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical. Declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Documental. Con expresa impugnación de los documentos señalados por la acusación derivados de la nulidad de…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 368 CP
- artículo 368 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- artículo 18.3 de la Constitución
- art. 18.3 CE
- art. 784 LECRIM
- art. 579 LECRIM
- art. 777.2 LECr

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

### Formulario 0563 · Tráfico de drogas con intervenciones telefónicas nulas: defensa

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 2 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales en un procedimiento abreviado por delito de tráfico de drogas del art. 368 CP, alegando nulidad de las intervenciones telefónicas y, por tanto, del resto de pruebas derivadas de las mismas.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito contra la salud pública del artículo 368 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. El procedimiento judicial está viciado de origen, dado que las intervenciones telefónicas son nulas ante la vulneración del derecho fundamental del/de la acusado/a al secreto de las comunicaciones de artículo 18.3 de la Constitución, habida cuenta que: (2)

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No constan en el oficio policial instando la orden de intervención telefónica los requisitos previstos en el art. 588 ter d LECRIM.

El auto judicial de intervención telefónica se ha dictado en base a una investigación policial escasa y el oficio instándolo es meramente prospectivo, constando solo meras sospechas en el mismo, tras el agotamiento de una investigación policial.

La duración de la medida de intervención telefónica ha sido excesiva, conforme prevé el artículo 588 ter g LECRIM, puesto que ha durado por encima de los
3 meses, sin acordarse la prórroga
18 meses con prórrogas

En la petición policial de prórroga de las escuchas telefónicas no constan debidamente fundadas las razones por las que se entiende necesaria la misma, conforme al art. 588 ter h LECRIM.

No ha habido transcripción ante el/la Letrado/a de la AJ de los pasajes de la grabación que resulten relevantes para el procedimiento, conforme al art. 588 ter f y h LECRIM.

No podrán ser valoradas, ni surtirán efecto, las pruebas cuyo contenido derive directamente de la violación constitucional. Así, en el caso de que se declare la infracción del derecho al secreto de las comunicaciones, directamente no es valorable el contenido de tales escuchas.

Esta nulidad de la escucha conlleva la nulidad de la diligencia de intervención de la sustancia aprehendida al/a la acusado/a, dado que las intervenciones telefónicas son radicalmente nulas y que por lo tanto no pueden producir efecto en el procedimiento y no pueden operar como prueba de cargo las vigilancias policiales, ni las demás diligencias obtenidas por la policía, dado que se derivan directa o indirectamente de las diligencias de intervención telefónica, y además, sí concurre la conexión de antijuridicidad entre la ilegalidad de las escuchas telefónicas y las demás diligencias con las que pretende acreditar los hechos que son objeto de acusación.

Aplicando la teoría de los "frutos del árbol envenenado" se debe declarar la nulidad de las intervenciones telefónicas debido a la vulneración del derecho fundamental al secreto de las comunicaciones ( art. 18.3 CE) y que por ello se considera que las escuchas carecen de legitimidad como fuente de prueba y también como prueba en sentido estricto, al no haberse acreditado la legitimidad de las escuchas telefónicas y con ello es nulo el registro practicado y la sustancia aprehendida que tienen como fuente y origen, en conexión de antijuridicidad, una prueba nula, no existiendo ninguna otra prueba que pueda valorarse con sentido incriminatorio contra el/la acusado/a que esté desconectada de la nulidad de las escuchas.

SEGUNDA.- Los hechos no son constitutivos de un delito del art. 368 CP.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical. Declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes policiales que llevaron a cabo la investigación con nº [NÚMERO].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental. Con expresa impugnación de los documentos señalados por la acusación derivados de la nulidad de las escuchas y, en concreto, se citan:

- La transcripción de las escuchas.
- La diligencia de entrada y registro.
- El análisis de la sustancia aprehendida.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) La regulación legal de las escuchas telefónicas está contemplada en los arts. 588 ter a LECRIM y ss. Sin embargo, para evaluar en qué casos se puede acordar una escucha telefónica hay que remitirse al art. 579 LECRIM, conforme al artículo 588 ter a LECRIM, que fija en qué delitos se puede acordar una escucha telefónica y que son:

1.º Delitos dolosos castigados con pena con límite máximo de [COMPLETAR], al menos, tres años de prisión.
2.º Delitos cometidos en el seno de un grupo u organización criminal.
3.º Delitos de terrorismo.

Con ello, los delitos contra la salud pública son susceptibles de ser investigados con escuchas.

Presupuestos habilitantes de las intervenciones telefónicas (STS 841/2016, de 8 de noviembre, rec. 541/2016)

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
