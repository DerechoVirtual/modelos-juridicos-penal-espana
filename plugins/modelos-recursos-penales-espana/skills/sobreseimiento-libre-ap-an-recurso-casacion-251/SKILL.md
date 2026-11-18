---
name: sobreseimiento-libre-ap-an-recurso-casacion-251
description: "Redacta el escrito «Sobreseimiento libre de la AP o la AN: recurso de casación» (formulario 251 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sobreseimiento libre de la AP o la AN: recurso de casación

> Formulario 0251 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] Nº
- [ ] LOCALIDAD (4 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NÚMERO (7 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO (2 veces)
- [ ] FECHA (3 veces)
- [ ] SEDE (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…interpuesto por la defensa de la víctima»; «…, de»; «…ación fundada contra el/la investigado/a»; «… la evidencia de que el/la investigado/a»; «…amente el sobreseimiento libre basado en»

## Elecciones que hay que hacer

- de Instrucción del Tribunal de Instancia / Central de Instancia
- el juez instructor / la Audiencia Provincial / la Sala de lo Penal de la Audiencia Nacional

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 848 LECRIM
- artículo 637 LECRIM
- art. 848 LECRIM
- art. 637 LECRIM

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

### Formulario 0251 · Sobreseimiento libre de la AP o la AN: recurso de casación

- Año del modelo: 2022
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 2 bloques de alternativas señalados; 29 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la sección nº [Nº] de la Audiencia Provincial de [LOCALIDAD]

A la Sala de lo Penal de la Audiencia Nacional

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] en DP nº [NÚMERO] contra D./Dña. [NOMBRE Y APELLIDOS] que ejerce la acusación particular en el procedimiento nº [Nº DE PROCEDIMIENTO] por delito de [DELITO], ante el órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Mediante el presente escrito, y a tenor de lo dispuesto en el artículo 848 LECRIM, se interpone RECURSO DE CASACIÓN contra el auto de sobreseimiento libre de fecha [FECHA], en base a los siguientes

FUNDAMENTOS

PRIMERO.- Con fecha [FECHA] se ha dictado por la

Sección nº [NÚMERO] de la Audiencia Provincial de [LOCALIDAD]

Sala de lo Penal de la Audiencia Nacional auto de sobreseimiento libre de las presentes diligencias.

SEGUNDO.- Preceptúa el artículo 637 LECRIM que procederá el sobreseimiento libre:

"1.º Cuando no existan indicios racionales de haberse perpetrado el hecho que hubiere dado motivo a la formación de la causa.

2.º Cuando el hecho no sea constitutivo de delito.

3.º Cuando aparezcan exentos de responsabilidad criminal los procesados como autores, cómplices o encubridores."

TERCERO.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

El auto de sobreseimiento libre que ahora se recurre viene dictado por esta Sala dimanante del recurso apelación interpuesto por la defensa de la víctima [COMPLETAR] contra el auto de la sección [ELEGIR: de Instrucción del Tribunal de Instancia / Central de Instancia], de [COMPLETAR], plaza nº [NÚMERO] por el que se desestimaba la petición de archivo reclamada por la defensa. Y es en virtud del recurso de apelación interpuesto por la defensa por el que se procede a dictar por la

Sección nº [NÚMERO] de la Audiencia Provincial de [LOCALIDAD]

Sala de lo penal de la Audiencia Nacional el auto de sobreseimiento libre.

El auto que ahora se desea recurrir viene dictado por confirmación por la

Sección nº [NÚMERO] de la Audiencia Provincial de [LOCALIDAD]

Sala de lo penal de la Audiencia Nacional del auto de sobreseimiento libre de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO].

CUARTO.- En las presentes actuaciones ha habido una imputación fundada contra el/la investigado/a [COMPLETAR], en base a las diligencias de investigación que se practicaron y que dieron lugar a la evidencia de que el/la investigado/a [COMPLETAR] ha realizado los siguientes hechos que se le imputan en la querella.

Se cumple, con ello, el presupuesto exigido en el art. 848 LECRIM de que exista una imputación fundada contra una persona frente a la que se dicta auto de sobreseimiento libre, que es lo que da viabilidad al recurso de casación presente.

Pero en este caso se ha tomado, dicho en términos estrictos de defensa, una decisión precipitada al adoptar directamente el sobreseimiento libre basado en [COMPLETAR], habiéndose practicado las siguientes diligencias de investigación que evidencian los indicios de la comisión del delito de [DELITO]. Pese a ello, sin embargo, todavía quedaban por practicar las siguientes diligencias interesadas por esta representación en el escrito de querella que no se han practicado y nos encontramos con un infundado auto de archivo definitivo.

Las diligencias pendientes de practicar eran las siguientes:

Por ello, se articula el presente recurso de casación basado en infracción de ley ex art. 848 LECRIM, en relación con el art. 637 LECRIM, por no existir razones que amparen el dictado del auto de archivo ante la existencia de un delito del art. del CP.

Existen indicios bastantes para el dictado del auto transformando las diligencias previas en procedimiento abreviado, no pudiendo [ELEGIR: el juez instructor / la Audiencia Provincial / la Sala de lo Penal de la Audiencia Nacional] anticipar una valoración de la prueba, entendiendo que no hay delito, que solo corresponde al órgano de enjuiciamiento al que se hurta de su función de conocer las pruebas que estamos aportando al presente procedimiento para demostrar la autoría de los hechos que imputamos al/a la investigado/a.

Por todo ello,

SUPLICO A LA SECCIÓN

La reapertura de las diligencias archivadas para la práctica de las diligencias interesadas y que en su momento se dicte auto de transformación de las DP en Procedimiento Abreviado, estimándose el recurso de casación y se remitan las diligencias para su continuación por la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] para la continuación de las que en su día se interesaron y que se han citado en el cuerpo de este escrito como las pendientes de práctica.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
