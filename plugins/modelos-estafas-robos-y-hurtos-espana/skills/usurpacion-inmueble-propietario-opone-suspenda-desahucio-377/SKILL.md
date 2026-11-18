---
name: usurpacion-inmueble-propietario-opone-suspenda-desahucio-377
description: "Redacta el escrito «Usurpación de inmueble: el propietario se opone a que se suspenda el desahucio» (formulario 377 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Usurpación de inmueble: el propietario se opone a que se suspenda el desahucio

> Formulario 0377 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La facultad judicial de suspender lanzamientos del art. 1 bis RDL 11/2020 dejó de surtir efecto el 31-12-2025; el RDL 2/2026, que la prorrogaba, fue derogado por el Congreso (BOE-A-2026-4667), lo que refuerza la oposición del propietario.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (10 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… presentado ante la agencia inmobiliaria»

## Elecciones que hay que hacer

- la ejecutoria penal / el procedimiento penal
- condenado/a / acusado/a

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 245.2 CP
- art. 1 bis del RDL 11/2020
- art. 1 bis del Real Decreto-ley 11/2020
- artículo 250.1 de la Ley 1/2000
- art. 13 LECRIM

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

### Formulario 0377 · Usurpación de inmueble: el propietario se opone a que se suspenda el desahucio

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (1); 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La facultad judicial de suspender lanzamientos del art. 1 bis RDL 11/2020 dejó de surtir efecto el 31-12-2025; el RDL 2/2026, que la prorrogaba, fue derogado por el Congreso (BOE-A-2026-4667), lo que refuerza la oposición del propietario.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito en ejecutoria penal o en procedimiento por delito leve de usurpación pacífica de inmueble del art. 245.2 CP por el que se solicita al juez que no suspenda el lanzamiento o desahucio acordado en dicha ejecutoria o como medida cautelar a raíz de la facultad que le otorga el art. 1 bis del RDL 11/2020.

Actualizado conforme al RDL 8/2023, de 27 de diciembre, vigente desde el 29 de diciembre de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] en representación de D./Dña. [NOMBRE Y APELLIDOS] acusación particular en [ELEGIR: la ejecutoria penal / el procedimiento penal] nº [Nº DE PROCEDIMIENTO] que se sigue por delito de usurpación de bien inmueble del art. 245.2 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Con fecha [FECHA] se ha recibido notificación de la resolución del/de la Ilustre Letrado/a de la Administración de Justicia del citado órgano judicial dando cuenta de la fijación del señalamiento del lanzamiento del inmueble sito en [LOCALIDAD], donde reside el/la [ELEGIR: condenado/a / acusado/a], para el próximo día [FECHA].

Con fecha [FECHA] se ha recibido traslado del escrito presentado por la defensa de el/la [ELEGIR: condenado/a / acusado/a] instando la suspensión del lanzamiento acordada por el LAJ de este órgano judicial y fijada para el día [FECHA], respecto del inmueble sito en [LOCALIDAD], propiedad de esta parte y que fue ocupado ilegalmentecomo ha resultado fijado en la sentencia dictada por este órgano judicial el día [FECHA]. (1)

Mediante el presente escrito, impugno la suspensión del lanzamiento solicitada, en base a las siguientes

ALEGACIONES

PRIMERA.- A tenor del art. 1 bis del Real Decreto-ley 11/2020, de 31 de marzo, por el que se adoptan medidas urgentes complementarias en el ámbito social y económico para hacer frente al COVID-19, se fija con claridad que:

«Artículo 1 bis. Suspensión hasta el 31 de diciembre de 2025 [NOTA DE REVISIÓN: Redacción vigente del art. 1 bis RDL 11/2020; la facultad de suspensión dejó de surtir efecto el 31-12-2025 y el RDL 2/2026, que la prorrogaba, fue derogado (BOE-A-2026-4667). Fuente: Real Decreto-ley 11/2020, BOE-A-2020-4208, art. 1 bis.] del procedimiento de desahucio y de los lanzamientos para personas económicamente vulnerables sin alternativa habitacional en los supuestos de los apartados 2.º, 4.º y 7.º del artículo 250.1 de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil, y en aquellos otros en los que el desahucio traiga causa de un procedimiento penal

1. Desde la entrada en vigor del presente real decreto-ley y hasta el 31 de diciembre de 2025, en todos los juicios verbales en los que se sustancien las demandas a las que se refieren los apartados 2.º, 4.º y 7.º del artículo 250.1 de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil, y en aquellos otros procesos penales en los que se sustancie el lanzamiento de la vivienda habitual de aquellas personas que la estén habitando sin ningún título habilitante para ello,el Juez tendrá la facultaddesuspender el lanzamiento hasta el 31 de diciembre de 2025.

Estas medidas de suspensión que se establecen con carácter extraordinario y temporal, dejarán de surtir efecto en todo caso el 31 de diciembre de 2025. »

SEGUNDA.- El/La [ELEGIR: condenado/a / acusado/a] alega en su solicitud que concurren en este caso todos los requisitos para la suspensión del lanzamiento o desahucio exigidos por el citado art. 1 bis del Real Decreto-ley 11/2020, de 31 de marzo.

Sin embargo, omite que lo que dice la norma no es que se acordará la suspensión fijada, sino que se faculta al juez para ello, y en este caso no hay que olvidar que la fecha de la ocupación fue el día [FECHA], y se instó por esta parte medida cautelar de expulsión por la vía del art. 13 LECRIM, ya que, aunque no se trate de morada, esta parte tiene intención de ponerlo en venta o alquiler. De suyo, se aporta como doc. nº 1 escrito presentado ante la agencia inmobiliaria [COMPLETAR] por el que se comunica el deseo de ponerlo en venta o alquiler por su mediación el día [FECHA] para firmar contrato de agencia de exclusividad con ellos para dicho fin, con lo que un nuevo retraso supondría un grave perjuicio económico para esta parte que ya lleva soportando la ocupación ilegal desde el día [FECHA], sin que por este órgano judicial se accediera en su momento a la medida cautelar de expulsión que hubiera resuelto este problema, y ahora se insta esta medida que agravaría el perjuicio ya existente de la pérdida de la posesión inmobiliaria.

A todo esto, hay que añadir que esta parte viene pagando los consumos de luz, agua, gastos de comunidad, IBI, basuras, etc del inmueble, ya que los ocupantes, obviamente, no han puesto estos gastos a su nombre y el corte de luz o agua podría constituir un ilícito penal.

Se aportan como docs. nº [NÚMERO] los gastos citados, por lo que un nuevo retraso supondría prolongar el perjuicio ya existente, y conllevaría un auténtico fraude a esta parte que ha tenido que esperar ya [Nº] meses a que se resuelva esta situación y no está en condiciones psicológicas ni económicas para esperar un nuevo retraso al precisar con urgencia el lanzamiento para proceder a la venta o alquiler.

Con ello, al tratarse en la norma este tema con un carácter facultativo del/de la juez/a adaptado a las circunstancias del caso,

Por todo ello,

SUPLICO A LA SECCIÓN:

Se admita el presente escrito, e intereso se deniegue la petición y no se suspenda la medida de lanzamiento de la vivienda y se mantenga la fecha fijada para el día [FECHA].

En [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Nótese que la decisión de lanzamiento puede serlo bien en ejecutoria penal, o bien por medida cautelar de expulsión, ya que el art. 245.2 CP permite, por la vía del art. 13 LECRIM, la adopción de la medida cautelar de expulsión del ocupante ilegal. Por ello, el escrito puede dimanar bien en la ejecutoria penal o bien en el procedimiento por delito leve del art. 245.2 CP cuando se ha interesado y adoptado por el propietario la medida cautelar de expulsión.

================================================================================
