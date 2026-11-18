---
name: acusado-pedir-estar-presente-fisicamente-juicios-desde-75
description: "Redacta el escrito «Acusado: pedir estar presente físicamente en los juicios (desde el 20 de marzo de 2024)» (formulario 75 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acusado: pedir estar presente físicamente en los juicios (desde el 20 de marzo de 2024)

> Formulario 0075 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 258 bis.2 LECrim no tiene ordinales. Su párrafo segundo regula los juicios por delito menos grave con pena de más de dos años de prisión y el tercero, el resto de juicios. En ambos casos el acusado comparece físicamente si lo pide él o su letrado o si el órgano judicial lo considera necesario, y la decisión se adopta por auto motivado.
- En los juicios por delito grave y en los del Jurado la presencia física del acusado es siempre necesaria (párrafo primero). Si el acusado reside en la demarcación del órgano judicial, la regla también es comparecer físicamente, salvo causa justificada o fuerza mayor (párrafo cuarto). Por eso el escrito solo tiene sentido fuera de esos casos.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…cia en sede judicial del/de la acusado/a»; «…logía en la Administración de Justicia."»; «… ello, se interesa que la declaración de»

## Elecciones que hay que hacer

- abreviado / por delito leve
- 2º / 3º

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 258 bis.1 y 2 LECRIM
- artículo 137 bis de la Ley 1/2000
- art. 258 bis LECRIM
- art. 258 bis.2 LECRIM

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

### Formulario 0075 · Acusado: pedir estar presente físicamente en los juicios (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 78) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el acusado en un procedimiento abreviado o por delito leve solicita su presencia física en el juicio oral, en lugar de la regla general de intervención mediante presencia telemática, conforme al art. 258 bis.2, párrafos segundo y tercero, LECRIM, conforme a la redacción dada por RDL 6/2023, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

(En juicio por delito leve)

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en el procedimiento [ELEGIR: abreviado / por delito leve] número [NÚMERO] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERA.- Que en fecha [FECHA] se ha señalado el juicio oral en el procedimiento antes indicado.

SEGUNDA.- Que por medio del presente escrito intereso que la comparecencia en sede judicial del/de la acusado/a [COMPLETAR] se haga presencialmente, así como que declare en último lugar en atención al criterio de la Sentencia del Tribunal Supremo 714/2023, de 28 de septiembre, que así lo permite.

FUNDAMENTOS JURÍDICOS

ÚNICO.-

Señala el art. 258 bis.1 y 2 LECRIM que:

"1. Constituido el órgano judicial en su sede, los actos de juicio, vistas, audiencias, comparecencias, declaraciones y, en general, todas las actuaciones procesales, se realizarán preferentemente, salvo que el juez o jueza o tribunal, en atención a las circunstancias, disponga otra cosa, mediante presencia telemática, siempre que las oficinas judiciales o fiscales tengan a su disposición los medios técnicos necesarios para ello, con las especialidades previstas en los artículos 325, 731 bis y 306 de la Ley de Enjuiciamiento Criminal, de conformidad con lo dispuesto en el apartado 3 del artículo 229 y artículo 230 de la Ley Orgánica del Poder Judicial, y supletoriamente por lo dispuesto en la el artículo 137 bis de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil. La intervención mediante presencia telemática se practicará siempre a través de punto de acceso seguro, de conformidad con la normativa que regule el uso de la tecnología en la Administración de Justicia."

[COMPLETAR]

"En los juicios por delito menos grave, cuando lapena exceda de dos años de prisión o, si fuera de distinta naturaleza, cuando su duración no exceda de seis años, el acusadocomparecerá físicamenteante la sede del órgano de enjuiciamientosi así lo solicita este o su letrado, o si el órgano judicial lo estima necesario. La decisión deberá adoptarse en auto motivado."

"En el resto de juicios, cuando el acusado comparezca, lo haráfísicamenteante la sede del órgano de enjuiciamientosi así lo solicita él o su letrado, o si el órgano judicial lo estima necesario. La decisión deberá adoptarse en auto motivado."

En el caso presente el párrafo [ELEGIR: 2º / 3º] del apartado 2 del art. 258 bis LECRIM exige expresa petición del/de la letrado/a del/de la acusado/a, puesto que la regla general es la comparecencia por vía telemática, pero se interesa expresamente, como exige la norma, la comparecencia física en el juicio oral y declarando en último lugar en la práctica de la prueba.

Por ello, se interesa que la declaración de [COMPLETAR] como acusado/a se lleve a cabo de forma presencial, puesto que el delito conlleva una pena de [PENA] y en último lugar en la práctica de la prueba, conforme a la Sentencia del Tribunal Supremo 714/2023, de 28 de septiembre.

Además, el párrafo 5º del art. 258 bis.2 LECRIM señala que:

"Cuando se disponga la presencia física del investigado o acusado, será también necesaria la presencia física de su defensa letrada. Cuando se permita su declaración telemática, el abogado del investigado o acusado comparecerá junto con este o en la sede del órgano judicial."

Por ello, en este caso comparecerá presencialmente también la dirección técnica del/de la acusado/a.

En consecuencia,

SUPLICO A LA SECCIÓN:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se dicte auto motivado aceptando la declaración presencial del/de la acusado/a junto con su letrado/a el día señalado para el juicio en la sede física del órgano judicial.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 258 bis.2 LECrim no tiene ordinales. Su párrafo segundo regula los juicios por delito menos grave con pena de más de dos años de prisión y el tercero, el resto de juicios. En ambos casos el acusado comparece físicamente si lo pide él o su letrado o si el órgano judicial lo considera necesario, y la decisión se adopta por auto motivado.]

[NOTA DE REVISIÓN: En los juicios por delito grave y en los del Jurado la presencia física del acusado es siempre necesaria (párrafo primero). Si el acusado reside en la demarcación del órgano judicial, la regla también es comparecer físicamente, salvo causa justificada o fuerza mayor (párrafo cuarto). Por eso el escrito solo tiene sentido fuera de esos casos.]
