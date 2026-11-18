---
name: propiedad-intelectual-internet-acusacion-626
description: "Redacta el escrito «Propiedad intelectual por internet: acusación» (formulario 626 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Propiedad intelectual por internet: acusación

> Formulario 0626 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] NÚMERO
- [ ] IMPORTE (3 veces)
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…n las siguientes: CONCLUSIONES PRIMERA.-»; «…icio económico directo y en perjuicio de»; «…titular de la obra»; «…o la localización en internet de la obra»; «…sin la autorización del perjudicado»; «…sa el bloqueo del acceso a la página web»; «… 1 de adveración de que en la página web»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que…
- D./Dña. [NOMBRE Y APELLIDOS] agente de la brigada de delitos tecnológicos que detectó la IP del ordenador desd…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial del perito D./Dña. [NOMBRE Y APELLIDOS] que ha evaluado el perjuicio causado al autor de la obra.…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 270.2 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- artículo 270.2 CP
- art. 22 CP
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

### Formulario 0626 · Propiedad intelectual por internet: acusación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 21 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en procedimiento abreviado presenta sus conclusiones provisionales calificando los hechos de delito contra la propiedad intelectual del art. 270.2 CP, al permitir el acusado el acceso a obras a través de enlaces en páginas web, sin autorización del autor.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- [COMPLETAR], mayor de edad, con ánimo de obtener un beneficio económico directo y en perjuicio de [COMPLETAR] titular de la obra [COMPLETAR] ha estado facilitando de modo activo y no neutral y sin limitarse a un tratamiento meramente técnico, el acceso o la localización en internet de la obra [COMPLETAR] que es objeto de propiedad intelectual por medio del registro en la SGAE nº [NÚMERO] sin la autorización del perjudicado [COMPLETAR] y en particular ofreciendo listados ordenados y clasificados de enlaces a la obra antes citada desde la página web abierta por el acusado cuyo acceso es www cobrando por acceso la suma deeuros a cada usuario, siendo el precio de la obra de

El acusado ha llevado a cabo esta actividad de permisividad de acceso a la obra en los últimos dos años calculándose un perjuicio de [IMPORTE] euros según informe pericial.

No existe autorización del autor de la obra para permitir estos accesos a la obra.

SEGUNDA.- Tales hechos son constitutivos del delito contra la propiedad intelectual del artículo 270.2 CP.

TERCERA.- Es responsable del delito en concepto de autor el acusado.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al acusado circunstancias agravantes.

Concurre con respecto al acusado la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al acusado/a, por el delito contra la propiedad intelectual la pena de de prisión y [Nº] meses de multa a razón de [IMPORTE] euros diarios. Se interesa el bloqueo del acceso a la página web [COMPLETAR] Y se ordenará la interrupción de la prestación del mismo al prestador del servicio.

Además, procede imponer la pena de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. (2)

SEXTA.- Los daños y perjuicios causados al autor titular de la obra asciende a la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados
judicialmente
mediante exhorto

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] agente de la brigada de delitos tecnológicos que detectó la IP del ordenador desde el que se llevaba a cabo la comisión del ilícito penal.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial del perito D./Dña. [NOMBRE Y APELLIDOS] que ha evaluado el perjuicio causado al autor de la obra.

[OPCIONAL — incluir si procede]

.- Documental:

-Copia de registro en SGAE de los derechos de autor del perjudicado respecto de la obra.
-Acta notarial como doc. nº 1 de adveración de que en la página web [COMPLETAR] se permite el acceso a la obra previo pago del importe de (4)

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) En este caso, ante la inexistencia de una previsión de esta pena se ha optado por acudir al mecanismo de la "prohibición de acudir al lugar del delito" que se configura en este caso por medio de identificar el "lugar" con "internet", en cuyo caso se acuerda esta pena por la vía del art. 48 CP, en relación con el art. 57 CP. ( SJP Barcelona 243/2019, de 29 de mayo, Rec. 7/2018)

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

(4) Dado que se trata de delito cometido on line es necesario aportar acta notarial de constancia on line y probar su difusión.

================================================================================
