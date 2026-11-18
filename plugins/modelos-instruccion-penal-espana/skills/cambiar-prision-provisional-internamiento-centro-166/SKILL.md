---
name: cambiar-prision-provisional-internamiento-centro-166
description: "Redacta el escrito «Cambiar la prisión provisional por internamiento en centro de deshabituación» (formulario 166 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cambiar la prisión provisional por internamiento en centro de deshabituación

> Formulario 0166 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… esa fecha en el Centro Penitenciario de»; «… base a los siguientes MOTIVOS PRIMERO.-»; «…sistencia hospitalaria obrantes en folio»; «…el director del centro de deshabituación»; «…ometerse a tratamiento, obrante en folio»; «…do en un centro especializado. SEGUNDO.-»; «…contactó con el centro de deshabituación»; «…rnamiento en el centro de deshabituación»; «…, a [FECHA]. Conforme:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 505, 528 y 539 de la LECrim
- art. 508 de la LECrim

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

### Formulario 0166 · Cambiar la prisión provisional por internamiento en centro de deshabituación

- Año del modelo: 2022
- Revisión 17-11-2026: 17 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Abogado/a, actuando en representación y defensa de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Por auto de fecha [FECHA] fue dictado auto de prisión provisional sin fianza contra mi defendido/a D./Dña. [NOMBRE Y APELLIDOS], que se halla ingresado/a desde esa fecha en el Centro Penitenciario de [COMPLETAR], por lo que, al amparo de lo dispuesto en los art. 505, 528 y 539 de la LECrim., en relación con lo establecido en el art. 508 de la LECrim., por medio del presente escrito, solicito la modificación de la situación de prisión de mi defendido/a y su sustitución por la medida de internamiento en un centro de deshabituación, en base a los siguientes

MOTIVOS

PRIMERO.- [COMPLETAR]

En fecha [FECHA] mi defendido/a ingresó en prisión por la comisión de un presunto delito de [DELITO], habiéndose practicado diferentes diligencias en la fase de instrucción, de las que se desprende que mi defendido/a está afecto a una adicción de más de años a que le ha provocado, asimismo, diferentes enfermedades asociadas.

Así se desprende claramente de los partes de asistencia hospitalaria obrantes en folio [COMPLETAR] de las actuaciones, del informe del médico forense y del informe del director del centro de deshabituación [COMPLETAR] donde ha ingresado varias veces para someterse a tratamiento, obrante en folio [COMPLETAR] y aportado por esta parte como prueba documental.

En este último informe, se hace constar que el ingreso en prisión puede tener efectos negativos en la evolución de la enfermedad de mi defendido/a, por cuanto puede suponer un total abandono del tratamiento de deshabituación, afirmándose la necesidad de que ingrese en un centro adecuado al tratamiento de su adicción. El propio médico forense hace referencia a la conveniencia del tratamiento médico en su informe, entendiendo que debe ser tratado en un centro especializado.

SEGUNDO.- [COMPLETAR]

Como consecuencia de lo anterior, esta parte realizó las correspondientes gestiones para procurar un centro adecuado para el tratamiento de mi defendido/a, a cuyo efecto contactó con el centro de deshabituación [COMPLETAR], donde ya había sido tratado, que ha aceptado la admisión, si S.S.ª lo estima oportuno, y ha elaborado un plan de tratamiento que se seguirá en régimen cerrado, con arreglo a las pautas terapéuticas que se recogen en el documento que se acompaña a este escrito (acompaño como documento número 1 certificado emitido por el Director del Centro acreditativo de la admisión de mi defendido y del plan de tratamiento de deshabituación).

Por lo anterior, y al amparo de los preceptos antes citados, esta parte solicita a V.I. acuerde la sustitución de la medida de prisión por la de internamiento en el centro de deshabituación [COMPLETAR], entendiendo que favorece especialmente la reinserción de mi defendido/a, quien de esta manera podrá seguir un tratamiento adecuado a su adicción, y no menoscaba la finalidad cautelar de la medida, en tanto que el tratamiento se sigue en régimen cerrado, estando el/la investigado/a a disposición del juez, en todo momento.

Por último, esta parte debe poner de manifiesto la expresa voluntad de mi defendido/a de someterse al tratamiento de deshabituación, a cuyo efecto firma conmigo este escrito.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, acuerde reformar el auto de prisión provisional de fecha [FECHA], dictando otro por el que se acuerde medida cautelar de internamiento del/de la investigado/a en el Centro de Deshabituación.

Es justicia que pido, en [LUGAR], a [FECHA].

Conforme: [COMPLETAR]

Firma de investigado/a	Firma de Abogado/a

================================================================================
