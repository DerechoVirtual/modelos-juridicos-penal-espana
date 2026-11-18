---
name: pedir-diligencias-previas-pasen-juicio-delito-leve-119
description: "Redacta el escrito «Pedir que las diligencias previas pasen a juicio por delito leve» (formulario 119 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que las diligencias previas pasen a juicio por delito leve

> Formulario 0119 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- El art. 779.1.2.ª LECrim sigue hablando de «falta»: la mención se entiende hecha al delito leve (DA 2.ª LO 1/2015). Desde el 3-10-2025 juzga los delitos leves la Sección de Instrucción del Tribunal de Instancia (art. 14.1 LECrim, redacción LO 1/2025), salvo los atribuidos a las Secciones de Violencia sobre la Mujer o de Violencia contra la Infancia y la Adolescencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…la declaración del testigo presencial Sr»; «…(folio»; «… el informe del forense obrante en folio»; «…asistencia hospitalaria obrante en folio»; «… delitos leves. Es justicia que pido, en»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 147.2 del Código Penal
- art. 147.3 del Código Penal

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

### Formulario 0119 · Pedir que las diligencias previas pasen a juicio por delito leve

- Año del modelo: 2023
- Revisión 17-11-2026: 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 108) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa del investigado, una vez finalizada la instrucción, solicita la transformación de las diligencias previas en juicio por delito leve, conforme al art. 779.1 2º LECRIM, al haber quedado probado que, a lo sumo, se ha cometido un delito de lesiones leves.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dª [NOMBRE Y APELLIDOS], Procurador de los Tribunales, actuando en representación de D/Dª [NOMBRE Y APELLIDOS], según consta acreditado en las diligencias previas número [Nº DE PROCEDIMIENTO], seguidas ante ese órgano judicial, comparezco y como proceda en Derecho, DIGO:

Que habiéndose practicado las diligencias necesarias para el esclarecimiento de los hechos, y al amparo de lo dispuesto en los arts. 779.1.2º de la LECrim, y preceptos concordantes, solicito la transformación de las diligencias previas en JUICIO POR DELITO LEVE, en base a los siguientes,

MOTIVOS

PRIMERO.- Las presentes diligencias previas se iniciaron por presunto delito de robo con violencia e intimidación contra mi defendido quien, desde un principio, si bien ha reconocido que tuvo una reyerta con el denunciante, ha manifestado reiteradamente que en ningún momento se apoderó de ningún objeto, ni actuó con ánimo de lucro.

Esta calificación inicial de robo con violencia se basó exclusivamente en la versión del denunciante y presunta víctima, quien manifestó que mi defendido le agredió y le sustrajo de un tirón una cadena de oro que llevaba en el cuello.

Esta versión ha quedado totalmente desvirtuada por las diligencias realizadas en la fase de instrucción, puesto que las distintas declaraciones practicadas, tanto de mi defendido como de los dos testigos que presenciaron el incidente, ponen de manifiesto que se produjo una agresión mutua entre el denunciante y mi representado, tras mantener una discusión, acometiéndose recíprocamente, lo cual no concuerda con la versión del denunciante, quien omite cualquier referencia a esta discusión previa, e incluso negó conocer a mi defendido, cuando los dos testigos manifiestan que les habían visto discutir en otra ocasión, porque se habían peleado sus perros en el parque.

Esto corrobora la versión de mi defendido, quien refirió que habían tenido dos discusiones porque el perro del denunciante agredió al suyo, constando en las actuaciones el parte de asistencia veterinaria del día en que se produjo dicho incidente.

En cuanto a la versión que ofrece el denunciante sobre el robo de la cadena de oro, queda totalmente desvirtuada con la declaración del testigo presencial Sr [COMPLETAR] (folio [COMPLETAR] de las diligencias previas), quien manifiesta literalmente: " que después de la trifulca su vecino, el denunciante, dijo que le faltaba la cadena de oro que tenía colgada en el cuello. Que durante lo sucedido el dicente vio durante un agarrón algo brillante volar por los aires, sin saber precisar de qué se trataba. Que después de los hechos, cuando ya se había ido el denunciado, vieron una medalla en un rincón y un pendiente en otro ".

De ello se evidencia que la violencia desplegada no lo fue para sustraer la cadena al denunciante, sino que hubo una pelea entre denunciante y denunciado, en la que se causaron lesiones recíprocamente, y en el transcurso de la cual se produjo el incidente con la cadena, sin que ello fuera causa de la reyerta, ni mi representado tuviera en ningún momento intención de apoderarse de ella, habiendo manifestado los testigos que mi representado no se llevó ningún objeto.

Por tanto, los hechos, si tuvieran relevancia penal, podrían constituir un delito leve de lesiones, puesto que, en el caso del denunciante, las lesiones tardaron en curar [Nº] días, sin necesidad de más de una primera asistencia facultativa, tal como consta en el informe del forense obrante en folio [COMPLETAR] de las diligencias previas. En el caso de mi defendido, tuvo lesiones consistentes en rasguños, tal como consta en el parte de asistencia hospitalaria obrante en folio [COMPLETAR] de las diligencias previas, aunque no causaran ningún tipo de impedimento, según se refleja en el informe médico-forense.

En consecuencia, los hechos podrían tener encaje, a lo sumo, en el delito leve de lesiones del art. 147.2 del Código Penal o, en su caso, en el delito de maltrato de obra del art. 147.3 del Código Penal, por lo que se solicita que se transforme el procedimiento en el de juicio por delitos leves.

SEGUNDO.- Se ampara la petición de transformación del procedimiento en lo dispuesto en el art. 779.1.2º de la LECrim, al haber finalizado la fase de instrucción, en la cual se han esclarecido suficientemente los hechos, quedando totalmente acreditado que no encajan en el tipo de robo con violencia sino, a lo sumo, en el de delito leve de lesiones.

Solicitamos, por tanto, que se dicte la resolución de adecuación del procedimiento a los hechos objeto del mismo, como delito leve, al haberse cumplido con la finalidad que el ordenamiento jurídico atribuye a la instrucción penal, que es la de aportación de los datos relevantes que respecto de los hechos objeto de la denuncia o querella resultan necesarios para valorar si los mismos poseen trascendencia penal, siendo que el derecho a la tutela judicial se satisface dictando, con prontitud, la resolución que corresponde cuando, como en este caso, ya se han agotado las diligencias de instrucción.

La jurisprudencia constitucional establece que el Juez, cuando aprecie de forma evidente que los hechos denunciados carecen de relevancia penal y en los mismos términos si son de menor entidad, debe realizar, con la mayor premura, las actuaciones necesarias para el inmediato archivo o transformación de la causa, según se recoge, entre otras muchas, en la STC núm. 138/1997, de 22 de julio."

Por todo ello, solicitamos que se declaren los hechos como delito leve, de conformidad a lo dispuesto en el art. 779.1.2ª de la LECrim, continuando su tramitación por el procedimiento del juicio de delitos leves.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, acuerde dictar auto declarando los hechos como delito leve y continuando la tramitación del procedimiento por el de juicio de delitos leves.

Es justicia que pido, en [COMPLETAR]

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 779.1.2.ª LECrim sigue hablando de «falta»: la mención se entiende hecha al delito leve (DA 2.ª LO 1/2015). Desde el 3-10-2025 juzga los delitos leves la Sección de Instrucción del Tribunal de Instancia (art. 14.1 LECrim, redacción LO 1/2025), salvo los atribuidos a las Secciones de Violencia sobre la Mujer o de Violencia contra la Infancia y la Adolescencia.]
