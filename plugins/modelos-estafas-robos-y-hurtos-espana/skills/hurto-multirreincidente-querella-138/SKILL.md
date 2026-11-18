---
name: hurto-multirreincidente-querella-138
description: "Redacta el escrito «Hurto multirreincidente: querella» (formulario 138 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto multirreincidente: querella

> Formulario 0138 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde el 10-4-2026 (LO 1/2026, BOE-A-2026-7966) el hurto de hasta 400 euros se castiga con la pena del art. 234.1 CP si el culpable tiene al menos tres condenas ejecutorias por delitos de la misma naturaleza del Título XIII, siendo al menos una leve; ya no se exige cuantía acumulada ni que las tres sean leves.
- La expresión «este y otros delitos contra la propiedad» debe ajustarse: el art. 234.2 CP vigente exige condenas por delitos «de la misma naturaleza» comprendidos en el Título XIII (LO 1/2026).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] NÚMERO
- [ ] Nº
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (2 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] IMPORTE
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dirección»; «…se del Presidente del órgano judicial de»; «…. SUPLICO A LA SECCIÓN»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a.…
- .- Testifical:…
- .- Pericial de tasación de los bienes sustraídos, incluyendo el IVA, que se aporta en este acto.…
- .- Documental siguiente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 270 de la Ley de Enjuiciamiento Criminal
- art. 234.2 y 3 CP
- artículos 277 LECRIM
- artículo 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 48 CP
- art. 281 de la Ley de Enjuiciamiento Criminal
- Ley Orgánica 9/2022

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

### Formulario 0138 · Hurto multirreincidente: querella

- Año del modelo: 2023
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE COLEGIADO)
- Avisos de la revisión: Desde el 10-4-2026 (LO 1/2026, BOE-A-2026-7966) el hurto de hasta 400 euros se castiga con la pena del art. 234.1 CP si el culpable tiene al menos tres condenas ejecutorias por delitos de la misma naturaleza del Título XIII, siendo al menos una leve; ya no se exige cuantía acumulada ni que las tres sean leves. · La expresión «este y otros delitos contra la propiedad» debe ajustarse: el art. 234.2 CP vigente exige condenas por delitos «de la misma naturaleza» comprendidos en el Título XIII (LO 1/2026).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor, mediante

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº], por si no es posible la consulta automatizada.

Actuando bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes, por un delito de hurto leve del art. 234.2 y 3 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor del artículo 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- El/la querellante es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD]

TERCERO.- El/la querellado/a es D/Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], con domicilio en [LOCALIDAD].

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes:

El/La querellado/a D/Dña. [NOMBRE Y APELLIDOS] el día [FECHA] entró en el establecimiento del que es titular el/la querellante sito en [LOCALIDAD] dirección [COMPLETAR] y se apoderó, sin fuerza ni violencia, de objetos tasados en 300 euros consistentes en [DESCRIBIR]. El/La querellado/a fue sorprendido cuando estaba ya en la calle y se había apoderado de los objetos.

El/La querellado/a es una persona que habitualmente comete este tipo de delitos en esta zona, causando un grave perjuicio al comercio de la misma, habida cuenta que en otras ocasiones habrá podido llevarse objetos sin haber sido detectado, por cuanto utiliza el hurto en comercios como una profesión.

Constan ya más de tres condenas firmes por este y otros delitos contra la propiedad, y una de ellas era por delito leve de hurto, aun con independencia de que la cuantía acumulada de lo sustraído no supera los 400 euros.

El/La querellado/a ha utilizado en la comisión del hecho elementos para neutralizar, eliminar o inutilizar los dispositivos de alarma o seguridad instalados en las cosas sustraídas que fueron interceptados en el momento de la detención por el vigilante de seguridad D

El/La cajero/a del local donde se perpetró el hecho D./Dña [NOMBRE Y APELLIDOS] fue el/la que dio la alerta al vigilante de seguridad de que estaba viendo al/a la querellado/a cómo sustraía los objetos.

QUINTO.- Sin perjuicio de una más exacta calificación jurídica posterior, los hechos expuestos revisten los caracteres de un delito del art. 234.2 y 3 CP.

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

—Declaración del vigilante de seguridad que intervino D. [NOMBRE Y APELLIDOS]
—Declaración del/de la cajero/a D./Dña. [NOMBRE Y APELLIDOS]
—Declaración del/de la titular del establecimiento D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial de tasación de los bienes sustraídos, incluyendo el IVA, que se aporta en este acto.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

-Que se solicite del Registro Central de penados los antecedentes penales del/de la querellado/a a fin de acreditar la existencia de condenas previas.
-Que se interese del Presidente del órgano judicial de [COMPLETAR], que se se expida atento oficio a los órganos judiciales correspondientes para que remitan testimonio de sentencias firmes de condena del/de la querellado/a por delitos del Título XIII del CP.
-Se interesa del Ministerio Fiscal que, en base a la Circular 1/2022, de 12 de diciembre, sobre la reforma del delito de hurto operada en virtud de la Ley Orgánica 9/2022, de 28 de julio, y posterior LO 1/2026, de 8 de abril, recaben de los respectivos órganos judiciales testimonio íntegro de cada una de las sentencias condenatorias, permitiendo de ese modo conocer con seguridad dicho extremo al objeto de acreditarlo con las necesarias garantías.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita y se practiquen las diligencias interesadas.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa que se adopten las siguientes medidas cautelares:

-Sobre la situación personal del/de la querellado/a, se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros.
-Se le impida regresar al lugar del delito, conforme al art. 48 CP y a los arts. 13 y 544 bis LECRIM, prohibiéndole el acceso al establecimiento comercial sito en [LOCALIDAD].

SUPLICO A LA SECCIÓN [COMPLETAR]: Que tenga por hecha esta manifestación.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
