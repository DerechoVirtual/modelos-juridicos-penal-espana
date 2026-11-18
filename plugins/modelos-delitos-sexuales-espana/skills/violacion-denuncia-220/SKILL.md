---
name: violacion-denuncia-220
description: "Redacta el escrito «Violación: denuncia» (formulario 220 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación: denuncia

> Formulario 0220 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde la LO 4/2023 el art. 179 CP distingue el 179.1 (de cuatro a doce años) y el 179.2 (de seis a doce años con violencia, intimidación o voluntad anulada); la calificación debe precisar el apartado según la fecha de los hechos.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] ESTADO CIVIL
- [ ] PROFESIÓN
- [ ] LOCALIDAD
- [ ] DNI/NIE
- [ ] FECHA (3 veces)
- [ ] Nº
- [ ] CALLE
- [ ] LUGAR
- [ ] ÓRGANO
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con DNI número [DNI/NIE] expedido en»; «…aba tirada en el monte que reconocí como»; «…, cerca de»; «…a persona denunciada que se conocen son:»; «… médicos de asistencia del centro médico»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 259 a 269 de la LECRIM
- art. 26 de la Ley 4/2015
- art. 681.3 LECRIM
- art. 179 CP

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

### Formulario 0220 · Violación: denuncia

- Año del modelo: 2022
- Revisión 17-11-2026: 1 rangos de artículos despegados («25 a31» → «25 a 31»); 1 llamadas a nota sin texto retiradas; 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Desde la LO 4/2023 el art. 179 CP distingue el 179.1 (de cuatro a doce años) y el 179.2 (de seis a doce años con violencia, intimidación o voluntad anulada); la calificación debe precisar el apartado según la fecha de los hechos.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], y profesión [PROFESIÓN], con domicilio en [LOCALIDAD], con DNI número [DNI/NIE] expedido en [COMPLETAR], el día [FECHA], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, por medio del presente escrito, y con base en los artículos 259 a 269 de la LECRIM, formulo denuncia con base en los siguientes

HECHOS

PRIMERO.- El día [FECHA], sobre las [Nº] horas, cuando me dirigía a mi casa y caminaba por la acera, un coche paró a mi lado y su conductor, un desconocido, me preguntó cómo se iba a la calle [CALLE] Mientras yo le explicaba el camino, abrió la puerta contigua, me agarró por el brazo y me introdujo dentro del coche con un fuerte tirón. Rápidamente me ató, me amordazó y me tapó los ojos. Seguidamente me llevó a un lugar desierto, me quitó la mordaza y la venda de los ojos y me penetró vaginal y analmente. Después me golpeó hasta que perdí la consciencia. Cuando de nuevo la recuperé, me encontraba tirada en el monte que reconocí como [COMPLETAR], cerca de [COMPLETAR]. Comencé a andar hasta encontrar una carretera o el edificio más cercano. Llegué a una casa, llamé y pedí ayuda.

SEGUNDO.- Los datos de la persona denunciada que se conocen son: [COMPLETAR].

En consecuencia, y dado que me considero víctima de un delito,

SUPLICO A LA SECCIÓN:

Que se sirva acordar lo pertinente para la comprobación y averiguación de los hechos y sus autores.

PRIMER OTROSÍ DIGO: que intereso la práctica de las siguientes DILIGENCIAS:

1. Que se reciba declaración al/a la denunciado/a.
2. Que se reciba declaración a los siguientes testigos:
-Declaración de la víctima Dña. [NOMBRE Y APELLIDOS].

En base a lo dispuesto en el art. 26 de la Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, según redacción dada por la LO 10/2022, se interesa que la declaración de la víctima de delito sexual sea grabada en la instrucción y reproducida en sede judicial en base a que señala que: "1. En el caso de las víctimas menores de edad, víctimas con discapacidad necesitadas de especial protección, y víctimas de violencias sexuales, además de las medidas previstas en el artículo anterior se adoptarán, de acuerdo con lo dispuesto en la Ley de Enjuiciamiento Criminal, las medidas que resulten necesarias para evitar o limitar, en la medida de lo posible, que el desarrollo de la investigación o la celebración del juicio se conviertan en una nueva fuente de perjuicios para la víctima del delito.

En particular, serán aplicables las siguientes: a) Las declaraciones recibidas durante la fase de investigación serán grabadas por medios audiovisuales y podrán ser reproducidas en el juicio en los casos y condiciones determinadas por la Ley de Enjuiciamiento Criminal."

-
3. Pericial siguiente:

Se interesa sea reconocida por el médico forense y que se reclamen los partes médicos de asistencia del centro médico [COMPLETAR] a donde acudí nada más producirse el hecho y en donde constan datos de relevancia médica, también en relación con las lesiones causadas.

4.

SEGUNDO OTROSÍ DIGO: que solicito las siguientes medidas cautelares:

1. De conformidad con lo dispuesto en el art. 681.3 LECRIM, según redacción dada por Ley orgánica de garantía integral de la libertad sexual, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a mi identidad, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre mis necesidades de protección, así como la obtención, divulgación o publicación de imágenes mías o de mis familiares.
2. Se solicita, también, la inmediata detención e ingreso en prisión del autor de este delito tipificado en el art. 179 CP.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

================================================================================
