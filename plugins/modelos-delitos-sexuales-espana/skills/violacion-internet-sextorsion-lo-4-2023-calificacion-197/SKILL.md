---
name: violacion-internet-sextorsion-lo-4-2023-calificacion-197
description: "Redacta el escrito «Violación por internet (sextorsión, LO 4/2023): calificación provisional del acusador particular» (formulario 197 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación por internet (sextorsión, LO 4/2023): calificación provisional del acusador particular

> Formulario 0197 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] CIRCUNSTANCIA
- [ ] PENA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN (2 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…s en el periodo comprendido entre el año»; «…y el año»

## Elecciones que hay que hacer

- Instrucción / Violencia sobre la Mujer

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical:…
- - D./Dña. [NOMBRE Y APELLIDOS] amigas/os a los/as que la víctima contó lo ocurrido.…
- .- Pericial.…
- .- Documental, (prueba digital) teniendo por reproducido los documentos aportados. Entre ellos, los correos el…
- SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella y dada la gravedad de los hechos, se…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 651 LECrim
- artículo 179.2 CP
- art. 74 CP
- art. 197.1 CP
- art. 22 del CP
- art. 179.2 CP
- art. 57 CP
- art. 48.1 y 57 CP
- art. 192 CP
- art. 192.3 CP
- art. 13 LECrim
- art. 544 bis LECrim
- art. 468.2 CP
- art. 681.3 LECrim

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

### Formulario 0197 · Violación por internet (sextorsión, LO 4/2023): calificación provisional del acusador particular

- Año del modelo: 2022
- Revisión 17-11-2026: 5 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 25 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento de sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de la Sección de [ELEGIR: Instrucción / Violencia sobre la Mujer] plaza nº [NÚMERO], comparezco ante la Sala y como mejor proceda en derecho, DIGO:

En aplicación del artículo 651 LECrim. y concordantes formulo escrito de calificación, con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- El/La acusado/a ha estado realizando actos de sextorsión a D./Dña. [NOMBRE Y APELLIDOS] al menos en el periodo comprendido entre el año [COMPLETAR] y el año [COMPLETAR]. Por medio de procedimientos informáticos accedió al ordenador enviándole un correo electrónico con un virus que, al abrirlo, le permitió que se introdujera en los archivos privados del ordenador de la víctima. A continuación, se puso en contacto con él/ella por correo electrónico haciéndole saber que disponía de material (fotos y videos) comprometedor para él/ella y que, si no accedía a sus deseos de realizar actos sexuales ante él/ella por medio de una cámara web, los subiría a las redes sociales. Le enviaba correos electrónicos comunicándole la hora en la que debía conectarse con él/ella por webcam. Los actos consistían en introducción de objetos por la vagina/ano de la víctima, así como masturbaciones forzadas por la intimidación ejercida por el autor de los hechos, al modo de la denominada «ciberintimidación».

SEGUNDA.- Los hechos expuestos son constitutivos de un delito de violación del artículo 179.2 CP, al llevarse a cabo con extorsión, que equivale a intimidacion a que se refiere el citado artículo y con introducción de objetos por vía vagina o anal, en relación con el art. 74 CP, por ser continuado, y de un delito de descubrimiento y revelación de secretos del art. 197.1 CP, de los que presuntamente es culpable el/la querellado/a.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de violación del art. 179.2 CP la pena de [PENA] y por el del descubrimiento y revelación de secretos del art. 197.1 CP la pena de [PENA] de prisión y multa de [IMPORTE]. Y que se imponga la pena de alejamiento del art. 57 CP a fin de que no se acerque la víctima a menos de [DISTANCIA EN METROS] metros durante [DURACIÓN], así como la pena de prohibición de comunicación por cualquier medio, la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades, conforme a la STS 547/2022 de 2 de junio, Rec. 1615/2020.

Ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del/de la acusado/a a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar su no acceso a internet, dada la gravedad de los hechos y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

Además, deberá imponérsele la pena de libertad vigilada por [Nº] años después de cumplida la pena de prisión, del art. 192 CP y la de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

SEXTA.- Procede condenar al/a la acusado/a a que indemnice a la víctima por el importe de [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

.- Interrogatorio de la víctima D./Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] agentes que practicaron la detención y la investigación, así como la intervención en el ordenador y en el ipad del/de la acusado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] amigas/os a los/as que la víctima contó lo ocurrido.

[OPCIONAL — incluir si procede]

.- Pericial.

- Pericial informática del ordenador donde se describe la operativa llevada a cabo por el/la acusado/a al acceder al ordenador de la víctima y los contenidos habidos en el mismo, así como su manipulación por el/la acusado/a por el envío del virus que le permitió acceder.

- Pericial de la brigada de delitos tecnológicos de la policía nacional.

[OPCIONAL — incluir si procede]

.- Documental, (prueba digital) teniendo por reproducido los documentos aportados. Entre ellos, los correos electrónicos del/de la acusado/a desde el inicial que le permitió acceder y enviarle un virus hasta los que de forma reiterada le enviaba para que se comunicara a horas determinadas con él/ella por cámara web.

Acta notarial del/de la Ilmo/a. Sr./Sra. Notario/a D./Dña. [NOMBRE Y APELLIDOS] donde consta la constatación de ajustarse a la realidad al ser adverado notarialmente cada documento aportado en base al cotejo en el propio ordenador.

Por todo lo expuesto,

SUPLICO A LA SALA: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella y dada la gravedad de los hechos, se interesa que, por la vía del art. 13 LECrim. y art. 544 bis LECrim. 2º párrafo, se adopte la medida cautelar de prohibición de comunicación del/de la acusado/a con la víctima por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos, realizándose el preceptivo requerimiento o apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que se postula.

Del mismo modo, se interesa que se adopte como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al acusado con las advertencias legales.

Se interesa, además, se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECrim., de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. Todo ello en base a la STS 547/2022 de 2 de junio, Rec. 1615/2020.

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del/de la acusado/a a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del/de la acusado/a, dada la gravedad de los hechos que se están juzgando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

De conformidad con lo dispuesto en el art. 681.3 LECrim., se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre mis necesidades de protección, así como la obtención, divulgación o publicación de imágenes de la víctima o de sus familiares.

SUPLICO A LA SALA: Que adopte las medidas cautelares solicitadas y las necesarias para asegurar las responsabilidades civiles y las costas y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha «ut supra» indicados.

Firma de Abogado/a:	Firma de Procurador/a:

================================================================================
