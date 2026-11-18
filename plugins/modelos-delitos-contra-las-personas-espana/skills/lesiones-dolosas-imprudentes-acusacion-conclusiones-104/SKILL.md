---
name: lesiones-dolosas-imprudentes-acusacion-conclusiones-104
description: "Redacta el escrito «Lesiones dolosas o imprudentes: acusación con conclusiones alternativas» (formulario 104 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones dolosas o imprudentes: acusación con conclusiones alternativas

> Formulario 0104 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] NOMBRE DEL REPRESENTADO/A (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] MATRÍCULA (2 veces)
- [ ] CALLE (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] PENA
- [ ] DURACIÓN
- [ ] IMPORTE (3 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] LUGAR
- [ ] Otros 26 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, a las [Nº] horas, el acusado»; «…y asegurado en la compañía»; «…, cuando se observó que»; «…a la acera con intención de atropellar a»; «…zándose hacia la derecha, tropezando con»; «…ayendo al suelo. A consecuencia de ello,»; «…ospital en el vehículo el propio acusado»; «…ció a trasladarle, siendo acompañado por»; «…y»; «…La curación de las lesiones producidas a»; «…, a las [Nº] horas, el acusado»; «…y asegurado en la compañía»; …

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1. Interrogatorio del acusado.…
- 2. Testifical, debiendo ser citados por el Tribunal los siguientes testigos:…
- 3. Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 781.1 de la Ley de Enjuiciamiento Criminal
- art. 650 y 653 de la LECrim
- arts. 147 y 148.1 del Código Penal
- art. 147.1 del Código Penal
- art. 28 del Código Penal
- art. 784.1 de la LECrim

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

### Formulario 0104 · Lesiones dolosas o imprudentes: acusación con conclusiones alternativas

- Año del modelo: 2023
- Revisión 17-11-2026: 3 párrafos opcionales señalados; 53 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 103) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación en un procedimiento abreviado presenta sus conclusiones provisionales, conforme al art. 781 LECRIM, calificando los hechos como delito de lesiones dolosas del art. 147 y 148.1 CP y, para el caso de que no se aprecie dolo, se califiquen de lesiones por imprudencia grave del art. 152.1.1º CP.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A], según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho, DIGO:

Que, evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo dispuesto en el art. 781.1 de la Ley de Enjuiciamiento Criminal, en relación con los art. 650 y 653 de la LECrim, intereso la apertura del juicio oral ante la Sección de lo Penal de este Tribunal de Instancia y presento escrito de acusación, contra [ACTO O RESOLUCIÓN], formulando las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- El día [FECHA], a las [Nº] horas, el acusado [COMPLETAR], mayor de edad y sin antecedentes penales, conducía su vehículo matrícula [MATRÍCULA] y asegurado en la compañía [COMPLETAR], por la calle [CALLE], cuando se observó que [COMPLETAR], con quien tenía una conocida relación de enemistad, estaba en la acera de la citada calle, a la altura del número [NÚMERO] hablando con otras dos personas, ante lo cual giró el vehículo subiendo a la acera con intención de atropellar a [COMPLETAR]. Al percatarse éste de la maniobra, le esquivó desplazándose hacia la derecha, tropezando con [COMPLETAR] y cayendo al suelo. A consecuencia de ello, [COMPLETAR] impactó con su cabeza en el suelo produciéndose un traumatismo cráneo-encefálico, con pérdida de conocimiento, siendo trasladado al Hospital en el vehículo el propio acusado [COMPLETAR] quien, al ver el resultado de su acción y asustado por las consecuencias que podía depararle, se ofreció a trasladarle, siendo acompañado por [COMPLETAR] y [COMPLETAR]. La curación de las lesiones producidas a [COMPLETAR]. requirieron de ingreso hospitalario durante 3 días, inmovilización durante 30 días, tardando en curar 60 días con impedimento para sus ocupaciones habituales.

CASO DE NO ESTIMARSE PROBADA LA ANTERIOR, ALTERNATIVAMENTE: El día [FECHA], a las [Nº] horas, el acusado [COMPLETAR], mayor de edad y sin antecedentes penales, conducía su vehículo matrícula [MATRÍCULA] y asegurado en la compañía [COMPLETAR], por la calle [CALLE], cuando se observó que [COMPLETAR], con quien tenía una conocida relación de enemistad, estaba en la acera de la citada calle, a la altura del número [NÚMERO] hablando con otras dos personas, ante lo cual giró el vehículo subiendo a la acera con intención de asustar a [COMPLETAR] y con desprecio de las más elementales reglas de la circulación rodada. Al percatarse éste de la maniobra, le esquivó desplazándose hacia la derecha, tropezando con [COMPLETAR] y cayendo al suelo. A consecuencia de ello, [COMPLETAR] impactó con su cabeza en el suelo produciéndose un traumatismo cráneo-encefálico, con pérdida de conocimiento, siendo trasladado al Hospital en el vehículo el propio acusado [COMPLETAR] quien, al ver el resultado de su acción, se ofreció a trasladarle, siendo acompañado por [COMPLETAR] y [COMPLETAR]. La curación de las lesiones producidas a [COMPLETAR] requirieron de ingreso hospitalario durante 3 días, inmovilización durante 30 días, tardando en curar 60 días con impedimento para sus ocupaciones habituales.

SEGUNDA.- Los hechos relatados son constitutivos de un delito de lesiones previsto y penado en los arts. 147 y 148.1 del Código Penal.

ALTERNATIVAMENTE Los hechos relatados son constitutivos de un delito de lesiones por imprudencia grave previsto y penado en el art. 152.1.1º CP, en relación con art. 147.1 del Código Penal.

TERCERA.- Es responsable criminalmente el acusado de los hechos descritos en concepto de autor, conforme al art. 28 del Código Penal.

CUARTA.- No concurren circunstancias modificativas de la responsabilidad criminal.

QUINTA.- Procede imponer al acusado la pena de [PENA], y costas.

ALTERNATIVAMENTE procede imponer al acusado la pena de y privación del permiso de conducir por tiempo de [DURACIÓN]. Condena en costas.

Responsabilidad civil: El acusado indemnizará a mi representado [NOMBRE DEL REPRESENTADO/A] en la cantidad de [IMPORTE] euros por las lesiones ocasionadas, debiendo declararse la responsabilidad civil directa de la aseguradora [COMPLETAR].

PRIMER OTROSÍ DIGO: Solicito que se emplace a la aseguradora [COMPLETAR] con domicilio en [LOCALIDAD] en concepto de responsable civil directa para que, en su caso, pueda formular escrito de defensa conforme al art. 784.1 de la LECrim.

SEGUNDO OTROSÍ DIGO: Esta representación, para el acto de la vista oral, interesa los siguientes MEDIOS DE PRUEBA:

[OPCIONAL — incluir si procede]

1. Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

2. Testifical, debiendo ser citados por el Tribunal los siguientes testigos:

– [COMPLETAR], interesando sea citado a través de esta representación procesal.
– [COMPLETAR], con domicilio en [LOCALIDAD]
– [COMPLETAR], con domicilio en [LOCALIDAD]

[OPCIONAL — incluir si procede]

3. Documental:

– 2-4 (Partes asistencia hospitalaria)
– 21 (Hoja Histórico Penal del acusado).
– 27-28 (pericial médico-forense documentada)

TERCER OTROSÍ DIGO: Procede mantener la situación personal del acusado.

CUARTO OTROSÍ DIGO: Intereso que se formen las oportunas piezas de responsabilidad civil, requiriendo al acusado para que preste fianza por importe de [IMPORTE] euros y a la responsable civil directa para que preste fianza por importe de [IMPORTE] euros.

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, se sirva admitirlo y tenga por evacuado el traslado conferido, por dirigida la acusación y solicitada la apertura del juicio oral ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] contra [ACTO O RESOLUCIÓN], emplazar a la aseguradora [COMPLETAR] como responsable civil directa, resolver de conformidad con las medidas cautelares, y la práctica de la prueba que dejo interesada para ante el órgano de enjuiciamiento.

Es justicia que pido, en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
