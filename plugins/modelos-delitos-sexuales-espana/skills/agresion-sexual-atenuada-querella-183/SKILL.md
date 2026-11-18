---
name: agresion-sexual-atenuada-querella-183
description: "Redacta el escrito «Agresión sexual atenuada: querella» (formulario 183 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual atenuada: querella

> Formulario 0183 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] IMPORTE

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del querellado sobre los hechos de la querella.…
- .- Testifical:…
- -D./Dña. [NOMBRE Y APELLIDOS] amiga de la víctima que estuvo con ella en la cafetería…
- -D./Dña. [NOMBRE Y APELLIDOS] empleado de la cafetería que auxilió a la víctima.…
- .- Pericial siguiente:…
- .- Documental: teniendo por reproducidos los documentos que se acompañan a la querella.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 681.3 LECRIM
- art. 544 bis LECRIM
- art. 281 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0183 · Agresión sexual atenuada: querella

- Año del modelo: 2022
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 3 llamadas a nota sin texto retiradas; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 17 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº DE COLEGIADO)
- Avisos de la revisión: Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, por un delito de agresión sexual del art 178.1 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- La querellante es Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El querellado es D. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

Con fecha [FECHA] mi mandante fue con unas amigas a una cafetería y en un momento dado se acercó al cuarto de baño. Cuando se disponía a entrar salió del de caballeros el querellado, que se acercó a ella y le empezó a manosear por todo el cuerpo, incluidas partes sexuales, ante lo que comenzó a gritar y llegaron dos empleados que lo pararon e identificaron.

QUINTO.- Los hechos expuestos, sin perjuicio de una mejor calificación jurídica posterior, revisten los caracteres de un delito de agresión sexual que define el artículo 178. 1 del Código penal.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del querellado sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical:

Declaración de los/as testigos que se mencionan y que deberán ser citados/as:

- Declaración de la víctima D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS] amiga de la víctima que estuvo con ella en la cafetería

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS] empleado de la cafetería que auxilió a la víctima.

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

- D./Dña. [NOMBRE Y APELLIDOS] perito psicólogo para que declare sobre la afectación psicológica de la víctima por los hechos ocurridos.

[OPCIONAL — incluir si procede]

.- Documental: teniendo por reproducidos los documentos que se acompañan a la querella.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita y se practiquen las diligencias interesadas.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa que se tomen las pertinentes medidas cautelares sobre la situación personal del querellado, disponiendo se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, según redacción dada por LO 10/2022, de garantía integral de la libertad sexual, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares.

Del mismo modo, y para el supuesto de que pudiera adoptarse la decisión judicial de libertad provisional y en base a lo dispuesto en el art. 544 bis LECRIM, según redacción dada por LO 10/2022 [NOTA DE REVISIÓN: El art. 544 bis LECrim tiene hoy la redacción de la LO 1/2026 (vigente desde el 10-4-2026), que mantiene en su último párrafo los dispositivos telemáticos para los delitos del art. 3 LO 10/2022 y añade la finalidad de evitar la reiteración delictiva. Fuente: LO 1/2026, BOE-A-2026-7966, art. primero.tres (art. 544 bis LECrim).], de garantía integral de la libertad sexual, se interesa se acuerde mediante resolución motivada la utilización de dispositivos telemáticos para el control de su cumplimiento.

Que en el caso de quedar en libertad y en base al art. 544 bis LECRIM se acuerde la orden de alejamiento.

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las medidas anteriores.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
