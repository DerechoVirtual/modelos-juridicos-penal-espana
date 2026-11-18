---
name: acuse-recibo-orden-europea-investigacion-560
description: "Prepara «Acuse de recibo de una orden europea de investigación» (formulario 560 de cooperación penal internacional, revisado el 17-11-2026): es un modelo oficial; localiza el modelo vigente en la fuente oficial, pide los datos que exige y ayuda a rellenarlo. Requiere Jurisprudenciator."
---

# Acuse de recibo de una orden europea de investigación

> Formulario 0560 del plugin **Cooperación penal internacional** · revisado el 17-11-2026. Uso interno.

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

## Es un modelo oficial: no se redacta un escrito libre

El original no traía texto: solo remitía al acuse de recibo de una orden europea de investigación del anexo XIV de la Ley 23/2014. Este documento se presenta en el modelo oficial vigente, con sus casillas y apartados; no lo sustituyas por un escrito redactado.

- **Dónde está el modelo:** en el BOE, en los anexos de la Ley 23/2014 (`leer_boe` con BOE-A-2014-12029). Descarga siempre la versión vigente y di al usuario el enlace y la fecha de consulta.
- **Normas que lo regulan** (compruébalas con `buscar_articulo` o `buscar_boe` → `leer_boe` antes de usarlo):
  - Ley 23/2014, art. 187.2 (el Ministerio Fiscal registra la OEI y acusa recibo a la autoridad de emisión)

## Qué tienes en esta carpeta

- `formulario.md`: la referencia al modelo oficial y a sus normas (el original no traía más texto).
- `marco.md`: guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Los que exija el modelo oficial. Cuando lo tengas, recorre sus apartados y pide los datos en una sola tanda (identificación del interesado o de la autoridad, datos del procedimiento, documentación que se acompaña…). No inventes casillas: si un apartado no se entiende, cítalo literalmente y pregunta.

## Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Localiza el modelo oficial vigente en la fuente indicada. Si es un anexo de una norma (BOE o EUR-Lex), léelo con `leer_boe`; si está en una sede electrónica, búscalo en ella y anota el enlace y la fecha.
3. Comprueba con Jurisprudenciator las normas de la lista y la parte de `marco.md` que afecte al caso (plazos, órgano, procedimiento).
4. Pide al usuario los datos que exige el modelo y explícale qué documentación tiene que acompañar.
5. Rellena el modelo con esos datos. Si el modelo es un PDF rellenable, entrega los datos ordenados por apartado para pasarlos al PDF; si es un formulario de una norma, entrégalo en **Word (.docx)** con su estructura.
6. Indica dónde y cómo se presenta (sede electrónica, oficina o autoridad competente) y el plazo, si lo hay.
7. Cierra con: datos pendientes, enlace y fecha del modelo usado y normas comprobadas con Jurisprudenciator.
