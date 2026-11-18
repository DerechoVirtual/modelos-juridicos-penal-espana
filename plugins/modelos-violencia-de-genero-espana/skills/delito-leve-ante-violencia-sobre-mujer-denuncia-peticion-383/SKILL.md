---
name: delito-leve-ante-violencia-sobre-mujer-denuncia-peticion-383
description: "Redacta el escrito «Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato» (formulario 383 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato

> Formulario 0383 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (7 veces)
- [ ] CALLE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] CORREO ELECTRÓNICO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…eque por turno de reparto corresponda Dª»; «…, C/ [CALLE], teléfono móvil»; «…rtículo 173.4 del Código Penal, contra D»; «…ación, la cual finalizó el pasado mes de»; «…l último mes y especialmente en la plaza»; «…la denunciante estaba en la citada plaza»; «… cuando se ha encontrado con su vecino D»; «…, interesando al tiempo que se cite a D»; «…, teléfono fijo»; «…gentemente la medida de alejamiento de D»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- OTROSI II DIGO: De conformidad con lo dispuesto en el artículo 258 bis de la LECrim, se interesa que la declar…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 173.4 CP
- art. 964.2 LECRIM
- artículo 173.4 del Código Penal
- art. 89.5 d) de la LOPJ
- art. 14.5.d) de la LECrim
- art. 173.4 del Código Penal
- art. 964.2 de la LECrim
- art. 544 bis de la LECrim
- art. 57 del CP
- artículo 258 bis de la LECrim

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

### Formulario 0383 · Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato

- Año del modelo: 2021
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que una víctima de violencia de género denuncia ante el juez unos hechos que pueden ser constitutivos de un delito leve de injurias del art. 173.4 CP [NOTA DE REVISIÓN: La injuria o vejación injusta leve sobre las personas del art. 173.2 se tipifica en el art. 173.4 CP, como cita el propio escrito más adelante. Fuente: Código Penal, BOE-A-1995-25444, art. 173.4.] y solicita su enjuiciamiento inmediato por la vía del art. 964.2 LECRIM.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia deque por turno de reparto corresponda

Dª [COMPLETAR], mayor de edad, con D.N.I., con domicilio en [LOCALIDAD], C/ [CALLE], teléfono móvil [COMPLETAR], con la asistencia letrada de D. [NOMBRE Y APELLIDOS], Abogado del Iltre. Colegio de [LOCALIDAD], ante este órgano judicial, como mejor proceda en derecho, comparezco y DIGO:

Que, mediante el presente escrito, formulo DENUNCIA por delito de leve de injurias y vejaciones injustas del artículo 173.4 del Código Penal, contra D [COMPLETAR], ex pareja de la denunciante, con domicilio en [LOCALIDAD], en base a los siguientes

HECHOS

PRIMERO.- Que la denunciante y el denunciado tuvieron una relación de pareja de hecho de tres años de duración, la cual finalizó el pasado mes de [COMPLETAR]. Durante esta relación de pareja, ambos estuvieron conviviendo en el domicilio de la denunciante, que consta en el encabezamiento, el cual abandonó el denunciado tras llegar a su fin la relación sentimental mantenida por ambos.

En el tiempo que ha transcurrido desde el fin de la convivencia, la denunciante ha observado que, a la hora que pasea a su perro por las mañanas, el denunciado acude con cierta frecuencia a las proximidades de su domicilio, dos ó tres veces a la semana, sobre todo en el último mes y especialmente en la plaza [COMPLETAR], que se encuentra enfrente de la vivienda, si bien no había tenido ninguna conversación con el denunciado, ni tan siquiera se habían saludado, puesto que la ruptura no fue amistosa y ambos no han mantenido más contacto desde entonces.

SEGUNDO.- En la mañana del día de hoy, sobre las 9 horas, la denunciante estaba en la citada plaza [COMPLETAR], paseando su perro como hace habitualmente todas las mañanas, cuando se ha encontrado con su vecino D [COMPLETAR], quien también estaba con su perro, entablando una conversación. A los pocos minutos, de repente, se ha aproximado el denunciado en actitud alterada y, sin mediar otra palabra, le ha gritado "puta, ya te has buscado a otro", ante lo cual el vecino con el que estaba hablando la denunciante ha recriminado al denunciado su actitud, marchándose éste seguidamente.

Este episodio ha producido el lógico temor a la denunciante, quien ha vuelto a su domicilio y, por precaución, no ha salido en toda la mañana. Hallándose en su domicilio, ha recibido una llamada en su teléfono móvil sobre las 15.15 horas y, al identificar el teléfono del denunciado, no ha cogido la llamada. Posteriormente, ha recibido dos llamadas más, a las 15.25 horas y a las 15.40 horas, del mismo teléfono, que tampoco ha contestado.

Esto ha generado una gran preocupación y miedo en la denunciante, quien ha llamado al buzón de voz, donde el denunciado dejó dos mensajes correspondientes a las llamadas de las 15.15 horas y 15.40 horas, en los cuales textualmente dice lo siguiente:

MENSAJE 1 (15.15 horas): "Vamos, zorra, que ya te he visto con tu nuevo amiguito, seguro que ya habéis follado toda la mañana".

MENSAJE 2 (15.40 horas): "¿Qué pasa que no contestas? ¿Aun estás follando o qué?".

Acompaño soporte informático en los cuales se incluyen los mensajes del buzón de voz señalados como archivos AUDIO 1 y AUDIO 2.

TERCERO.- Estos hechos pueden ser constitutivos de un delito leve de injurias y vejaciones injustas contra la denunciante del que es autor el denunciado, con quien ha estado ligada en relación de pareja, dirigiendo esta denuncia a la Sección de Violencia sobre la Mujer al ser un delito de su competencia, de conformidad a lo dispuesto en el art. 89.5 d) de la LOPJ y art. 14.5.d) de la LECrim [NOTA DE REVISIÓN: El conocimiento y fallo de los delitos leves por la Sección de Violencia sobre la Mujer está en la letra d) del art. 89.5 LOPJ; la letra a) se refiere a la instrucción. Fuente: LOPJ, BOE-A-1985-12666, art. 89.5 d) (redacción LO 1/2025, BOE-A-2025-76).], correspondiéndole el conocimiento y fallo de los procedimientos por delito leve, entre otros, del art. 173.4 del Código Penal, existiendo claros indicios de la comisión de este delito por el denunciado, como se pone de manifiesto en esta denuncia.

CUARTO.- Estos hechos han generado una grave preocupación y temor en la denunciante, puesto que son subsiguientes a una conducta de presencia regular del denunciado en las inmediaciones del domicilio de la víctima, lo cual ha generado un intenso miedo ante la posibilidad de que puedan realizarse hechos más graves por el denunciado, por lo que se solicitará, por medio de otrosí, que se dicte medida cautelar conforme al art. 13 y 544 bis y ter de la LECrim.

QUINTO.- A tenor de los anteriores hechos y entendiendo concurrentes los requisitos del art. 964.2 de la LECrim., solicito el enjuiciamiento inmediato de los hechos, puesto que el denunciado puede ser citado bien en su domicilio sito en [LOCALIDAD], bien en su lugar de trabajo sito en [LOCALIDAD], siendo además titular y portador del teléfono móvil número [NÚMERO], interesando al tiempo que se cite a D [COMPLETAR], vecino con quien estaba hablando la denunciante en el momento de producirse los hechos en la plaza, con domicilio en [LOCALIDAD], teléfono fijo [COMPLETAR] y número de teléfono móvil

En su virtud,

SUPLICO A LA SECCIÓN

Que teniendo por presentado este escrito con los documentos que al mismo se acompañan, se sirva tener por formulada denuncia en mi calidad de víctima y perjudicada, y acuerde la inmediata celebración del juicio, ordenando las citaciones que dejo propuestas.

OTROSÍ I DIGO que existiendo una situación de grave riesgo para la denunciante, derivada de la conducta del denunciado que está acudiendo regularmente a las proximidades de su domicilio y que ha materializado estos hechos que constituyen un delito contra la integridad moral, los cuales pudieran dar lugar a otras conductas de mayor entidad si no se adoptan medidas preventivas, y dado el intenso miedo que estos hechos han provocado en la denunciante, solicito de este órgano judicial que se dicte urgentemente la medida de alejamiento de D [COMPLETAR], al amparo de lo dispuesto en el art. 13 y 544.bis de la LECrim., a fin de que el denunciante no pueda aproximarse a menos de 200 metros, ni comunicarse con la víctima.

La medida solicitada cumple los requisitos del art. 544 bis de la LECrim., al tratarse de uno de los delitos mencionados en el art. 57 del CP, la cual puede imponerse, asimismo, por la comisión de delitos leves conforme al apartado 3 del citado art. 57, y es proporcionada, por cuanto que la restricción de la libertad del denunciado es mínima, al no tener ningún contacto con la víctima desde la ruptura de la convivencia, y tener su residencia y trabajo en lugares muy alejados del domicilio de la víctima, sin que coincidan en su vida personal, social o laboral diaria.

SUPLICO A LA SECCIÓN acuerde de conformidad y dicte la medida de alejamiento y prohibición de comunicación solicitada.

[OPCIONAL — incluir si procede]

OTROSI II DIGO: De conformidad con lo dispuesto en el artículo 258 bis de la LECrim, se interesa que la declaración de la denunciante en el acto de la vista oral se realice de forma telemática.

SUPLICO A LA SECCIÓN tenga por hecha la anterior petición.

OTROSI III DIGO: Que designo para que me defienda en este asunto al/a la Letrado/a del Iltre, Colegio de Abogados de [COLEGIO] a D./Dña. [NOMBRE Y APELLIDOS], con domicilio profesional en [LOCALIDAD] y con dirección de correo electrónico [CORREO ELECTRÓNICO] la cual se designa a efectos de comunicaciones y que firma conmigo en prueba de aceptación.

SUPLICO A LA SECCIÓN tenga por hecha la anterior manifestación.

En [LUGAR], a [FECHA].

Firma de la denunciante	Firma de Abogado/a

================================================================================
