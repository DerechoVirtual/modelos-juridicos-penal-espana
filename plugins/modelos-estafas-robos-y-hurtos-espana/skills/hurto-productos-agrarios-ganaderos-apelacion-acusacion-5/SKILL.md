---
name: hurto-productos-agrarios-ganaderos-apelacion-acusacion-5
description: "Redacta el escrito «Hurto de productos agrarios o ganaderos: apelación de la acusación contra la sentencia» (formulario 5 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto de productos agrarios o ganaderos: apelación de la acusación contra la sentencia

> Formulario 0005 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o en tiempo y forma recurso de apelación»; «…icilio para notificaciones el situado en»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 803.1 LECrim
- art. 790 LECrim
- art. 792.2 LECrim
- art. 790.2 LECrim

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

### Formulario 0005 · Hurto de productos agrarios o ganaderos: apelación de la acusación contra la sentencia

- Año del modelo: 2026
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del acusador particular D./Dña. [NOMBRE Y APELLIDOS], según tengo ya acreditado en el Procedimiento para el enjuiciamiento rápido número [NÚMERO], dirigido contra [ACTO O RESOLUCIÓN] por el presunto delito del art. 235.1.4º CP, ante este órgano judicial, como mejor proceda en derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte la sentencia dictada el día [FECHA] y estimándola perjudicial y gravosa para mi representado/a, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado, interpongo en tiempo y forma recurso de apelación [COMPLETAR], al amparo de lo establecido en el art. 803.1 LECrim., en relación con el art. 790 LECrim., con base en las siguientes:

ALEGACIONES

ÚNICA.-

Infracción de normas del ordenamiento jurídico.

En el presente caso se ha dictado sentencia absolutoria por no haber acreditado el grave perjuicio causado a la finca donde se produjo el hurto, elemento objetivo del tipo que no consta ya en la redacción del art. 235.1.4º CP, suprimido por la LO 1/2026, y solo exige que lo sustraído exceda de 400 euros, como consta en la tasación aportada como documental, por lo que se ha exigido un elemento del tipo que está derogado, por lo que se solicita la nulidad de la sentencia y que se vuelva a celebrar nuevo juicio con juez distinto.

Hay que recordar que, conforme a la redacción del art. 792.2 LECrim.:

«2. La sentencia de apelación no podrá condenar al encausado que resultó absuelto en primera instancia ni agravar la sentencia condenatoria que le hubiera sido impuesta por error en la apreciación de las pruebas en los términos previstos en el tercer párrafo del artículo 790.2.

No obstante, la sentencia, absolutoria o condenatoria, podrá ser anulada y, en tal caso, se devolverán las actuaciones al órgano que dictó la resolución recurrida. La sentencia de apelación concretará si la nulidad ha de extenderse al juicio oral y si el principio de imparcialidad exige una nueva composición del órgano de primera instancia en orden al nuevo enjuiciamiento de la causa.».

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por interpuesto recurso de apelación contra la sentencia recaída en estos autos, se admita en ambos efectos, dando traslado del mismo a las demás partes para que presenten sus escritos de alegaciones, y remita las actuaciones a la Audiencia Provincial para que se declare la nulidad de la sentencia recurrida y se ordene la repetición del juicio con juez distinto, mandando se dicte otra ajustada a Derecho.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, cumpliendo el art. 790.2 LECrim., designo como domicilio para notificaciones el situado en [COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN: que tenga por realizada la anterior manifestación.

Es Justicia que reitero en el Lugar y fecha ut supra indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
