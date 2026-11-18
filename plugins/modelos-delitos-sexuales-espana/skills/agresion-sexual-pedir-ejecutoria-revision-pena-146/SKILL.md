---
name: agresion-sexual-pedir-ejecutoria-revision-pena-146
description: "Redacta el escrito «Agresión sexual: pedir en ejecutoria la revisión de la pena» (formulario 146 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual: pedir en ejecutoria la revisión de la pena

> Formulario 0146 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- La LO 4/2023 (BOE-A-2023-10213) restableció desde el 29-4-2023 penas más altas: violación con violencia, intimidación o voluntad anulada, de seis a doce años (art. 179.2 CP). La rebaja a cuatro años solo cabe aplicando la LO 10/2022 como ley intermedia más favorable a hechos anteriores (art. 2.2 CP; DT 1.ª y 2.ª LO 4/2023).
- La STS 930/2022 citada aplica la numeración de la LO 10/2022 (arts. 181.3 y 181.4 a); tras la LO 4/2023 el acceso carnal con menor de 16 años está en el art. 181.4 CP (de ocho a doce años) y las agravantes en el art. 181.5.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…A la sección»; «…, procedente del Rollo»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 179 del Código Penal
- art. 179 del CP
- art. 2.2 del Código Penal
- art. 181.3 CP
- art. 181.4 a) CP
- art. 179 CP
- Ley Orgánica 10/2022

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

### Formulario 0146 · Agresión sexual: pedir en ejecutoria la revisión de la pena

- Año del modelo: 2023
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; 1 llamadas a nota sin texto retiradas; 11 campos de relleno marcados en blanco
- Avisos de la revisión: La LO 4/2023 (BOE-A-2023-10213) restableció desde el 29-4-2023 penas más altas: violación con violencia, intimidación o voluntad anulada, de seis a doce años (art. 179.2 CP). La rebaja a cuatro años solo cabe aplicando la LO 10/2022 como ley intermedia más favorable a hechos anteriores (art. 2.2 CP; DT 1.ª y 2.ª LO 4/2023). · La STS 930/2022 citada aplica la numeración de la LO 10/2022 (arts. 181.3 y 181.4 a); tras la LO 4/2023 el acceso carnal con menor de 16 años está en el art. 181.4 CP (de ocho a doce años) y las agravantes en el art. 181.5.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la sección [COMPLETAR] de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña [NOMBRE Y APELLIDOS], según consta acreditado en la Ejecutoria número [Nº DE PROCEDIMIENTO], procedente del Rollo [COMPLETAR], seguida ante el Tribunal al que me dirijo, comparezco y como proceda en Derecho

DIGO:

PRIMERO.- Que en fecha [FECHA] se dictó Sentencia en este proceso por el cual se condenaba a mi representado/a D./Dª. [NOMBRE Y APELLIDOS], como autor/a de un delito de agresión sexual del art. 179 del Código Penal a la pena de [Nº] años de prisión.

Con fecha [FECHA] se dictó auto declarando la firmeza de la sentencia, cuya pena está cumpliendo en la actualidad.

SEGUNDO.- Que desde el día mi representado/a está cumpliendo la pena impuesta.

TERCERO.- Que el día 7 de octubre de 2022 entró en vigor la Ley Orgánica 10/2022, de 6 de septiembre, de garantía integral de la libertad sexual, que minora la pena contemplada para el delito de agresión sexual del art. 179 del CP, por el que fue condenado mi representado/a, por lo que, de conformidad a lo dispuesto en el art. 2.2 del Código Penal, solicito la REVISIÓN de la pena impuesta en la expresada Sentencia, con arreglo a los siguientes

FUNDAMENTOS JURÍDICOS

ÚNICO.-

Por medio del presente escrito se solicita la revisión de la pena impuesta a mi representado/a en la Sentencia expresada, de conformidad a lo dispuesto en el art. 2.2 del Código Penal, por aplicación de la norma penal más favorable.

Es cierto que la Ley orgánica 10/2022 de 6 de septiembre no contiene disposición transitoria alguna que delimite la posibilidad de revisión de pena, pero es principio general la revisión de la misma en el caso de reformas legales que beneficien al reo, y que se pueden aplicar en varios casos:

1.- Al acusado pendiente de juicio.
2.- Al condenado pendiente de resolver recurso de apelación.
3.- Al condenado pendiente de resolver recurso de casación.
4.- Al condenado con sentencia firme cumpliendo pena.

La STS 930/2022 de 30 de noviembre, Rec. 2811/2020 aplicó la pena de 9 años de prisión en un caso en el que la pena a imponer era de 10 a 12 años de prisión, al ser ahora la penalidad de 6 a 12 años de prisión [NOTA DE REVISIÓN: Marco de la LO 10/2022 (antiguo art. 181.3). La LO 4/2023 renumeró el art. 181: el acceso carnal con menor de 16 años está en el art. 181.4 (ocho a doce años; doce a quince en los casos del 181.2) para hechos desde el 29-4-2023. Fuente: Código Penal, BOE-A-1995-25444, art. 181 (redacción LO 4/2023, BOE-A-2023-10213).], y debiendo aplicar la mínima en su mitad superior, ahora la mínima ya no es de 10 años de prisión, sino de 9 años.

En este caso concreto, el TS señaló que los hechos se incluían en: "el art. 183.1, 3 y 4 b) CP, que si bien es cierto que antes de la reforma reciente del CP fijaba la pena en el arco entre los 10 y 12 años de prisión es preciso, en beneficio del reo, aplicar la ley penal más favorable, a raíz de la LO 10/2022 de 6 de septiembre que ahora sitúa el arco de base entre los 6 y los 12 años de prisión en estos casos ( art. 181.3 CP) en relación con el art. 181.4 a) CP en su mitad superior, lo que lleva a la pena de entre 9 años y un día y 12 años de prisión frente a los 10 años y un día a 12 años de la regulación anterior."

En el caso de mi representado/a, se le condenó por un delito de agresión sexual con acceso carnal del art. 179 del CP, con imposición de la pena mínima de 6 años y el tribunal argumentó la pena mínima en lo siguiente:

Pero la Ley Orgánica 10/2022 ha modificado la pena del citado delito de agresión sexual tipificado en el art. 179 del CP, de manera que la pena en abstracto pasa de 6 a 12 años de prisión, a la vigente de 4 a 12 años de prisión [NOTA DE REVISIÓN: Desde el 29-4-2023 la LO 4/2023 castiga con seis a doce años la violación con violencia, intimidación o voluntad anulada (art. 179.2 CP). El marco de cuatro a doce años de la LO 10/2022 (hoy art. 179.1) solo opera como ley intermedia más favorable para hechos anteriores a esa fecha. Fuente: LO 4/2023, BOE-A-2023-10213, art. único.cuatro y DT 1.ª; Código Penal, BOE-A-1995-25444, arts. 2.2 y 179.], lo que supone que su límite mínimo pasa de ser de 6 años a ser de 4 años.

Es por ello, por lo que se interesa la revisión de pena y que se reduzca a los 4 años de prisión como "nueva pena mínima" aplicable al delito del art. 179 CP.

Por todo ello;

SUPLICO A LA SALA:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y tenga por solicitada la revisión de la pena impuesta a mi representado/a por la Sentencia firme dictada en este proceso y, tras los trámites correspondientes, acuerde sustituir la pena de 6 años de prisión impuesta en este proceso, por la de 4 años de prisión, por aplicación retroactiva de la ley penal más favorable.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
