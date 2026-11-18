---
name: insolvencia-punible-escrito-defensa-393
description: "Redacta el escrito «Insolvencia punible: escrito de defensa» (formulario 393 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Insolvencia punible: escrito de defensa

> Formulario 0393 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o exactamente lo que se le imputa ya que»; «…ierta/s la/s misma/s, habida cuenta que:»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [EL…
- - D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre la inexistencia de insolvencia patrimonial.…
- - D./Dña. [NOMBRE Y APELLIDOS], acreedor/a al que se le han hecho pagos reales.…
- .- Informe pericial que contradice el aportado por la acusación acreditando la inexistencia de insolvencia y d…
- .- Documental siguiente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 259 CP
- artículo 259 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 259.1 CP
- art. 784 LECRIM
- art. 259.2 CP
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

### Formulario 0393 · Insolvencia punible: escrito de defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 3 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado por un delito de insolvencia punible del art. 259 CP en un procedimiento abreviado presenta sus conclusiones provisionales, alegando que no se encuentra en situación de insolvencia, ni ha realizado ninguna de las conductas enumeradas en el apartado 1 del art. 259 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del artículo 259 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que [COMPLETAR], por un lado, no se encontraba en situación de insolvencia patrimonial, sino ante dificultades de pago propias del momento de crisis en el que nos encontramos, y llevando a cabo actuaciones para poder hacer frente al pago de las deudas, por lo que se rompe el primero de los requisitos del art. 259 CP acerca de que la situación del/de la acusado/a no es de insolvencia patrimonial actual o inminente, sino, tan solo, de estar pasando por dificultades económicas sobre las que se están llevando a cabo esfuerzos para asumir y hacer frente a las deudas en el menor tiempo posible.

Con respecto a la/s conducta/s que se citan del art. 259.1 CP no es/son cierta/s la/s misma/s, habida cuenta que: [COMPLETAR].

Faltando ambos presupuestos del art. 259 CP el/la acusado/a no es autor/a del delito del citado artículo. (2) (Si se tratara de la conducta del art. 260 CPse alegaría que no hay acto de favorecimiento doloso a acreedores ficticios, sino que los pagos son correctos y amparados en deuda existente y real y no creada de propósito)

SEGUNDA.- Los hechos no son constitutivos de un delito del art. 259 CP.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no existir responsabilidad penal.

SEXTA.- Disconforme con las correlativas. Al no existir responsabilidad penal no hay tampoco responsabilidad civil.

Las costas deberán declararse de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical: de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre la inexistencia de insolvencia patrimonial.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], acreedor/a al que se le han hecho pagos reales.

[OPCIONAL — incluir si procede]

.- Informe pericial que contradice el aportado por la acusación acreditando la inexistencia de insolvencia y del acto que se cita de los expresados en el art. 259.1 CP.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

- Recibos de pago a acreedores/as reales.
- Contabilidad adecuada de la llevanza del negocio.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) El delito del art. 259 CP debe identificarse con un pronóstico razonable que, en sede penal, ya incluso para la admisión a trámite de la querella o para dar curso a la denuncia, debe estar amparado por un elenco de indicios de suficiente solidez.

La acreditación indiciaria inicial puede llevarse a cabo mediante la aportación a este órgano judicial instructor de datos que pongan de manifiesto claramente la crisis o déficit patrimonial del deudor a quien se imputa la comisión del delito (por ejemplo: relación de acreedores en caso de multiplicidad, inventarios del deudor que reflejen la situación deficitaria, y especialmente, relación de impagos).

Los requisitos de la persona contra quien se dirige la acción penal son dos:

a.- Situación de insolvencia actual o inminente.

La Insolvencia penal es sólo la definitiva «de naturaleza estructural». No coincide completamente con la insolvencia concursal, es más exigente en el carácter del incumplimiento de los pagos. (STS 652/2018, de 14 de diciembre, Rec. 45/2018)

b.- Realizar alguna de las conductas que se citan en el art. 259.1 CP.

• Que supongan una disminución del patrimonio (1ª a 4ª) o la asunción de un riesgo de perdidas injustificadas (5ª).

• Que infrinjan deberes legales contables («insolvencia documental») (6ª a 8ª)

• Cláusula de cierre (9ª) que introduce dos requisitos cumulativos (infracción grave y disminución patrimonial/ocultación) que parte de la jurisprudencia y de la doctrina consideran extensivos al resto de conductas del art. 259.1 CP.

El apartado 1º del art. 259 CP es definido como la insolvencia no causal y el apartado 2º como la insolvencia causal.

Así, cabe, en segundo lugar, (art. 259.2 CP) que mediante alguna de las conductas a que se refiere el apartado anterior, cause su situación de insolvencia, con lo que si en el apartado 1º se exige que se encuentre el querellado en situación de insolvencia y lleve a cabo alguna de estas conductas, en el apartado 2º se admite que "con una de esas conductas" provoque su insolvencia.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
