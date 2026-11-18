---
name: revenge-porn-denuncia-ante-fiscalia-menores-515
description: "Redacta el escrito «Revenge porn: denuncia ante la Fiscalía de Menores» (formulario 515 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revenge porn: denuncia ante la Fiscalía de Menores

> Formulario 0515 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

- [ ] DNI/NIE (2 veces)
- [ ] LOCALIDAD
- [ ] Nº (2 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 13 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… la víctima. A la Fiscalía de Menores de»; «…D Con DNI nº [DNI/NIE] y Dª»; «…, padres de el/la menor»; «…RIMERO.- Aproximadamente hacia el mes de»; «…de»; «…n con el/la también menor y denunciado/a»; «…motivó constantes llamadas y mensajes de»; «…SEGUNDO.- El/la autor/a de los hechos es»; «…- Acta notarial de el/la Notario/a»; «…- Escrito remitido por el/la letrado/a»; «…s a internet identificando al/a la menor»; «…y al/ a la denunciado/a»; …

## Párrafos opcionales (9)

Inclúyelos solo si encajan en los hechos:

- - Acta notarial de el/la Notario/a [COMPLETAR] del Ilustre colegio de acerca de la existencia en internet de l…
- - Referencia on line de la web donde estaba ubicada.…
- - Escrito remitido por el/la letrado/a [COMPLETAR] al prestador de servicios a fin de que retiraran de interne…
- - Acta notarial de desaparición del contenido 10 días después de la comunicación fehaciente al prestador de se…
- - Se tome declaración al/a la menor.…
- - Se tomen declaración a los siguientes testigos que han visualizado las imágenes subidas a internet identific…
- - D/Dña [NOMBRE Y APELLIDOS]…
- - Se requiera al prestador de servicios para que certifique el contenido del escrito enviado on line para la r…
- - Se realice investigación policial acerca del ordenador del/de la menor y la posibilidad de que del mismo se …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 13 LECRIM
- art. 544 bis LECRIM
- art. 7 LO 5/2000
- art. 468.2 CP
- art. 7.1 i) LO 5/2000

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

### Formulario 0515 · Revenge porn: denuncia ante la Fiscalía de Menores

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos repetibles señalados; 8 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (DNI/NIE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Los padres de un menor, en su representación, denuncian ante la fiscalía de menores unos hechos que pueden ser constitutivos de un delito de revelación de secretos, concretamente de sexting en su modalidad de "revenge porn" del art. 197.7 CP, al haberse colgado en redes sociales imágenes de un encuentro sexual entre su hijo menor y otro menor que las subió sin el consentimiento de la víctima.

A la Fiscalía de Menores de [COMPLETAR]

D Con DNI nº [DNI/NIE] y Dª [COMPLETAR] con DNI nº [DNI/NIE] y con domicilio en [LOCALIDAD], padres de el/la menor [COMPLETAR] de [Nº] años de edad, comparecemos y, como mejor proceda en derecho, DECIMOS:

Que, por medio del presente escrito formulamos denuncia ante esta Fiscalía (1) contra [ACTO O RESOLUCIÓN] por la comisión de un delito del art. 197.7 CP, con base en los siguientes:

HECHOS

PRIMERO.- Aproximadamente hacia el mes de [COMPLETAR] de [COMPLETAR] nuestro/a hijo/a de [Nº] años y, por tanto, menor de edad, mantuvo una relación con el/la también menor y denunciado/a [COMPLETAR] durante la cual ambos mantuvieron relaciones sexuales que fueron grabadas por el/la denunciado/a. Más tarde, nuestro/a hijo/a decidió poner fin a la relación, lo que motivó constantes llamadas y mensajes de [COMPLETAR] a nuestro/a hijo/a para que no rompieran la relación. Al no querer ceder él/ella a la insistencia, el/la denunciado/a subió a las redes sociales, sin consentimiento de nuestro/a hijo/a, videos íntimos grabados en las relaciones sexuales mantenidas, (2) habiéndose difundido de forma constante estos videos desde el día [FECHA] al día en que el prestador de esos servicios on line los suprimió, tras ser requerido por los servicios de nuestro/a letrado/a por difusión de videos sexuales de menores. (3)

SEGUNDO.- El/la autor/a de los hechos es [COMPLETAR] compañero/a del colegio de nuestro/a hijo/a.

En consecuencia, y dado que consideramos a nuestro/a hijo/a víctima de un delito, lo ponemos en conocimiento de esta Fiscalía para que se sirva acordar lo pertinente para la comprobación y averiguación de los hechos y sus autores.

Dada la gravedad de los hechos se interesa que, por la vía del art. 13 LECRIM y art. 544 bis LECRIM, 2º párrafo con relación al art. 7 LO 5/2000, se adopte la medida cautelar de prohibición de comunicación de el/la denunciado/a con el/la menor por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos realizándose el preceptivo requerimiento/apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden, que como medida cautelar se postula se adopte en el auto de admisión de la denuncia, comunicándose por cualquier medio con el/la menor. (4)

Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación a la víctima a su lugar de residencia, o a cualquiera de los que frecuente, apercibiendo y requiriendo de ello a el/la denunciado/a con las advertencias legales.

TERCERO.- Se aporta como prueba de los hechos denunciados:

[OPCIONAL — incluir si procede]

- Acta notarial de el/la Notario/a [COMPLETAR] del Ilustre colegio de acerca de la existencia en internet de las imágenes con grabación notarial de las mismas en su proyección on line, con constancia del día y fecha de su existencia en internet y de su contenido preconstituido.

[OPCIONAL — incluir si procede]

- Referencia on line de la web donde estaba ubicada.

[OPCIONAL — incluir si procede]

- Escrito remitido por el/la letrado/a [COMPLETAR] al prestador de servicios a fin de que retiraran de internet el contenido ya descrito en los hechos.

[OPCIONAL — incluir si procede]

- Acta notarial de desaparición del contenido 10 días después de la comunicación fehaciente al prestador de servicios.

CUARTO.- Se interesa se practiquen las siguientes diligencias:

[OPCIONAL — incluir si procede]

- Se tome declaración al/a la menor.

[OPCIONAL — incluir si procede]

- Se tomen declaración a los siguientes testigos que han visualizado las imágenes subidas a internet identificando al/a la menor [COMPLETAR] y al/ a la denunciado/a [COMPLETAR]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D/Dña [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

- Se requiera al prestador de servicios para que certifique el contenido del escrito enviado on line para la retirada de las imágenes y la decisión adoptada y la razón de esta retirada.

[OPCIONAL — incluir si procede]

- Se realice investigación policial acerca del ordenador del/de la menor y la posibilidad de que del mismo se hayan subido a internet los videos.

En [COMPLETAR].

Firma de la madre del/de la menor:	Firma del padre del/de la menor:

NOTAS DEL FORMULARIO

(1) La denuncia se presenta ante la fiscalía de menores al ser el denunciado menor de edad.

(2) El delito conocido como "Revenge Porn" (porno de venganza) es una modalidad del "sexting" tipificado en el art. 197.7 CP y ésa es justo su finalidad: causar daños como respuesta a una decepción amorosa, pero también se ha convertido en una forma de humillación pública.

(3) Es recomendable actuar directamente con el prestador de servicios para que suprima esos contenidos de internet, aunque preconstituyendo debidamente la prueba para dejar constancia de ella, en evitación de que desaparezca su rastro de internet.

(4) La adopción de la medida cautelar de prohibición de comunicación es fundamental para evitar la reiteración delictiva mientras se sustancie el procedimiento y concluya en sentencia condenatoria con medida del art. 7.1 i) LO 5/2000. (SAP Madrid 291/2017, de 20 de noviembre, Rec. 1591/2017).

================================================================================
