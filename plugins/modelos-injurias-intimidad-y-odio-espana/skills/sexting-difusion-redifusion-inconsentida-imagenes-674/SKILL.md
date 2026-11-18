---
name: sexting-difusion-redifusion-inconsentida-imagenes-674
description: "Redacta el escrito «Sexting (difusión o redifusión inconsentida de imágenes por internet): defensa» (formulario 674 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sexting (difusión o redifusión inconsentida de imágenes por internet): defensa

> Formulario 0674 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…imo lugar tras la práctica de la prueba.»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso del acusado del delito del art. 197.7 CP pfo 1º y 3º / En caso del acusado del delito del art. 197.7 CP pfo 2º — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- .- Declaración de los siguientes testigos, que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental. Se aporta:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 197.3 CP

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

### Formulario 0674 · Sexting (difusión o redifusión inconsentida de imágenes por internet): defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales en procedimiento abreviado negando que los hechos sean constitutivos de un delito de sexting del art. 197.7 CP, para el caso del acusado de difundir imágenes sin consentimiento pero obtenidas con la anuencia de la querellante y para el caso del acusado de redifundir esas imágenes sin autorización.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador de los Tribunales, en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de sexting del art. 197.7 CP (1), comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (2) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso del acusado del delito del art. 197.7 CP pfo 1º y 3º / En caso del acusado del delito del art. 197.7 CP pfo 2º — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Los hechos no son constitutivos de un delito de sexting.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

1.- La declaración del acusado será en último lugar tras la práctica de la prueba. [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Declaración de los siguientes testigos, que deberán ser citados [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental. Se aporta:

- Correo electrónico en el que le comunicaba que quería modificar la pensión. (4)
- Correo electrónico en el que le envía que iba a subir el video si él/ella no se oponía.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Se castiga en el art. 197.7 CP, como delito de sexting, introducido en el CP en la LO 1/2015 al que, sin autorización de la persona afectada, difunda, revele o ceda a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros, cuando la divulgación menoscabe gravemente la intimidad personal de esa persona.

La pena se impondrá en su mitad superior cuando los hechos hubieran sido cometidos por el cónyuge o por persona que esté o haya estado unida a él por análoga relación de afectividad, aun sin convivencia, la víctima fuera menor de edad o una persona con discapacidad necesitada de especial protección, o los hechos se hubieran cometido con una finalidad lucrativa.

Se trata de un tipo penal que exige la existencia de tres elementos concurrentes:

1.- No consentimiento de la víctima a la difusión de una grabación obtenida con consentimiento de ambos. (Si tampoco existiera consentimiento en la grabación se sanciona con la pena prevista en el art. 197.3 CP de dos a cinco años de prisión).

En este caso la carga de la prueba de la existencia del consentimiento del afectado en difundir las imágenes correspondería al acusado al efectuar el descargo de que la víctima fue la que prestó su consentimiento a que el video o las imágenes se trasladaran a terceros y/o difundieran, ya que de lo contrario se trataría de una prueba diabólica al no poder obligarse a la víctima a que ella probara que «no prestó el consentimiento a que el video se difundiera». En cualquier caso, resultará obvio pensar que determinados videos o imágenes no están autorizadas normalmente a que se difundan, de ahí que se tenga que exigir la prueba del consentimiento al acusado si así lo alega.

2.- La conducta que se sanciona es la de difundir, revelar o ceder a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros.
3.- Que la divulgación menoscabe gravemente la intimidad personal de esa persona. No debe perderse de vista que esta exigencia es un elemento del tipo, por lo que, si se efectúa una difusión de imágenes, pero no llega a considerarse que ello supone una afectación o menoscabo a su intimidad el hecho no será delito. Pero es que el bien jurídico protegido por este delito es, precisamente, la intimidad, y en conjunción con la propia imagen. Pero se exige no una mera afectación a ambas, sino que esta sea grave, de lo que se debe concluir que no se podrá derivar al ámbito de la persecución penal cualquier hecho de divulgación de imágenes o videos, sino aquellos que menoscaben de forma grave esa intimidad personal de la víctima. Se trata de un elemento valorativo del juez, lo que puede ser objeto y materia del recurso en casos de condena.

La defensa podría incidir en este aspecto para desarticular un elemento del tipo entendiendo que no se ha producido tal ataque a la intimidad.

Hasta la reforma operada por LO 10/2022, de garantía integral de la libertad sexual, vigente desde el 7 de octubre de 2022, no estaba sancionado nada más que el primer envío, pero no los reenvíos sucesivos, habida cuenta que el art. 197.7 CP no se remitía al art. 197.3 CP que sí lo sancionaba, lo que se resuelve con el párrafo 2º del art. 197.7 CP que sí sanciona el segundo reenvío de quien ha recibido esa imagen sin autorización, tampoco, de la persona afectada.

(2) Este escrito debe presentarse en el plazo de 10 días desde que se recibe el escrito de acusación.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

(4) El correo electrónico se aporta impreso donde consta la dirección de email del remitente y destinatario a fin de acreditar la referencia de origen y destino del envío. Solo si existiese un medio impugnatorio de la parte a quien perjudique estaría obligado la parte que lo aportó a proponer para el acto del plenario una pericial informática que valide su existencia.

================================================================================
