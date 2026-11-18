---
name: pedir-reapertura-diligencias-previas-archivadas-117
description: "Redacta el escrito «Pedir la reapertura de diligencias previas archivadas» (formulario 117 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la reapertura de diligencias previas archivadas

> Formulario 0117 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] FECHA (3 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] LOCALIDAD (2 veces)
- [ ] LUGAR

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0117 · Pedir la reapertura de diligencias previas archivadas

- Año del modelo: 2023
- Revisión 17-11-2026: 14 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 106) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa de una entidad aseguradora de un vehículo accidentado, solicita la reapertura de las diligencias previas que fueron archivadas, por conocer nuevos hechos que demuestran que el investigado y conductor del citado vehículo, estafó a la aseguradora.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Que en fecha [FECHA] se dictó auto de archivo de estas diligencias previas, habiendo tenido conocimiento esta parte de nuevos elementos fácticos que permiten afirmar la existencia de delito, por lo que, mediante el presente escrito, se solicita la REAPERTURA de las mismas, en base a los siguientes

MOTIVOS

PRIMERO.- Las presentes diligencias se incoaron contra [ACTO O RESOLUCIÓN] por un presunto delito de estafa, habiéndose archivado las diligencias por auto de fecha [FECHA] al entender el Instructor que el accidente de tráfico por el cual el/la investigado/a percibió la indemnización no fue simulado.

En la actualidad, transcurridos dos meses desde el auto de archivo, esta parte ha tenido conocimiento de hechos relevantes que ponen de manifiesto que el/la investigado/a causó los daños de forma dolosa.

En primer lugar, el/la investigado/a, sabedor de que se había archivado el proceso y en la confianza de que ya no podía ser reabierto, comentó con D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], empleado/a de la aseguradora a la que represento, la forma en que ocurrió el accidente, el cual se produjo al salirse de la vía el/la investigado/a con su vehículo, sin que interviniera ningún otro implicado. Asimismo, le refirió que viajaba acompañado en el vehículo por D./Dña. [NOMBRE Y APELLIDOS], persona totalmente desconocida hasta este momento, la cual no constaba en el parte amistoso que simuló con el/la otro/a investigado/a.

En segundo lugar, y como consecuencia de lo anterior, esta parte realizó gestiones para venir en conocimiento del domicilio de este testigo, resultando que tiene su domicilio en [LOCALIDAD].

SEGUNDO.- De acuerdo a los nuevos elementos de prueba que esta parte ha conocido, aparece claramente que el accidente fue simulado con la única finalidad de estafar a mi representada, por lo que se interesa la reapertura de las diligencias, a fin de investigar nuevamente los hechos con los nuevos elementos de prueba conocidos, a cuyo fin esta parte propone que se reciba declaración a D./Dña. [NOMBRE Y APELLIDOS], empleado/a de mi representada, quien comparecerá voluntariamente el día y hora que V.I. señale, y a D./Dña. [NOMBRE Y APELLIDOS], persona que ocupaba el vehículo del/de la investigado/a cuando ocurrió el accidente, quien podrá dar razón de que el accidente se produjo al salirse el vehículo de la vía, sin intervención de terceros, como siempre sostuvo esta parte.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y acuerde la reapertura de las diligencias previas número [Nº DE PROCEDIMIENTO], practicando las diligencias de prueba solicitadas.

Es justicia que pido, en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
