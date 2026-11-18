---
name: acuerdo-reparacion-investigado-pide-archivo-causa-penal-46
description: "Redacta el escrito «Acuerdo de reparación: el investigado pide el archivo de la causa penal» (formulario 46 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acuerdo de reparación: el investigado pide el archivo de la causa penal

> Formulario 0046 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA (3 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…os servicios de justicia restaurativa de»; «…sta el acuerdo alcanzado consistente en:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Seleccionar si se trata de delito privado o en el que el perdón extingue la responsabilidad criminal…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 963 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0046 · Acuerdo de reparación: el investigado pide el archivo de la causa penal

- Año del modelo: 2025
- Revisión 17-11-2026: 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 31) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa del investigado en un procedimiento penal seguido por un delito leve o privado o que permite el perdón del ofendido, solicita al juez de instrucción el sobreseimiento y archivo de la causa al haberse alcanzado un acuerdo con el denunciante tras haber acudido a la mediación penal o proceso de justicia restaurativa, conforme a la DA 9ª LECRIM, según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales, en representación de D./Dña [NOMBRE Y APELLIDOS], en calidad de denunciado/a en procedimiento nº [Nº], comparezco ante este órgano judicial y, como mejor proceda en Derecho, DIGO:

Con fecha [FECHA] se acordó derivar la presente causa a los servicios de justicia restaurativa de [COMPLETAR] a los efectos de poder alcanzarse un acuerdo entre denunciante y denunciado.

Con fecha [FECHA] el servicio de justicia restaurativa de ha presentado un informe donde consta el acuerdo alcanzado consistente en: [COMPLETAR].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Las presentes diligencias se siguen por el delito leve de. En consecuencia, procede aplicar la DA 9ª.9 a) LECRIM que señala que:

"En caso de existir acuerdo, el órgano judicial, previa audiencia del Ministerio Fiscal, de las partes personadas y de la víctima del delito, por término de tres días, valorando los acuerdos a los que las partes hayan llegado, las circunstancias concurrentes y el estado del procedimiento, podrá:

a) Si se tratase de un delito leve,decretar el archivo, a la vista del cumplimiento de los acuerdos alcanzados, de conformidad con lo establecido en el artículo 963 de la Ley de Enjuiciamiento Criminal."

Las presentes diligencias se siguen por el delito de [DELITO] que es privado (o que permite el perdón del ofendido). En consecuencia, procede aplicar la DA 9ª.9 b) LECRIM que señala que:

" b) Si la causa se siguiera por un delito privado o un delito en el que el perdón extingue la responsabilidad criminal, acordarel sobreseimiento del procedimiento y su archivo, dejando sin efecto las medidas cautelares que se hubieren acordado en su caso."

Por ello,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y acuerde el archivo de las presentes diligencias.

[OPCIONAL — incluir si procede]

Seleccionar si se trata de delito privado o en el que el perdón extingue la responsabilidad criminal

OTROSÍ DIGO: Se interesa, al mismo tiempo, que se dejen sin efecto las medidas cautelares que fueron acordadas por auto de fecha consistentes en.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
