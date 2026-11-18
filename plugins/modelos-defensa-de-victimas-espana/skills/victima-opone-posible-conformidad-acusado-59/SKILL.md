---
name: victima-opone-posible-conformidad-acusado-59
description: "Redacta el escrito «Víctima que se opone a la posible conformidad del acusado» (formulario 59 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima que se opone a la posible conformidad del acusado

> Formulario 0059 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Los arts. 655.2 y 785.4 LECrim no dan a la víctima un derecho de veto sobre la conformidad. Lo que hacen es obligar al Fiscal a oírla antes, aunque no esté personada, cuando sea posible y necesario y, en todo caso, si los hechos son especialmente graves o la víctima es especialmente vulnerable. Si está personada como acusación, su escrito cuenta para fijar la acusación más grave con la que debe conformarse el acusado (arts. 655.1 y 785.4 LECrim).
- La nota 2 es coherente con la DT 9ª.1 LO 1/2025: la reforma se aplica solo a los procedimientos incoados después de su entrada en vigor.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ación que tiene acreditada de la víctima»; «…d del delito que recordemos consistió en»; «…CP por las circunstancias que se indican»

## Elecciones que hay que hacer

- Procedimiento abreviado / sumario
- no se ha satisfecho todavía / se ha satisfecho solo parcialmente
- A LA SECCIÓN / AL TRIBUNAL / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de procedimiento ordinario / En caso de procedimiento abreviado — el texto de cada opción no venía en el formulario original

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

### Formulario 0059 · Víctima que se opone a la posible conformidad del acusado

- Año del modelo: 2025
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 3 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 54) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la víctima se opone a la aceptación de la petición de conformidad planteada por la defensa y a la consiguiente posible rebaja de pena del acusado, con base en el art. 655.2 LECRIM, para el procedimiento ordinario y en el art. 785.4 LECRIM, para el procedimiento abreviado, conforme a la redacción dada por LO 1/2025, de Eficiencia de la Justicia, vigente desde el 3 de abril de 2025.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala de lo Penal de la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de la víctima [COMPLETAR]. en [ELEGIR: Procedimiento abreviado / sumario] nº [Nº DE PROCEDIMIENTO] por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que manifiesto mi oposición a una posible rebaja de pena planteada por la defensa del/de la acusado/a en el traslado que se me ha dado de su petición de conformidad, en base a las siguientes

ALEGACIONES

ÚNICA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de procedimiento ordinario / En caso de procedimiento abreviado — el texto de cada opción no venía en el formulario original]

Ante ello, mostramos nuestra oposición a la aceptación de la petición de conformidad planteada por la defensa del/de la acusado/a, en cuanto a una posible rebaja de pena y modificación del escrito inicial de calificación del Ministerio Fiscal, así como nuestra negativa a rebajar la pena solicitada por esta representación procesal, personada como acusación particular en el que se solicitaba la siguiente pena al acusado.

Nos oponemos, por ello, a cualquier admisión de circunstancias modificativas de responsabilidad Criminal en base a la gravedad del delito que recordemos consistió en [COMPLETAR], ya que, además, [ELEGIR: no se ha satisfecho todavía / se ha satisfecho solo parcialmente] la responsabilidad civil.

Debemos hacer notar que la gravedad del hecho delictivo y la victimización producida por el acusado en la persona de la víctima, hacen inviable cualquier tipo de rebaja penal, negándonos a la apreciación de la atenuante de reparación del daño del art 21.5 CP por las circunstancias que se indican [COMPLETAR].

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / AL TRIBUNAL / A LA SALA]:

Que tenga por presentado este escrito con sus copias, los admita y por opuestos a cualquier tipo de rebaja de pena por las acusaciones para conseguir una conformidad en la presente causa, manteniéndose la petición de pena formulada en el escrito de acusación particular.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Si se tratara de escrito de víctima no personada como acusación particular, se interesaría que el Fiscal mantenga la pena planteada en su escrito de acusación

(2) Este escrito es válido para procedimientos incoados a partir del 3 de abril de 2025, fecha de la entrada en vigor de la LO 1/2025. No obstante, para procedimientos incoados antes del 3 de abril de 2025 no debe haber inconveniente para que la víctima presente escrito oponiéndose a cualquier tipo de conformidad en el abreviado, pero no así en el procedimiento ordinario

[NOTA DE REVISIÓN: Los arts. 655.2 y 785.4 LECrim no dan a la víctima un derecho de veto sobre la conformidad. Lo que hacen es obligar al Fiscal a oírla antes, aunque no esté personada, cuando sea posible y necesario y, en todo caso, si los hechos son especialmente graves o la víctima es especialmente vulnerable. Si está personada como acusación, su escrito cuenta para fijar la acusación más grave con la que debe conformarse el acusado (arts. 655.1 y 785.4 LECrim).]

[NOTA DE REVISIÓN: La nota 2 es coherente con la DT 9ª.1 LO 1/2025: la reforma se aplica solo a los procedimientos incoados después de su entrada en vigor.]
