---
name: mediacion-penal-diligencia-ingreso-cantidad-tras-acuerdo-730
description: "Redacta el escrito «Mediación penal: diligencia de ingreso de cantidad tras el acuerdo» (formulario 730 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mediación penal: diligencia de ingreso de cantidad tras el acuerdo

> Formulario 0730 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- Desde el 3-4-2025 la DA 9.ª LECrim (LO 1/2025) regula la justicia restaurativa: remisión judicial a instancia de parte o de oficio (ap. 5), plazo máximo de tres meses prorrogable por otros tres (ap. 6), informe y acta de reparación firmada por las partes y sus letrados (ap. 8) y audiencia de tres días antes de valorar el acuerdo (ap. 9).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº
- [ ] AÑO
- [ ] NÚMERO
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…/[AÑO] Servicio de Mediación Penal»; «… adscrito al Servicio de Mediación Penal»; «…firmado el»

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0730 · Mediación penal: diligencia de ingreso de cantidad tras el acuerdo

- Año del modelo: 2017
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº)
- Avisos de la revisión: Desde el 3-4-2025 la DA 9.ª LECrim (LO 1/2025) regula la justicia restaurativa: remisión judicial a instancia de parte o de oficio (ap. 5), plazo máximo de tres meses prorrogable por otros tres (ap. 6), informe y acta de reparación firmada por las partes y sus letrados (ap. 8) y audiencia de tres días antes de valorar el acuerdo (ap. 9).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el mediador pone en conocimiento del Juez que, después de llegar a un acuerdo de mediación penal, el denunciado ha ingresado la cantidad acordada dentro de plazo.

Expediente de Mediación Penal nº [Nº]/[AÑO]

Servicio de Mediación Penal [COMPLETAR]

El mediador adscrito al Servicio de Mediación Penal [COMPLETAR], da traslado a S.Sª Iltma, de que en el Acuerdo de Mediación Nº [NÚMERO] firmado el [COMPLETAR], se ha procedido por el mediado denunciado D./Dña. [NOMBRE Y APELLIDOS] a efectuar el ingreso de [IMPORTE] euros en el número de cuenta facilitado por el mediado denunciante D./Dña. [NOMBRE Y APELLIDOS] que representa el/la Letrado/a D./Dña. [NOMBRE Y APELLIDOS], cantidad establecida en el acuerdo de mediación alcanzado, y que de este modo perfecciona el acuerdo y los compromisos alcanzados en el mismo, completamente, al haberse producido dentro del término acordado por ambos mediados.

Se significa que el propio denunciante, a través de su letrado/a D./Dña. [NOMBRE Y APELLIDOS], ha remitido a este Servicio de Mediación, el correspondiente fax con copia acreditativa del ingreso; de lo que se da traslado a los efectos oportunos.

En [LUGAR], a [FECHA].

EL MEDIADOR

================================================================================
