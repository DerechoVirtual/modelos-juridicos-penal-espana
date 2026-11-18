---
name: utilizar-menores-personas-discapacidad-pornografia-570
description: "Redacta el escrito «Utilizar menores o personas con discapacidad en pornografía por internet: acusación» (formulario 570 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Utilizar menores o personas con discapacidad en pornografía por internet: acusación

> Formulario 0570 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (6 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…RIMERA.- El/La acusado/a sobre el mes de»; «…de la personalidad y de la sexualidad de»

## Elecciones que hay que hacer

- menor de edad / persona necesitada de especial protección
- su corta edad / su discapacidad
- menor / discapacitado necesitado de especial protección
- menor / discapacitado/a

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado/a.…
- .- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba p…
- .- Testifical:…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial…
- .- Documental referida a los videos grabados al objeto de su reproducción en el juicio oral.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 189.1 b) CP
- art. 189 CP
- art. 22 del CP
- art. 57 CP
- art. 48.1 y 57 CP
- art. 48 CP
- art. 192 CP
- art. 192.3 CP
- art. 681.3 LECRIM
- art. 449 ter LECRIM
- art. 777.3 LECRIM
- art. 730.2 LECRIM
- art. 13 LECRIM
- art. 544 bis LECRIM
- art. 468.2 CP
- art. 48.3 CP
- art. 14.5 LECRIM
- art. 89.5 LOPJ
- art. 14.6 LECRIM
- artículos 14.7 LECrim
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

### Formulario 0570 · Utilizar menores o personas con discapacidad en pornografía por internet: acusación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 5 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 bloques de alternativas señalados; 5 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en el procedimiento abreviado calificando los hechos de delito de utilización de menores o discapacitados para pornografía y luego difundirla por internet del art. 189.1 b) y 189.2 a) CP, si la víctima es menor de 16 años, al grabar a un menor o discapacitado en un acto sexual para luego difundirlo en internet.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022 y conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Audiencia Provincial, por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a sobre el mes de [COMPLETAR], utilizando engaño, convenció a [ELEGIR: menor de edad / persona necesitada de especial protección] a dirigirse a su domicilio con la excusa de que era director de cine y que iba a rodar una película con niños y que pensaba que él podría ser uno de los protagonistas. Atraído con esa idea abandonó el parque donde se encontraba jugando con sus amigos y se dirigió con el/la acusado/a a su domicilio. Una vez allí le convenció para rodar una escena realizando actos de masturbación. Una vez grabada la escena el/la acusado/a la subió a una plataforma de pago en internet que había creado para el acceso de quienes quisieran visionar esta grabación.

En la diligencia de entrada y registro efectuada en el domicilio del/de la acusado/a el día [FECHA] los agentes encontraron material de películas pornográficas en su IPAD y ordenador y en concreto también la escena referida.

Todos estos hechos han incidido en el desarrollo de la personalidad y de la sexualidad de [COMPLETAR] de manera negativa, al exponerle a comportamientos y situaciones de naturaleza sexual no acordes a [ELEGIR: su corta edad / su discapacidad].

SEGUNDA.- Tales hechos son constitutivos del delito del art. 189.1 b) CP.

TERCERA.- Es responsable del delito del art. 189 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a, por el delito del art. 189.1 b) CP, la pena de [PENA], así como la pena de alejamiento de la víctima del art. 57 CP, a fin de que no se le acerque a menos de [DISTANCIA EN METROS] metros durante [Nº] años, así como la pena de prohibición de comunicación por cualquier medio, la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. Por ello, y a tenor de la STS Pleno 547/2022 de 2 de junio, Rec. 1615/2020, se solicita se acuerde la prohibición de acudir al uso de internet por [Nº] años, en base al art. 48 CP de prohibir regresar al lugar del delito. Ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar su no acceso a internet, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

Además, en caso de imponer prisión, procederá también la libertad vigilada por [Nº] años, después de cumplida la pena de prisión, del art. 192 CP.

Igualmente, deberá imponérsele la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, según redacción dada por LO 10/2022, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre mis necesidades de protección, así como la obtención, divulgación o publicación de imágenes de la víctima o de sus familiares.

SEXTA.- En concepto de responsabilidad civil se indemnizará con el importe de [IMPORTE] euros

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO PRIMERO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y, además, los siguientes (2):

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado/a.

[OPCIONAL — incluir si procede]

.- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba preconstituida, en base al art. 449 ter LECRIM, en relación con el art. 777.3 LECRIM y el art. 730.2 LECRIM. (3)

[OPCIONAL — incluir si procede]

.- Testifical:

- D./Dña. [NOMBRE Y APELLIDOS] padre/madre del menor.

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] agentes que practicaron la detención y la investigación, así como la intervención en el ordenador y en el ipad del acusado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial

- Judicial respecto a la credibilidad del [ELEGIR: menor / discapacitado necesitado de especial protección] a fin de que declare en el plenario el autor del informe pericial D./Dña. [NOMBRE Y APELLIDOS]

- Informática respecto de la prueba aportada sobre contenido de material aprehendido en el ordenador del acusado/a.

[OPCIONAL — incluir si procede]

.- Documental referida a los videos grabados al objeto de su reproducción en el juicio oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

OTROSÍ DIGO SEGUNDO:

No habiéndose acordado en la admisión de la querella y dada la gravedad de los hechos, se interesa que, por la vía del art. 13 LECRIM y art. 544 bis LECRIM, 2º párrafo, se adopte la medida cautelar de prohibición de comunicación del/de la querellado/a con el/la [ELEGIR: menor / discapacitado/a] por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos, realizándose el preceptivo requerimiento o apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que se postula.

Del mismo modo, se interesa que se adopte como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al acusado con las advertencias legales.

No habiéndose acordado en la admisión de la querella, dada la gravedad de los hechos, se interesa que como medida cautelar, por la vía de los arts. 13 y 544 bis LECRIM, 2º párrafo se adopte la medida cautelar de prohibición de comunicación del/de la querellado/a con el/la el/la [ELEGIR: menor / discapacitado/a] por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos realizándose el preceptivo requerimiento/apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que como medida cautelar se postula se adopte en el auto de admisión de la querella comunicándose por cualquier medio con la parte querellante. Y ello, con independencia de que luego se postule la pena del art. 48.3 CP.

Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al/a la acusado/a con las advertencias legales.

Se interesa, además, se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales.

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

SUPLICO A LA SECCIÓN: Que adopte las medidas cautelares solicitadas y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

El órgano judicial competente para la instrucción de los delitos contra la libertad sexual es la Sección de Violencia sobre la Mujer del Tribunal de Instancia cuando la víctima sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género y, desde el 3 de octubre de 2025, tras la reforma operada por la LO 1/2025, de Eficiencia de la Justicia, también instruye estos delitos cuando la víctima sea una mujer (art. 14.5 LECRIM y art. 89.5 LOPJ).

Cuando la víctima sea un niño, niña o adolescente la competencia para la instrucción es de la Sección de Violencia contra la Infancia y la Adolescencia, si la hay (art. 14.6 LECRIM y art. 89 bis 5 LOPJ). No obstante, los artículos 14.7 LECrim y art. 89 bis 7 LOPJ disponen que "en caso de que los hechos objeto de instrucción por la Sección de Violencia contra la Infancia y Adolescencia también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia corresponderá, en todo caso, a la segunda". En este punto, el grupo de expertos del Observatorio de Violencia Doméstica y de Género del CGPJ entiende que la Sección de Violencia sobre la Mujer conocerá de tales delitos en aquellos supuestos en que la víctima, menor de edad, es o ha sido pareja sentimental del presunto agresor, para lo que habrá que tener en cuenta la edad de aquella a efectos de determinar si tiene madurez suficiente para que pueda considerarse dicha relación análoga a la matrimonial.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr).

(3) En casos como el presente en los que se analizan hechos relacionados con la libertad sexual es altamente frecuente - como recuerda la STS. 845/2012, de 10 de octubre, rec. 10233/2012- que el testimonio de la víctima - haya sido o no denunciante de los mismos- se erija en la principal prueba sometida al examen del Tribunal.

La declaración de la víctima no es prueba indiciaria sino prueba directa y ha sido admitida como prueba de cargo tanto por la doctrina del tribunal constitucional (STC 201/1989, STC 173/1990, y STC 229/1991), como del TS (STS 706/2000, de 26 de abril, rec. 2212/1999 y STS 313/2002, de 22 de febrero, rec. 532/2000). Esto no quiere decir que la existencia de esa declaración se convierta por sí misma y automáticamente en prueba de cargo suficiente, pues, como todas, está sometida a la valoración del Tribunal sentenciador. Una reiterada jurisprudencia establece cuales son los tres parámetros mínimos de contraste a los efectos de la valoración racional de la declaración del denunciante como prueba de cargo. Son la ausencia de incredibilidad subjetiva, la verosimilitud de su versión y la persistencia en la incriminación. Pero incluso en el caso de que alguno de estos tres elementos no fuere, en todo o en parte, favorable a la credibilidad del testimonio de la víctima, puede el órgano judicial concederle validez como prueba de cargo siempre, eso sí, que motive suficientemente las razones de su proceder (STS 119/2019, de 6 de marzo, Rec. 779/2018 y STS 989/2016, de 12 de enero de 2017, Rec. 971/2016).

================================================================================
