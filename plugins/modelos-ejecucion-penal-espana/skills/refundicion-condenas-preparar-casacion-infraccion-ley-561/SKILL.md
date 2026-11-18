---
name: refundicion-condenas-preparar-casacion-infraccion-ley-561
description: "Redacta el escrito «Refundición de condenas: preparar la casación por infracción de ley» (formulario 561 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Refundición de condenas: preparar la casación por infracción de ley

> Formulario 0561 del plugin **Ejecución penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA
- [ ] FECHA DEL AUTO
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…sobre delito de [DELITO] del artículo»; «…nada no haya tomado en consideración las»; «…ado 1º del art. 76 del mismo texto legal»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 849 LECRIM
- art. 76 CP
- art. 988 LECRIM
- artículo 988 de la Ley de Enjuiciamiento Criminal
- art. 849 de la LECrim
- art. 5.4 de la LOPJ
- art. 852 de la LECrim
- art. 25.2 y 24.1 de la CE
- artículo 988 de la LECrim
- artículos 988 de la Ley de Enjuiciamiento Criminal
- art. 76 del Código Penal
- artículo 76.1 del CP
- artículo 76 CP
- artículo 76.2 CP

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

### Formulario 0561 · Refundición de condenas: preparar la casación por infracción de ley

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se prepara recurso de casación por infracción de ley del art. 849 LECRIM, contra auto de refundición de condenas, con arreglo al art. 76 CP, conforme a lo previsto en el art. 988 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de el/la condenado/a D/Dña. [NOMBRE Y APELLIDOS] en ejecutoria número [Nº DE PROCEDIMIENTO] sobre delito de [DELITO] del artículo [COMPLETAR] del CP, ante el órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se me ha notificado el auto de refundición de condena practicado con arreglo al art. 76 CP y, por no considerarlo ajustado a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal presento preparación del recurso de casación, conforme a lo prevenido en el artículo 988 de la Ley de Enjuiciamiento Criminal,

ALEGACIONES

PRIMERA.- Con independencia de que luego se desarrolle en la interposición del recurso de casación ante la Sala de lo Penal del Tribunal Supremo, se advierte su articulación, vía preparación por:

-Infracción de Ley del art. 849 de la LECrim por indebida aplicación del art 76 del CP y
- Infracción de precepto constitucional al amparo de lo establecido en el art. 5.4 de la LOPJ y art. 852 de la LECrim, por vulneración del art. 25.2 y 24.1 de la CE.

Así, en la formación de los bloques de sentencias dictadas por la vía del art. 76 CP se denuncia la inaplicación de dicho artículo por no haber fijado la resolución impugnada un límite máximo de cumplimiento respecto a las penas cuya acumulación se solicitó. Esta omisión determina que el órgano judicial que ha dictado la resolución ahora impugnada no haya tomado en consideración las [COMPLETAR] ejecutorias acumuladas, y no las haya incluido en su pronunciamiento. Si incluimos en la refundición estas otras ejecutorias podrían darse otras posibilidades distintas a la analizada en la resolución invocada, más favorables para el reo, que es lo que se debe tener en cuenta por la vía del art. 76 CP, ya que deben formarse bloques de sentencias para valorar cuál es el que más beneficia al reo, pues dado que la pena más alta que le había sido impuesta es de dos años de prisión, el triple sería de seis años, inferior a la suma de las penas impuestas (siete años de prisión, más la responsabilidad personal de 90 días que también debe incluirse), por lo que, en consecuencia, la refundición favorece al reo y es legalmente procedente.

El Tribunal Supremo dictó STS 900/2016, de 30 de Noviembre señalando que:

"La regla general de cumplimiento de las penas privativas de libertad viene establecida en el art. 75 del C. penal que dispone: "cuando todas o algunas de las penas correspondientes a las diversas infracciones no puedan ser cumplidas simultáneamente por el condenado, se seguirá el orden de su respectiva gravedad para su cumplimiento sucesivo, en cuanto sea posible." Esta regla general tiene su limitación en el apartado 1º del art. 76 del mismo texto legal [COMPLETAR], que dispone: "No obstante lo dispuesto en el artículo anterior, el máximo de cumplimiento efectivo de la condena del culpable no podrá exceder del triple del tiempo por el que se le imponga la más grave de las penas en que haya incurrido, declarándose extinguidas las que procedan desde que las ya impuestas cubran dicho máximo, que no podrá exceder de veinte años", junto a las reglas especiales que siguen a continuación; y el apartado segundo de este artículo, modificado por la LO 1/2015, de 30 de marzo, con entrada en vigor a partir del 1 de julio de 2015, sigue diciendo: "La limitación se aplicará aunque las penas se hayan impuesto en distintos procesos cuando lo hayan sido por hechos cometidos antes de la fecha en que fueron enjuiciados los que, siendo objeto de acumulación, lo hubieran sido en primer lugar." Por su parte, el artículo 988 de la LECrim., regula el trámite que debe seguir el juzgador al que corresponda refundir las condenas: "Cuando el culpable de varias infracciones penales haya sido condenado en distintos procesos por hechos que pudieron ser objeto de uno solo, conforme a lo prevenido en el art. 17 de esta Ley ".

La doctrina de esta Sala (SSTS 1249/1997, 11/1998, 109/1998, 328/1998, 1159/2000, 649/2004, y SSTS 192/2010 y 253/2010, 1169/2011, entre otras muchas, y Acuerdo de Pleno no jurisdiccional de la Sala II del Tribunal Supremo de 29/11/2005), ha adoptado un criterio favorable al reo en la interpretación del requisito de la conexidad que se exige en los artículos 988 de la Ley de Enjuiciamiento Criminal y art. 76 del Código Penal para la acumulación jurídica de penas al estimar que, más que la analogía o relación entre sí, lo relevante es la conexidad " temporal ". Y en concreto, el contenido del Acuerdo del pleno no jurisdiccional de esta Sala de 29 de noviembre de 2005 según el cual " no es necesaria la firmeza de la sentencia para el límite de la acumulación ".

Así pues, deben únicamente excluirse:

1) Los hechos que ya estuviesen sentenciados cuando se inicia el período de acumulación contemplado, que lo será en la fecha de la sentencia que resulte más beneficiosa para el condenado;
2) Los hechos posteriores a la sentencia que determina la acumulación.

Ello porque ni unos ni otros podrían haber sido enjuiciados en el mismo proceso. Habiéndose acordado, como ya hemos dicho, en el Pleno no jurisdiccional del TS de 29 de Noviembre de 2005, que a estos efectos no es necesaria la firmeza de la sentencia para determinar el límite de la acumulación.

SEGUNDA.- En cuanto a los requisitos que exige esta Sala para que proceda la acumulación de condenas, se tiene establecido en reiterada jurisprudencia que, conforme al artículo 76.1 del CP y artículo 988 de la Ley de Enjuiciamiento Criminal, en la fijación del límite máximo de cumplimiento las sentencias cuya acumulación se pretenda deben computarse hechos que pudieran haber sido objeto de enjuiciamiento conjunto en un único proceso. Esto solo podrá entenderse así cuando las condenas lo fueran con relación a hechos que no estuvieren sentenciados al tiempo de cometer otros sobre los que también haya recaído sentencia cuya acumulación se pretenda; de modo que solo serían susceptibles de acumulación las condenas referidas a aquellos hechos próximos o lejanos en el tiempo que no se encuentren separados por una sentencia firme; y ello, aunque no sea la fecha de firmeza la relevante a efectos de acumulación sino la fecha de dictado de la misma. Una vez comprobada la posibilidad de acumulación conforme a este criterio general, habrá de determinarse si el límite máximo de cumplimiento, fijado conforme al artículo 76 CP, es superior o inferior a la suma aritmética de todas las condenas impuestas, pues solo en este último caso, cuando fuera inferior, procedería la acumulación (SSTS 854/2006, de 12 de Septiembre, Rec. 1292/2005; 954/2006, de 10 de Octubre, Rec. 10022/2006; 1293/2011, de 27 de noviembre, Rec. 10658/2011; y 13/2012, de 19 de Enero, Rec. 11418/2011, entre otras). (1)

La nueva refundición que se opere solo será procedente cuando, en su conjunto, ésta resulte favorable al reo, dado que la condena posterior no puede perjudicar retroactivamente la acumulación ya realizada (STS 707/2013, de 30 de septiembre, Rec. 10128/2013), una vez que se entra a revisar una acumulación anterior, la revisión no se limita a las penas efectivamente acumuladas, sino a todas las que fueron objeto de examen en el Auto, sin perjuicio de que entonces su acumulación se considerara improcedente ya que sí podrían ser acumulables con la nueva Sentencia.

TERCERA.- Esta Sala Casacional ha tomado el siguiente Acuerdo de Pleno para la Unificación de Criterios de 3 de febrero de 2016:

"La acumulación de penas deberá realizarse partiendo de la sentencia más antigua, pues al contenerse en ella los hechos enjuiciados en primer lugar, servirá de referencia respecto de los demás hechos enjuiciados en las otras sentencias. A esa condena se acumularán todas las posteriores relativas a hechos cometidos antes de esa primera sentencia.

Las condenas cuya acumulación proceda respecto de esta sentencia más antigua, ya no podrán ser objeto de posteriores operaciones de acumulación en relación con las demás sentencias restantes. Sin embargo, si la acumulación no es viable, nada impediría su reconsideración respecto de cualquiera de las sentencias posteriores, acordando su acumulación si entre sí son susceptibles de ello.

A los efectos del artículo 76.2 CP hay que estar a la fecha de la sentencia dictada en la instancia y no la del juicio."

En su virtud,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, en tiempo y forma oportunos, se digne admitirlo y tenga por preparado RECURSO DE CASACIÓN contra el auto de fecha [FECHA DEL AUTO], dando a los autos el curso legal correspondiente.

PRIMER OTROSÍ DIGO: Que se ha realizado el correspondiente y necesario depósito en la cuenta designada por la Secretaría de este Tribunal, para poder interponer el presente escrito de preparación de Recurso al no gozar esta parte del beneficio de la justicia gratuita, adjuntando el resguardo del ingreso del referido importe.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR]

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) El Tribunal Supremo dictó STS 367/2015, 11 de junio, Rec. 10043/2015, en la que se recogen los requisitos exigidos para la refundición de condenas tras la entrada en vigor de la reforma del Código Penal por LO 1/2015.

Como primer principio se abandona la exigencia de conexión entre los hechos delictivos para la aplicación de los límites previstos en el anterior art 76.2 CP.

Como segundo, señalar que los Autos de Refundición de Condenas tendrán que incluir las fechas de enjuiciamiento de los hechos, además de las fechas de comisión y las fechas de las sentencias porque inciden directamente en la determinación de las sentencias a acumular.

================================================================================
