---
name: pedir-compruebe-exactitud-traduccion-interpretacion-745
description: "Redacta el escrito «Pedir que se compruebe la exactitud de la traducción o interpretación (defensa del investigado)» (formulario 745 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que se compruebe la exactitud de la traducción o interpretación (defensa del investigado)

> Formulario 0745 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»; «…- Donde dice»; «…mi defendido/a declaró»; «…porque el/la intérprete le tradujo»; «…y debería haber traducido»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- - Donde dice [COMPLETAR] mi defendido/a declaró [COMPLETAR] porque el/la intérprete le tradujo [COMPLETAR] y d…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 124.3 de la LECRIM
- art. 123 LECRIM
- art. 11 LO 5/2024
- artículo 124.3 LECRIM
- artículo 777.2 LECRIM
- artículo 125 LECRIM

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

### Formulario 0745 · Pedir que se compruebe la exactitud de la traducción o interpretación (defensa del investigado)

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 párrafos repetibles señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el investigado/a solicita que se lleven a cabo las actuaciones necesarias para comprobar la exactitud de la traducción en su toma de declaración en la instrucción y, en caso de no haber sido correcta, se proceda a nombrar nuevo intérprete y a repetir dicha declaración, en base al artículo 124.3 de la LECRIM.

Actualizado conforme a la LO 5/2024, del Derecho de Defensa, vigente desde el 4/12/2024

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en el procedimiento nº [Nº DE PROCEDIMIENTO]/[AÑO] por el supuesto delito de [DELITO] del artículo [COMPLETAR] del CP, comparezco ante este órgano judicial (1) y, como mejor proceda en derecho, DIGO:

Que en fecha [FECHA] se celebró la toma de declaración a mi representado/a.

Que en la citada declaración, y en base a lo dispuesto en el art. 123 LECRIM y en el art. 11 LO 5/2024, del Derecho de Defensa, se proveyó de intérprete a mi representado/a. No obstante, lo cual, una vez leída la transcripción de la declaración, no estamos conformes con ello, en base a lo que dispone el artículo 124.3 LECRIM :

"3. Cuando el Tribunal, el Juez o el Ministerio Fiscal, de oficio o a instancia de parte, aprecie que la traducción o interpretación no ofrecen garantías suficientes de exactitud, podrá ordenar la realización de las comprobaciones necesarias y, en su caso, ordenar la designación de un nuevo traductor o intérprete. En este sentido, las personas sordas o con discapacidad auditiva que aprecien que la interpretación no ofrece garantías suficientes de exactitud, podrán solicitar la designación de un nuevo intérprete."

Se indican a continuación los puntos de la interpretación que fueron incorrectos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- Donde dice [COMPLETAR] mi defendido/a declaró [COMPLETAR] porque el/la intérprete le tradujo [COMPLETAR] y debería haber traducido [COMPLETAR].

Dado que la declaración se grabó en video, en base a lo dispuesto en el artículo 777.2 LECRIM, si hubiese dudas sobre esta declaración, se ruega se proceda al visionado de la misma.

Se interesa, por tanto, se proceda a hacer las pertinentes comprobaciones sobre la exactitud de la interpretación y, en su caso, se repita la declaración con designación de nuevo intérprete, en base al perjuicio que le causaría a mi defendido/a la posibilidad de contrastar luego en el plenario las declaraciones llevadas a cabo en la instrucción con las del juicio oral, si con nuevo intérprete que traduzca correctamente se apreciasen diferencias con la declaración en la fase de instrucción y se interesase por la fiscalía la lectura de la declaración sumarial antes referida que fue incorrecta.

Por lo expuesto,

SUPLICO A LA SECCIÓN

que tenga por presentado este escrito, lo admita y tenga por realizado el trámite para interesar la comprobación de la exactitud de la traducción y, en su caso, el nombramiento de nuevo intérprete y repetición de la declaración en la fecha que se indique.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito se presentará:

-Ante la Sección de instrucción del Tribunal de Instancia si la inexactitud se produce en la fase de investigación.

-Si esta circunstancia se diera en el juicio oral y la defensa del acusado lo descubriese posteriormente, solo quedaría la opción de recurrir la sentencia apelando a la nulidad del juicio en base a la infracción del artículo 125 LECRIM y haberse detectado tras ver el video del juicio oral con un traductor que le apercibió de los errores en la traducción que dieron lugar a un dictado de la sentencia en un sentido, lo que daría lugar a la nulidad del juicio y sentencia por grave defecto de forma referido a errores en la traducción que podrían haber llevado al juez o tribunal a valorar la prueba en un determinado sentido.

================================================================================
