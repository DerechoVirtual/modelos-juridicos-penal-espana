---
name: usurpacion-inmueble-violencia-okupas-acusacion-866
description: "Redacta el escrito «Usurpación de inmueble con violencia (okupas): acusación» (formulario 866 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Usurpación de inmueble con violencia (okupas): acusación

> Formulario 0866 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
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
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] IMPORTE (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte]…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial del/de la perito que ha elaborado informe de daños causados.…
- .- Documental: escritura pública de titularidad del inmueble e informe documental de daños causados.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 245.1 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- artículo 245.1 CP
- art. 22 CP
- art. 245 CP
- art. 964.2.b) LECRIM
- art. 777.2.3 LECr

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

### Formulario 0866 · Usurpación de inmueble con violencia (okupas): acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 17 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales por delito de usurpación de inmueble con violencia (movimiento okupa) del art. 245.1 CP

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, dirigido por el/la Letrado/a abajo firmante D./Dña. [NOMBRE Y APELLIDOS], colegiado/a n.º [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (1) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- En el inmueble propiedad de D./Dña. [NOMBRE Y APELLIDOS] se ha introducido de forma ilegal y sin autorización de su titular D./Dña. [NOMBRE Y APELLIDOS] desde hace un mes aproximadamente, según nos informó el/la presidente/a de la comunidad, ya que el/la acusado/a irrumpió en el inmueble y rompió la cerradura y la cambió por otra, y al mismo tiempo empujó al conserje y le dio una bofetada, aunque sin causar lesión, cuando le preguntó por qué había causado el daño y entrado en el inmueble sin autorización del/de la dueño/a. El/la acusado/a no dispone de ningún título que habilite su presencia en el inmueble, ni dispone de ninguna autorización para residir en él. Existe oposición del/de la titular del inmueble a este hecho al haber acudido al mismo en tres ocasiones realizándole requerimiento notarial para que lo abandone con resultado negativo, habiendo empujado y tirado al suelo, en una de ellas, al/a la dueño/a cuando le recriminó para que abandonara el inmueble, aunque sin causar lesión.

Los daños causados en el inmueble ascienden a un valor de [IMPORTE] euros en razón al valor de cambio de cerradura y daños causados en el interior una vez tasados cuando se ejecutó la medida cautelar de entrada en el inmueble. (2)

SEGUNDA.- Tales hechos son constitutivos del delito de usurpación de inmueble del artículo 245.1 CP.

TERCERA.- Es responsable del delito de usurpación en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a circunstancias modificativas de la responsabilidad criminal.

Concurre con respecto al/a la acusado/a la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de usurpación la pena de [PENA] de prisión.

SEXTA.- Los daños causados en el inmueble ascienden a un valor de [IMPORTE] euros, en razón al valor de cambio de cerradura y daños causados en el interior una vez tasados cuando se ejecutó la medida cautelar de entrada en el inmueble.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS], conserje del edificio, que fue agredido/a por el/la acusado/a.

[OPCIONAL — incluir si procede]

.- Pericial del/de la perito que ha elaborado informe de daños causados.

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental: escritura pública de titularidad del inmueble e informe documental de daños causados.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que se recibe traslado de las actuaciones.

(2) Debe entenderse que a estas alturas del procedimiento se habrá acordado la medida cautelar de expulsión del inmueble, ya que se debe haber instado con la denuncia o querella para que se ejecute rápidamente la expulsión.

La frontera en este delito entre el ilícito civil del precario y el art. 245.1 CP radica en el uso de la violencia o intimidación y la permanencia en el inmueble forzando la entrada sin ningún título que le habilite para su permanencia en el inmueble, mientras que en las situaciones de precario hay siempre dudas acerca de la titularidad o razón de esa permanencia. Pero en el delito del art. 245.1 CP existen datos de inexistencia de autorización de acceso tales como haber forzado la cerradura o actos violentos de acceso típicos en la "ocupación" y la violencia empleada.

Debe tenerse en cuenta que, si no se emplea violencia o intimidación, los hechos serían constitutivos de delito leve del apartado 2º del art. 245 CP, y no habría escrito de acusación, sino citación a juicio por delito leve por la vía del art. 964.2.b) LECRIM. Para imponer la pena de prisión en el caso del art. 245.1 CP se gradúa atendiendo a la utilidad obtenida, que podría medirse por el tiempo disfrutado y el valor de los daños causados.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2.3 LECr.).

================================================================================
