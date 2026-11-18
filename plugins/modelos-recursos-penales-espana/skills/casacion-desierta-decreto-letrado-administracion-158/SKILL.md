---
name: casacion-desierta-decreto-letrado-administracion-158
description: "Redacta el escrito «Casación desierta: decreto del Letrado de la Administración de Justicia» (formulario 158 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Casación desierta: decreto del Letrado de la Administración de Justicia

> Formulario 0158 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] FECHA (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…OFICINA JUDICIAL DE»; «…LETRADO DE LA ADMINISTRACIÓN DE JUSTICIA»; «…Recurso»; «…ta la de esta resolución ha transcurrido»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 873 de la LECrim
- art. 859 de la LECrim

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

### Formulario 0158 · Casación desierta: decreto del Letrado de la Administración de Justicia

- Año del modelo: 2023
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Nota explicativa incorporada desde la colección Procesal (formulario 122) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Resolución del Letrado de la Administración de Justicia por la que se declara desierto el recurso de casación, conforme al art. 873 LECRIM, por haber transcurrido el plazo del art. 859 LECRIM sin haberlo interpuesto. Frente a ella cabe recurso de revisión ante el TS Recuerde que....

---

OFICINA JUDICIAL DE [COMPLETAR]

LETRADO DE LA ADMINISTRACIÓN DE JUSTICIA [COMPLETAR]

Recurso [COMPLETAR]

DECRETO

En [LUGAR], a [DÍA] de [MES] de [AÑO].

ANTECEDENTES DE HECHO

PRIMERO. El día [FECHA] tuvo entrada en esta Oficina Judicial, el Rollo de recurso de casación número [Nº DE PROCEDIMIENTO] contra la sentencia de fecha [FECHA] dictada por la Audiencia Provincial de [LOCALIDAD] preparado por D. [NOMBRE Y APELLIDOS], habiendo sido emplazado en fecha [FECHA].

FUNDAMENTOS DE DERECHO

PRIMERO. El art. 873 de la LECrim establece que el recurso de casación se interpondrá ante la Sala Segunda del Tribunal Supremo dentro de los términos señalados en el art. 859 de la LECrim, siendo que en este caso el plazo de interposición ha transcurrido, habida cuenta que desde la fecha del emplazamiento reseñada en el antecedente hasta la de esta resolución ha transcurrido [COMPLETAR] por lo que debe declararse desierto el recurso.

PARTE DISPOSITIVA

Se declara desierto el recurso de casación núm. preparado por declarándose la pérdida del depósito para recurrir.

Firme que sea esta resolución, remítase comunicación al Tribunal de instancia a los efectos que procedan.

Esta resolución no es firme y contra ella cabe recurso de revisión ante la Sala Segunda del Tribunal Supremo dentro de los cinco días siguientes al de su notificación.

Así lo acuerdo y mando, doy fe.

Firma del Letrado de la Administración de Justicia

================================================================================
