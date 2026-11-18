---
name: publicidad-enganosa-internet-querella-539
description: "Redacta el escrito «Publicidad engañosa por internet: querella» (formulario 539 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Publicidad engañosa por internet: querella

> Formulario 0539 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «…, de profesión [PROFESIÓN], vecinos de»; «…, padres del/de la menor»; «…y administrador/a único/a de la sociedad»; «…comercializadora del producto denominado»; «…icidad los siguientes efectos curativos:»; «…ele los siguientes efectos perjudiciales»; «…o. - Exploración del/de la perjudicado/a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], empleado/a de la empresa fabricante del producto.…
- .- Pericial del/de la médico D./Dña. [NOMBRE Y APELLIDOS] que atendió al/a la menor, sobre el estado del/de la…
- .- Documental:…
- 1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querel…
- .- Se interesa como medida cautelar la orden de retirada del citado producto y se dirija oficio a la agencia d…
- .- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 282 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC

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

### Formulario 0539 · Publicidad engañosa por internet: querella

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 7 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos que presentan los caracteres de un delito contra el mercado y los consumidores de publicidad engañosa, del art. 282 CP, al publicitar por internet los efectos curativos de un producto que no eran ciertos.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mis mandantes, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 282 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim. y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- Los querellantes son D. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, y Dña. [NOMBRE Y APELLIDOS], de profesión [PROFESIÓN], vecinos de [COMPLETAR], con domicilio en [LOCALIDAD], padres del/de la menor [COMPLETAR].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes: el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, propietario/a y administrador/a único/a de la sociedad [COMPLETAR] comercializadora del producto denominado [COMPLETAR], con total intención de aprovecharse de la confianza de los consumidores respecto al consumo del mismo, dadas las características que ofertaba con efectos curativos, difundió por internet el producto citado conteniendo en su publicidad los siguientes efectos curativos: [COMPLETAR].

Tras cinco meses de consumo del citado producto por el/la hijo/a menor de los querellantes empezaron a producírsele los siguientes efectos perjudiciales [COMPLETAR], lo que motivó que tuviera que acudir al médico, quien le recomendó que dejara de consumir el producto que era el causante de los efectos negativos, tras realizar diversos análisis que determinaron que, efectivamente, esa era la causa de sus molestias.

QUINTO.- Los hechos expuestos revisten los caracteres de un delito contra el mercado y los consumidores de publicidad engañosa del art. 282 CP, del que presuntamente es culpable el/la querellado/a.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], empleado/a de la empresa fabricante del producto.

- Exploración del/de la perjudicado/a [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Pericial del/de la médico D./Dña. [NOMBRE Y APELLIDOS] que atendió al/a la menor, sobre el estado del/de la menor y sobre los efectos del producto y la engañosa publicidad anunciada, pero, sobre todo, de la potencialidad de causar el perjuicio. (3)

[OPCIONAL — incluir si procede]

.- Documental:

- Acta notarial del/de la notario/a D./Dña. [NOMBRE Y APELLIDOS] de la página web donde se anunciaba el producto.
- Pantallazo de la página web anunciadora.
- Referencia documental del contenido del producto que consta en cada bote.

SÉPTIMO.- Como medidas cautelares solicitamos:

[OPCIONAL — incluir si procede]

1.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Se interesa como medida cautelar la orden de retirada del citado producto y se dirija oficio a la agencia del medicamento para su análisis y retirada de la comercialización.

[OPCIONAL — incluir si procede]

.- Se interesa se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del/de la investigado/a y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. (4)

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del/de la investigado/a a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del/ de la perjudicado/a en la presente causa.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Se trata de un delito que es de peligro y no de resultado, ya que el tipo penal del art. 282 CP castiga a los que en sus ofertas o publicidad de productos o servicios, hagan alegaciones falsas o manifiesten características inciertas sobre los mismos, de modo que puedan causar un perjuicio grave y manifiesto a los consumidores. No es, pues, un delito de resultado.

La facilidad de su difusión por internet provoca un efecto multiplicador tremendo ya que las tecnologías y redes sociales tienen un efecto de difusión que debe evitarse con medidas cautelares si se detecta la potencialidad de causar daño sin exigirse un concreto resultado. Pero sí decir que si no es potencialmente susceptible de causar perjuicio no está incluido en el art. 282 CP. Se exige, pues, prueba pericial de esta "potencialidad".

Véase STS 1097/2009, de 17 Noviembre, Rec. 946/2009 y STS 522/2009, de 14 Mayo, Rec. 852/2008.

Directiva 2006/114/CE del Parlamento Europeo y del Consejo de la Unión Europea.

Directiva 2005/29/CE, de 11 de Mayo de 2005, del Parlamento Europeo y del Consejo, conocida como " Directiva sobre las prácticas comerciales desleales".

(4) La cautelar que se solicita tiene su base y razón de ser, no solo en la protección de los derechos del perjudicado por el delito, sino en aras a una protección general para evitar la reiteración delictiva de la comisión del ilícito penal por medio de las tecnologías de la comunicación y especialmente por el uso de internet a cualquier futuro perjudicado mientras se tramita la causa y hasta sentencia y su posible transformación en pena.

================================================================================
