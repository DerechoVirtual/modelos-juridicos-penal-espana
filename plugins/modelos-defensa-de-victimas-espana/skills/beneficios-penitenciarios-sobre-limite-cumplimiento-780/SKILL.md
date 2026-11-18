---
name: beneficios-penitenciarios-sobre-limite-cumplimiento-780
description: "Redacta el escrito «Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima» (formulario 780 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima

> Formulario 0780 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- El art. 13.1.b) Ley 4/2015 remite al art. 78.3 CP, pero desde la LO 1/2015 el art. 78 CP solo tiene dos apartados: la facultad del juez de vigilancia de volver al régimen general está en el art. 78.2.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO (2 veces)
- [ ] FECHA (5 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… de beneficios penitenciarios del penado»; «… aplican los beneficios penitenciarios a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 13.1 b) Ley 4/2015
- artículo 13.3 Ley 4/2015
- artículo 78 CP
- artículo 76 CP
- artículo 13.1 a) Ley 4/2015
- artículo 13.1.2 Ley 4/2015

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

### Formulario 0780 · Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 15 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Avisos de la revisión: El art. 13.1.b) Ley 4/2015 remite al art. 78.3 CP, pero desde la LO 1/2015 el art. 78 CP solo tiene dos apartados: la facultad del juez de vigilancia de volver al régimen general está en el art. 78.2.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima de un delito no personada en el proceso presenta recurso de reforma, y subsidiario de apelación, contra el auto que aplica al penado beneficios penitenciarios sobre el límite de cumplimiento de la pena, en vez de sobre la suma de las penas impuestas, conforme al artículo 13.1. b) de la L 4/15, del Estatuto de la víctima del delito.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de la víctima (1) D./Dña. [NOMBRE Y APELLIDOS] en expediente nº [Nº DE PROCEDIMIENTO]/[AÑO] contra D./Dña. [NOMBRE Y APELLIDOS] por delito de [DELITO] ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Mediante el presente escrito, y a tenor de lo dispuesto en el artículo 13.1 b) Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, interpone RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN contra el auto de aplicación de beneficios penitenciarios del penado [COMPLETAR] de fecha [FECHA] en base a los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- Con fecha [FECHA] se presentó escrito interesando le fuere denegada al penado la posibilidad de que se le aplicaran beneficios penitenciarios tras el traslado que se le dio por la vía del artículo 13.3 Ley 4/2015, de 27 de abril.

SEGUNDO.- Con fecha [FECHA] se ha dictado por el juez de vigilancia penitenciaria auto por el que se aplican los beneficios penitenciarios a [COMPLETAR] que me ha sido notificado a mi dirección de correo electrónico.

El juez de vigilancia penitenciaria basa su auto en el artículo 78 CP, en relación con el artículo 76 CP.

Mi representado/a ha sido víctima de un delito de [DELITO] incluido en el artículo 13.1 a) Ley 4/2015, un delito de gravedad y el informe de la junta de tratamiento fue negativo y constaban observaciones acerca del peligro de la reincidencia, dada la gravedad de los hechos de que fue víctima, así como por no haber recibido completamente la indemnización acordada aplazada, faltando todavía por recibir la suma de [IMPORTE] euros.

TERCERO.- Con fecha [FECHA] se presentó escrito por la víctima anunciando en legal plazo el deseo de recurrir presentándose el presente recurso dentro del plazo de 15 días previsto en el artículo 13.1.2 Ley 4/2015, de 27 de abril.

Por todo ello

SUPLICO A LA SECCIÓN

Se revoque el auto dictado y se apliquen, en su caso, los beneficios penitenciarios sobre las sumas de las penas impuestas y no sobre el límite de cumplimiento de la pena, estimándose el recurso de reforma y, en su defecto, se remitan las diligencias por testimonio a la Audiencia Provincial admitiéndose recurso de apelación contra el auto dictado.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) No hace falta que la víctima esté personada en el proceso para recurrir. (Artículo 13.1 b) Ley 4/2015)

================================================================================
