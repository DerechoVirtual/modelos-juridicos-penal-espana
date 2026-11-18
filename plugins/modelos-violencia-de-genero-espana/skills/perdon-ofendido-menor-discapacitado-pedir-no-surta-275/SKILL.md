---
name: perdon-ofendido-menor-discapacitado-pedir-no-surta-275
description: "Redacta el escrito «Perdón del ofendido menor o discapacitado: pedir que no surta efecto (hasta el 2 de abril de 2025)» (formulario 275 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Perdón del ofendido menor o discapacitado: pedir que no surta efecto (hasta el 2 de abril de 2025)

> Formulario 0275 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ún consta acreditado en el Procedimiento»; «…to por la defensa del/de la denunciado/a»

## Elecciones que hay que hacer

- menor de edad / discapacitado/a

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 201 CP

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

### Formulario 0275 · Perdón del ofendido menor o discapacitado: pedir que no surta efecto (hasta el 2 de abril de 2025)

- Año del modelo: 2022
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 3 desplegables y casillas convertidos en elección en blanco; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D/Dña [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento [COMPLETAR] seguido ante ese Tribunal, comparezco y como proceda en Derecho DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese juzgado por los padres del/de la [ELEGIR: menor de edad / discapacitado/a] que ejercen la acusación particular por la comisión de un delito de tipificado en el artículoCP, habiéndonos personado en las actuaciones por escrito de fecha

Que con fecha [FECHA] se ha presentado escrito por la defensa del/de la denunciado/a [COMPLETAR], interesando que se declare extinguida la responsabilidad penal habida cuenta que el/la [ELEGIR: menor de edad / discapacitado/a], en su declaración judicial asistido/a por expertos, ha declarado el perdón expreso al/a la denunciado/a por los hechos ocurridos.

Que el CP recoge en el art. 130.1.5º CP, conforme a la redacción dada por LO 8/2021, de 4 de junio, que:

"La responsabilidad criminal se extingue: [NOTA DE REVISIÓN: Texto literal del art. 130.1 CP («responsabilidad criminal»); el ordinal 5.º conserva la redacción de la LO 8/2021. Fuente: Código Penal, BOE-A-1995-25444, art. 130.1.5.º.]... 5.º Por el perdón de la persona ofendida, cuando se trate de delitos leves perseguibles a instancias de la persona agraviada o la ley así lo prevea. El perdón habrá de ser otorgado de forma expresa antes de que se haya dictado sentencia, a cuyo efecto la autoridad judicial sentenciadora deberá oír a la persona ofendida por el delito antes de dictarla.

En los delitos cometidos contra personas menores de edad o personas con discapacidad necesitadas de especial protección que afecten a bienes jurídicos eminentemente personales, el perdón de la persona ofendida no extingue la responsabilidad criminal."

Además, el artículo 201 CP señala, tras la LO 8/2021, de 4 de junio que:

«1. Para proceder por los delitos previstos en este Capítulo será necesaria denuncia de la persona agraviada o de su representante legal.
2. No será precisa la denuncia exigida en el apartado anterior para proceder por los hechos descritos en el artículo 198 de este Código, ni cuando la comisión del delito afecte a los intereses generales, a una pluralidad de personas o si la víctima es una persona menor de edad o una persona con discapacidad necesitada de especial protección.
3. El perdón del ofendido o de su representante legal, en su caso, extingue la acción penal sin perjuicio de lo dispuesto en el artículo 130.1.5.º, párrafo segundo.»

Es por ello por lo que, al ser el ofendido [ELEGIR: menor de edad / discapacitado/a], no es posible, en modo alguno, que opere el perdón del ofendido ante sus características personales que impiden que pueda surtir efectos el perdón recogido en su declaración, dado que no se han negado los hechos, sino que se han "perdonado", pero este perdón no tiene virtualidad a los efectos penales.

Por lo expuesto.

SUPLICO AL TRIBUNAL:

Que tenga por presentado este escrito, lo admita y tenga por realizada la alegación de esta parte como acusación particular de la no extinción de la responsabilidad penal con motivo de lo dispuesto en el art. 130.1.5º CP y, por ello, la continuación de la causa.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
