---
name: negativa-pruebas-alcoholemia-defensa-pide-proceso-799
description: "Redacta el escrito «Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto» (formulario 799 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto

> Formulario 0799 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- No se pudo verificar con el conector la redacción vigente del proceso por aceptación de decreto (arts. 803 bis a) y siguientes LECrim).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 383 CP
- art. 803 bis a) LECRIM
- art. 803 bis a) de la Ley de Enjuiciamiento Criminal
- art. 801 LECrim
- artículo 80 del Código Penal
- art. 803 bis c) LECrim
- art. 803 bis f) LECrim

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

### Formulario 0799 · Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto

- Año del modelo: 2016
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (1); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: No se pudo verificar con el conector la redacción vigente del proceso por aceptación de decreto (arts. 803 bis a) y siguientes LECrim).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en procedimiento abreviado por delito de negativa a someterse a las pruebas de alcoholemia del art. 383 CP solicita que se acuda a la vía del proceso por aceptación de decreto del art. 803 bis a) LECRIM, para evitar así el acusado la aplicación de la pena de prisión y su régimen de suspensión de ejecución de pena, pasando por una pena de multa o TBC, que no está prevista como alternativa para este delito.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD],, en representación del acusado/a, D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento / por el supuesto delito del art. 383 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, teniendo conocimiento de la incoación de unas diligencias previas nº [Nº DE PROCEDIMIENTO] y por la vía del art. 803 bis a) de la Ley de Enjuiciamiento Criminal, solicito la tramitación del proceso por aceptación de decreto, interesando se dé traslado al Ministerio Fiscal de la presente al no haberse tramitado las diligencias como urgentes y no haber podido verificar la conformidad privilegiada de rebaja de un tercio de la pena que prevé el art. 801 LECrim. (1)

Concurren los presupuestos del art. 803 bis a) LECrim, dado que el delito [NOTA DE REVISIÓN (sin verificar en el BOE): No se pudo obtener con el conector la redacción vigente de los arts. 803 bis a) a 803 bis j) LECrim (proceso por aceptación de decreto) para confirmar requisitos y remisiones. Fuente: Ley de Enjuiciamiento Criminal, BOE-A-1882-6036, art. 803 bis a).] que es objeto de investigación es el art. 383 CP y por ello:

1.º Que el delito esté castigado con pena de multa o de trabajos en beneficio de la comunidad o con pena de prisión que no exceda de un año y que pueda ser suspendida de conformidad con lo dispuesto en el artículo 80 del Código Penal, con o sin privación del derecho a conducir vehículos a motor y ciclomotores.
2.º Que el Ministerio Fiscal entienda que la pena en concreto aplicable es la pena de multa o trabajos en beneficio de la comunidad y, en su caso, la pena de privación del derecho a conducir vehículos a motor y ciclomotores.
3.º Que no esté personada acusación popular o particular en la causa.

En este sentido, la defensa solicita se dé traslado del presente escrito a la Fiscalía para que sea esta la que inste el proceso por aceptación de decreto del art. 803 bis a) LECrim, en base a lo dispuesto y con el contenido del art. 803 bis c) LECrim.

Al estar sancionado el delito del art. 383 CP con pena de prisión de seis meses a un año es viable que se aplique esta vía y que la pena interesada por la fiscalía sea la de multa de tres meses a razón de 4 euros por día, dada la ausencia de actividad laboral del acusado o de trabajos en beneficio de la comunidad de 31 días y en cualquier caso la privación del permiso de conducir por tiempo de un año y un día al posibilitarlo el art. 803 bis a) 2ª LECrim.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite y por interesado el traslado a la fiscalía en los términos interesados, a fin de que se dicte auto por este órgano judicial y se me cite a la comparecencia prevista en el art. 803 bis f) LECrim, a fin de aceptar la propuesta contenida en el decreto.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de acusado/a

NOTAS DEL FORMULARIO

(1) La ventaja de este sistema es que se evita el acusado la aplicación de la pena de prisión y su régimen de suspensión de ejecución de pena, pasando por una pena de multa o TBC que no está prevista como alternativa en el art. 383 CP y puede utilizarse esta vía del proceso por aceptación de decreto previsto a instancia de la fiscalía para hechos no graves y que reúnan las características del art. 803 bis a) LECrim.

Puede utilizarse para cuando este órgano judicial no haya tramitado las diligencias como urgentes y el abogado del acusado no quiera acudir a la conformidad en procedimiento abreviado, ya que ello no lleva rebaja penal.

================================================================================
