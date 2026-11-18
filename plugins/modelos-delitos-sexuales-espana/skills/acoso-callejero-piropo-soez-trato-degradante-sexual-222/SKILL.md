---
name: acoso-callejero-piropo-soez-trato-degradante-sexual-222
description: "Redacta el escrito «Acoso callejero o piropo soez (trato degradante sexual): escrito de acusación» (formulario 222 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acoso callejero o piropo soez (trato degradante sexual): escrito de acusación

> Formulario 0222 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- Las penas del art. 173.4 CP (localización permanente o trabajos en beneficio de la comunidad de cinco a treinta días, o multa de uno a cuatro meses) son leves según los arts. 13.4 y 33.4 CP: es delito leve, que se enjuicia por el juicio sobre delitos leves (art. 14.1 LECrim), no por procedimiento abreviado.
- El último párrafo del art. 173.4 CP solo permite perseguir estos hechos mediante denuncia de la persona agraviada o de su representante legal.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…el/la acusado/a»; «…nde vive, con las siguientes expresiones»; «… agravantes. Concurre en el/la acusado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Informe Pericial psicológico emitido por el perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humil…
- .- Documental consistente en facturas pagadas en el despacho del psicólogo D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 173.4 CP
- art. 22 del CP

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

### Formulario 0222 · Acoso callejero o piropo soez (trato degradante sexual): escrito de acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 24 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Las penas del art. 173.4 CP (localización permanente o trabajos en beneficio de la comunidad de cinco a treinta días, o multa de uno a cuatro meses) son leves según los arts. 13.4 y 33.4 CP: es delito leve, que se enjuicia por el juicio sobre delitos leves (art. 14.1 LECrim), no por procedimiento abreviado. · El último párrafo del art. 173.4 CP solo permite perseguir estos hechos mediante denuncia de la persona agraviada o de su representante legal.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El pasado día [FECHA] cuando el/la perjudicada paseaba por la calle acompañado/a de D./Dña [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] el/la acusado/a [COMPLETAR] se dirigió a él/ella por conocerle/a del barrio donde vive, con las siguientes expresiones [COMPLETAR] que causaron en la persona del/de la perjudicado/a una situación objetivamente humillante, hostil o intimidatoria, ante el tono peyorativo y despreciativo con que utilizó y empleó las expresiones antes citadas.

Esta conducta la lleva realizando esta persona, tanto con el/la perjudicado/a como con otros/as amigos/as suyos/as desde hace tiempo, pero a raíz de la tipificación de estos hechos es por lo que se ha decidido a interponer la presente querella por haberle causado un fuerte impacto emocional que le ha impedido volver a pasear por la citada calle desde que ocurrieron los hechos.

SEGUNDA.- Tales hechos son constitutivos de un delito de acoso callejero del art. 173.4 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros y facturas de asistencia al psicólogo D./Dña. [NOMBRE Y APELLIDOS] por importe de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de los siguientes testigos que iban con el/la perjudicado/a el día de los hechos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Testifical del psicólogo D./Dña. [NOMBRE Y APELLIDOS] a cuya consulta asiste el/la perjudicado/a a raíz de los hechos.

-Testifical de la víctima D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre los hechos.

[OPCIONAL — incluir si procede]

.- Informe Pericial psicológico emitido por el perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humillación provocada en la víctima por los hechos ocurridos y estado de depresión causado para acreditar daño moral.

[OPCIONAL — incluir si procede]

.- Documental consistente en facturas pagadas en el despacho del psicólogo D./Dña. [NOMBRE Y APELLIDOS]

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
