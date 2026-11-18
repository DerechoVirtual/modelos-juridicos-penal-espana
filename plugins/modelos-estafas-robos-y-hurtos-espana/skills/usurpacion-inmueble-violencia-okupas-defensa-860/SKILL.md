---
name: usurpacion-inmueble-violencia-okupas-defensa-860
description: "Redacta el escrito «Usurpación de inmueble con violencia (okupas): defensa» (formulario 860 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Usurpación de inmueble con violencia (okupas): defensa

> Formulario 0860 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Declaración de los/as siguientes testigos, vecinos/as del inmueble, que darán razón de la situación comunic…
- - D./Dña. [NOMBRE Y APELLIDOS].…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 245.1 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 245 CP
- art. 964.2.b) LECRIM
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

### Formulario 0860 · Usurpación de inmueble con violencia (okupas): defensa

- Año del modelo: 2016
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la defensa del acusado en procedimiento abreviado presentando sus conclusiones provisionales por delito de usurpación de inmueble con violencia del art. 245.1 CP (movimiento okupa)

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, dirigido por el/la Letrado/a abajo firmante D./Dña. [NOMBRE Y APELLIDOS], colegiado/a n.º [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], con despacho profesional abierto en [LOCALIDAD], en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas / por el delito de usurpación de inmueble del art. 245.1 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo lo que se le atribuye, ya que para que concurra el delito de usurpación de inmueble debe existir una voluntad de permanencia y ésta no se da en el caso analizado, sino que mi representado/a no tenía dónde vivir y una persona, cuya identidad desconoce, le facilitó una llave del inmueble de autos para pasar unos días, pero sin intención de permanencia ni continuidad, por lo que no concurre el delito por el que se le acusa ya que, cuando compareció la comisión judicial el día [FECHA] abandonó el inmueble ante la medida cautelar judicialmente adoptada, saliendo voluntariamente del inmueble. No había voluntad de permanencia. Además, no es cierto que agrediera al conserje en ningún caso. Simplemente discutió con él cuando le reprochó que estuviera allí.

SEGUNDA.- Los hechos no son constitutivos de un delito de usurpación de inmueble del art. 245.1 CP [NOTA DE REVISIÓN (comprobar): La acusación que se contesta es por usurpación con violencia del art. 245.1 CP (multa de tres a seis meses en el 245.2; prisión de uno a dos años en el 245.1). Fuente: Código Penal, BOE-A-1995-25444, art. 245.].

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede, ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito, ya que esos daños los ocasionaría, en su caso, quien le cedió las llaves. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (2)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Declaración de los/as siguientes testigos, vecinos/as del inmueble, que darán razón de la situación comunicada a éstos/as de permanencia puntual y de que antes de que llegara el/la acusado/a al inmueble ya estaba destrozada la cerradura. Deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

- D./Dña. [NOMBRE Y APELLIDOS], para que declare sobre inexistencia de agresión al conserje.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que se le da traslado de las actuaciones.

La frontera en este delito entre el ilícito civil del precario y el art. 245.1 CP radica en el uso de la violencia o intimidación y la permanencia en el inmueble, forzando la entrada, sin ningún título que le habilite para su permanencia en el inmueble, mientras que en las situaciones de precario hay siempre dudas acerca de la titularidad o razón de esa permanencia. Pero en el delito del art. 245.1 CP existen datos [NOTA DE REVISIÓN: La nota trata de la ocupación con violencia o intimidación (art. 245.1 CP); el art. 245.2 CP castiga la ocupación pacífica de inmueble que no constituye morada. Fuente: Código Penal, BOE-A-1995-25444, art. 245.] de inexistencia de autorización de acceso tales como haber forzado la cerradura o actos violentos de acceso típicos en la "ocupación" y la violencia empleada.

Debe tenerse en cuenta que, si no se emplea violencia o intimidación, los hechos serían constitutivos de delito leve del apartado 2º del art. 245 CP, y no habría escrito de acusación, sino citación a juicio por delito leve por la vía del art. 964.2.b) LECRIM. Para imponer la pena de prisión en el caso del art. 245.1 CP se gradúa atendiendo a la utilidad obtenida, que podría medirse por el tiempo disfrutado y el valor de los daños causados.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
