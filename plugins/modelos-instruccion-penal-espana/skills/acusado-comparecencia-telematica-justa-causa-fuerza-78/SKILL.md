---
name: acusado-comparecencia-telematica-justa-causa-fuerza-78
description: "Redacta el escrito «Acusado: comparecencia telemática por justa causa o fuerza mayor (desde el 20 de marzo de 2024)» (formulario 78 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acusado: comparecencia telemática por justa causa o fuerza mayor (desde el 20 de marzo de 2024)

> Formulario 0078 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- La excepción por causa justificada o fuerza mayor (art. 258 bis.2, párrafo cuarto, LECrim) no se aplica a los juicios por delito grave ni a los del Jurado, en los que la presencia física del acusado es siempre necesaria (párrafo primero).
- Si se autoriza la comparecencia telemática, el abogado debe estar junto al acusado o en la sede del órgano judicial. El acusado que decida no comparecer en la sede debe comunicarlo con al menos cinco días de antelación (art. 258 bis.2, párrafos quinto y sexto).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…cia en sede judicial del/de la acusado/a»; «…as o de fuerza mayor son las siguientes:»; «… ello, se interesa que la declaración de»; «… órgano judicial, deberá notificarlo con»; «…nga por interesado que la declaración de»

## Elecciones que hay que hacer

- abreviado / por delito leve

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

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

### Formulario 0078 · Acusado: comparecencia telemática por justa causa o fuerza mayor (desde el 20 de marzo de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 10 campos de relleno marcados en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 81) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el letrado del acusado que vive en la demarcación del órgano judicial competente solicita comparecer a juicio en procedimiento abreviado o por delito leve por vía telemática, en lugar de presencialmente, que es la regla general, por una causa justificada o de fuerza mayor, conforme al art. 258 bis 2 LECRIM, vigente desde el 20 de marzo de 2024.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en Procedimiento [ELEGIR: abreviado / por delito leve] número [NÚMERO] en causa seguida ante el órgano judicial al que me dirijo, comparezco y como proceda en Derecho, presento las siguientes

ALEGACIONES

PRIMERO.- Que en fecha [FECHA] se ha señalado el juicio oral en el procedimiento antes indicado.

SEGUNDO.- Que intereso que la comparecencia en sede judicial del/de la acusado/a [COMPLETAR] se haga por vía telemática, a pesar de residir en la misma demarcación que el órgano judicial que conoce de la causa, por existir causas justificadas o de fuerza mayor, así como que declare en último lugar en atención al criterio de la Sentencia del Tribunal Supremo 714/2023, de 28 de septiembre que así lo permite.

FUNDAMENTOS JURÍDICOS

PRIMERO.- Señala el art. 258 bis.2, pfo. 4º LECRIM que:

"En todo caso, en los procesos y juicios, cuando el acusado resida en la misma demarcación del órgano judicial que conozca o deba conocer de la causa, su comparecencia en juicio deberá realizarse de manera física en la sede del órgano judicial o enjuiciamiento, salvo que concurran causas justificadas o de fuerza mayor."

Así, la regla general es la comparecencia a juicio por vía telemática, pero este párrafo 4º establece la excepción de la presencia física, salvo expresa petición de la defensa del acusado si se interesa expresamente, como exige la norma, y se justifican las razones de la comparecencia telemática.

En el presente caso las razones justificadas o de fuerza mayor son las siguientes: [COMPLETAR].

Por ello, se interesa que la declaración de [COMPLETAR] como acusado/a se lleve a cabo por videoconferencia y se nos designe el punto seguro donde asistir para ello.

Se cumple así con lo dispuesto en el párrafo 6º del art. 258 bis.2 LECRIM de que cuando el acusado decida no comparecer en la sede del órgano judicial, deberá notificarlo con [COMPLETAR], al menos, cinco días de antelación.

Además, el párrafo 5º del art. 258 bis.2 LECRIM señala que:

"Cuando se disponga la presencia física del investigado o acusado, será también necesaria la presencia física de su defensa letrada. Cuando se permita su declaración telemática, el abogado del investigado o acusado comparecerá junto con este o en la sede del órgano judicial."

Por ello, en este caso comparecerá presencialmente en el juicio la dirección técnica del/de la acusado/a.

SEGUNDO.- Solicitamos, además, que declare en último lugar en la práctica de la prueba conforme al criterio establecido por la STS 714/2023, de 28 de septiembre que así lo permite.

Por todo ello

SUPLICO A LA SECCIÓN:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que la declaración de [COMPLETAR] como acusado/a se lleve a cabo por videoconferencia el día señalado para el juicio y se dicte auto motivado aceptándolo, así como que se nos designe el punto seguro donde asistir para dicha videoconferencia.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: La excepción por causa justificada o fuerza mayor (art. 258 bis.2, párrafo cuarto, LECrim) no se aplica a los juicios por delito grave ni a los del Jurado, en los que la presencia física del acusado es siempre necesaria (párrafo primero).]

[NOTA DE REVISIÓN: Si se autoriza la comparecencia telemática, el abogado debe estar junto al acusado o en la sede del órgano judicial. El acusado que decida no comparecer en la sede debe comunicarlo con al menos cinco días de antelación (art. 258 bis.2, párrafos quinto y sexto).]
