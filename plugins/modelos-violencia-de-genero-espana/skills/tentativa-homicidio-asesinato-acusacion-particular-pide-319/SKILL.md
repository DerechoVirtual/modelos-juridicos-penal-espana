---
name: tentativa-homicidio-asesinato-acusacion-particular-pide-319
description: "Redacta el escrito «Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad» (formulario 319 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad

> Formulario 0319 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] Nº DE DOCUMENTO
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…contra D.»; «…tipificado en el artículo»; «…ento, tutela, curatela o guarda de hecho»; «… dicho matrimonio nacieron dos hijos: 1º»; «…de [Nº] años de edad y el 2º»; «…a potestad respecto de los hijos comunes»; «…y»; «…sión de la patria potestad al denunciado»

## Elecciones que hay que hacer

- homicidio / asesinato

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 544 ter de la Ley de Enjuiciamiento Criminal
- arts. 61 LO 1/2004
- artículo 544 ter.7 LECRIM
- artículo 158 del Código Civil
- artículo 57 del Código Penal
- art. 57 CP
- artículo 29 LO 8/2021
- artículo 48 CP
- artículo 57.2 CP
- Ley Orgánica 8/2021

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

### Formulario 0319 · Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 26 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 4 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia, que fue turnada a ese órgano judicial, por Dña. [NOMBRE Y APELLIDOS] contra D. [COMPLETAR], por la comisión de un delito de tentativa de [ELEGIR: homicidio / asesinato] tipificado en el artículo [COMPLETAR] CP, habiéndonos personado en las actuaciones por escrito de fecha [FECHA] en las DP nº [Nº DE PROCEDIMIENTO]

Que mediante el presente escrito formulo solicitud de adopción de las siguientes medidas cautelares civiles, junto con las penales que se fijen, en el auto resolviendo sobre la orden de protección interesada, en base al artículo 544 ter de la Ley de Enjuiciamiento Criminal, en relación con los arts. 61 LO 1/2004 y ss.

ALEGACIONES

PRIMERA.- Señala el artículo 544 ter.7 LECRIM, en su redacción dada por la Ley Orgánica 8/2021, de protección de la infancia y la adolescencia contra la violencia, que.

«Las medidas de naturaleza civil deberán ser solicitadas por la víctima o su representante legal, o bien por el Ministerio Fiscal cuando existan hijos menores o personas con la capacidad judicialmente modificada, determinando su régimen de cumplimiento y, si procediera, las medidas complementarias a ellas que fueran precisas, siempre que no hubieran sido previamente acordadas por un órgano del orden jurisdiccional civil, y sin perjuicio de las medidas previstas en el artículo 158 del Código Civil. Cuando existan menores o personas con discapacidad necesitadas de especial protección que convivan con la víctima y dependan de ella, el Juez deberá pronunciarse en todo caso, incluso de oficio, sobre la pertenencia de la adopción de las referidas medidas.

Estas medidas podrán consistir en la forma en que se ejercerá la patria potestad, acogimiento, tutela, curatela o guarda de hecho [COMPLETAR], atribución del uso y disfrute de la vivienda familiar, determinar el régimen de guarda y custodia, suspensión o mantenimiento del régimen de visitas, comunicación y estancia con los menores o personas con discapacidad necesitadas de especial protección, el régimen de prestación de alimentos, así como cualquier disposición que se considere oportuna a fin de apartarles de un peligro o de evitarles perjuicios.

Además, el art. 544 quinquies LECRIM señala que:

«1. En los casos en los que se investigue un delito de los mencionados en el artículo 57 del Código Penal, el Juez o Tribunal, cuando resulte necesario al fin de protección de la víctima menor de edad o con la capacidad judicialmente modificada, en su caso, adoptará motivadamente alguna de las siguientes medidas:

a) Suspender la patria potestad de alguno de los progenitores».

En el presente caso se está investigando la comisión de un delito contra la vida de la víctima incluido en el art. 57 CP, siendo viable, por ello, la adopción de la medida de suspensión de la patria potestad.

SEGUNDA.- La peticionaria de las medidas Dña. contrajo matrimonio con el denunciado D. [NOMBRE Y APELLIDOS] en fecha [FECHA] como consta en el documento nº [Nº DE DOCUMENTO] aportado de la inscripción en el registro civil de [LOCALIDAD]. De dicho matrimonio nacieron dos hijos: 1º [COMPLETAR] de [Nº] años de edad y el 2º [COMPLETAR] de [Nº] años de edad. Por lo tanto, ambos menores de edad.

Por ello, y no habiendo procedimiento civil abierto de separación o divorcio, existe obligación del dictado de las medidas civiles en el auto resolviendo sobre la orden de protección, que tendrán una vigencia temporal de 30 días hasta la presentación de la demanda de divorcio, que se presentará ante este órgano judicial por la vía del párrafo 4º del artículo 544 ter.7 LECRIM [NOTA DE REVISIÓN: La LO 8/2021 intercaló en el art. 544 ter.7 LECrim un párrafo tercero sobre la suspensión del régimen de visitas; la vigencia de 30 días de las medidas civiles figura ahora en el párrafo cuarto. Fuente: LECrim, BOE-A-1882-6036, art. 544 ter.7 (redacción LO 8/2021, BOE-A-2021-9347).].

Pero es que, además, en el art. 140 bis 2 CP se especifica el carácter preceptivo, en su caso, de la imposición de la pena de privación de la patria potestad en el caso de la existencia de un delito de homicidio o asesinato a la madre de los menores comunes sobre los que se insta ahora la medida de suspensión de la patria potestad.

Es por ello, y dado que lo permite el art. 544 quinquies LECRIM, y se anuda ahora la preceptividad de esta pena en el art. 140 bis 2 CP, por lo que debe resultar viable que sin esperar a la imposición de dicha pena y en garantía, protección e interés del menor se adopte esta medida de suspensión de la patria potestad respecto de los hijos comunes [COMPLETAR] y [COMPLETAR].

El citado «interés de los menores» exige que se adopte esta medida y que, además, los hijos también son víctimas directas de la violencia de género. El artículo 29 LO 8/2021, de 4 de Junio que lleva por rúbrica «Situación de violencia de género en el ámbito familiar», señala que:

«1. Las administraciones públicas deberán prestar especial atención a la protección del interés superior de los niños, niñas y adolescentes que conviven en entornos familiares marcados por la violencia de género, garantizando la detección de estos casos y su respuesta específica, que garantice la plena protección de sus derechos»

Se debe hacer constar que los menores son víctimas de la violencia ejercida sobre su madre, de ahí la proporcionalidad de esta medida de suspensión del ejercicio de la patria potestad hasta que se dicte sentencia firme.

Además, se interesa que se adopten las siguientes medidas:

1. Se ha solicitado en la denuncia la adopción de la medida cautelar penal de prohibición de aproximación del denunciado del artículo 48 CP, en relación con el artículo 57.2 CP, por lo que se interesa en el presente escrito la adopción de la medida civil de atribución del uso de la vivienda familiar sita en [LOCALIDAD], al ser el interés de la denunciante y de los hijos, los más necesitados de protección, dada la condición de menores de edad de estos y la carencia de actividad laboral de la denunciante.
2. Se solicita la atribución del régimen de guarda y custodia de los menores a Dña. [NOMBRE Y APELLIDOS] y la suspensión de la patria potestad al denunciado [COMPLETAR].
3. Se solicita la atribución por el denunciado de una pensión compensatoria por importe de [IMPORTE] euros en favor de la denunciante al carecer de trabajo, y en razón a los ingresos del denunciado que ascienden a la suma de [IMPORTE], como se acredita con copia del documento de declaración de IRPF del último año.
4. Se solicita la atribución por el denunciado de una pensión por alimentos en favor de cada hijo de [IMPORTE] euros, en razón al mismo documento anteriormente citado.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite para el dictado de la orden de protección, incluyendo como cautelares las medidas civiles interesadas y con suspensión de la patria potestad interesada.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
