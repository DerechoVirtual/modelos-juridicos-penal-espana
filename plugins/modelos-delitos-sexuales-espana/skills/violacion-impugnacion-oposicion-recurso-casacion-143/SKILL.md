---
name: violacion-impugnacion-oposicion-recurso-casacion-143
description: "Redacta el escrito «Violación: impugnación y oposición al recurso de casación» (formulario 143 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación: impugnación y oposición al recurso de casación

> Formulario 0143 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] FECHA (3 veces)
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en Rollo»; «…stancia. Tal como se observa en el folio»; «…ción de la prueba, en el folio del Rollo»; «…(o en el minuto»; «…, a [FECHA]. Firma Abogado»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 850.1 de la LECrim
- art. 884.5 de la LECrim
- art. 849.1 de la LECrim
- art. 884 de la LECrim
- art. 179 del Código Penal
- art. 882 bis de la LECrim

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

### Formulario 0143 · Violación: impugnación y oposición al recurso de casación

- Año del modelo: 2023
- Revisión 17-11-2026: 11 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Nota explicativa incorporada desde la colección Procesal (formulario 120) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Modelo de escrito a la Sala Segunda del Tribunal Supremo, de la defensa del acusado impugnando el recurso de casación contra sentencia por agresión sexual, por entender que el mismo incurre en alguna de las causas de inadmisión y, subsidiariamente, presenta motivos de oposición al recurso. Solicita la celebración de vista solicitada por el recurrente.

---

A LA SALA SEGUNDA DEL TRIBUNAL SUPREMO

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en nombre y representación de D. [NOMBRE Y APELLIDOS], parte recurrida en el Rollo de recurso de casación núm. [Nº], tal como tengo acreditado en autos, ante la Sala comparezco y como mejor proceda en derecho DIGO:

1) Que en fecha [FECHA] se ha conferido traslado a esta parte del escrito de la recurrente por el que interpone recurso de casación por quebrantamiento de forma e infracción de ley contra la sentencia de fecha [FECHA] dictada por la Audiencia Provincial de [LOCALIDAD] en Rollo [COMPLETAR].

2) Instruida esta parte del recurso, por medio del presente escrito expresa la impugnación a la admisión del recurso y, subsidiariamente, formula oposición al mismo, en base a los siguientes motivos:

IMPUGNACIÓN A LA ADMISIÓN

PRIMERO. En relación al primer motivo por quebrantamiento de forma alegado por el recurrente al amparo del art. 850.1 de la LECrim, alegamos la aplicación de la causa de inadmisión del apartado quinto del art. 884 la LECrim, puesto que la parte recurrente no hizo constar su protesta ante la denegación de la suspensión del juicio, aquietándose a la resolución del Tribunal de instancia.

Tal como se observa en el folio [COMPLETAR] de las actuaciones (acta de juicio oral), la parte recurrente solicitó la suspensión del juicio, puesto que no había comparecido el testigo Sr. al acto de la vista. El Tribunal denegó en principio la suspensión, a la espera del resultado de la prueba practicada.

A la finalización de la prueba, en el folio del Rollo [COMPLETAR] (o en el minuto [COMPLETAR] del acta de grabación) consta que el Tribunal acordó no dar lugar a la suspensión por considerarse suficientemente ilustrado sobre los hechos, entendiendo innecesaria la prueba, sin que la parte recurrente hiciera manifestación alguna.

Por tanto, no se cumple el preceptivo requisito de la protesta exigido en el art. 884.5 de la LECrim y reiterado por la jurisprudencia de la Sala en numerosas sentencias, tales como las SSTS 18 de noviembre de 1992, 28 de enero de 1994 y 11 febrero 2009, entre otras muchas.

SEGUNDO. En relación al segundo motivo por infracción de ley al amparo del art. 849.1 de la LECrim, la exposición de la recurrente pone de manifiesto claramente que no respeta el relato de hechos probados establecido en la sentencia, por lo que alegamos la aplicación de la causa de inadmisibilidad del apartado tercero del art. 884 de la LECrim.

Así, claramente se infiere del relato fáctico que el agresor «intentó penetrar vaginalmente a la víctima, no pudiendo lograrlo por la resistencia ofrecida por ésta».

Frente a la contundente afirmación del relato de hechos probados, no puede invocarse la infracción del art. 179 del Código Penal, puesto que la pretensión del recurrente, de aplicar el tipo de agresión sexual en lugar del de violación en grado de tentativa, sólo se sostiene en una versión fáctica que facilita en su escrito de recurso, totalmente irreverente con el relato de hechos probados, que afirmaba la tentativa del agresor de penetrar vaginalmente a la víctima.

Concurre, por tanto, la causa de inadmisibilidad del art. 884.3º de la LECrim.

MOTIVOS DE OPOSICIÓN

Para el caso de admitirse el recurso, esta parte formula los siguientes motivos de oposición:

PRIMERO. En relación al motivo de quebrantamiento de forma, debe significarse que la prueba testifical que se pretende hacer valer por la recurrente carece de virtualidad alguna para modificar el relato de hechos probados, por lo que es totalmente innecesaria por irrelevante.

La jurisprudencia de la Sala distingue entre pertinencia y necesidad de la prueba, de manera que lo necesario se sitúa en un plano superior a lo pertinente.

Por lo que, aún siendo declarada pertinente la prueba, ahora se presenta como innecesaria, pues el testigo propuesto debía ser interrogado sobre la presunta relación sentimental existente entre la víctima y el acusado, lo que es totalmente inocuo al objeto del proceso, puesto que la propia víctima reconoce que tuvo una relación de amistad con el acusado unos meses antes, lo cual en nada afecta al acto delictivo aquí enjuiciado, que se produce una vez ambos habían finalizado toda relación, tal como reconocen el acusado y la víctima.

Por tanto, la innecesariedad de la prueba es manifiesta, por lo que solicitamos la desestimación del motivo.

SEGUNDO. En cuanto a la infracción de ley por aplicación indebida del art. 179 del Código Penal, ha de subrayarse que la jurisprudencia de la Sala ha venido apreciando la tentativa de violación en todos los casos en que se exterioriza de modo patente el ánimo de yacer, como en el caso ahora contemplado, donde el acusado realizó todos los actos tendentes a consumar la violación, arrojando al suelo a la víctima y echándose encima de ella, y si no pudo lograrlo sólo fue por la resistencia opuesta por la víctima y por la presencia providencial de un vecino que hicieron huir al agresor.

La Sala ha reiterado que el desistimiento no se produce cuando viene impuesto por circunstancias ajenas a la libre determinación del sujeto, como indican las SSTS de 14 de marzo de 1990 y 3 de mayo de 1993, como es el caso del acusado que sólo huyó ante la presencia inesperada de un tercero, que fue, junto a la resistencia de la víctima, lo que frustró su acción delictiva.

Solicitamos la desestimación del motivo, al hallarse debidamente aplicado el referido art. 179 del Código Penal.

Por lo expuesto,

SUPLICO A LA SALA que tenga por presentado este escrito con sus copias, se sirva admitirlo y, en su virtud, tenga por impugnada la admisión del recurso de casación por quebrantamiento de forma e infracción de ley contra la sentencia dictada en el Rollo arriba indicado formalizado por la parte recurrente y, para el caso de admisión, tenga por formalizada la oposición al mismo, interesando la confirmación de la sentencia de instancia, con imposición de costas al recurrente.

(Posible solicitud de vista)

OTROSÍ DIGO que al amparo de lo dispuesto en el art. 882 bis de la LECrim solicito la celebración de vista.

Por lo que SUPLICO A LA SALA acuerde de conformidad a la solicitud.

En [LUGAR], a [FECHA].

Firma Abogado [COMPLETAR]

Firma Procurador

================================================================================
