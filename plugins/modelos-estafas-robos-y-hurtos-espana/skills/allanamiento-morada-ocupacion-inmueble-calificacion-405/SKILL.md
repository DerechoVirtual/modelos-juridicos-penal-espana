---
name: allanamiento-morada-ocupacion-inmueble-calificacion-405
description: "Redacta el escrito «Allanamiento de morada por ocupación de inmueble: calificación provisional de la defensa» (formulario 405 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Allanamiento de morada por ocupación de inmueble: calificación provisional de la defensa

> Formulario 0405 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] Nº DE DOCUMENTO
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… casa solo tenía los siguientes muebles:»; «…eron que comprar los siguientes muebles:»

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental de los recibos de pago del importe de los muebles adquiridos.…
- (Si desea solicitar diligencias preliminares)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 202.1 CP
- artículos 652 de la Ley de Enjuiciamiento Criminal
- artículo 29.2 de la Ley Orgánica 5/1995
- art. 29.4 LO 5/1995
- art. 30 LO 5/1995
- art. 202 CP
- art. 245.2 CP

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

### Formulario 0405 · Allanamiento de morada por ocupación de inmueble: calificación provisional de la defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 párrafos repetibles señalados; 3 párrafos opcionales señalados; 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en un procedimiento ante el Tribunal del Jurado presenta sus conclusiones provisionales frente a acusación por delito de allanamiento de morada del art. 202.1 CP, alegando que dicho inmueble o bien no era morada o bien no lo había ocupado, sino que lo había arrendado.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en el procedimiento número [Nº DE PROCEDIMIENTO] por el supuesto delito del art. 202.1 CP comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que habiéndose recibido traslado de la causa por parte del/de la Letrado/a de la Administración de Justicia y, de conformidad con los artículos 652 de la Ley de Enjuiciamiento Criminal y artículo 29.2 de la Ley Orgánica 5/1995, del Tribunal del Jurado formulamos (1) (2) las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que una persona cuya identidad desconoce le arrendó el inmueble que ya contaba con la cerradura nueva, porque les facilitó una llave con la que se accedía al mismo. La sorpresa sobreviene cuando el día [FECHA] una persona llamó a la puerta reclamando el acceso y alegando ser el/la propietario/a y se le comunicó que habían arrendado verbalmente el inmueble a una persona.

Por otro lado, se alega que la casa solo tenía los siguientes muebles: [COMPLETAR]. Por lo tanto, no es cierto que pueda constituir morada de nadie, ya que tuvieron que comprar los siguientes muebles: [COMPLETAR], como se acredita con los documentos nº [Nº DE DOCUMENTO]. Ello evidencia que no se ha cometido delito del art. 202.1 CP que requiere que el inmueble constituya morada.

SEGUNDA.- Los hechos no son constitutivos de un delito.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, sin declaración de responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio Fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical:

-Testifical de los/as siguientes testigos que declararán sobre la existencia del contrato verbal de arrendamiento:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Testifical de los encargados del establecimiento donde se compraron los muebles que hay en la vivienda.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental de los recibos de pago del importe de los muebles adquiridos.

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias preliminares)

SEGUNDO OTROSÍ DIGO: De conformidad con lo dispuesto en el art. 29.4 LO 5/1995, se interesa la práctica de las siguientes diligencias complementarias para la audiencia preliminar:

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica y se proceda según lo prevenido en el art. 30 LO 5/1995 conforme a lo interesado.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se recibe el escrito de calificación de la acusación (art. 29. 2 LOTJ)

(2) La defensa tratará de acreditar que el inmueble no es morada, ya que ello excluye la comisión del delito de allanamiento del art. 202 CP y nos encontraríamos ante un delito leve de usurpación del art. 245.2 CP.

Las vías para perseguir la ocupación ilegal de inmuebles son:

1.- Acceso a casa que constituye morada, es decir, amueblada y con los servicios esenciales de suministro dados de alta evidenciando un uso del inmueble, aunque no sea permanente, pero sí ocasional: delito de allanamiento de morada del art. 202 CP.

Dice la STS 731/2013, de 7 de octubre, rec. 11142/2012: "Encontrarán la protección dispensada al domicilio aquellos lugares en los que, permanente o transitoriamente, desarrolle el individuo esferas de su privacidad, alejadas de la intromisión de terceros no autorizados. "

Por lo tanto, el concepto de domicilio es más amplio que el que se deriva de una mera constatación administrativa o tributaria relativa al lugar donde se fija la residencia a esos efectos para constituir el lugar cerrado que una persona dedica al desarrollo de todos o de algunos aspectos de su privacidad. (STS 852/2014, de 11 de diciembre, rec. 1068/2014; STS 509/2012, de 19 de junio, rec. 11121/2011; STS 1775/2000, de 17 de noviembre 2000, rec. 1458/1999).

2.- Acceso a inmueble que no constituya morada, es decir, no amueblada y no usada, ni siquiera ocasionalmente, sin suministro de servicios que evidencian la falta de uso, sin violencia o intimidación en las personas: delito leve de usurpación del art. 245.2 CP, o bien demanda civil.

Véase Instrucción 1/2020 FGEº, de 15 de septiembre, sobre criterios de actuación para la solicitud de medidas cautelares en los delitos de allanamiento de morada y usurpación de bienes inmuebles.

================================================================================
