---
name: infidelidad-custodia-documentos-calificacion-provisional-441
description: "Redacta el escrito «Infidelidad en la custodia de documentos: calificación provisional de la defensa» (formulario 441 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infidelidad en la custodia de documentos: calificación provisional de la defensa

> Formulario 0441 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a ya que, tratándose de un expediente de»; «…s preciso la incorporación del documento»; «…, ya que la norma»; «…erto sobre tramitación de expedientes de»; «…lementarias para la audiencia preliminar»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical de los/as siguientes testigos que deberán ser citados/as [ELEGIR: judicialmente / mediante exhor…
- - D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre el curso del procedimiento y la no exigencia de incorporac…
- - D./Dña. [NOMBRE Y APELLIDOS], funcionario/a que ha actuado también en la tramitación del expediente.…
- .- Pericial de experto sobre tramitación de expedientes de [COMPLETAR] y documentos que deben incorporarse al …
- .- Documental de la contestación dada por el/la acusado/a al requerimiento efectuado explicando con claridad y…
- (Si desea solicitar diligencias preliminares)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 413 CP
- artículos 652 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0441 · Infidelidad en la custodia de documentos: calificación provisional de la defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 5 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el funcionario acusado por delito de infidelidad en la custodia de documentos del art. 413 CP presenta sus conclusiones provisionales en un procedimiento ante el Tribunal del Jurado negando la comisión del delito alegando que no es obligatorio que el documento reclamado conste en un expediente concreto.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en el procedimiento número [Nº DE PROCEDIMIENTO] por el supuesto delito de infidelidad en la custodia de documentos del art. 413 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que habiéndose recibido traslado de la causa por parte del/de la Letrado/a de la Administración de Justicia y, de conformidad con los artículos 652 de la Ley de Enjuiciamiento Criminal y artículo 29.2 de la Ley Orgánica del Tribunal del Jurado formulamos (1) las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que, tratándose de un expediente de [COMPLETAR] no es preciso la incorporación del documento [COMPLETAR], ya que la norma [COMPLETAR] no lo exige. Por otro lado, el delito de infidelidad en la custodia de los documentos exige una comisión estrictamente dolosa y no culposa, por lo que, incluso en el caso de que se tratara de una imprudencia, el hecho quedaría impune y no sería delictivo, quedando su tratamiento en el ámbito puramente disciplinario. (2)

SEGUNDA.- Los hechos no son constitutivos de un delito de infidelidad en la custodia de los documentos del art 413 CP.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

QUINTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio fiscal y el acusador particular y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical de los/as siguientes testigos que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre el curso del procedimiento y la no exigencia de incorporación al expediente del documento reclamado.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], funcionario/a que ha actuado también en la tramitación del expediente.

[OPCIONAL — incluir si procede]

.- Pericial de experto sobre tramitación de expedientes de [COMPLETAR] y documentos que deben incorporarse al mismo.

[OPCIONAL — incluir si procede]

.- Documental de la contestación dada por el/la acusado/a al requerimiento efectuado explicando con claridad y nitidez la no incorporación y su fundamento.

[OPCIONAL — incluir si procede]

(Si desea solicitar diligencias preliminares)

SEGUNDO OTROSÍ DIGO: De conformidad con lo dispuesto en el art. 29.4 LOTJ, se interesa la práctica de las siguientes diligencias complementarias para la audiencia preliminar [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica y se proceda conforme a lo prevenido en el art. 30 LOTJ conforme a lo interesado

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 5 días desde que se recibe el escrito de calificación de la acusación (art. 29. 2 LOTJ).

(2) Los verbos típicos de la acción ilícita del art. 413 CP son: sustraer, destruir, inutilizar u ocultar. Habrá que valorar a la hora de interponer la querella cuál es la acción que va a ser objeto de acusación y redactarla.

Se trata de un delito eminentemente doloso al usar la expresión a sabiendas. Si lo que ha ocurrido es que el documento se ha extraviado no habrá delito, o si ha habido imprudencia en su custodia tampoco lo hay, porque las acciones de los verbos descritos exigen una actuación con dolo.

La actuación de defecto en la custodia podría dar lugar a responsabilidad disciplinaria, pero no penal. El principio de intervención mínima del derecho penal impide acudir a la vía penal si el hecho se debe a imprudencia o defecto de custodia.

Debe tratarse de documento sobre el que exista deber de conservar. Nótese que el tipo exige que se trate de documento "cuya custodia tenga encomendada", por lo que si no concurre este elemento tampoco se podrá acudir a la vía penal. Si el documento en cuestión no era preciso que se debiera conservar o custodiar, o fuera prescindible por poder ser sustituido por otro u otros que consten tampoco habrá delito, podría ser disciplinario, pero no penal.

Doctrina jurisprudencial: (STS 167/2018, de 11 de abril, rec. 1087/2017) (STS 542/2016, de 20 de junio, rec. 4/2016) (STS 941/2009, de 29 de septiembre, rec. 635/2008) (STS 497/2012, de 4 de junio, rec. 250/2011)

================================================================================
