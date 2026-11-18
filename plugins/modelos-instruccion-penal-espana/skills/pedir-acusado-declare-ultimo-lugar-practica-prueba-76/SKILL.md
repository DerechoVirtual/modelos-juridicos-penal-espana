---
name: pedir-acusado-declare-ultimo-lugar-practica-prueba-76
description: "Redacta el escrito «Pedir que el acusado declare en último lugar en la práctica de la prueba» (formulario 76 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que el acusado declare en último lugar en la práctica de la prueba

> Formulario 0076 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, según consta acreditado en»

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 701 LECRIM
- art. 786.2 LECRIM
- art. 701.2 LECRIM
- arts. 2 y 3 de la Ley Orgánica 5/2024

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

### Formulario 0076 · Pedir que el acusado declare en último lugar en la práctica de la prueba

- Año del modelo: 2024
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 79) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la defensa del acusado en cualquier proceso penal por el que solicita que el acusado declare en último lugar en la práctica de la prueba en juicio oral, en base a la STS 714/2023, de 28 de septiembre que sienta doctrina en este sentido y, desde el 3 de abril de 2025, fecha de entrada en vigor de la LO 1/2025, de Eficiencia de la Justicia, también conforme al art. 701 LECRIM.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial nº de

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en [COMPLETAR] seguido ante este órgano judicial al que me dirijo, comparezco y como proceda en Derecho, DIGO:

HECHOS

PRIMERO.- Que en fecha [FECHA] se ha señalado el juicio oral en el procedimiento antes indicado.

SEGUNDO.- Que por medio del presente escrito intereso que la declaración del/de la acusado/a se haga en último lugar, en atención al criterio de la Sentencia del Tribunal Supremo 714/2023, de 28 de septiembre, que así lo permite y al art. 701 LECRIM (según redacción dada por LO 1/2025, de Eficiencia de la Justicia, vigente desde el 3 de abril de 2025).

TERCERO.- Que, aunque ya se ha presentado escrito de defensa, la petición de que el/la acusado/a declare en último lugar se puede realizar hasta el inicio del juicio oral en cuestiones previas.

FUNDAMENTOS JURÍDICOS

PRIMERO.- Señala la Sentencia del Tribunal Supremo 714/2023 de 28 de septiembre que:

"Esta Sala del Tribunal Supremo en Sentencia 750/2021 de 6 Oct. 2021, Rec. 21019/2019 ya ha admitido que el acusado declare en último lugar tras la práctica del resto de la prueba al solicitarlo en juicio oral de aforado la letrada, lo que fue admitido por el Presidente del tribunal al suponer un mejor ejercicio del derecho de defensa.

Hay que señalar a este respecto que no es posible desdeñar las indudables ventajas que le suponen al acusado declarar tras finalizar la práctica de la prueba en relación a lo que declararon los testigos, sobre todo, o los documentos que se han elevado al plenario como "utilizables" a la hora de que el juez o Tribunal dicte sentencia, el informe pericial ratificado y explicado en el plenario. Su declaración puede quedar más "matizada" si conoce lo que declararon los testigos y en algún dato técnico del informe de los peritos, como decimos.

Sin embargo, no es posible comparar la declaración del acusado con el derecho de última palabra para que en este punto añada el acusado lo que le interese de las declaraciones efectuadas en la práctica de la prueba, ya que en el derecho de última palabra no hay "interrogatorio" por las partes, sino una explicación del acusado a modo de resumen. No se entiende protegido el "mejor derecho de defensa" por la circunstancia de que exista el derecho de última palabra. La defensa podrá en trámite de cuestiones previas, o bien antes en su escrito de calificación provisional instar que el acusado declare en último lugar, porque no hay precepto de la LECRIM que obligue a que lo haga en primer lugar.

Además, el Código procesal penal (art. 567) pendiente de aprobación ya apostó cuando fue redactado por los técnicos que lo elaboraron por que el acusado declare en último lugar al apostar por un mejor ejercicio del derecho de defensa señalando en su Exposición de motivos que el sistema actual de declaración inicial del acusado distorsiona el juego efectivo del principio de presunción de inocencia y genera una práctica procesal puramente dialéctica en la que el juez parece encaminado a elegir la tesis más verosímil entre dos opciones de igual valor, cuando en realidad quien ha de demostrar plenamente su tesis es la parte acusadora. La defensa ha de poder limitarse a generar una duda razonable sobre la misma. A esta idea responde la variación de la posición de la declaración del acusado en la estructura del juicio oral.

A mayor abundamiento, el art. 701 LECRIM señala en sus párrafos 4, 5 y 6 que:

"Acto continuo se pasará a la práctica de las diligencias de prueba y al examen de los testigos, empezando por la que hubiere ofrecido el Ministerio Fiscal, continuando con la propuesta por los demás actores, y por último con la de los procesados.

Las pruebas de cada parte se practicarán según el orden con que hayan sido propuestas en el escrito correspondiente. Los testigos serán examinados también por el orden con que figuren sus nombres en las listas.

El Presidente, sin embargo, podrá alterar este orden a instancia de parte y aun de oficio cuando así lo considere conveniente para el mayor esclarecimiento de los hechos o para el más seguro descubrimiento de la verdad."

La LECRIM no exige, por ello, que el acusado declare en primer lugar, y debemos circunscribirnos al orden que propongan las partes, y si lo interesa la defensa conforme exponemos, no hay razón para negar ese derecho.

Con ello, cabe que la defensa exponga en su escrito de calificación provisional, en escrito posterior, o en el trámite de cuestiones previas, que el acusado declare en último lugar, lo que garantiza mejor el derecho de defensa, y debería ser admitido, porque no se ejerce igual el derecho de defensa con el interrogatorio por el letrado en último lugar que con la "autodefensa" que pueda suponer el ejercicio del derecho a la última palabra, ya que en base al interrogatorio del juicio oral podrá construir, también, la defensa su alegato en el informe del plenario en resumen de la práctica de la prueba.

Con ello, se puede fijar que:

1.- El letrado del acusado tiene derecho a solicitar del juez o Presidente del Tribunal que éste declare en último lugar tras concluir el resto de la práctica de la prueba admitida.
2.- Esta petición deberá cursarse con sentido preclusivo al comienzo del juicio en el trámite del art. 786.2 LECRIM [NOTA DE REVISIÓN: Tras la LO 1/2025 (desde el 3-4-2025) el art. 786.2 ya no regula el turno de cuestiones previas: se plantean en la audiencia preliminar del art. 785.1, y el derecho del acusado a declarar en último lugar figura en el art. 701, párrafo segundo. Fuente: LECrim, BOE-A-1882-6036, arts. 701, 785 y 786 (redacción LO 1/2025, BOE-A-2025-76).], tanto en el sumario como en el procedimiento abreviado y resto de procedimientos penales.
3.- Que se curse esta petición no impide que el juez o presidente del Tribunal siga interrogando al acusado al comienzo del juicio sobre si reconoce los hechos y se muestra conforme con la más grave de las acusaciones. A continuación, comenzará el interrogatorio, salvo que el letrado del acusado le solicite que declare tras la práctica del resto de la prueba.
4.- En el caso de ser varios los acusados y alguno de ellos lo interesara, el juez o presidente del Tribunal preguntará al resto y si no lo interesan todos lo acordará con respecto a aquél o aquéllos que lo hubieren solicitado, declarando el resto al principio de la práctica de la prueba.
5.- El derecho a la última palabra se mantiene inalterable aunque el acusado declare tras concluir el resto de la práctica de la prueba. Es el derecho de autodefensa, en el que el acusado expone lo que le interese al concluir el juicio y sin preguntas de las partes.
6.- El acusado tiene derecho a declarar junto a su letrado."

SEGUNDO.- Del mismo modo, señala el art. 701.2 LECRIM (según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025) que:

"Las pruebas de cada parte se practicarán según el orden con que hayan sido propuestas en el escrito correspondiente. Los testigos serán examinados también por el orden con que figuren sus nombres en las listas. No obstante lo anterior, si a propuesta de su defensa el acusado solicitara declarar en último lugar, el Presidente así lo acordará expresamente."

Es por ello que, para un mejor ejercicio del derecho de defensa, se interesa que la declaración del acusado se haga en último lugar en la práctica de la prueba en el acto del juicio oral, para un mayor reconocimiento del derecho de defensa plasmado en los arts. 2 y 3 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa.

Por todo ello,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración del/de la acusado/a se produzca en último lugar en el orden en la práctica de la prueba en el juicio oral.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
