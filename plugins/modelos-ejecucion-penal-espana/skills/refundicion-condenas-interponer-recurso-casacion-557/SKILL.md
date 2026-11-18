---
name: refundicion-condenas-interponer-recurso-casacion-557
description: "Redacta el escrito «Refundición de condenas: interponer recurso de casación» (formulario 557 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Refundición de condenas: interponer recurso de casación

> Formulario 0557 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] SEDE
- [ ] NÚMERO
- [ ] LUGAR (2 veces)
- [ ] ...

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se ha fijado el máximo de cumplimiento / Si no se ha considerado el "mejor bloque" que determina una pena inferior en la acumulación — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 849 LECRIM
- art. 76 CP
- art. 988 LECRIM
- artículo 849 de la LECrim
- art. 874 LECrim
- art. 849.1 LECrim
- art. 874.2 LECrim
- art. 859 LECrim
- art. 988 de la Ley de Enjuiciamiento Criminal
- art. 76.2 CP

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

### Formulario 0557 · Refundición de condenas: interponer recurso de casación

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 10 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se interpone recurso de casación ante el TS por infracción de ley del art. 849 LECRIM, contra auto de refundición de condenas penales, con arreglo al art. 76 CP, conforme a lo previsto en el art. 988 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sala Segunda del Tribunal Supremo

D/Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del condenado D/Dña. [NOMBRE Y APELLIDOS] en ejecutoria número [Nº DE PROCEDIMIENTO] sobre delito de [DELITO], ante La Sala Segunda del Tribunal Supremo comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se me ha notificado el auto de refundición de condena practicado con arreglo al art. 76 CP y, por no considerarlo ajustado a derecho, dicho con todo respeto y en términos de estricta defensa, se preparó recurso de casación ante la Sección de lo Penal del Tribunal de Instancia, por lo que dentro del término legal presento escrito de interposición del recurso de casación, conforme a lo prevenido en los arts. 873 y ss LECrim.

Se interpone el presente recurso por permitirlo el art. 988 LECrim.

MOTIVOS DEL RECURSO

ÚNICO.-

Se interpone recurso de casación por infracción de Ley del artículo 849 de la LECrim., por indebida aplicación del art 76 del C. penal.

Con fecha se dictó auto por la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] por el que se procedió a la acumulación de condenas de...

Conforme a lo dispuesto en el art. 874 LECrim., se procede a la cita del precepto infringido por la vía del art. 849.1 LECrim., en relación al art. 76 CP, a cuyo tenor: "el máximo de cumplimiento efectivo de la condena del culpable no podrá exceder del triple del tiempo por el que se le imponga la más grave de las penas en que haya incurrido, declarando extinguidas las que procedan desde que las ya impuestas cubran dicho máximo, que no podrá exceder de 20 años"

No obstante, el apartado 2º fija la clave de limitación al señalar que: "La limitación se aplicará aunque las penas se hayan impuesto en distintos procesos cuando lo hayan sido por hechos cometidos antes de la fecha en que fueron enjuiciados los que, siendo objeto de acumulación, lo hubieran sido en primer lugar."

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se ha fijado el máximo de cumplimiento / Si no se ha considerado el "mejor bloque" que determina una pena inferior en la acumulación — el texto de cada opción no venía en el formulario original]

En su virtud,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, en tiempo y forma oportunos, se digne admitirlo y tenga por interpuesto RECURSO DE CASACIÓN contra el auto de fecha [FECHA], dando a los autos el curso legal correspondiente y, estimando el recurso, se proceda a admitir la fórmula del bloque de acumulación que se propone.

Es justicia que pido en [LUGAR]

OTROSÍ DIGO: A tenor del art. 874.2 LECrim. se presenta el testimonio entregado del art. 859 LECrim.

SUPLICO A LA SALA: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR]

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) El Acuerdo del Pleno del TS de 3 de febrero de 2016 hace referencia a la fijación del criterio del cómputo del máximo de cumplimiento en los supuestos de acumulación de condenas (art. 76 CP y art. 988 de la Ley de Enjuiciamiento Criminal, LECrim).

El contenido del Acuerdo gira en torno a tres pilares fundamentales:

A. «La acumulación de penas deberá realizarse partiendo de la sentencia más antigua, pues al contenerse en ella los hechos enjuiciados en primer lugar, servirá de referencia respecto de los demás hechos enjuiciados en otras sentencias. A esa condena se acumularán todas las posteriores relativas a hechos cometidos antes de esa primera sentencia».
B. «Las condenas cuya acumulación proceda respecto de esta sentencia más antigua, ya no podrán ser objeto de posteriores operaciones de acumulación en relación con las demás sentencias restantes. Sin embargo, si la acumulación no es viable, nada impediría su reconsideración respecto de cualquiera de las sentencias posteriores, acordando su acumulación si entre si son susceptibles de ello».
C. «A efectos del art. 76.2 CP hay que estar a la fecha de la sentencia en la instancia y no la de juicio».

Se explica en la STS 142/2016, de 25 de febrero, Rec. 10155/2015 que esa interpretación literal, por plantear varios problemas, llevó a la Sala a la adopción del acuerdo reseñado de estar a la fecha de la sentencia dictada en la instancia y no a la del juicio. Las razones de ese acuerdo, basadas todas en la complejidad que añadiría al proceso de acumulación una interpretación literal, son las siguientes:

1.ª) Seguridad jurídica. Dice la Sala que la fecha de la sentencia consta con certeza en la certificación de antecedentes penales, siendo fija, mientras que la de enjuiciamiento es en ocasiones más difícil de localizar, pudiendo, por otra parte, ser variable. De esta forma, en los casos en que el juicio da comienzo en una determinada fecha y concluye días después «pueden plantearse problemas interpretativos entre utilizar una u otra fecha, que generarían una nueva perturbación en una materia ya bastante compleja».

2.ª) Coherencia jurisprudencial. No aprecia el TS motivos de fondo para que el Legislador procediese a modificar, sin argumentar nada en la exposición de motivos, un criterio jurisprudencial consolidado en la materia que, tras diferentes controversias (fecha se la sentencia/fecha de su firmeza), se reafirmó mediante el APTS de 29 de noviembre de 2005: «no es necesaria la firmeza de la sentencia para el límite de la acumulación [...]». A juicio de la Sala, no parece justificado desvirtuar ese criterio unificado con una modificación que sólo añade, otra vez, una mayor complejidad al proceso de refundición.

3.ª) Favorabilidad para el reo. En efecto, en el supuesto de un hecho cometido después del juicio pero antes de recaída sentencia, la interpretación tradicional seguida por la Sala (fecha de la sentencia) permitiría la acumulación (los nuevos hechos serían anteriores a la misma), pero la interpretación literal de la reforma no pues los nuevos hechos serían posteriores al enjuiciamiento. Considera el TS que esta condición de norma posterior más desfavorable plantearía serios problemas de retroactividad, lo que, al fin y a la postre, daría lugar, nuevamente, a una innecesaria complejidad.

En definitiva, para la STS 142/2016, de 25 de febrero, Rec. 10155/2015, en motivación del APTS de 3 de febrero de 2016, la adopción de una interpretación literal de «fecha de enjuiciamiento» como «fecha del juicio», conduciría a una situación manifiestamente disfuncional, que debe ser evitada en una materia tan delicada en la que está en juego el tiempo de privación de libertad de los penados, «por lo que debe adoptarse la interpretación de "fecha en la que los hechos fueron sentenciados"».

================================================================================
