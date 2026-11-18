---
name: paso-abreviado-jurado-denegado-tacitamente-queja-159
description: "Redacta el escrito «Paso del abreviado a jurado denegado tácitamente: queja de la acusación particular» (formulario 159 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Paso del abreviado a jurado denegado tácitamente: queja de la acusación particular

> Formulario 0159 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO (2 veces)
- [ ] Nº DE DOCUMENTO
- [ ] FECHA (4 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ra de poder especial otorgado a mi favor»; «…ada, en situación legal de separación de»; «…r los trámites del juicio con Jurado. En»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 309 bis y 760 de la LECrim
- art. 202 del Código Penal
- arts. 309 bis y 760 de la LECrim
- art. 25 de la LO 5/1995

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

### Formulario 0159 · Paso del abreviado a jurado denegado tácitamente: queja de la acusación particular

- Año del modelo: 2023
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 13 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE DOCUMENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 123) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación particular presenta recurso de queja ante la Audiencia Provincial por haber solicitado el cambio de diligencias previas en juicio con Jurado y no haber resuelto el juez de instrucción en plazo, conforme al art. 309 bis y 760 LECRIM. Recuerde que....

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de Dña. [NOMBRE Y APELLIDOS], acusación particular en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante la Sección de Instrucción del Tribunal de Instancia de [SEDE], plaza nº [NÚMERO], según consta en escritura de poder especial otorgado a mi favor [COMPLETAR], mediante

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada.

Comparezco ante este órgano judicial y, como proceda en Derecho, DIGO:

1) Que en fecha [FECHA] esta representación presentó escrito ante el referido órgano judicial en las diligencias previas antes citadas, solicitando la conversión de este procedimiento abreviado en juicio con jurado, sin que se haya dictado resolución alguna, pese a haber transcurrido dos días.
2) Que, mediante el presente escrito, y al amparo de lo dispuesto en el art. 309 bis y 760 de la LECrim, acudo en QUEJA ante la Sala en base a los siguientes

MOTIVOS

PRIMERO. Con fecha [FECHA] se incoaron diligencias previas por denuncia de mi representada, en situación legal de separación de [COMPLETAR] en virtud de sentencia dictada en fecha [FECHA], por haber accedido su ex cónyuge al que fuera domicilio conyugal, y actualmente de mi representada, sin que ésta lo hubiera consentido, valiéndose de un juego de llaves que el investigado poseía con anterioridad a la separación.

SEGUNDO. Personada en autos esta representación, solicitó que se incoara procedimiento ante el Tribunal de Jurado al entender que los hechos tienen su encaje típico en el art. 202 del Código Penal, por rellenar todos los elementos del delito de allanamiento de morada, y al efecto así lo solicitó al Juez en escrito de fecha [FECHA] que no ha sido contestado.

TERCERO. Conforme a los anteriores antecedentes, es indudable que el hecho delictivo objeto de este proceso debe ser enjuiciado por el Tribunal de Jurado, conforme dispone el art. 1.2 de su LO 5/1995, puesto que los hechos encajan en el tipo de allanamiento de morada del art. 202 del Código Penal, y existe una persona determinada responsable de los mismos, el ex cónyuge de mi representada, lo que determina que deba seguirse el proceso por los trámites del juicio de jurado conforme ordenan los arts. 309 bis y 760 de la LECrim y art. 25 de la LO 5/1995, del Tribunal de Jurado.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito de queja y, previos los trámites legales, dicte auto por el cual se acuerde la continuación de las diligencias previas arriba referenciadas por los trámites del juicio con Jurado.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================
