---
name: revenge-porn-alegaciones-acusacion-516
description: "Redacta el escrito «Revenge porn: alegaciones de la acusación» (formulario 516 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revenge porn: alegaciones de la acusación

> Formulario 0516 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] NÚMERO (2 veces)
- [ ] FECHA
- [ ] IMPORTE
- [ ] Otros 24 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…etrado/a de la acusación particular de D»; «…y Dña»; «… Dña [COMPLETAR], padres del/de la menor»; «…ulta que aproximadamente hacia el mes de»; «…el/la menor»; «…n con el/la también menor y denunciado/a»; «…/la acusado/a subió a las redes sociales»; «…7 CP. (2) TERCERA.- Es autor el/la menor»; «…as particulares que atañen a el/la menor»; «…orme en el que se recoge la necesidad de»; «…sta el momento con la medida cautelar de»; «…. La adopción de la medida cautelar»; …

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Examen de el/la menor encausado/a.…
- .- Testifical, debiendo ser citadas las siguientes personas a través de la oficina judicial:…
- - D./Dña. [NOMBRE Y APELLIDOS] que han visualizado las imágenes subidas a internet identificando a el/la menor…
- .- Documental:…
- OTROSÍ TERCERO DICE: No habiéndose acordado en la admisión de la denuncia, dada la gravedad de los hechos, se …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 31 de la LO 5/2000
- art. 7 de la LO 5/2000
- art. 7.1 i) de la Ley Orgánica 5/2000
- artículo 31 de la Ley Orgánica 5/2000
- art. 35.2 de la Ley Orgánica 5/2000
- art. 13 LECRIM
- art. 468.2 CP
- art. 7.1 i) LO 5/2000
- Ley Orgánica 1/1996

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

### Formulario 0516 · Revenge porn: alegaciones de la acusación

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 33 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus alegaciones calificando los hechos como un delito de descubrimiento y revelación de secretos, en concreto de sexting en su modalidad de "revenge porn" del art. 197.7 CP al haber colgado el denunciado menor de edad en redes sociales imágenes de un encuentro sexual con otro menor, sin el consentimiento de la víctima.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Menores del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Letrado/a de la acusación particular de D [COMPLETAR] y Dña [COMPLETAR], padres del/de la menor [COMPLETAR], en el expediente nº [Nº DE EXPEDIENTE] comparezco ante la Sección de Menores del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] y, como mejor proceda en Derecho, DIGO:

Que, de acuerdo con la facultad que me atribuye el art. 31 de la LO 5/2000, Reguladora de la Responsabilidad Penal de los Menores, vengo a presentar las siguientes:

ALEGACIONES

PRIMERA.- De las actuaciones practicadas resulta que aproximadamente hacia el mes de [COMPLETAR] el/la menor [COMPLETAR] de [Nº] años y, por tanto, menor de edad, mantuvo una relación con el/la también menor y denunciado/a [COMPLETAR] en las que ambos mantuvieron relaciones sexuales que fueron grabadas por este último. Más tarde, el/la menor, decidió poner fin a la relación, lo que motivó constantes llamadas y mensajes de el/la denunciado/a al/a la menor para que no rompieran la relación. Al no querer ceder él/ella a la insistencia, el/la acusado/a subió a las redes sociales [COMPLETAR] videos íntimos grabados sin el consentimiento de el/la menor, en las relaciones sexuales mantenidas entre ambos, habiéndose difundido de forma constante estos videos desde el día al día [FECHA] en que el prestador de esos servicios on line los suprimió, tras ser requeridos por los servicios del/de la letrado/a de el/la denunciante por difusión de videos sexuales de menores (1).

SEGUNDA.- Los hechos relatados son constitutivos de un delito de difusión sin autorización de imágenes que menoscaban su intimidad (sexting) del art. 197.7 CP. (2)

TERCERA.- Es autor el/la menor [COMPLETAR] que aparece como tal de los hechos relatados.

CUARTA.- En la actualidad son circunstancias particulares que atañen a el/la menor [COMPLETAR]

QUINTA.- Por el Equipo Técnico se emitió el correspondiente informe en el que se recoge la necesidad de [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Consolidar los logros obtenidos hasta el momento con la medida cautelar de [COMPLETAR].

La adopción de la medida cautelar [COMPLETAR], de manera inicial o sustitutiva a la de [COMPLETAR]

SEXTA.- Procede, por tanto, imponer al/a la menor la medida de [COMPLETAR] prevista en el art. 7 de la LO 5/2000, por cuanto que resulta procedente atendiendo a la gravedad de los hechos.

Además, procede imponer la medida prevista en el art. 7.1 i) de la Ley Orgánica 5/2000, de 12 de enero, reguladora de la responsabilidad penal de los menores, que señala: "La prohibición de aproximarse o comunicarse con la víctima o con aquellos de sus familiares u otras personas que determine el Juez. Esta medida impedirá al menor acercarse a ellos, en cualquier lugar donde se encuentren, así como a su domicilio, a su centro docente, a sus lugares de trabajo y a cualquier otro que sea frecuentado por ellos. La prohibición de comunicarse con la víctima, o con aquellos de sus familiares u otras personas que determine el Juez o Tribunal, impedirá al menor establecer con ellas, por cualquier medio de comunicación o medio informático o telemático, contacto escrito, verbal o visual. Si esta medida implicase la imposibilidad del menor de continuar viviendo con sus padres, tutores o guardadores, el Ministerio Fiscal deberá remitir testimonio de los particulares a la entidad pública de protección del menor, y dicha entidad deberá promover las medidas de protección adecuadas a las circunstancias de aquél, conforme a lo dispuesto en la Ley Orgánica 1/1996"

SÉPTIMA.- El/la menor y sus padres deberán indemnizar a [COMPLETAR] en la cantidad de [IMPORTE]. euros por daño moral.

En virtud de ello,

SE INTERESA: [COMPLETAR]

Se acuerde la apertura de la correspondiente audiencia para la que se proponen los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Examen de el/la menor encausado/a.

[OPCIONAL — incluir si procede]

.- Testifical, debiendo ser citadas las siguientes personas a través de la oficina judicial:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] que han visualizado las imágenes subidas a internet identificando a el/la menor [COMPLETAR] y al/ a la denunciado/a [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] y D/ña [COMPLETAR] agentes que llevaron a cabo la diligencia de examen del ordenador del menor a fin de explicar su resultado.

[OPCIONAL — incluir si procede]

.- Documental:

- Acta notarial del Notario [COMPLETAR] del Ilustre colegio de acerca de la existencia en internet de las imágenes con grabación notarial de las mismas en su proyección on line, con constancia del día y fecha de su existencia en internet y de su contenido preconstituido.
- Referencia on line de la web donde estaba ubicada.
- Escrito remitido por el/la letrado/a [COMPLETAR] al prestador de servicios a fin de que retiraran de internet el contenido ya descrito en los hechos.
- Acta notarial de desaparición del contenido 10 días después de la comunicación fehaciente al prestador de servicios.
- Equipo de Asesoramiento Técnico, a través de los responsables del informe que aparece en los folios nº [NÚMERO] del expediente y con el objeto de que declaren acerca del contenido del mismo.

Y hace suya la prueba propuesta por las demás partes, con derecho de intervenirla aun cuando fuese renunciada.

OTROSÍ DICE: Que, en interés del menor, y de conformidad con lo establecido en el artículo 31 de la Ley Orgánica 5/2000 Reguladora de la Responsabilidad Penal de los Menores, se presenta este escrito y se propone la participación en el acto de la audiencia de

En todo caso, llámese al acto de la audiencia a [COMPLETAR] como perjudicado civilmente y a [COMPLETAR] como responsable civil.

OTROSÍ SEGUNDO DICE: Que, en interés del menor, y de conformidad con lo establecido en el art. 35.2 de la Ley Orgánica 5/2000 Reguladora de la Responsabilidad Penal de los Menores, se solicita se acuerde la no publicidad de los menores.

[OPCIONAL — incluir si procede]

OTROSÍ TERCERO DICE: No habiéndose acordado en la admisión de la denuncia, dada la gravedad de los hechos, se interesa que por la vía del art. 13 LECRIM y art. 544 bis, 2º párrafo LECRIM se adopte la medida cautelar de prohibición de comunicación del/de la denunciado/a con la víctima por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos realizándose el preceptivo requerimiento/apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden, que como medida cautelar se postula se adopte en el auto de admisión de la querella, comunicándose por cualquier medio con la víctima. Y ello, con independencia de que luego se postule la medida del art. 7.1 i) de la Ley Orgánica 5/2000. (3)

Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al acusado con las advertencias legales.

En [COMPLETAR].

Firma de Abogado/a

NOTAS DEL FORMULARIO

(1) Es recomendable actuar directamente con el prestador de servicios para que suprima esos contenidos de internet, aunque preconstituyendo debidamente la prueba para dejar constancia de ella, en evitación de que desaparezca su rastro de internet.

(2) El delito conocido como "Revenge Porn" (Porno de venganza) es una modalidad del "sexting" tipificado en el art. 197.7 CP y ésa es justo su finalidad: causar daños como respuesta a una decepción amorosa, pero también se ha convertido en una forma de humillación pública.

(3) La adopción de la medida cautelar de prohibición de comunicación es fundamental para evitar la reiteración delictiva mientras se sustancie el procedimiento y concluya en sentencia condenatoria con medida del art. 7.1 i) LO 5/2000. (SAP Madrid 291/2017, de 20 de noviembre, Rec. 1591/2017)

================================================================================
