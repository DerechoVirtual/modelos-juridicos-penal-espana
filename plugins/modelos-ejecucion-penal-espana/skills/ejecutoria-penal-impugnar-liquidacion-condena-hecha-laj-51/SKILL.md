---
name: ejecutoria-penal-impugnar-liquidacion-condena-hecha-laj-51
description: "Redacta el escrito «Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ» (formulario 51 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ

> Formulario 0051 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (6 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… que los días que restan por cumplir son»; «… que los días que quedan por cumplir son»

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 988 bis.4 LECRIM
- art. 59 del Código Penal
- artículos 292 a 297 de la LOPJ

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

### Formulario 0051 · Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ

- Año del modelo: 2025
- Revisión 17-11-2026: 1 rangos de artículos despegados («25 a31» → «25 a 31»); 1 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 36) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el condenado impugna la liquidación de condena efectuada por el LAJ ante el órgano judicial que dictó la sentencia condenatoria, en base al art. 988 bis.4 LECRIM, introducida por LO 1/2025, vigente desde el 3 de abril de 2025.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala de lo Penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según tengo debidamente acreditado en la Ejecutoria nº [Nº DE PROCEDIMIENTO], ante este órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

Que, mediante el presente escrito, impugno en plazo la liquidación de condena de fecha efectuada por el letrado de la Administración de Justicia, en virtud del art. 988 bis.4 LECRIM, con base en las siguientes

ALEGACIONES

PRIMERA.- En la liquidación practicada no se ha procedido al abono de los días pasados por mi representado/a en prisión provisional, a raíz del auto de fecha [FECHA] hasta el auto de libertad provisional del día [FECHA] en que quedó la libertad.

SEGUNDA.- Igualmente, no se han tenido en cuenta las comparecencias apud acta realizadas desde el día [FECHA] hasta el día [FECHA] para aplicarlo al cumplimiento de la pena de prisión.

Hay que tener en cuenta que por cada 10 comparecencias apud acta hay que abonar un día de prisión, y no se ha realizado ese abono en la liquidación practicada. Se realizaron... comparecencias estando en libertad provisional, por lo que habría que abonar en el descuento de la pena... días de prisión para restarlos.

Señala el Tribunal Supremo, en STS 1045/2013 de 7 de enero 2014, Rec. 10184/2013 que:

"Las comparecencias quincenales efectuadas durante 18 meses por el acusado han sido compensadas a razón de 1 día de prisión por cada 10 comparecencias, lo que totalizan 4 días a restar de los 3 años de condena que le fueron impuestos a aquél y que ahora han de ser abonados en la liquidación definitiva. Se trata de un cómputo equilibrado, razonable y, por tanto, susceptible de aplicación en supuestos de igual o similar naturaleza.

4.- La decisión que ahora se acuerda es conforme al criterio expresado en el Pleno no jurisdiccional de esta Sala, celebrado el día 19 de diciembre de 2013, en el que se proclamó que "la obligación de comparecencia periódica ante el órgano judicial es la consecuencia de una medida cautelar de libertad provisional. Como tal medida cautelar puede ser compensada conforme al art. 59 del Código Penal, atendiendo al grado de aflictividad que su efectivo y acreditado cumplimiento haya comportado ".

La Sala estima que el criterio de la compensación, además de su indudable apoyo en el significado constitucional de la libertad como valor superior del ordenamiento jurídico (Art. 1 CE), tendrá consecuencias benéficas para el sistema de cumplimiento de las penas y para la propia efectividad de las medidas cautelares. De una parte, por cuanto que contribuirá a eliminar la rutinaria aplicación de una medida restrictiva de la libertad cuya ejecución, vigilancia y seguimiento jurisdiccional no siempre están siendo ejemplares. De otra parte, porque facilitará el efecto pedagógico asociado a la idea de que el cumplimiento por el imputado de esas comparecencias siempre conllevará la expectativa favorable de su futura compensación."

TERCERA.- Se solicita también el abono del tiempo de prisión preventiva pasado en el procedimiento abreviado nº dado que mi representante fue absuelto.

Conforme señala la STS 547/2019 de 12 Nov. 2019, Rec. 10403/2019:

"La STS 70/2007 (ROJ:STS 485/2007), de modo tajante indica:

En todo caso, el abono de la prisión preventiva en causa distinta de aquella en la que se decretó es procedente, bien en el caso de que en ésta fuese absuelto el acusado, o bien de que la pena privativa de libertad impuesta en la misma fuese de menor duración que la prisión preventiva sufrida: pues, de no hacerse así, se habría causado un indudable perjuicio al penado, que, de no tener otra u otras ejecutorias pendientes, podría demandar, en su caso, la correspondiente compensación por la vía de los artículos 292 a 297 de la LOPJ."

Por todo ello se entiende que los días que restan por cumplir son [COMPLETAR] una vez actualizado el abono de [Nº] días.

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que tenga por presentado este escrito y documentos que se acompañan, lo admita, tenga por impugnada la liquidación de condena de fecha [FECHA] y acuerde modificarlo y conceder a mi representado/a que los días que quedan por cumplir son [COMPLETAR], en lugar de los que figuran en la liquidación de condena.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Plazo para la impugnación: las partes tienen 2 días desde que se les da traslado de la liquidación de condena hecha por el LAJ
