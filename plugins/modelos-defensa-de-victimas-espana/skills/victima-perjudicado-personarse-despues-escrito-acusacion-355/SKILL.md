---
name: victima-perjudicado-personarse-despues-escrito-acusacion-355
description: "Redacta el escrito «Víctima o perjudicado: personarse después del escrito de acusación» (formulario 355 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima o perjudicado: personarse después del escrito de acusación

> Formulario 0355 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- Quien se persona después del plazo de acusación solo puede ejercer la acción penal hasta el inicio del juicio oral, adhiriéndose al escrito de acusación del Fiscal o de otra acusación (arts. 109 bis.1 y 110 LECrim).
- Desde el 3-4-2025, en la audiencia preliminar (art. 785.1 LECrim) pueden aportarse informes, certificaciones y documentos, pero solo pueden proponerse nuevas pruebas de las que no se tuviera conocimiento al presentar los escritos de acusación o defensa. Al inicio del juicio (art. 787.3) solo cabe incorporar ese tipo de documentos y proponer pruebas que se desconocieran al celebrar dicha audiencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] Nº DE DOCUMENTO
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»; «…iscal. Por ser de Justicia que pido en a»

## Elecciones que hay que hacer

- esta Sección / esta sección de la AP
- de la víctima / del perjudicado
- víctima / perjudicado

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: En el caso de víctima del delito / En el caso de perjudicado por el delito — el texto de cada opción no venía en el formulario original

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

### Formulario 0355 · Víctima o perjudicado: personarse después del escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 3 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE DOCUMENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 163) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la víctima o el perjudicado se personan en un procedimiento abreviado una vez transcurrido el plazo para presentar escrito de acusación y antes del juicio oral, conforme a los arts. 109 bis y 110 LECRIM, según la redacción dada por LO 8/2021, de protección integral a la infancia y la adolescencia frente a la violencia, con entrada en vigor el 25 de junio de 2021 Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en representación de D./Dña. [NOMBRE Y APELLIDOS], como consta en escritura de poder inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme, acompañando certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada, comparezco ante la Sección
Tribunal
 y como mejor proceda en derecho, DIGO:

Que estando ya en trámite en [ELEGIR: esta Sección / esta sección de la AP] el procedimiento abreviado nº [Nº DE PROCEDIMIENTO] por hechos constitutivos de delito de [DELITO] del artículo [COMPLETAR] CP, contra D./Dña. [NOMBRE Y APELLIDOS], en uso del derecho reconocido en los artículos 101, 109 bis(En el caso de víctima del delito) y 110(En el caso de perjudicado del delito) y 761 de la Ley de Enjuiciamiento Criminal, me persono en el presente PA para ejercitar la acusación particular del referido delito, aun cuando haya transcurrido ya el plazo para presentar el escrito de acusación.

[ELEGIR UNA OPCIÓN Y REDACTARLA: En el caso de víctima del delito / En el caso de perjudicado por el delito — el texto de cada opción no venía en el formulario original]

Nótese que en materia de personación [ELEGIR: de la víctima / del perjudicado] por el delito ha habido jurisprudencia del Tribunal Supremo (STS 18/2018 de 17 Ene. 2018, Rec. 625/2017) proclive a «ensanchar» los contornos temporales de este acto de personación de ambos, siempre y cuando no se postule retrotraer actuaciones, pero sin que tenga que haber un impedimento al ejercicio de la acción penal cuando se considere oportuno.

En el presente caso, por ello, solo se postula la admisión de personación en concepto de [ELEGIR: víctima / perjudicado], sin retrotraer las actuaciones y adhiriéndonos al escrito del fiscal para poder intervenir en calidad de acusación particular el día del juicio oral.

Hacemos constar que el límite que se pone en estos casos es que, en base al respeto al principio acusatorio, lo que no puede llevar a cabo la víctima o perjudicado es sostener una pretensión de acusación y condena con hechos y tipos ajenos a los que conforman el escrito de acusación pública o particular distinta a la suya, ya que esta acusación de tipicidad y hechos ya ha sido cerrada una vez ha concluido el plazo para la acusación y la defensa ha contestado a esos hechos y esa acusación.

Pero ello no nos debe impedir que se nos admita la personación una vez precluya el plazo para la acusación, sosteniendo los mismos hechos y tipos penales que la acusación ya ejercida en su momento procesal, que es lo que mantenemos con el presente escrito.

Por lo expuesto,

SUPLICO A LA SECCIÓN
A LA AUDIENCIA

Que tenga por presentado este escrito y documentos adjuntos, los admita, teniéndome por personado en la representación de D./Dña. [NOMBRE Y APELLIDOS], como acusador particular, ejercitando las acciones penales y civiles que se deriven de los hechos, y acuerde se entiendan conmigo las sucesivas diligencias, dándome vista de lo actuado y adhiriéndonos al escrito de acusación del Ministerio Fiscal.

Por ser de Justicia que pido en a [COMPLETAR]

Firma de Abogado/a:	Firma de Procurador/a:	Firma del cliente: (En caso de no adjuntar poder o designación de turno de oficio)

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) El perjudicado puede mostrarse parte en la causa sin necesidad de formular querella. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023). Esta personación tardía lo que sí permitiría, en todo caso, es aportar pruebas por la vía del art. 786.2 LECRIM(hasta el 2 de abril de 2025), en la audiencia preliminar del art. 785 LECrim o antes del juicio oral ex art. 787.3 LECrim. (desde el 3 de abril de 2025, fecha de entrada en vigor de la reforma de la LO 1/2025)

[NOTA DE REVISIÓN: Quien se persona después del plazo de acusación solo puede ejercer la acción penal hasta el inicio del juicio oral, adhiriéndose al escrito de acusación del Fiscal o de otra acusación (arts. 109 bis.1 y 110 LECrim).]

[NOTA DE REVISIÓN: Desde el 3-4-2025, en la audiencia preliminar (art. 785.1 LECrim) pueden aportarse informes, certificaciones y documentos, pero solo pueden proponerse nuevas pruebas de las que no se tuviera conocimiento al presentar los escritos de acusación o defensa. Al inicio del juicio (art. 787.3) solo cabe incorporar ese tipo de documentos y proponer pruebas que se desconocieran al celebrar dicha audiencia.]
