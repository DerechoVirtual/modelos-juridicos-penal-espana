---
name: hurto-movil-apelacion-condenado-contra-sentencia-19
description: "Redacta el escrito «Hurto de móvil: apelación del condenado contra la sentencia» (formulario 19 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto de móvil: apelación del condenado contra la sentencia

> Formulario 0019 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO (2 veces)
- [ ] FECHA (2 veces)
- [ ] LOCALIDAD
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e los Tribunales y del/de la condenado/a»; «…s de la sentencia se dice literalmente "»; «…icilio para notificaciones el situado en»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 235.1.10 CP
- art. 803.1 LECrim
- art. 790 LECrim
- artículo 790.2 LECrim
- art. 235 CP
- art. 234.2 CP
- art. 790.3 LECrim
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

### Formulario 0019 · Hurto de móvil: apelación del condenado contra la sentencia

- Año del modelo: 2026
- Revisión 17-11-2026: 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del/de la condenado/a [COMPLETAR], según tengo ya acreditado en el Procedimiento para el enjuiciamiento rápido número [NÚMERO], seguido en la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], por el presunto delito del art. 235.1.10 CP, ante este órgano judicial, como mejor proceda en derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte la sentencia dictada el día [FECHA] y estimándola perjudicial y gravosa para mi representado, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado interpongo en tiempo y forma recurso de apelación para ante la Audiencia Provincial de [LOCALIDAD], al amparo de lo establecido en el art. 803.1 LECrim., en relación con el art. 790 LECrim., con base en las siguientes:

ALEGACIONES

PRIMERA.- Sobre quebrantamiento de normas y garantías procesales

En el acta de juicio oral consta la petición de subsanación de la falta, presentada por esta parte a efectos de cumplimiento del artículo 790.2 LECrim., pfo. 2º.

SEGUNDA.- Sobre error en la apreciación de las pruebas

En el apartado de hechos probados de la sentencia se dice literalmente " [COMPLETAR] ". Y ello está en contradicción con las siguientes pruebas:

TERCERA.- Sobre infracción de normas del ordenamiento jurídico.

El art. 235.1.10 CP solo sanciona como delito de hurto ex art. 235 CP como delito menos grave la sustracción en vía pública o lugar privado, pero de aparatos que contengan datos, excluyendo de la tipicidad del art. 235 CP que "A los efectos de este numeral, no se considerarán incluidos los que se encuentren a la venta, almacén o exposición en establecimientos comerciales". Por ello, habiéndose sustraído en un establecimiento comercial se solicita se absuelva de esta condena ex art. 235 CP y, en su caso, se imponga la condena por delito de hurto del art. 234.2 CP a pena de un mes de multa a razón de 2 euros/día, porque el valor estaba por debajo de 400 euros y no haber sido ejecutoriamente condenado tres veces ex art. 234.2 CP.

PRUEBAS

En aplicación del art. 790.3 LECrim., por no haberse podido practicar en la primera instancia por causa no imputable al recurrente, que insistió en su necesidad en el acto del juicio, se solicitan las siguientes:

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, y tenga por interpuesto recurso de apelación contra la sentencia recaída en estos autos, se admita en ambos efectos dando traslado del mismo a las demás partes para que presenten sus escritos de alegaciones, y remita las actuaciones a la Audiencia Provincial para que admita las pruebas propuestas y dicte sentencia en la que, estimando el recurso, revoque la apelada, dictando otra por la que se absuelva a mi representado del delito de [DELITO] o, en su caso, se imponga la condena por delito de hurto del art. 234.2 CP a pena de un mes de multa a razón de 2 euros/día, porque el valor estaba por debajo de 400 euros y no haber sido ejecutoriamente condenado tres veces ex art. 234.2 CP.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, cumpliendo el art. 790.2 LECrim., designo como domicilio para notificaciones el situado en [COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN: que tenga por realizada la anterior manifestación.

Es Justicia que reitero en el Lugar y fecha ut supra indicados.

Firma Abogado/a	Firma Procurador/a

================================================================================
