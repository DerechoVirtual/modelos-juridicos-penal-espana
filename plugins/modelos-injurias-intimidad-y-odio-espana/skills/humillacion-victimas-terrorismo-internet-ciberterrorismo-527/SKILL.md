---
name: humillacion-victimas-terrorismo-internet-ciberterrorismo-527
description: "Redacta el escrito «Humillación a víctimas del terrorismo por internet (ciberterrorismo): acusación» (formulario 527 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Humillación a víctimas del terrorismo por internet (ciberterrorismo): acusación

> Formulario 0527 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…RIMERA.- El/La acusado/a ha publicado en»; «…diversos mensajes en fechas»; «…a del terrorismo y que fue asesinada por»; «…ma del terrorismo, que fue asesinada por»; «…sobre la que expuso que»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical:…
- .- Documental, (prueba digital) teniendo por reproducido los documentos aportados. Entre ellos Acta notarial d…
- SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la medida…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 578 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 578.1, 2 y 4 CP
- art. 22 del CP
- artículos 572 a 577 CP
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

### Formulario 0527 · Humillación a víctimas del terrorismo por internet (ciberterrorismo): acusación

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta las conclusiones provisionales calificando los hechos de delito de humillación a víctimas del terrorismo del art. 578 CP al haber vertido en redes sociales comentarios de menosprecio a víctimas del terrorismo.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de los acusadores particulares D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a ha publicado en [COMPLETAR] diversos mensajes en fechas [COMPLETAR] en los que señala que: D./Dña. [NOMBRE Y APELLIDOS], víctima del terrorismo y que fue asesinada por [COMPLETAR] merecía morir y que debió hacerlo mucho antes. Lo mismo hizo constar con D./Dña. [NOMBRE Y APELLIDOS], víctima del terrorismo, que fue asesinada por [COMPLETAR] sobre la que expuso que [COMPLETAR]. En ambos casos con clara y demostrada intención de humillar a las víctimas del terrorismo.

Ambas víctimas son hijos/as de los/as querellantes.

SEGUNDA.- Tales hechos son constitutivos del delito de humillación a víctimas del terrorismo del art. 578.1, 2 y 4 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a la pena de [PENA] a razón de [IMPORTE] euros/día y responsabilidad personal subsidiaria de 1 día por cada dos cuotas insatisfechas.

SEXTA.- Procede condenar al/a la acusado/a a que indemnice a la/s víctima/s por el importe de [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], padres de las víctimas.
- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes que accedieron al inmueble del/de la acusado/a para la intervención del ordenador.
- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes del Grupo de delitos tecnológicos que realizaron la localización del ordenador de procedencia.

.- Pericial informática del ordenador del/de la acusado/a y los contenidos habidos en el mismo.

Pericial de la brigada de delitos tecnológicos de la Policía Nacional.

[OPCIONAL — incluir si procede]

.- Documental, (prueba digital) teniendo por reproducido los documentos aportados. Entre ellos Acta notarial del/de la Ilmo/a. Sr./Sra. Notario/a D./Dña. [NOMBRE Y APELLIDOS] donde consta la constatación de ajustarse el documento anterior a la realidad, al ser adverado notarialmente cada documento aportado en base al cotejo en el propio ordenador.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO: No habiéndose acordado en la admisión de la querella se reitera la solicitud de la medida cautelar de retirada de los contenidos por el prestador de servicio que sigue sin verificarse, bajo apercibimiento de desobediencia a la orden judicial.

SUPLICO A LA SECCIÓN: Que adopte las medidas cautelares solicitadas y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) En el art. 578 CP se prevén dos tipos de conductas:

1.- Enaltecimiento o la justificación públicos de los delitos comprendidos en los artículos 572 a 577 CP [NOTA DE REVISIÓN: El art. 578.1 CP remite a los delitos de los arts. 572 a 577. Fuente: Código Penal, BOE-A-1995-25444, art. 578.1.] o de quienes hayan participado en su ejecución.
2.- La realización de actos que entrañen descrédito, menosprecio o humillación de las víctimas de los delitos terroristas o de sus familiares.

Y al objeto del ciberdelito, una agravación en el apartado segundo si se lleva a cabo por Internet. Sobre esta modalidad de delito cometido por redes sociales existe una importante doctrina de la Sala Segunda del Tribunal Supremo que trata de delimitar claramente el delito.

STS 378/2017, de 25 de Mayo, rec. 8/2017: el tipo exige formalmente una actuación del sujeto que suponga justificar delitos de terrorismo o enaltecer a los que hayan participado en ellos.

STS 706/2017, de 21 de Octubre, rec. 514/2017: la mera reproducción de imágenes y el "retuiteo" con difusión pública, aunque hubieran sido tomadas por un tercero, constituyen delito del art. 578 CP. El tipo penal no exige que el acusado asuma como propio, razone o argumente la imagen y su mensaje, o que los haya creado, sino que basta que disponga de ellos y les de publicidad. La expansión del mensaje posibilita que terceras personas se percaten de que están enalteciendo la trayectoria personal y los "méritos" de alguien cuya fama procede de los actos terroristas ejecutados.

STS 812/2011, de 21 de Julio, rec. 46/2011: distinción con la apología del terrorismo.

STS 334/2018, de 4 de Julio, rec. 2193/2017: el conjunto de los mensajes analizados no traspasan los límites para ser calificados como delito de humillación a las víctimas del terrorismo. Límites fronterizos entre la vía penal y la civil. Necesidad de que se adopten medidas organizativas en los prestadores de servicio para cortar la difusión inmediata de tales expresiones.

STS 95/2018, de 26 Febrero, Rec. 979/2017.

STS 4/2017, de 18 Enero, Rec. 1619/2016: "Tuits" publicados en la cuenta de famoso cantante-letrista de rap metal.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
