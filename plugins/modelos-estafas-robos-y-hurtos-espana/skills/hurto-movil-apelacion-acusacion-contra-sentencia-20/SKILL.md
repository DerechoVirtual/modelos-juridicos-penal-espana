---
name: hurto-movil-apelacion-acusacion-contra-sentencia-20
description: "Redacta el escrito «Hurto de móvil: apelación de la acusación contra la sentencia» (formulario 20 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto de móvil: apelación de la acusación contra la sentencia

> Formulario 0020 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] FECHA (3 veces)
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…era infringido el derecho constitucional»; «…del art. de la CE puesto que»; «…nerado efectiva indefensión debido a que»; «…e prueba, que era pertinente y necesaria»; «…anto esta se basó en la siguiente prueba»; «… de la prueba en los siguientes términos»; «…s de la sentencia se dice literalmente «»; «…icilio para notificaciones el situado en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se pide nulidad por quebrantamiento de forma / Si se pide nulidad por otros motivos — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sent…
- SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión, por indebida denegación de prueba…
- TERCERA.- Error en la apreciación de las pruebas…
- CUARTA.- Infracción de normas del ordenamiento jurídico.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 235.1.10 CP
- art. 803.1 LECrim
- art. 790 LECrim
- artículos 24.1 y 120.3 de la Constitución
- artículo 790.2 LECrim
- artículo 24.2 de la Constitución
- art. 24.2 CE
- art. 790.2.3 LECrim
- art. 235.1 CP
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

### Formulario 0020 · Hurto de móvil: apelación de la acusación contra la sentencia

- Año del modelo: 2026
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del acusador particular D./Dña. [NOMBRE Y APELLIDOS], según tengo ya acreditado en el Procedimiento para el enjuiciamiento rápido número [NÚMERO], dirigido contra [ACTO O RESOLUCIÓN] por el presunto delito del art. 235.1.10 CP, ante este órgano judicial, como mejor proceda en derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte la sentencia dictada el día [FECHA] y estimándola perjudicial y gravosa para mi representado, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado interpongo en tiempo y forma recurso de apelación para ante la Audiencia Provincial de [LOCALIDAD], al amparo de lo establecido en el art. 803.1 LECrim., en relación con el art. 790 LECrim., con base en las siguientes:

ALEGACIONES

[OPCIONAL — incluir si procede]

PRIMERA.- Quebrantamiento de normas y garantías procesales, con indefensión por falta de motivación de la sentencia, con infracción de lo dispuesto en los artículos 24.1 y 120.3 de la Constitución.

Se considera infringido el derecho constitucional [COMPLETAR] del art. de la CE puesto que [COMPLETAR].

Con tal infracción se ha generado efectiva indefensión debido a que [COMPLETAR]

En el acta de juicio oral consta la petición de subsanación de la falta, presentada por esta parte a efectos de cumplimiento del artículo 790.2 LECrim.

[OPCIONAL — incluir si procede]

SEGUNDA.- Quebrantamiento de normas y garantías procesales, con indefensión, por indebida denegación de prueba, con infracción de lo dispuesto en el artículo 24.2 de la Constitución.

Sobre el planteamiento de indebida denegación de prueba señalamos que en el escrito de acusación propusimos la siguiente prueba, que era pertinente y necesaria [COMPLETAR], y que, sin embargo, se inadmitió por auto de fecha [FECHA], volviendo a interesar la prueba y la suspensión del juicio el día del señalamiento, siendo de nuevo denegado por el juez de lo penal, lo que supone una vulneración de la tutela judicial efectiva causante de indefensión material.

La doctrina constitucional configura el derecho a la prueba como un derecho fundamental (art. 24.2 CE), cuya vulneración es susceptible de amparo, pero para ello es preciso (SSTC 121/2009, 185/2007, 1/2004, 43/2003, 237/1999): a) Que la prueba sea pertinente, pues sólo a ella se refiere el artículo 24.2 de la Constitución. b) Que, dada su configuración legal, la parte la haya propuesto en tiempo y forma de acuerdo con las previsiones legales. c) Que el tribunal sentenciador la haya denegado y se haya reaccionado protestando o recurriendo frente a la denegación, siempre que sea procesalmente posible. d) Que, al tratarse de un derecho medial-procedimental, se acredite que tal denegación ha podido tener una influencia en el fallo, porque podría haberse variado de haberse admitido, y es esa aptitud de la prueba denegada en relación con el fondo del asunto lo que motiva el amparo al haberse causado indefensión a la parte, indefensión que por ello se considera que es material y no simplemente formal.

En el presente caso, hacemos la advertencia de la indebida denegación de prueba en el juicio ex post a la sentencia, en tanto en cuanto esta se basó en la siguiente prueba [COMPLETAR], y de haberse admitido, podría haberse rebatido la prueba de la contraparte y llevar todo ello a una sentencia condenatoria, por cuanto hubiera alterado la valoración de la prueba en los siguientes términos [COMPLETAR].

Existe, por ello, una clara vulneración de la tutela judicial efectiva (arts 5.4 LOPJ y art. 24.2 CE) causante de indefensión material ante la indebida denegación de la prueba propuesta en tiempo y forma y reiterada en el juicio oral, como es preceptivo. Ello provoca que en este recurso planteemos la nulidad en primer término.

[OPCIONAL — incluir si procede]

TERCERA.- Error en la apreciación de las pruebas

En este caso acudimos al art. 790.2.3 LECrim., por cuanto: «Cuando la acusación alegue error en la valoración de la prueba para pedir la anulación de la sentencia absolutoria o el agravamiento de la condenatoria, será preciso que se justifique la insuficiencia o la falta de racionalidad en la motivación fáctica, el apartamiento manifiesto de las máximas de experiencia o la omisión de todo razonamiento sobre alguna o algunas de las pruebas practicadas que pudieran tener relevancia o cuya nulidad haya sido improcedentemente declarada»

En este caso concreto, en el apartado de hechos probados de la sentencia se dice literalmente « [COMPLETAR] ». Y ello está en contradicción con las siguientes pruebas:

Justificamos la insuficiencia o falta de racionalidad en la motivación fáctica, así como apartamiento manifiesto de las máximas de experiencia o la omisión de todo razonamiento sobre alguna o algunas de las pruebas practicadas en los siguientes extremos que constan en la sentencia

[OPCIONAL — incluir si procede]

CUARTA.- Infracción de normas del ordenamiento jurídico.

En el presente caso se ha dictado sentencia absolutoria por no haber acreditado la tasación o valor del dispositivo electrónico objeto del hurto, cuando la LO 1/2026, de 8 de abril, ha incluido el nº 10 en el art. 235.1 CP. referido al delito de sustracción de un teléfono móvil, sin exigencias de su tasación, puesto que el valor del teléfono no es requisito del tipo penal, por lo que se solicita la nulidad de la sentencia y que se vuelva a celebrar nuevo juicio con juez distinto.

Hay que recordar que, conforme al art. 792.2 LECrim.:

«2. La sentencia de apelación no podrá condenar al encausado que resultó absuelto en primera instancia ni agravar la sentencia condenatoria que le hubiera sido impuesta por error en la apreciación de las pruebas en los términos previstos en el tercer párrafo del artículo 790.2.

No obstante, la sentencia, absolutoria o condenatoria, podrá ser anulada y, en tal caso, se devolverán las actuaciones al órgano que dictó la resolución recurrida. La sentencia de apelación concretará si la nulidad ha de extenderse al juicio oral y si el principio de imparcialidad exige una nueva composición del órgano de primera instancia en orden al nuevo enjuiciamiento de la causa.»

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por interpuesto recurso de apelación contra la sentencia recaída en estos autos, se admita en ambos efectos dando traslado del mismo a las demás partes para que presenten sus escritos de alegaciones, y remita las actuaciones a la Audiencia Provincial para que

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se pide nulidad por quebrantamiento de forma / Si se pide nulidad por otros motivos — el texto de cada opción no venía en el formulario original]

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, cumpliendo el art. 790.2 LECrim., designo como domicilio para notificaciones el situado en [COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN: que tenga por realizada la anterior manifestación.

Es Justicia que reitero en el Lugar y fecha ut supra indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
