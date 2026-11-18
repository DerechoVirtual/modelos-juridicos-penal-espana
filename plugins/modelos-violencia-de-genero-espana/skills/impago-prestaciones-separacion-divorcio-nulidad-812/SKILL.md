---
name: impago-prestaciones-separacion-divorcio-nulidad-812
description: "Redacta el escrito «Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación» (formulario 812 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación

> Formulario 0812 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] NÚMERO
- [ ] IMPORTE
- [ ] FECHA (2 veces)
- [ ] Nº DE DOCUMENTO
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…cha prestación económica desde el mes de»

## Elecciones que hay que hacer

- separación / divorcio / nulidad del matrimonio
- contribución a las cargas familiares / pensión compensatoria y de alimentos

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Interrogatorio de la víctima.…
- .- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 227 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- art. 14.5 y 6 LECRIM
- artículo 227 CP
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

### Formulario 0812 · Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 2 bloques de alternativas señalados; 3 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos como delito de impago de prestación económica del art. 227 CP.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- En el asunto /, promovido ante la Sección Civil en funciones de Familia del Tribunal de Instancia de [SEDE], plaza nº [NÚMERO], en el juicio de [ELEGIR: separación / divorcio / nulidad del matrimonio] respecto de su cónyuge D./Dña. [NOMBRE Y APELLIDOS] se dictó resolución a fin de que éste/a abonara a favor del cónyuge denunciante y de sus hijos la cantidad de [IMPORTE] euros mensuales, en concepto de [ELEGIR: contribución a las cargas familiares / pensión compensatoria y de alimentos], habiendo dejado de satisfacer dicha prestación económica desde el mes de [COMPLETAR] hasta la fecha, lo que constituye un periodo mayor que dos meses consecutivos o cuatro no consecutivos.

El/La denunciado/a ha hecho caso omiso del requerimiento judicial que personalmente se le hizo al efecto en su propio domicilio, sito en [LOCALIDAD], en cumplimiento de lo ordenado en la providencia de fecha [FECHA], dictada en el citado procedimiento, y cuyas copias constan como documentos nº [Nº DE DOCUMENTO].

SEGUNDA.- Tales hechos son constitutivos del delito de impago de pensiones del art. 227 CP. (2)

TERCERA.- Es responsable del delito de impago de pensiones del art. 227 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la agravante genérica de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de impago de pensiones la pena de [PENA].

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Interrogatorio de la víctima.

[OPCIONAL — incluir si procede]

.- Documental, por lectura de todo lo actuado hasta el momento de la vista oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

Órgano competente para la instrucción (art. 14.5 y 6 LECRIM y art. 89.5 y 89 bis 5 LOPJ). El grupo de expertos del Observatorio de Violencia Doméstica y de Género del CGPJ, con respecto al delito de abandono de familia en la modalidad de impago de pensiones del artículo 227 CP, distingue 3 supuestos: 1º) Cuando la pensión presuntamente impagada sea la de los hijos, la competencia para conocer del delito de impago corresponderá a la Sección de Violencia contra la Infancia y Adolescencia en caso de existir, pues son aquellos los sujetos pasivos del tipo penal, sin perjuicio de la legitimidad de la madre para denunciar el impago de la pensión alimenticia de sus hijos menores, con discapacidad, o de los hijos mayores con los que conviva. 2º) Cuando la pensión presuntamente impagada sea la compensatoria establecida a favor de la mujer, la competencia corresponderá a la Sección de Violencia sobre la Mujer. 3º) Cuando se denuncie de forma conjunta el impago de la pensión compensatoria y la de alimentos de los hijos, la competencia corresponderá a la Sección de Violencia sobre la Mujer.

(2) Este es un delito esencialmente doloso por el que se sanciona al que dejare de pagar durante dos meses consecutivos o cuatro meses no consecutivos cualquier tipo de prestación económica en favor de su cónyuge o sus hijos. El tipo penal exige como elementos constitutivos:

a) Que una resolución de naturaleza judicial establezca la obligación de prestación económica, y que dicha resolución sea dictada dentro de los procesos a los que el tipo penal hace referencia (aprobando un convenio o en los de separación, divorcio, nulidad, sobre filiación o sobre alimentos, en este caso circunscrito a los exigidos a favor de hijos) (STS 937/2007, de 21 de noviembre, Rec. 434/2007).
b) La realidad de la no realización del pago de esa prestación, en los tiempos y cuantía que el tipo penal refleja,
c) La posibilidad de que dicho pago pueda ser realizado por el obligado (in necesitate nemo tenetur), sin que, sin embargo, se requiera una situación de necesidad por parte del que tiene derecho a la prestación ni que se derive para éste perjuicio alguno diverso del de la no percepción de la prestación, tratándose de un delito de mera inactividad, y
d) El conocimiento de la resolución judicial unido a la voluntad de no realizar el pago, cuya voluntad se estima ausente en los supuestos de imposibilidad de hacer efectiva la prestación, lo que le aleja del reproche de delito que instaure la prisión por deudas.

El Supremo considera "violencia económica" el impago de pensiones alimenticias (STS 239/2021, de 17 de marzo, rec. 2293/2019)

No obstante, si el acusado demuestra que no puede pagar por falta de solvencia ello le beneficiará, de tal manera que si no puede pagar será absuelto.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
