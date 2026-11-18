---
name: amenazas-calificacion-provisional-acusacion-814
description: "Redacta el escrito «Amenazas: calificación provisional de la acusación» (formulario 814 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Amenazas: calificación provisional de la acusación

> Formulario 0814 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (12 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a de un local destinado a restaurante en»; «…el/la acusado/a»; «…icadas con anterioridad, las siguientes:»

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
- - D./Dña. [NOMBRE Y APELLIDOS] cliente que estaba en el local al ocurrir los hechos.…
- - D./Dña. [NOMBRE Y APELLIDOS] trabajador del local que presenció los hechos.…
- (Si desea solicitar diligencias complementarias)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 169 CP
- art. 27.4 LO 5/1995
- artículo 29 de la Ley Orgánica 5/1995
- art. 650 LECRIM
- art. 22 del CP
- art. 29.4 LO 5/1995

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

### Formulario 0814 · Amenazas: calificación provisional de la acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 21 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento ante el Tribunal de Jurado presenta sus conclusiones provisionales calificando los hechos de delito de amenazas del art. 169 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Evacuando en el plazo (1), concedido por el traslado bajo el amparo del art. 27.4 LO 5/1995, que se ha verificado a los fines dispuestos en el artículo 29 de la Ley Orgánica 5/1995 del Tribunal del Jurado, en relación al art. 650 LECRIM, solicitamos la apertura de juicio oral y formulamos, por medio del presente escrito de calificación provisional, contra D./Dña. [NOMBRE Y APELLIDOS] las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] es propietario/a de un local destinado a restaurante en [COMPLETAR]. Justo al lado de su local ejerce la misma actividad el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] con el mismo objeto social. En los últimos tiempos han tenido diferencias a raíz de la actitud del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS] de cierta animadversión hacia D./Dña. [NOMBRE Y APELLIDOS] por tener este/a último/a más clientela en su local y, sin embargo, estar casi vacío el del/de la acusado/a amenazándole desde que abrió el local con gestos, molesto, quizás, porque le achaca a D./Dña. [NOMBRE Y APELLIDOS] que su mal funcionamiento se debe a haber abierto justo a su lado otro restaurante.

Con fecha [FECHA] el/la acusado/a [COMPLETAR] entró en su restaurante gritando y diciéndole que o se marchaba de allí o le iba a partir las piernas, ya que le había arruinado su negocio, profiriendo gritos y haciendo gestos despectivos a los clientes y camareros del local. Al salir le dijo que le daba dos días para irse de allí o que ejecutaría su amenaza y que estaba muy bien hasta que D./Dña. [NOMBRE Y APELLIDOS] abrió su local.

SEGUNDA.- Tales hechos son constitutivos del delito de amenaza del art. 169.1º CP. (2)

TERCERA.- Es responsable del delito de amenaza del art. 169.1º CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre con respecto al/a la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de amenaza la pena de [PENA] de prisión.

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Se tenga por presentado este escrito, evacuadas las conclusiones y se tenga por solicitada la apertura de juicio oral contra D./Dña. [NOMBRE Y APELLIDOS].

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ 1º DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] cliente que estaba en el local al ocurrir los hechos.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] trabajador del local que presenció los hechos.

Por todo lo expuesto,

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias complementarias)

OTROSÍ 2º DIGO: Se proponen además, de conformidad con lo dispuesto en el art. 29.4 LO 5/1995, como diligencias complementarias para su práctica en la audiencia preliminar, y que no son reiteración de las que han sido practicadas con anterioridad, las siguientes: [COMPLETAR].

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se le da traslado de la causa (art. 27.4 LOTJ).

(2) Este es un delito esencialmente doloso que castiga la actitud amenazante de alguien con causarle a él, a su familia o a otras personas con las que esté íntimamente vinculado un mal que constituya delitos de homicidio, lesiones, aborto, contra la libertad, torturas y contra la integridad moral, la libertad sexual, la intimidad, el honor, el patrimonio y el orden socioeconómico.

Una circunstancia es la de la amenaza de revelar o denunciar la comisión de algún delito en cuyo caso el ministerio fiscal podrá, para facilitar el castigo de la amenaza, abstenerse de acusar por el delito cuya revelación se hubiere amenazado, salvo que éste estuviere castigado con pena de prisión superior a dos años. En este último caso, el juez o tribunal podrá rebajar la sanción en uno o dos grados.

================================================================================
