---
name: violacion-bajo-sumision-quimica-calificacion-provisional-176
description: "Redacta el escrito «Violación bajo sumisión química: calificación provisional de la defensa» (formulario 176 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación bajo sumisión química: calificación provisional de la defensa

> Formulario 0176 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- Sumisión química: desde la LO 4/2023 la voluntad anulada es elemento del art. 179.2 CP (de seis a doce años) y la agravante 180.1.7.ª eleva la pena del 179.2 a doce a quince años; la concurrencia se resuelve por el art. 8.4 CP (art. 180.1, último párrafo).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] SEDE
- [ ] NÚMERO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…epresentación que tengo acreditada de D.»; «… quiso iniciar con ella una relación. Dª»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- La declaración del acusado, que será en último lugar tras la práctica de la prueba.…
- .- Testifical de los siguientes testigos:…
- -D./Dña [NOMBRE Y APELLIDOS] amigo/a del acusado que les vio irse juntos en el coche agarrados y a quien contó…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 652 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0176 · Violación bajo sumisión química: calificación provisional de la defensa

- Año del modelo: 2022
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 3 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 10 campos de relleno marcados en blanco
- Avisos de la revisión: Sumisión química: desde la LO 4/2023 la voluntad anulada es elemento del art. 179.2 CP (de seis a doce años) y la agravante 180.1.7.ª eleva la pena del 179.2 a doce a quince años; la concurrencia se resuelve por el art. 8.4 CP (art. 180.1, último párrafo).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en la representación que tengo acreditada de D. [COMPLETAR], acusado en el procedimiento de sumario ordinario número [Nº DE PROCEDIMIENTO] del año [AÑO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] por el supuesto delito de los arts. art. 178.2, 179 y 180.1.7º CP [NOTA DE REVISIÓN (comprobar): Desde la LO 4/2023 la violación de víctima con la voluntad anulada se castiga en el art. 179.2 CP (seis a doce años) y el art. 180.1 fija doce a quince años para el 179.2 agravado; si la circunstancia 7.ª ya integra el tipo, el último párrafo del art. 180.1 remite al art. 8.4 CP. Fuente: Código Penal, BOE-A-1995-25444, arts. 179 y 180 (redacción LO 4/2023, BOE-A-2023-10213).], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 652 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de calificación provisional del Fiscal y de la acusación particular y formulo escrito de calificación con base en las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular.

Mi representado no hizo exactamente lo que se le atribuye ya que fue Dña. la que le insinuó iniciar una relación con él, y que le acompañó en el coche, obviamente para estar juntos, siendo absolutamente incierto que éste se aprovechara de que estaba bebida o bajo los efectos de drogas o alcohol, sino que la relación fue consentida, ya que cuando se despertó discutieron por una cuestión que a ella no le gustó y se fue enfadada, siendo esta la posible causa de que ahora denuncie que tuvo lugar la relación sexual cuando ella estaba bajo los efectos del alcohol o drogas, lo que es absolutamente incierto, ya que ella sabía lo que hacía, y lo llevó a cabo voluntariamente.

El hecho de que se hayan encontrado restos de semen del acusado es fruto de una relación consentida, ya que el acto sexual lo hicieron de manera voluntaria. Lo que ocurrió es que, al día siguiente, ella se pudo arrepentir de lo que hizo, y/o pudo presentar la querella porque discutieron, o fue una venganza porque mi representado no quiso iniciar con ella una relación.

Dª [COMPLETAR] consintió expresamente la relación sexual, lo que hace impune la conducta.

SEGUNDA.- Niego las correlativas. Los hechos no son constitutivos de un delito de agresión sexual.

TERCERA.- Niego las correlativas. Mi representado no es el autor del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado con todos los pronunciamientos favorables, por no ser el autor.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- La declaración del acusado, que será en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical de los siguientes testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña [NOMBRE Y APELLIDOS] amigo/a del acusado que les vio irse juntos en el coche agarrados y a quien contó los hechos de la extraña reacción de la querellante al día siguiente.

Por lo expuesto,

SUPLICO A LA SALA: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
