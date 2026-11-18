---
name: omision-deber-impedir-delitos-acusacion-841
description: "Redacta el escrito «Omisión del deber de impedir delitos: acusación» (formulario 841 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Omisión del deber de impedir delitos: acusación

> Formulario 0841 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (2 veces)
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…or se apoderó de la cartera que contenía»; «…tuado hasta el momento de la vista oral.»

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: a cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas, que tra…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 450 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 777.2 LECr

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

### Formulario 0841 · Omisión del deber de impedir delitos: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos repetibles señalados; 3 párrafos opcionales señalados; 15 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular en un procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales por un presunto delito de omisión del deber de impedir delitos del art. 450 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia, por la vía del art. 781 LECRIM, y en plazo (1) escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] D./Dña. [NOMBRE Y APELLIDOS] fue objeto de un ataque contra su persona por parte de una persona desconocida al salir de su domicilio sito en [LOCALIDAD], quien le comenzó a golpear para quitarle sus objetos personales, momento en el que el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] salía del portal de su inmueble, siendo conocido por la víctima, por lo que reclamó su ayuda ante el ataque que estaba sufriendo. En ese instante, el/la acusado/a, en lugar de acudir en ayuda o recabar la de los agentes policiales salió corriendo del lugar sin mostrar ayuda alguna ni llamar a los agentes policiales. A resultas del ataque de que fue objeto el/la perjudicado/a, el agresor se apoderó de la cartera que contenía [COMPLETAR], teléfono móvil y las llaves de su inmueble y vehículo.

Una vez puso los hechos en conocimiento de la policía, no había constancia de llamada alguna del/de la acusado/a, por lo que no solicitó en modo alguno la ayuda policial pese a tener conocimiento inmediato y directo de la comisión de un delito contra la integridad del/de la perjudicado/a. No se trataba de que el/la acusado/a realizara un acto heroico que pusiera en peligro su vida, pero sí de llevar a cabo alguna actitud disuasoria de la conducta del atacante para que éste pensara que iba a llamar a los agentes policiales, o simplemente advertirle de que dejara de atacar a la víctima, lejos de lo cual se limitó a salir corriendo del lugar sin hacer nada.

SEGUNDA.- Tales hechos son constitutivos del delito de omisión del deber de impedir la comisión de determinados delitos del art. 450 CP.

TERCERA.- Es responsable del delito del art. 450 CP en concepto de autor/a el/la acusado/a. (2)

CUARTA.- No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de las responsabilidad penal.

QUINTA.- Procede imponer al/a la acusado/a por el delito de omisión del deber de impedir la comisión de determinados delitos del art. 450 CP la pena de [PENA] multa con cuota diaria de [IMPORTE] euros. (3)

SEXTA.- Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: a cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas, que tramitaron la denuncia ante comisaría presentada por el/la querellante por la agresión de que fue objeto:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Aun cuando, en principio, el mandato de actuación vaya dirigido a todos los ciudadanos, el círculo de posibles sujetos activos se restringe a aquellos que estén en condiciones de impedir, con su intervención inmediata y sin riesgo propio o ajeno, la perpetración de un delito que afecte a las personas en su vida, integridad o salud, libertad o libertad sexual.

Respecto de los delitos afectados por el mandato de intervenir, la relación típica es aparentemente reducida e imprecisa. En cuanto a su brevedad, el criterio seguido por la Ley es exigir la intervención solamente en delitos contra bienes jurídicos personalísimos y tangibles, es decir, no «espirituales» como la intimidad o el honor.

(3) En cuanto a la penalidad a imponer se castiga con la pena de prisión de seis meses a dos años si el delito fuera contra la vida, y la de multa de seis a veinticuatro meses en los demás casos, salvo que al delito no impedido le correspondiera igual o menor pena, en cuyo caso se impondrá la pena inferior en grado a la de aquél.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
