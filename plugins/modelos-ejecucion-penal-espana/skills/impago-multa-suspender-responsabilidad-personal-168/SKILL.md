---
name: impago-multa-suspender-responsabilidad-personal-168
description: "Redacta el escrito «Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025)» (formulario 168 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025)

> Formulario 0168 del plugin **Ejecución penal** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- este juzgado / esta sección penal de Audiencia
- el Tribunal / la Sala

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 53 CP
- artículo 53 del Código Penal
- artículo 35 del Código Penal
- artículo 84 del Código Penal

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

### Formulario 0168 · Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025)

- Año del modelo: 2022
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de ejercitando la defensa en nombre y representación del condenado D./Dña. [NOMBRE Y APELLIDOS] en ejecutoria penal nº [NÚMERO] que se sigue en [ELEGIR: este juzgado / esta sección penal de Audiencia] por delito de del CP, ante [ELEGIR: el Tribunal / la Sala] comparezco y, como más procedente sea en derecho, DIGO:

Con fecha se dictó sentencia en el Procedimiento abreviado nº juicio oral por la que se condenaba a D./Dña. [NOMBRE Y APELLIDOS] a la pena de con responsabilidad personal subsidiaria de días, en caso de impago.

Requerido para el pago de la multa y ante el incumplimiento de la misma, se dictó resolución con fecha [FECHA] por la que se acuerda su ingreso en prisión por... días, conforme al art. 53 CP.

El art. 53 CP establece la preceptividad de que, ante el impago de la multa "quedará sujeto" a la responsabilidad personal subsidiaria de un día de privación de libertad por cada dos cuotas no satisfechas.

Ahora bien, la medida de suspensión de ejecución de la responsabilidad personal subsidiaria es viable, y puede acordarse, en base al Acuerdo del Pleno de la Sala Segunda del Tribunal Supremo, en la STS 603/2018, de 28-11, Rec. 828/2018, que señala que:

"...Pese a la equivocidad de los términos...del párrafo segundo del apartado 1 del artículo 53 del Código Penal ..., debemos considerar que nos encontramos ante la imposición de una pena privativa de libertad, ya que así califica el artículo 35 del Código Penal a la denominada responsabilidad personal subsidiaria por impago de multa. Y cuando se habla de que esa pena se pueda "cumplir" mediante los trabajos en beneficio de la comunidad, lo hace como acuerdo del juez o tribunal "previa conformidad del penado". Es decir, se trata de un supuesto de suspensión de la pena privativa sometida a esa condición aceptada por el penado.

Pues bien, cuando de incumplimiento de condiciones de suspensión de la pena se trata, el ordenamiento jurídico establece la consecuencia que corresponde imponer. Así el artículo 84 del Código Penal prevé la posibilidad de tal suspensión de la ejecución de la pena a, entre otras, la condición de realizar trabajos en beneficio de la comunidad. Y, a su vez, el artículo 86 prevé las posibles consecuencias anudadas por el legislador a las diversas hipótesis descritas en sus apartados 1 y 2..."

Por ello, se interesa se acuerde la suspensión de la responsabilidad personal subsidiaria del art. 53 CP por impago de multa, con sometimiento a la condición de [Nº] días de trabajos en beneficio de la comunidad en los términos indicados.

En su virtud,

SUPLICO AL TRIBUNAL
A LA SALA
 :

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
