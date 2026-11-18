---
name: acoso-telefonico-stalking-acusacion-816
description: "Redacta el escrito «Acoso telefónico o stalking: acusación» (formulario 816 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acoso telefónico o stalking: acusación

> Formulario 0816 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…u teléfono fijo y móvil reclamándole que»; «…, llegando a recibir al día un total de»; «…o contestado de la compañía de telefonía»; «…r el cliente con número de teléfono fijo»; «…y móvil»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental, teniendo por reproducidos los documentos que se acompañan a la querella y oficio contestado de …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 172 ter CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- art. 173.2 CP
- art. 20.1 CP
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

### Formulario 0816 · Acoso telefónico o stalking: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 17 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos como un delito de acoso telefónico o stalking del art. 172 ter CP.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Desde el día [FECHA] el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] está realizando llamadas telefónicas a mi representado/a de forma insistente, a cualquier hora del día y de la noche, a su teléfono fijo y móvil reclamándole que [COMPLETAR], llegando a recibir al día un total de [COMPLETAR] llamadas, lo que hace sin tener o disponer de autorización alguna para llevar a cabo este acoso insistente, menoscabando y vulnerando su derecho a la libertad y alterando gravemente su vida cotidiana.

Se le ha advertido de que, en el caso de persistir en el acoso telefónico, acudiría al órgano judicial ejercitando acciones penales, pese a lo cual ha seguido insistiendo en sus llamadas a cualquier hora del día, incluso a altas horas de la madrugada, perturbando la vida de su familia, entendiendo mi mandante que la solución a este grave problema no es cambiar de número de teléfono, por cuanto no debe cambiar sus hábitos ni conducta.

Esta actitud del/de la acusado/a ha supuesto para mi mandante un claro ataque contra la libertad con afectación a la vida de las personas al perturbarle en su tranquilidad y en su vida diaria sin poder convencerle de que cese en su conducta insistente.

SEGUNDA.- Tales hechos son constitutivos del delito de acoso o stalking del art. 172 ter CP. (2)

TERCERA.- Es responsable del delito de acoso del art. 172 ter CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de acoso la pena de [PENA].

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], y que han presenciado las llamadas persistentes

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos que se acompañan a la querella y oficio contestado de la compañía de telefonía [COMPLETAR] con informe acerca del número de llamadas recibidas en el número de teléfono de D./Dña. [NOMBRE Y APELLIDOS] por el cliente con número de teléfono fijo [COMPLETAR] y móvil [COMPLETAR], identificando al titular de ambos números de teléfono, en los últimos tres meses, especificándolo por fechas y horas al objeto de acreditar el acoso telefónico.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde la notificación del auto del juez por la vía del art. 780 LECRIM.

(2) El delito del art. 172 ter CP está incluido dentro de los delitos contra la libertad y fue preciso añadirlo en el texto penal ante la impunidad de estos hechos que atacan la libertad de los ciudadanos a no verse acosados de forma persistente e insistente por una persona. No solo afecta a actos de cercanía física, sino a cualesquiera que determinen el acoso con alguien incluido el telefónico.

Si la persona del querellado fuera alguna de las personas del art. 173.2 CP existe una agravación de la conducta por tratarse de violencia doméstica o de género

La SJ Primera Instancia en Instrucción Tudela, de 23 de marzo de 2016. Rec. 260/2016 dicta la primera sentencia condenatoria por el delito de acoso o «stalking» del art. 172 ter CP que estableció estos tres requisitos fundamentales para su concurrencia:

a) Una estrategia sistemática de persecución a través de conductas insistentes y reiteradas dirigidas al logro de una determinada finalidad que las vincule, es decir, un patrón de conducta que descarta actos aislados.
b) La alteración grave del desarrollo de la vida cotidiana del sujeto pasivo. A partir de la LO 10/2022, de garantía integral de la libertad sexual, vigente desde el 7 de octubre de 2022, ya no se exige el requisito de que la alteración sea grave.
c) Denuncia previa del agraviado salvo que el ofendido sea alguna de las personas del art. 173.2 CP.

El TS, en su primer pronunciamiento sobre este delito (STS 324/2017, de 8 de mayo, Rec. 1775/2016), incide en el primero de los requisitos citados, estableciendo que el delito de ‘stalking’ requiere una vocación de persistencia o una intencionalidad, latente o explícita, de sistematizar o enraizar una conducta intrusiva sistemática (persecución, reiteración de llamadas...) capaz de perturbar los hábitos, costumbres, rutinas o forma de vida de la víctima. No bastan por ello unos episodios, más o menos intensos o más o menos numerosos pero concentrados en pocos días y sin nítidos visos de continuidad, que además no comporten repercusiones en los hábitos de la víctima.

Se exige implícitamente una cierta prolongación en el tiempo; o, al menos, que quede patente, que sea apreciable, esa voluntad de perseverar en esas acciones intrusivas, que no se perciban como algo puramente episódico o coyuntural, pues en ese caso no serían idóneas para alterar las costumbres cotidianas de la víctima –asevera la Sala-.El tipo no exige planificación pero sí una metódica secuencia de acciones que obligan a la víctima, como única vía de escapatoria, a variar, sus hábitos cotidianos, matiza el Supremo.

La SAP Madrid 80/2017, de 27 de marzo, Rec. 415/2016, señala también que no es aplicable la atenuante de "enamoramiento" a este tipo penal (alteración psíquica del art. 20.1 CP), pues de otro modo todo enamoramiento se convertiría en justificativo de la conducta perseguida, destipificándola.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
