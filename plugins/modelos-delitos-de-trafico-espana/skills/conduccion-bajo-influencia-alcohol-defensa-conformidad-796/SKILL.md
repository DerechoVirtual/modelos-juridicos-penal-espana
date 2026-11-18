---
name: conduccion-bajo-influencia-alcohol-defensa-conformidad-796
description: "Redacta el escrito «Conducción bajo la influencia del alcohol: defensa con conformidad en juicio rápido» (formulario 796 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción bajo la influencia del alcohol: defensa con conformidad en juicio rápido

> Formulario 0796 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, en representación del/ de la acusado/a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 379 CP
- artículo 801 de la Ley de Enjuiciamiento Criminal
- art. 382 CP
- artículo 787 ter LECrim
- artículo 789.2 LECrim

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

### Formulario 0796 · Conducción bajo la influencia del alcohol: defensa con conformidad en juicio rápido

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la defensa en juicio rápido por el que se conforma con la pena solicitada por la acusación por delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP, sin concurrir con ningún otro delito, con lo que verá reducida en un tercio su pena.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] (1) y con despacho profesional abierto en [LOCALIDAD],, en representación del/ de la acusado/a [COMPLETAR], en el procedimiento número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito de conducción bajo la influencia de bebidas alcohólicas del art. 379 CP (2), comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al artículo 801 de la Ley de Enjuiciamiento Criminal, formulo escrito de defensa manifestando la conformidad con el escrito de acusación presentado por el Ministerio Fiscal, que solicita la pena (3) de multa de cuatro meses a razón de 4 euros/día (4), y privación del derecho a conducir vehículos a motor y ciclomotores por tiempo de ocho meses, firmando también el/la acusado/a en prueba de conformidad.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la defensa y manifestada la conformidad con el escrito de acusación del Fiscal.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma del acusado/a

NOTAS DEL FORMULARIO

(1) El abogado designado para la defensa tendrá también habilitación legal para la representación de su defendido en todas las actuaciones ante el juez de guardia. (Art. 797.3 LECrim).

(2) Puede tramitarse este hecho por juicio rápido en el caso de tratarse solo de un delito del art. 379 CP ya que si concurriera con otro de lesiones se aplicaría el art. 382 CP y deberían tramitarse diligencias previas por la necesidad de practicar diligencias penales de informe forense y de daños que excluirían la tramitación por la vía del juicio rápido.

(3) Solo puede prestarse conformidad por la vía del art. 801.1.2º LECrim en el caso de calificación por delito castigado con pena hasta 3 años de prisión, o pena de multa cualquiera que sea su cuantía, u otra pena de distinta naturaleza de duración no superior a 10 años en juicio rápido en el que está admitido el del art. 379 CP.

El juez de guardia realizará el control de la conformidad prestada en los términos previstos en el artículo 787 ter LECrim y, en su caso, dictará oralmente sentencia de conformidad que se documentará con arreglo a lo previsto en el artículo 789.2 LECrim, en la que impondrá la pena solicitada reducida en un tercio, aun cuando suponga la imposición de una pena inferior al límite mínimo previsto en el Código Penal. Si el fiscal y las partes personadas expresasen su decisión de no recurrir, el juez, en el mismo acto, declarará oralmente la firmeza de la sentencia y, si la pena impuesta fuera privativa de libertad, resolverá lo procedente sobre su suspensión. (Art. 801.2 LECrim).

(4) Podría plantearse con el fiscal la multa a razón de 4 euros si la solvencia fuera reducida. De no ser así sería de 6 euros por día de multa.

================================================================================
