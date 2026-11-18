---
name: sexting-difusion-redifusion-inconsentida-imagenes-675
description: "Redacta el escrito «Sexting (difusión o redifusión inconsentida de imágenes por internet): acusación» (formulario 675 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sexting (difusión o redifusión inconsentida de imágenes por internet): acusación

> Formulario 0675 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (15 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…El/La acusado/a»; «…INTA.- Procede imponer al/a la acusado/a»; «…y al/a la acusado/a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatoriode los acusados.…
- .- Testifical de la víctima que declarará sobre los hechos.…
- .- Testifical: de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser…
- .- Informe pericial psicológico emitido por el perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humil…
- .- Documental, teniendo por reproducido los documentos aportados. Entre ellos acta notarial del Ilustre Notari…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- art. 197.3 CP
- art. 777.2 LECRIM

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

### Formulario 0675 · Sexting (difusión o redifusión inconsentida de imágenes por internet): acusación

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en procedimiento abreviado calificando los hechos como delito de sexting del art. 197.7 CP al haberse difundido en internet imágenes de contenido sexual grabadas con la anuencia de la víctima, pero difundidas sin autorización y luego refundidas nuevamente en grupos de WhatsApp sin consentimiento.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y en plazo (1) escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS], con base en las siguientes:

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] han mantenido una relación de pareja durante cinco años iniciada en fecha [FECHA] y concluida por decisión de esta última en fecha [FECHA]. A raíz de la ruptura, varios conocidos le comunicaron que circulaba por internet un video de ambos de contenido sexual en base a relaciones mantenidas de común acuerdo, grabación que también fue consentida, pero para uso privado de la pareja, sin que conste expresa autorización de la parte acusadora a que el contenido de la grabación se difundiera por internet, al contener imágenes que afectan a la privacidad de ambos y que suponen un claro menoscabo grave de la intimidad de la parte acusadora, que se ha visto expuesta a la humillación del/de la acusado/a en venganza por haber roto la relación con él/ella y, en consecuencia, subir a internet la citada grabación para menoscabar su intimidad y humillar a mi representado/a.

D./Dña. [NOMBRE Y APELLIDOS] pudo constatar entrando en internet la existencia del citado video, lo cual fue comprobado en la notaría del Notario D./Dña. [NOMBRE Y APELLIDOS]

El/La acusado/a [COMPLETAR], por su parte, también subió esa grabación sin autorización de la víctima a dos grupos de WhatsApp, resultando evidente que la divulgación menoscababa gravemente la intimidad personal de la víctima, habida cuenta que en el video aparecía como

La divulgación de estas imágenes por ambos querellados le ha ocasionado una grave afectación personal al haber aparecido en varios grupos de Whatsapp sin autorización y en posición gravemente humillante para su persona.

Con ello, ha tenido que acudir a la consulta del psicólogo D./Dña. [NOMBRE Y APELLIDOS] para recibir tratamiento a raíz de estos hechos.

La víctima requirió a los querellados para que retiraran el video, tanto de internet como de los grupos, sin haberlo realizado.

SEGUNDA.- Tales hechos son constitutivos del delito de sexting del art. 197.7 CP. (2)

TERCERA.- Son responsables del delito de sexting del art. 197.7 CP en concepto de autores los acusados.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a circunstancias agravantes

Concurre con respecto al/a la acusado/a la agravante de del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a [COMPLETAR] por el delito del art. 197.7 CP pfo 1º y 3º la pena de [PENA] y al/a la acusado/a [COMPLETAR] por el delito del art. 197.7 CP pfo 2º, según redacción dada por LO 10/2022, de garantía integral de la libertad sexual.

SEXTA.- Se solicita se imponga a los acusados la responsabilidad civil solidaria de [IMPORTE] euros por daño moral psicológico, más las facturas abonadas al psicólogo por importe de [IMPORTE].

Las costas deberán ser satisfechas por los acusados.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, para el juicio oral, intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatoriode los acusados.

[OPCIONAL — incluir si procede]

.- Testifical de la víctima que declarará sobre los hechos.

[OPCIONAL — incluir si procede]

.- Testifical: de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto].

- D./Dña. [NOMBRE Y APELLIDOS] amigo/a que visionó el video en internet.

-D./Dña. [NOMBRE Y APELLIDOS] agente de la Brigada tecnológica que llevó a cabo las diligencias de identificación del autor del delito.

- D./Dña. [NOMBRE Y APELLIDOS] agente que llevó a cabo las diligencias de investigación para detectar la IP del ordenador desde la que se llevó a cabo el delito. (4)

- D./Dña. [NOMBRE Y APELLIDOS] agente que redactó el oficio policial para interesar la entrada y registro para la intervención del ordenador.

- D./Dña. [NOMBRE Y APELLIDOS] agente que intervino en la diligencia de entrada y registro.

[OPCIONAL — incluir si procede]

.- Informe pericial psicológico emitido por el perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humillación provocada en la víctima por los hechos ocurridos y estado de depresión causado para acreditar daño moral.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido los documentos aportados. Entre ellos acta notarial del Ilustre Notario D./Dña. [NOMBRE Y APELLIDOS] del Colegio de [LOCALIDAD] donde consta un CD con la grabación del contenido difundido en internet visionado por el citado Notario como consta en el acta notarial, así como las visualizaciones llevadas a cabo a la fecha del acta notarial. (5)

-Facturas del/de la psicólogo/a.

- Requerimiento notarial a los acusados.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Se castiga en el art. 197.7 CP, como delito de sexting, introducido en el CP en la LO 1/2015 al que, sin autorización de la persona afectada, difunda, revele o ceda a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros, cuando la divulgación menoscabe gravemente la intimidad personal de esa persona.

La pena se impondrá en su mitad superior cuando los hechos hubieran sido cometidos por el cónyuge o por persona que esté o haya estado unida a él por análoga relación de afectividad, aun sin convivencia, la víctima fuera menor de edad o una persona con discapacidad necesitada de especial protección, o los hechos se hubieran cometido con una finalidad lucrativa.

Se trata de un tipo penal que exige la existencia de tres elementos concurrentes:

1.- No consentimiento de la víctima a la difusión de una grabación obtenida con consentimiento de ambos. (Si tampoco existiera consentimiento en la grabación se sanciona con la pena prevista en el art. 197.3 CP de dos a cinco años de prisión).

En este caso la carga de la prueba de la existencia del consentimiento del afectado en difundir las imágenes correspondería al acusado al efectuar el descargo de que la víctima fue la que prestó su consentimiento a que el video o las imágenes se trasladaran a terceros y/o difundieran, ya que de lo contrario se trataría de una prueba diabólica al no poder obligarse a la víctima a que ella probara que «no prestó el consentimiento a que el video se difundiera». En cualquier caso, resultará obvio pensar que determinados videos o imágenes no están autorizadas normalmente a que se difundan, de ahí que se tenga que exigir la prueba del consentimiento al acusado si así lo alega.

2.- La conducta que se sanciona es la de difundir, revelar o ceder a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros.
3.- Que la divulgación menoscabe gravemente la intimidad personal de esa persona. No debe perderse de vista que esta exigencia es un elemento del tipo, por lo que, si se efectúa una difusión de imágenes, pero no llega a considerarse que ello supone una afectación o menoscabo a su intimidad el hecho no será delito. Pero es que el bien jurídico protegido por este delito es, precisamente, la intimidad, y en conjunción con la propia imagen. Pero se exige no una mera afectación a ambas, sino que esta sea grave, de lo que se debe concluir que no se podrá derivar al ámbito de la persecución penal cualquier hecho de divulgación de imágenes o videos, sino aquellos que menoscaben de forma grave esa intimidad personal de la víctima. Se trata de un elemento valorativo del juez, lo que puede ser objeto y materia del recurso en casos de condena.

Hasta la reforma operada por LO 10/2022, de garantía integral de la libertad sexual, vigente desde el 7 de octubre de 2022, no estaba sancionado nada más que el primer envío, pero no los reenvíos sucesivos, habida cuenta que el art. 197.7 CP no se remitía al art. 197.3 CP que sí lo sancionaba, lo que se resuelve con el párrafo 2º del art. 197.7 CP que sí sanciona el segundo reenvío de quien ha recibido esa imagen sin autorización, tampoco, de la persona afectada.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECRIM)

(4) En estos casos de delitos informáticos, como lo es el sexting, los agentes de la policía judicial podrán haber detectado el número de IP del ordenador desde el que se subió el video a internet y, tras ello, por la vía del art. 588 ter k LECRIM se habrá interesado la orden judicial para la averiguación de la identidad del autor.

(5) Este dato es importante a la hora de acreditar el perjuicio por las visualizaciones realizadas que se cerrarán a la fecha del juicio para acreditar el número de visitas de la grabación a la hora de valorar el contenido de la responsabilidad civil. Pero no exige una pericial psicológica como sí se exige en otros casos, ya que esa afectación se deducirá de los hechos probados, pero es importante que en el interrogatorio a la víctima se le pregunte sobre este extremo acerca de su afectación y si se siente afectada por ello en su intimidad.

================================================================================
