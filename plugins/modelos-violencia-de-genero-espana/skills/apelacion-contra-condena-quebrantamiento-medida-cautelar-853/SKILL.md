---
name: apelacion-contra-condena-quebrantamiento-medida-cautelar-853
description: "Redacta el escrito «Apelación contra la condena por quebrantamiento de medida cautelar de alejamiento» (formulario 853 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por quebrantamiento de medida cautelar de alejamiento

> Formulario 0853 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] FECHA (5 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en el inmueble»; «…del órgano judicial»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 468.2 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 90.3 LOPJ
- art. 847 LECrim
- artículo 849 de la LECrim

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

### Formulario 0853 · Apelación contra la condena por quebrantamiento de medida cautelar de alejamiento

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación contra sentencia condenatoria por delito de quebrantamiento de condena del art. 468.2 CP por haber incumplido una orden de alejamiento, basado en errores en la apreciación de la prueba.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de D. condenado en el juicio oral número por delito de quebrantamiento de condena del art. 468.2 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2), interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (3)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

La estancia de D. [NOMBRE Y APELLIDOS] en el inmueble [COMPLETAR] lo fue solo de forma momentánea para recoger a los niños y no existió dolo alguno de quebrantar la orden, sino de ejecutar una sentencia judicial que le otorgaba el derecho de visitas ese día y al no permitírselo Dña. fue a recogerlos para ejercer un derecho que se le estaba vulnerando. De suyo, el Tribunal Supremo, Sala Segunda, de lo Penal, Sentencia 559/2010, de 9 de Junio, Rec. 2011/2009 recuerda que el dolo es la conciencia y voluntad de infringir el precepto legal que en este supuesto impone una determinada conducta, la de no comunicarse con la protegida ni acercarse a la distancia que se marca en la medida cautelar impuesta, y esa conciencia y voluntad de quebrantar la orden no se daba en este caso al ejecutarse un derecho que tenía reconocido el recurrente en la resolución judicial de fecha [FECHA] del órgano judicial [COMPLETAR].

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado de la condena impuesta.

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada. Al tratarse de un supuesto instruido por un Juez de Violencia sobre la Mujer, el Juez de lo Penal que dictó la resolución será uno especializado, conforme establece el art. 90.3 LOPJ (según redacción dada por LO 1/2025).

(2) Plazo: 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse, de forma ordenada, las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento o que se denegaron indebidamente, si se formuló protesta, y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012 de 25 de enero, rec. 932/2011.

A partir del 6 de diciembre de 2015, fecha de entrada en vigor de la L 41/2015, de 5 de octubre, de reforma de la LECrim., contra las sentencias dictadas por las Audiencias Provinciales en grado de apelación ante las dictadas por las secciones de lo Penal de los Tribuanles de Instancia cabe, según el art. 847 LECrim., recurso de casación por infracción de ley del motivo previsto en el número 1.º del artículo 849 de la LECrim. Son las dictadas por los jueces de lo penal recurridas en apelación y resueltas por la Audiencia "Cuando, dados los hechos que se declaren probados en las resoluciones comprendidas en los dos artículos anteriores, se hubiere infringido un precepto penal de carácter sustantivo u otra norma jurídica del mismo carácter que deba ser observada en la aplicación de ley penal." Ahora bien, el recurrente deberá citar el precepto penal o la norma jurídica infringida, es decir, se trata de un claro error de norma, no una diferente valoración de la prueba.

================================================================================
