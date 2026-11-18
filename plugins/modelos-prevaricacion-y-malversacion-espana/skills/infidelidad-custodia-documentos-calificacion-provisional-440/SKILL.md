---
name: infidelidad-custodia-documentos-calificacion-provisional-440
description: "Redacta el escrito «Infidelidad en la custodia de documentos: calificación provisional de la acusación» (formulario 440 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infidelidad en la custodia de documentos: calificación provisional de la acusación

> Formulario 0440 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] DNI/NIE
- [ ] FECHA (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] DESCRIBIR
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] DURACIÓN
- [ ] LUGAR
- [ ] Nº DE DOCUMENTO
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ún consta acreditado en el Procedimiento»; «…con DNI [DNI/NIE] y domicilio»; «…ntó escrito en la Administración Pública»; «…al objeto de utilizarlo en»; «…a unido al expediente, habida cuenta que»; «…ebe constar en el expediente, por cuanto»; «…ue es de gran trascendencia al objeto de»; «… debe dejar unido al expediente dado que»; «…la pena de [PENA] de prisión,»; «…nalidad. - Documento relativo a la norma»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- - D./Dña. [NOMBRE Y APELLIDOS], compañero/a del/de la funcionario/a al que se ha recabado, de forma insistente…
- .- Documental,…
- (Si desea solicitar diligencias preliminares)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 413 CP
- artículo 29 de la Ley Orgánica 5/1995
- art. 650 LECRIM
- art. 22 del CP

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

### Formulario 0440 · Infidelidad en la custodia de documentos: calificación provisional de la acusación

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito en el que el acusador particular presenta sus conclusiones provisionales en procedimiento ante el Tribunal del Jurado calificando los hechos de delito de infidelidad en la custodia de documentos del art. 413 CP, por no aparecer un documento en un expediente administrativo en el que debería constar.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento [COMPLETAR] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Evacuando en el plazo concedido (1) por el traslado bajo el amparo del art. 27.4 LOTJ, que se ha verificado a los fines dispuestos en el artículo 29 de la Ley Orgánica 5/1995 del Tribunal del Jurado, en relación al art. 650 LECRIM, solicitamos la apertura de juicio oral y formulamos, por medio del presente escrito de calificación provisional, contra D./Dña. [NOMBRE Y APELLIDOS] con DNI [DNI/NIE] y domicilio [COMPLETAR] las siguientes,

CONCLUSIONES PROVISIONALES

PRIMERA.- Con fecha [FECHA] mi mandante presentó escrito en la Administración Pública [COMPLETAR] solicitando se le entregara copia testimoniada, o compulsada, del documento existente en el expediente administrativo nº [Nº DE EXPEDIENTE] referido a [DESCRIBIR] al objeto de utilizarlo en [COMPLETAR].

Nos consta que este documento estaba unido al expediente, habida cuenta que [COMPLETAR].

Ante el retraso en la entrega de la copia del documento o exhibición, se llevó a cabo requerimiento notarial con fecha [FECHA] contestándosele que el documento no está en el expediente, lo que determina que se haya sustraído, destruido, inutilizado u ocultado el mismo por el/la responsable de su custodia, el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS], ya que existe constancia de que ese documento debe constar en el expediente, por cuanto [COMPLETAR].

La parte acusada no ha dado ciencia o razón de la desaparición del documento en el expediente que es de gran trascendencia al objeto de [COMPLETAR] y cuantas veces se ha intentado acceder al/a la responsable de su custodia se ha negado respuesta alguna aun constando ya por escrito en el requerimiento que el documento no está en el expediente, cuando consta, como se ha indicado, que ese documento estaba unido al mismo.

No existe imprudencia o abandono en la custodia, ya que se niega la entrega sin más cuando ese documento estaba unido en el expediente.

Este documento exige la custodia del/ de la funcionario/a, dado que no se trata de un documento accesorio o prescindible, lo que no permitiría el ejercicio de la acción penal, sino que se debe dejar unido al expediente dado que [COMPLETAR]. Se cumple con ello la exigencia del elemento del tipo referido a que "se trate de un documento cuya custodia se exija al funcionario por razón de su cargo".

SEGUNDA.- Tales hechos son constitutivos del delito de infidelidad en la custodia de documentos del art. 413 CP. (2)

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] de prisión, [COMPLETAR] de multa a razón de [IMPORTE] euros/día e inhabilitación especial para empleo o cargo público por tiempo de [DURACIÓN].

Las costas deberán ser satisfechas por el/la acusado/a.

SEXTA.- Procede condenar al/a la acusado/a a que indemnice a D./Dña. [NOMBRE Y APELLIDOS] con [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Se tenga por presentado este escrito, evacuadas las conclusiones y se tenga por solicitada la apertura de juicio oral contra D./Dña. [NOMBRE Y APELLIDOS].

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

- D./Dña. [NOMBRE Y APELLIDOS], Notario/a que llevó a cabo el requerimiento.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], compañero/a del/de la funcionario/a al que se ha recabado, de forma insistente, la entrega de la copia del documento.

[OPCIONAL — incluir si procede]

.- Documental,

- Documentos nº [Nº DE DOCUMENTO] en los que constan las solicitudes llevadas a cabo con resultado negativo.

- Requerimiento notarial y su contenido.

- Copia del expediente en donde es preciso la entrega del documento que se interesa y su finalidad.

- Documento relativo a la norma [COMPLETAR] donde se indica la necesidad de conservarlo por el/la funcionario/a.

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias preliminares)

SEGUNDO OTROSÍ DIGO: Se proponen, además, como diligencias complementarias para su práctica en la audiencia preliminar, y que no son reiteración de las que han sido practicadas con anterioridad, las siguientes:

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica, así como las diligencias complementarias solicitadas.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se le da traslado de la causa (art. 27.4 LOTJ).

(2) Los verbos típicos de la acción ilícita del art. 413 CP son: sustraer, destruir, inutilizar u ocultar. Habrá que valorar a la hora de interponer la querella cuál es la acción que va a ser objeto de acusación y redactarla.

Se trata de un delito eminentemente doloso al usar la expresión a sabiendas. Si lo que ha ocurrido es que el documento se ha extraviado no habrá delito, o si ha habido imprudencia en su custodia tampoco lo hay, porque las acciones de los verbos descritos exigen una actuación con dolo.

La actuación de defecto en la custodia podría dar lugar a responsabilidad disciplinaria, pero no penal. El principio de intervención mínima del derecho penal impide acudir a la vía penal si el hecho se debe a imprudencia o defecto de custodia.

Debe tratarse de documento sobre el que exista deber de conservar. Nótese que el tipo exige que se trate de documento "cuya custodia tenga encomendada", por lo que si no concurre este elemento tampoco se podrá acudir a la vía penal. Si el documento en cuestión no era preciso que se debiera conservar o custodiar, o fuera prescindible por poder ser sustituido por otro u otros que consten tampoco habrá delito, podría ser disciplinario, pero no penal.

Doctrina jurisprudencial: (STS 167/2018, de 11 de abril, rec. 1087/2017) (STS 542/2016, de 20 de junio, rec. 4/2016) (STS 941/2009, de 29 de septiembre, rec. 635/2008) (STS 497/2012, de 4 de junio, rec. 250/2011)

================================================================================
