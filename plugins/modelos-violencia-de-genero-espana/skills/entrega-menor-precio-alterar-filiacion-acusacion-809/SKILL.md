---
name: entrega-menor-precio-alterar-filiacion-acusacion-809
description: "Redacta el escrito «Entrega de menor por precio para alterar la filiación: acusación» (formulario 809 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Entrega de menor por precio para alterar la filiación: acusación

> Formulario 0809 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…director/a del centro hospitalario»; «…Dña. dio a luz en su centro a un niño el»; «…rceptado/a por el guarda de seguridad D.»; «…enfermero/a que presenció los hechos. D.»; «…tuado hasta el momento de la vista oral.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de los acusados.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 221 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 CP
- art. 57.1 CP
- art. 48 CP
- art. 62 CP
- art. 777.2 LECr
- Ley 20/2011

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

### Formulario 0809 · Entrega de menor por precio para alterar la filiación: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 16 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos de delito de entrega de menor por precio para alterar la filiación del art. 221 CP

Actualizado conforme a la L 4/2023, de 28 de febrero, para la igualdad y garantía de derechos de las personas trans y LGTBI, vigente desde el 2 de marzo de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D. y Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA.- D./Dña. [NOMBRE Y APELLIDOS] director/a del centro hospitalario [COMPLETAR] tuvo conocimiento de que la acusada Dña. dio a luz en su centro a un niño el [COMPLETAR], como acredita el certificado expedido por el/la médico D./Dña. [NOMBRE Y APELLIDOS] que consta en autos. Al día siguiente, tuvo noticia de que el/la enfermero/a D./Dña. [NOMBRE Y APELLIDOS] presenció cómo el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] recibía el menor de manos de su progenitor gestante, la también acusada Dña. [NOMBRE Y APELLIDOS] en la misma habitación del hospital, comprobando como el/la acusado/a le entregaba a cambio un sobre con dinero, que pudo ver el/la enfermero/a desde el pasillo al estar la puerta entreabierta. Acto seguido, el/la acusado/a salió de la habitación corriendo dando aviso el/la enfermero/a al equipo de seguridad del hospital, siendo interceptado/a por el guarda de seguridad D. [COMPLETAR], antes de salir del centro hospitalario. Al progenitor gestante del menor se le intervino un sobre que le había entregado el/la acusado/a que contenía 3.000 euros.

SEGUNDA.- Tales hechos son constitutivos del delito de alteración de la paternidad, estado o condición del menor del art. 221 CP, en grado de tentativa. (2)

TERCERA.- Son responsables del delito de alteración de la filiación, estado o condición del menor del art. 221 CP, en grado de tentativa, los acusados D. y Dña. [NOMBRE Y APELLIDOS] en concepto de autores.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren con respecto a los acusados circunstancias modificativas de la responsabilidad criminal.

Concurre con respecto a los acusados la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer a cada uno de los acusados, por el delito de alteración de la filiación, estado o condición del menor en grado de tentativa, la pena de y prohibición de comunicarse con mi representado/a por cualquier medio de comunicación y de aproximación a la misma a su domicilio o su lugar de trabajo o aquellos que frecuente durante un periodo de años con prohibición de acercamiento genérico a una distancia inferior a los metros, en virtud del art. 57.1 CP, en relación con el art. 48 CP. (3)

SEXTA.- Las costas deberán ser satisfechas por los acusados.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

[OPCIONAL — incluir si procede]

1.- Interrogatorio de los acusados.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

D./Dña. [NOMBRE Y APELLIDOS], enfermero/a que presenció los hechos.

D. [COMPLETAR], guarda de seguridad que detuvo al acusado saliendo del centro con el bebé en brazos.

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral. [COMPLETAR].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.]

(2) Este es un delito esencialmente doloso. Se trata de un delito en el que, a cambio de precio, se provoca la alteración de la filliación, estado o condición de menor. Exige como elemento del tipo que "medie una compensación económica".

El objetivo real es establecer una relación análoga a la de filiación.

Se castiga tanto al que da al menor como al que lo recibe y al intermediario, aunque la entrega del menor se hubiese efectuado en país extranjero.

(3) Se aplicaría la pena inferior en grado al tratarse de tentativa de delito (art. 62 CP).

Con respecto a la distancia, lo normal es instarlo a una distancia de 500 metros, aunque pueden darse circunstancias particulares (por ejemplo, tener el acusado un piso a 300 metros de la víctima) que permitan su reducción. La distancia establecida en la orden de alejamiento debe medirse en la forma que determine la resolución judicial y, en su defecto, en línea recta. (STS 691/2018, de 21 de diciembre, Rec. 2357/2017)

En las parejas del mismo sexo registral, las referencias hechas a la madre se entenderán hechas a la madre o progenitor gestante y las referencias hechas al padre se entenderán referidas al padre o progenitor no gestante (DA 10ª Ley 20/2011, de 21 de julio, del Registro Civil, según redacción dada por L 4/2023, de 28 de febrero, para la igualdad y garantía de derechos de las personas trans y LGTBI).

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
