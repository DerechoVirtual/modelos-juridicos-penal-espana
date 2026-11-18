---
name: abreviado-oposicion-apelacion-contra-denegacion-apertura-101
description: "Redacta el escrito «Abreviado: oposición a la apelación contra la denegación de apertura del juicio oral» (formulario 101 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abreviado: oposición a la apelación contra la denegación de apertura del juicio oral

> Formulario 0101 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…seyendo las actuaciones. Por lo expuesto»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766.3 LECRIM
- art. 783.1 de la LECrim
- art. 766.3 de la LECrim

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

### Formulario 0101 · Abreviado: oposición a la apelación contra la denegación de apertura del juicio oral

- Año del modelo: 2023
- Revisión 17-11-2026: 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 101) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la defensa del acusado en un procedimiento abreviado por el que presenta alegaciones en contra del recurso de apelación interpuesto por la acusación particular, conforme al art. 766.3 LECRIM, contra el auto que deniega la apertura del juicio oral y decreta su sobreseimiento, conforme al art. 783.1 LECRIM.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO], seguido ante ese órgano judicial, ante él comparezco y, como proceda en Derecho, DIGO:

Que el día [FECHA] se ha dado traslado a esta representación del recurso de apelación interpuesto por la representación de la acusación particular contra el auto de denegación de la apertura del juicio oral de fecha [FECHA], por lo que, evacuando el traslado conferido, IMPUGNO EL RECURSO DE APELACIÓN interpuesto de contrario, conforme al art. 766.3 LECRIM, en base a los siguientes

MOTIVOS

PRIMERO.- La parte apelante pretende que el Juez de Instrucción decrete automáticamente la apertura del juicio oral, olvidando su función de dirección del proceso y las amplias facultades que le concede el art. 783.1 de la LECrim cuando, como en este caso, la acusación es infundada.

La existencia de un juicio indiciario, previo a la apertura del juicio oral, deriva de las garantías del proceso penal, y de la necesidad de evitar acusaciones infundadas, puesto que no debe olvidarse que la apertura del juicio oral supone un verdadero reproche anticipado, la pena de banquillo, que somete al acusado a la presión propia de esta situación procesal, a la vez que le supone un desvalor social por el mero hecho de su apertura.

En el marco de las facultades que le confiere la Ley, el Juez de Instrucción ha dictado una resolución razonada de sobreseimiento del proceso, garantizada por su posición imparcial ante las pretensiones de las partes.

En efecto, la resolución del Juez de Instrucción analiza de forma imparcial los elementos indiciarios derivados de la instrucción y deduce que es improcedente la acusación, lo que le lleva a dictar el sobreseimiento. En estas condiciones, no puede pretender el apelante que su criterio de parte sustituya al imparcial del Juez.

SEGUNDO.- Las alegaciones realizadas por el apelante en su recurso de apelación tratan de enmendar las graves carencias que presenta la acusación sostenida, valorando de forma parcial el resultado de las diligencias instructoras.

 Así, toda la argumentación de la parte apelante gira alrededor de los elementos indiciarios que se derivan de la declaración del perjudicado, sin tener en cuenta que los contraindicios son tan consistentes que desvirtúan la versión fáctica de la acusación. Así, el perjudicado reconoce a mi defendido como autor el robo, pero indica que no pudo ver bien a la persona que le robó porque se lo impedía el casco que portaba (folio 23) y en el reconocimiento en rueda identifica a mi defendido por la complexión física y aspecto externo, pero con dudas (folio 25); el perjudicado asegura que el robo fue el día 25 sobre las 17.00 horas, lo cual descartaría la autoría de los hechos de mi representado, puesto que esta defensa ha acreditado contundentemente que durante toda la mañana y tarde del día en que se produjo el robo mi representado estuvo en la localidad de B. en compañía de otras dos personas, trabajando en la obra de un edificio que está promoviendo construcciones C. (testifical, folios 32, 33, y 35 y contrato de trabajo, folio 27).

Por tanto, los indicios que podrían resultar de la declaración del denunciante se han desvirtuado con los contraindicios expuestos, al punto de determinar la inconsistencia del juicio indiciario de autoría y, en consecuencia, la improcedencia de la acusación, tal como ha apreciado con su imparcial criterio el Juez de Instrucción, sobreseyendo las actuaciones.

Por lo expuesto [COMPLETAR],

SUPLICO A LA SECCIÓN:

Que tenga por impugnado el recurso de apelación interpuesto por la representación de [NOMBRE DEL REPRESENTADO/A] contra el auto denegatorio de la apertura del juicio oral de fecha [FECHA], dando el trámite legal, y suplicando a la Sala que, con desestimación del recurso interpuesto, confirme la mencionada resolución.

Es justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO que al amparo de lo dispuesto en el art. 766.3 de la LECrim designo los siguientes particulares para que se adicionen a los señalados por el apelante: folios

SUPLICO A LA SECCIÓN tenga por adicionados los particulares designados y sean remitidos a la Sala para la resolución del recurso.

Es Justicia que reitero en lugar y fecha "ut supra"

Firma de Abogado/a	Firma de Procurador/a

================================================================================
