---
name: ejecutoria-penal-condenado-pide-derivacion-servicios-48
description: "Redacta el escrito «Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa» (formulario 48 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa

> Formulario 0048 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº DE RESOLUCIÓN
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… en representación del/de la condenado/a»; «… la de Que prevé el art. 84.1.1º CP que:»

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 80.2 CP

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

### Formulario 0048 · Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa

- Año del modelo: 2025
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 6 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.
- Nota explicativa incorporada desde la colección Procesal (formulario 33) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la defensa del condenado en ejecutoria penal por el que solicita acudir a un procedimiento de mediación o justicia restaurativa, en base a la disp. adic. 9ª.9 e) LECRIM, según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025 y que se le suspenda la ejecución de la pena, conforme al art. 84.1.1º CP.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala de lo Penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales, en representación del/de la condenado/a [COMPLETAR] en ejecutoria penal nº [Nº], comparezco ante este órgano judicial y, como mejor proceda en Derecho, DIGO:

Que se cumplen las condiciones para interesar la suspensión de la ejecución de la pena recaída en sentencia nº [Nº DE RESOLUCIÓN] por aplicación del art. 80.2 CP, dado que la pena es la de

Que prevé el art. 84.1.1º CP que: [COMPLETAR]

"1. El juez o tribunal también podrá condicionar la suspensión de la ejecución de la pena al cumplimiento de alguna o algunas de las siguientes prestaciones o medidas:

1.ª El cumplimiento del acuerdo alcanzado por las partes en virtud de mediación.

Que la Disposición Adicional 9ª.9 e) LECRIM dice:

"9. En caso de existir acuerdo, el órgano judicial, previa audiencia del Ministerio Fiscal, de las partes personadas y de la víctima del delito, por término de tres días, valorando los acuerdos a los que las partes hayan llegado, las circunstancias concurrentes y el estado del procedimiento, podrá: ...e) Resolversobre la suspensión de la ejecución de la pena privativa de libertad, valorando el resultado del procedimiento restaurativo para el establecimiento de las condiciones, medidas u obligaciones de la suspensión; o, en su caso, sobre el contenido de los trabajos en beneficio de la comunidad".

Es por ello, por lo que,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Se derive la presente ejecutoria a los servicios de justicia restaurativa para alcanzar un acuerdo y dar lugar a la petición de suspensión de la ejecución de la pena, ante la concurrencia de los requisitos para ello.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
