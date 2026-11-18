---
name: abreviado-apelacion-contra-auto-deniega-apertura-juicio-103
description: "Redacta el escrito «Abreviado: apelación contra el auto que deniega la apertura del juicio oral» (formulario 103 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abreviado: apelación contra el auto que deniega la apertura del juicio oral

> Formulario 0103 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] DELITO
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… en su escrito de acusación, imputando a»; «…ar el procedimiento abreviado. SEGUNDO.-»; «…icado. Se dice en el auto que el acusado»; «…nte en la declaración del propio acusado»; «… es que mi representado fue agredido por»; «…nien los siguientes particulares: folios»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766 de la LECrim
- art. 24 de la CE
- art. 783.1 de la LECrim
- art. 766.3 de la LECrim

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

### Formulario 0103 · Abreviado: apelación contra el auto que deniega la apertura del juicio oral

- Año del modelo: 2023
- Revisión 17-11-2026: 16 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 102) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la acusación particular en procedimiento abreviado interponiendo recurso de apelación, conforme al art. 766 LECRIM, contra el auto que deniega la apertura del juicio oral y decreta el sobreseimiento de la causa.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO], seguido ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Que el día [FECHA] se ha notificado a esta representación el auto de fecha [FECHA] denegando la apertura del juicio oral y decretando el sobreseimiento de la causa y, entendiendo dicha resolución no ajustada a derecho y lesiva para mis representados, dicho sea en términos de defensa, por medio del presente escrito, al amparo de lo dispuesto en el art. 766 de la LECrim y preceptos concordantes INTERPONGO RECURSO DE APELACIÓN, en base a los siguientes

MOTIVOS

PRIMERO.- INFRACCIÓN DEL ART. 24 DE LA CE EN RELACIÓN CON EL ART. 783.1 DE LA LECRIM

El auto de sobreseimiento libre dictado por el Instructor, dicho sea con el debido respeto y con ánimo de defensa, supone una verdadera subrogación de las facultades del órgano de enjuiciamiento, puesto que el Instructor ha realizado un juicio de certeza sobre los hechos, impropio de este momento procesal.

Tanto el TC (SSTC 186/90, 21/93, 62/98, entre otras) como el TS (SSTS 28 junio 1999 y 17 diciembre 2008) indican que el control del juicio oral es un control de garantía, es decir, un juicio sobre la consistencia y solidez de la acusación, de tal manera que la decisión judicial, asentada en valoraciones propias del plenario, excede de la permitida por la Ley en este momento procesal, para entrar de lleno en el ámbito de las facultades del órgano de enjuiciamiento, al cual se ha suplantado sin dar oportunidad a esta parte de practicar prueba de cargo, provocándole una situación de manifiesta indefensión.

Además, el escrito de acusación presentado por esta parte presenta sólidos indicios y está fundado en las diligencias instructoras practicadas. El propio Instructor, en el auto de incoación de procedimiento abreviado, delimitó el proceso en la forma que después ha sostenido esta parte en su escrito de acusación, imputando a [COMPLETAR] un delito de [DELITO], por lo que la resolución ahora recurrida es contradictoria con la resolución dictada por el propio Juez de Instrucción al finalizar la fase de diligencias previas, en tanto que el escrito de acusación comprende los mismos hechos y se dirige contra los mismos sujetos que se delimitaron en la citada resolución judicial.

Se infringe el art. 24 de la CE, puesto que se coloca a esta representación en una situación de indefensión, y produciéndose un evidente déficit de motivación, al dictarse una resolución como la ahora recurrida, de cierre del proceso y negando los indicios que el propio Juez había apreciado anteriormente, lo que exigía una motivación razonable que permitiera comprender este cambio de criterio, contrario a los propios actos, lo cual no se ha producido en ningún momento en la resolución recurrida.

Por último, se infringe el art. 783.1 de la LECrim, porque se prescinde del carácter general de la apertura del juicio oral cuando media petición de parte, y se prescinde del carácter excepcional del sobreseimiento, yendo más allá del juicio de probabilidad que le es dado hacer al Instructor, para entrar en un juicio de certeza, prescindiendo de los indicios que llevaron al propio Juez a incoar el procedimiento abreviado.

SEGUNDO.- [COMPLETAR]

De acuerdo con los motivos de infracción expuestos anteriormente, se observa que el Instructor se ha excedido en las funciones que marca la doctrina jurisprudencial, puesto que en su auto afirma sin ambages que concurre la eximente de legítima de defensa, prescindiendo de la declaración del perjudicado. Se dice en el auto que el acusado [COMPLETAR] respondió a la agresión con la navaja realizada por mi representado [NOMBRE DEL REPRESENTADO/A], cuando esta afirmación se basa únicamente en la declaración del propio acusado [COMPLETAR], puesto que mi representado siempre ha sostenido que en ningún momento exhibió ni mostró la navaja, si bien reconoce que la portaba en el bolsillo (declaración ante la Policía, folio 8, y declaración ante el Juez, folio 23); por este motivo, no puede afirmarse que exista una agresión ilegítima por mi representado, puesto que las versiones sobre este extremo son contradictorias, el acusado no presentaba ni el más mínimo rasguño (folio 15, parte asistencia hospitalaria) y lo único que ha quedado claro en la fase de instrucción es que mi representado fue agredido por [COMPLETAR] con un instrumento punzante, que le ocasionó graves lesiones, indicios suficientes para abrir el juicio oral, conforme interesó esta parte en su escrito de acusación.

Aplicar en este momento la eximente de legítima defensa, supone enjuiciar los hechos, afirmando que hubo agresión ilegítima, falta de provocación del agresor y proporcionalidad de medios, elementos éstos que únicamente pueden afirmarse tras la práctica de la prueba en el plenario, y no por meras manifestaciones del acusado, realizadas en fase de instrucción y no corroboradas por elemento alguno.

Por lo expuesto, es de justicia y

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, por interpuesto RECURSO DE APELACIÓN contra el auto de fecha [FECHA], denegatorio de la apertura del juicio oral y de sobreseimiento del proceso, remitiendo las actuaciones a la Ilma. Audiencia Provincial de [LOCALIDAD], suplicando a la Sala se revoque la citada resolución, acordando la apertura del juicio oral y demás pronunciamientos inherentes solicitados en el escrito de acusación formulado por esta representación.

Es Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO que de conformidad con lo dispuesto en el art. 766.3 de la LECrim intereso que se testimonien los siguientes particulares: folios [COMPLETAR]

SUPLICO ALA SECCIÓN que tenga por designados los particulares y sean remitidos a la Audiencia para la resolución del recurso de apelación interpuesto.

Es Justicia que reitero en lugar y fecha "ut supra"

Firma de Abogado/a	Firma de Procurador/a

================================================================================
