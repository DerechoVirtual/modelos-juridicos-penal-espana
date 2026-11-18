---
name: uso-imagen-ajena-sin-consentimiento-medios-difusion-237
description: "Redacta el escrito «Uso de la imagen ajena sin consentimiento en medios de difusión pública: querella» (formulario 237 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Uso de la imagen ajena sin consentimiento en medios de difusión pública: querella

> Formulario 0237 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (15 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…abrió en»; «…tarialmente para el cierre del perfil en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.-Declaración del/de la querellado/a.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial:…
- .- Documental siguiente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 26 de la Ley 4/2015
- art. 13 LECRIM
- art. 544 bis LECRIM
- art. 281 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0237 · Uso de la imagen ajena sin consentimiento en medios de difusión pública: querella

- Año del modelo: 2022
- Revisión 17-11-2026: 7 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, por un delito del art 172 ter 5 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- El/la querellante es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El/la querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a D./Dña. [NOMBRE Y APELLIDOS] abrió en [COMPLETAR] un perfil falso incluyendo fotografías del/de la querellante D./Dña. [NOMBRE Y APELLIDOS] y en la parte superior el nombre de la misma al objeto de aparentar y/o simular que, en realidad, el perfil es de el/la querellante, cuando no consta autorización alguna para esta finalidad.

El/la querellante rompió su relación de pareja con el/la querellado/a, razón por la cual este/a último/a llevó a cabo esta conducta.

En el perfil falso abierto en [LOCALIDAD] de el/la querellante se incluyen fotografías personales del/de la mismo/a de contenido sexual, así como datos relativos a que ofrece servicios sexuales a cambio de precio. Ello le ha ocasionado una situación de acoso y hostigamiento, tanto en redes sociales como en la vida real, por parte de muchas personas que contactan para solicitar dichos servicios sexuales, así como humillación por ello, habiendo recibido muchos comentarios denigrantes y vejatorios en las redes sociales.

Esta situación ha provocado a el/la querellante un estado de depresión al punto de necesitar asistencia psicológica en la consulta del especialista D./Dña. [NOMBRE Y APELLIDOS]

El/La querellado/a fue requerido notarialmente para el cierre del perfil en [COMPLETAR] negándose a ello.

QUINTO.- Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 172 ter 5 CP.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.-Declaración del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

-Testifical de los siguientes testigos que han visualizado el perfil falso y sus contenidos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Testifical del/de la psicólogo/a D./Dña. [NOMBRE Y APELLIDOS], a cuya consulta asiste el/la querellante a raíz de los hechos.

Testifical de la víctima D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre los hechos y sobre el impacto que han provocado en su realidad diaria.

En base a lo dispuesto en el art. 26 de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, según redacción dada por la LO 10/2022, se interesa que la declaración de la víctima de delito sexual sea grabada en la instrucción y reproducida en sede judicial en base a que señala que: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: a) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal."

[OPCIONAL — incluir si procede]

.- Pericial:

-Informe pericial psicológico emitido por el/la perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humillación provocada en la víctima por los hechos ocurridos y estado de depresión causado
-Que se oficie a la brigada de delitos tecnológicos a fin de que se averigüe la dirección IP y autoría.

Una vez que la BIT lleve a cabo las diligencias de investigación para detectar la IP desde la que se llevó a cabo el delito, que se redacte oficio policial para interesar la entrada y registro para la intervención del ordenador y se lleve a cabo la intervención y pericial informática de su contenido.

-Pericial informática sobre el contenido del perfil de la red social recibido a realizar por un perito judicial informático.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

-Facturas pagadas en el despacho del/de la psicólogo/a D./Dña. [NOMBRE Y APELLIDOS]
-Requerimiento notarial emitido por el/la notario/a D./Dña. [NOMBRE Y APELLIDOS] al/a la querellado en fecha [FECHA] para el cierre del perfil en redes.
-Acta notarial del/de la notario/a D./Dña. [NOMBRE Y APELLIDOS] sobre el contenido del perfil en la red social y reportaje de la misma de constancia en dicha acta notarial.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre la situación personal del/de la querellado/a disponiendo se proceda a la detención y prisión provisional del mismo, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y otra de [IMPORTE] euros para garantizar la responsabilidad civil.

Se solicita, además, que se acuerde, ex art. 13 LECRIM, la medida cautelar de cierre provisional del perfil falso del/de la querellante para evitar la continuidad en la causación de daños y perjuicios.

Se interesa se proceda a la adopción de la medida cautelar, ex art. 544 bis LECRIM, de la prohibición de acceso a internet del/de la investigado/a, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales.

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del/de la investigado/a a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del/ de la perjudicado/a en la presente causa.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
