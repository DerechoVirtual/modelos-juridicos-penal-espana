---
name: menor-discapacitado-defensa-propone-declare-plenario-419
description: "Redacta el escrito «Menor o discapacitado: la defensa propone que declare en el plenario» (formulario 419 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Menor o discapacitado: la defensa propone que declare en el plenario

> Formulario 0419 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] LUGAR

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 707 LECRIM
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- artículo 707 LECRIM
- art. 786.2 LECrim
- art. 785 LECrim
- art. 787.3 LECrim

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

### Formulario 0419 · Menor o discapacitado: la defensa propone que declare en el plenario

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales y solicita pruebas para practicar en el juicio oral, entre ellas que declare el menor (aunque mayor de 14 años) o discapacitado por videoconferencia en el plenario, conforme al art. 707 LECRIM.

Actualizado conforme a la LO 8/2021, con entrada en vigor a partir del 25 de junio de 2021.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de [LOCALIDAD], acusado/a en el procedimiento número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito del art. CP comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que no existe prueba alguna que evidencie la realidad de los hechos que se denuncian.

SEGUNDA.- Los hechos no son constitutivos de un delito del art. CP.

TERCERA.- Niego las correlativas. Mi representado/a no es autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser autor/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

1.- Testifical de los siguientes testigos que declararán sobre la inexistencia de la conducta de la que se le acusa por su conocimiento personal.
2.- Declaración del/ de la menor/discapacitado/a en el juicio oral. La STS 579/2019 de 26 de noviembre, Rec. 2104/2018 fija los criterios por los que el derecho de defensa hace mantener el derecho a que comparezca el menor en el juicio oral para garantizar la debida contradicción al impugnarse la documental aportada del informe médico que no acredita la realidad de un padecimiento que le permita no comparecer en el juicio oral. (1) No obstante, el párrafo segundo del artículo 707 LECRIM señala que:

«Fuera de los casos previstos en el artículo 703 bis, cuando una persona menor de dieciocho años o una persona con discapacidad necesitada de especial protección deba intervenir en el acto del juicio, su declaración se llevará a cabo, cuando resulte necesario para impedir o reducir los perjuicios que para ella puedan derivar del desarrollo del proceso o de la práctica de la diligencia, evitando la confrontación visual con la persona inculpada. Con este fin podrá ser utilizado cualquier medio técnico que haga posible la práctica de esta prueba, incluyéndose la posibilidad de que los testigos puedan ser oídos sin estar presentes en la sala mediante la utilización de tecnologías de la comunicación accesible.»

Y en este caso, al no existir informe que evidencie una "victimización secundaria" del/de la menor de entre 14 y 8 años/discapacitado/a se le cite a juicio oral para ser interrogado/a, aunque, en base al citado precepto, la declaración se haga por videoconferencia, por resultar necesario para impedir o reducir los perjuicios que para el/la menor/discapacitado/a puedan derivar del desarrollo del proceso o de la práctica de la diligencia, evitando la confrontación visual con el/la acusado.

3.- Se impugna la documentación aportada médica y psicológica que no evidencia en modo alguno el derecho que reclama la acusación de que el/la menor/discapacitado/a no declare en el juicio oral.

Por lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) A partir del 25 de junio de 2021, fecha de entrada en vigor de la reforma operada por la LO 8/2021, de 4 de junio, se permite que pueda interesarse la declaración de menores de edad de entre 14 y 18 años, pero no de menores de 14, para los que vale la prueba preconstituida reproducida en el juicio oral. STS 579/2019 de 26 de noviembre de 2019, Rec. 2104/2018 y STS 321/2020 de 17 de junio.

Lo normal es que la acusación proponga como prueba la reproducción en el juicio oral de la declaración del menor de 14 años como prueba preconstituida. Pero si la acusación no solicitó en su escrito de acusación que se reproduzca la declaración del menor grabada como prueba preconstituida y simplemente hizo mención a la "reproducción de la documental en el plenario" y lo hace después del escrito de defensa, el letrado de la defensa podrá proceder a presentar escrito instando a que comparezca en el juicio oral el menor de entre 14 y 18 años.

Nótese que la proposición de prueba pueden hacerla las partes hasta el mismo día del juicio ex art. 786.2 LECrim. (hasta el 2 de abril de 2025), en la audiencia preliminar del art. 785 LECrim. o al comienzo del juicio ex art. 787.3 LECrim. (desde el 3 de abril de 2025, fecha de entrada en vigor de la LO 1/2025)

================================================================================
