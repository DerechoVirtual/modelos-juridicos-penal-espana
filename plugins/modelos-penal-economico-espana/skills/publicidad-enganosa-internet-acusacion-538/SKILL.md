---
name: publicidad-enganosa-internet-acusacion-538
description: "Redacta el escrito «Publicidad engañosa por internet: acusación» (formulario 538 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Publicidad engañosa por internet: acusación

> Formulario 0538 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…y administrador/a único/a de la sociedad»; «…comercializadora del producto denominado»; «…icidad los siguientes efectos curativos:»; «…rir los siguientes efectos perjudiciales»; «…o. - Exploración del/de la perjudicado/a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Declaración de los padres del/de la menor.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], empleado/a de la empresa fabricante del producto.…
- .- Pericial del/de la médico D./Dña. [NOMBRE Y APELLIDOS] que atendió al/a la menor, sobre el estado del/de la…
- .- Documental:…
- SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella, se interesa como medida cautelar la…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 282 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- artículo 282 del Código Penal
- art. 22 del CP
- art. 48.1 y 57 CP
- art. 48 CP
- art. 57 CP
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

### Formulario 0538 · Publicidad engañosa por internet: acusación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 6 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en procedimiento abreviado calificando los hechos de delito contra el mercado y los consumidores de publicidad engañosa del art. 282 CP, al publicitar por internet los efectos curativos de un producto que no eran ciertos.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de los acusadores particulares D. y Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, propietario/a y administrador/a único/a de la sociedad [COMPLETAR] comercializadora del producto denominado [COMPLETAR], con total intención de aprovecharse de la confianza de los consumidores respecto al consumo del mismo, difundió por internet el producto citado conteniendo en su publicidad los siguientes efectos curativos: [COMPLETAR].

Tras cinco meses de consumo por el/la hijo/a menor de mis representados del citado producto, comenzó a sufrir los siguientes efectos perjudiciales [COMPLETAR], lo que motivó que tuviera que acudir al médico, quien le recomendó que dejara de consumir el producto, que era el causante de los efectos negativos, tras realizar diversos análisis que determinaron que era la causa de sus molestias.

SEGUNDA.- Tales hechos son constitutivos del delito contra el mercado y los consumidores de publicidad engañosa del artículo 282 del Código Penal. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 282 CP la pena de [PENA] o multa de [IMPORTE] en razón de [IMPORTE] euros día.

Además, procede imponer la pena de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. (3)

SEXTA.- Se reclama como daño moral la suma de [IMPORTE] euros, en razón al contenido del informe pericial que se adjunta.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Declaración de los padres del/de la menor.

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

— Acta notarial del/de la notario/a D./Dña. [NOMBRE Y APELLIDOS] de la página web donde se anunciaba el producto.
— Pantallazo de la página web anunciadora.
— Referencia documental del contenido del producto que consta en cada bote.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella, se interesa como medida cautelar la orden de retirada del citado producto y se dirija oficio a la agencia del medicamento para su análisis y retirada de la comercialización.

SUPLICO A LA SECCIÓN: Que adopte la medida cautelar solicitada y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Se trata de un delito que es de peligro y no de resultado, ya que el tipo penal del art. 282 CP castiga a los que en sus ofertas o publicidad de productos o servicios, hagan alegaciones falsas o manifiesten características inciertas sobre los mismos, de modo que puedan causar un perjuicio grave y manifiesto a los consumidores. No es, pues, un delito de resultado.

La facilidad de su difusión por internet provoca un efecto multiplicador tremendo ya que las tecnologías y redes sociales tienen un efecto de difusión que debe evitarse con medidas cautelares si se detecta la potencialidad de causar daño sin exigirse un concreto resultado. Pero sí decir que si no es potencialmente susceptible de causar perjuicio no está incluido en el art. 282 CP. Se exige, pues, prueba pericial de esta "potencialidad".

Véase STS 1097/2009, de 17 Noviembre, Rec. 946/2009 y STS 522/2009, de 14 Mayo, Rec. 852/2008.

Directiva 2006/114/CE del Parlamento Europeo y del Consejo de la Unión Europea.

Directiva 2005/29/CE, de 11 de Mayo de 2005, del Parlamento Europeo y del Consejo, conocida como " Directiva sobre las prácticas comerciales desleales".

(3) En este caso, ante la inexistencia de una previsión de esta pena se ha optado por acudir al mecanismo de la "prohibición de acudir al lugar del delito" que se configura en este caso por medio de identificar el "lugar" con "internet", en cuyo caso se acuerda esta pena por la vía del art. 48 CP, en relación con el art. 57 CP. (SJP Barcelona 243/2019, de 29 de mayo, Proc. 7/2018)

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
