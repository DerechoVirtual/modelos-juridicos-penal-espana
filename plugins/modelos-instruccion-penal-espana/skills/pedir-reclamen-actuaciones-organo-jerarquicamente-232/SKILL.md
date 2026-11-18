---
name: pedir-reclamen-actuaciones-organo-jerarquicamente-232
description: "Redacta el escrito «Pedir que se reclamen las actuaciones al órgano jerárquicamente inferior» (formulario 232 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que se reclamen las actuaciones al órgano jerárquicamente inferior

> Formulario 0232 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] NÚMERO (4 veces)
- [ ] Nº DE DOCUMENTO
- [ ] LOCALIDAD
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] SEDE (3 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] DELITO
- [ ] FECHA
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de la Brigada de Policía Judicial de»; «… siguientes diligencias de investigación»; «…legido Senador por la circunscripción de»; «…con suspensión del curso de la causa. En»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 52 de la LOPJ

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

### Formulario 0232 · Pedir que se reclamen las actuaciones al órgano jerárquicamente inferior

- Año del modelo: 2022
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 20 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO, Nº DE DOCUMENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 136) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa del investigado, que es aforado, solicita al TS que reclame las actuaciones a la Sección de Instrucción del Tribunal de Instancia que está conociendo del asunto, conforme a los arts. 52 y 57.1.2º de la LOPJ.

---

A la Sala Segunda del Tribunal Supremo

D/Dª [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A], según consta en escritura de poder especial otorgado a mi favor, mediante

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada.

Actuando bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [LOCALIDAD] colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y, como mejor en Derecho proceda, DIGO:

Que mediante el presente escrito solicito que se reclame la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza número [NÚMERO] el conocimiento del procedimiento número [Nº DE PROCEDIMIENTO], conforme a lo dispuesto en los art. 52 y 57.1.2º de la LOPJ, en base a los siguientes

MOTIVOS

PRIMERO.- Mi representado está investigado en el procedimiento número [Nº DE PROCEDIMIENTO] seguido ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza número [NÚMERO], por un presunto delito de [DELITO], habiéndose iniciado por atestado de fecha [FECHA] de la Brigada de Policía Judicial de [COMPLETAR], el cual acompaño a este escrito mediante copia como documento número 1, en el cual se han practicado las siguientes diligencias de investigación [COMPLETAR].

SEGUNDO.- Mi representado fue elegido Senador por la circunscripción de [COMPLETAR], hallándose actualmente en el ejercicio de dichas funciones públicas, según acredito mediante certificación de la Cámara que acompaño como documento número 2.

TERCERO.- De conformidad con lo dispuesto en el art. 57.1.2º de la LOPJ, corresponde a la Sala de lo Penal del TS la instrucción y enjuiciamiento de las causas contra los Diputados y Senadores, por lo que, sin perjuicio de la necesidad de otros requisitos procesales que ahora no es necesario exponer, es indudable que procede reclamar las actuaciones al órgano que está conociendo del asunto, ordenándole que se abstenga de todo procedimiento, suspendiendo el curso de la causa, y remitiendo las actuaciones a la Sala a la que me dirijo, conforme establecen los arts. 52 de la LOPJ y 21 de la LECrim.

Por lo expuesto,

SUPLICO A LA SALA

Que tenga por presentado este escrito con los documentos que se acompañan, y en su virtud, y previos los trámites legales, dicte resolución acordando reclamar las actuaciones arriba expresadas a la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza número [NÚMERO], ordenándole que se abstenga de todo procedimiento con suspensión del curso de la causa.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================
