---
name: decomiso-autonomo-apelacion-tercero-contra-sentencia-755
description: "Redacta el escrito «Decomiso autónomo: apelación del tercero contra la sentencia condenatoria» (formulario 755 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Decomiso autónomo: apelación del tercero contra la sentencia condenatoria

> Formulario 0755 del plugin **Ejecución penal** · revisado el 17-11-2026.

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
- [ ] NÚMERO (2 veces)
- [ ] DELITO
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…-»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- - [COMPLETAR]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 790.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0755 · Decomiso autónomo: apelación del tercero contra la sentencia condenatoria

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 párrafos repetibles señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso que presenta un tercero que ostenta la titularidad de los bienes objeto de decomiso contra la sentencia que condena a dicho decomiso en procedimiento de decomiso autónomo, conforme al art. 803 ter r de la LECrim. El presente recurso sigue los trámites previstos para el recurso de apelación de sentencia dictada en procedimiento abreviado.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], tercero afectado por el decomiso en el proceso de decomiso autónomo número [NÚMERO] contra D./Dña. [NOMBRE Y APELLIDOS] por delito de [DELITO] ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] he sido notificado/a de la sentencia recaída en fecha [FECHA], en procedimiento de decomiso autónomo (1) y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme prevé el art. 803 ter r de la LECRIM (2), siguiendo los trámites del artículo 790 de la Ley de Enjuiciamiento Criminal y ss, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

No se ha valorado debidamente la documentación aportada con respecto a la titularidad de los bienes objeto de decomiso que se exponen y que entendemos que se acredita con los siguientes documentos que se citan, aportados a la causa en escrito de personación:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR]

Ello provoca la ajenidad de la relación entre mi representado/a y los hechos que se investigan en el juicio oral nº [NÚMERO] en el que nada tiene que ver mi representado/a con el/la encausado/a en el mismo y por ello los bienes que son objeto de decomiso en sentencia, por un lado, pertenecen a mi representado/a, y además son de lícita procedencia, como se acredita con los documentos aportados, pero por otro ninguna vinculación o relación tiene mi representado/a con el/la encausado/a.

Por ello, se interesa se alcen los embargos sobre los referidos bienes y, revocando la sentencia condenatoria, se determine que los bienes pertenecen a mi representado/a levantando la medida de decomiso sobre los bienes y liberándolos de la ejecución sobre los mismos.

En su virtud,

SUPLICO A LA SECCIÓN

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se alce el decomiso acordado reconociendo la titularidad de los bienes citados como de propiedad del/de la recurrente.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La diferencia del recurso del art. 803 ter r LECRIM con el del art. 803 ter c LECRIM es que este se interpone contra sentencia dictada en proceso penal en el que se fija responsabilidad penal para el encausado y se resuelve sobre medida de decomiso en el que resultan condenados los terceros afectados, mientras que el del art. 803 ter r LECRIM es contra sentencia dictada en procedimiento específico de decomiso autónomo tramitado en vía penal por los trámites del juicio verbal civil en el que de forma exclusiva se resuelve sobre la medida del decomiso.

(2) Contra la sentencia recaída en procedimiento de decomiso autónomo caben los recursos previstos para el proceso penal abreviado.

================================================================================
