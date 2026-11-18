---
name: espionaje-informatico-descubrir-secretos-empresa-612
description: "Redacta el escrito «Espionaje informático para descubrir secretos de empresa: querella» (formulario 612 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Espionaje informático para descubrir secretos de empresa: querella

> Formulario 0612 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dentro de este partido, concretamente en»; «… edad, representante legal de la empresa»; «…, titular de la empresa»; «… de descubrir los secretos de la empresa»; «…me pericial de la empresa de informática»; «…s de una llamada telefónica recibida por»; «…bió la llamada de la empresa informática»; «…de entrada por orden judicial en la nave»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se han revelado, difundido o cedido los secretos descubiertos / Si se han revelado, difundido o cedido los secretos descubiertos — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- (Si se revelan los secretos descubiertos)…
- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Que se oficie a la brigada de delitos tecnológicos mediante orden judicial para que compruebe la identidad …
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial del/de la autor/a del dictamen pericial informático que avala el acceso ilegal al sistema informát…
- 1.- Sobre la situación personal del/de la querellado/a, que se proceda a su detención y prisión provisional, o…
- .- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querell…
- .- Se interesa la orden de entrada por orden judicial en la nave [COMPLETAR] sita en [LOCALIDAD] para la oport…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 278.1 y 2 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 277 de la LECRIM
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 278.2 CP

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

### Formulario 0612 · Espionaje informático para descubrir secretos de empresa: querella

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 8 párrafos opcionales señalados; 30 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se denuncian unos hechos que presentan los caracteres de un delito contra el mercado y los consumidores del art. 278.1 y 2 CP por acceder al sistema de información de una empresa, vulnerando sus sistemas de protección, para descubrir sus secretos.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS] por el delito del art. 278.1 y 2 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 de la LECRIM y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, representante legal de la empresa [COMPLETAR], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con domicilio en [LOCALIDAD], titular de la empresa [COMPLETAR]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes: El/La querellado/a D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, con total intención de descubrir los secretos de la empresa [COMPLETAR], de los que es titular el/la querellante ha accedido intencionadamente, y por medios tecnológicos, a su sistema de información vulnerando los sistemas de protección que impiden ese acceso sin autorización alguna del/de la querellante. Esta información se ha obtenido mediante un informe pericial de la empresa de informática [COMPLETAR] con la que se tiene contratada la cobertura informática de la citada empresa, constando el apoderamiento de datos y su alteración. La medida de seguridad de acceso vulnerada fue implantada por la citada empresa, quien nos informó inmediatamente de haber detectado la vulneración del acceso a la información, a través de una llamada telefónica recibida por [COMPLETAR] el día [FECHA].

[OPCIONAL — incluir si procede]

(Si se revelan los secretos descubiertos)

Estos datos se han cedido a terceros, habida cuenta que por medio del/de la empresario/a D./Dña. [NOMBRE Y APELLIDOS] se nos ha facilitado información acerca de la oferta de estos datos a cambio de precio, a lo que se accedió para obtener pruebas por el/la citado/a empresario/a, a fin de comprobar cuáles eran los datos que se habían obtenido y que fueron entregados a su legítimo titular por el tercero.

QUINTO.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no se han revelado, difundido o cedido los secretos descubiertos / Si se han revelado, difundido o cedido los secretos descubiertos — el texto de cada opción no venía en el formulario original]

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Que se oficie a la brigada de delitos tecnológicos mediante orden judicial para que compruebe la identidad del ordenador del/de la querellado/a para acreditar la autoría del punto desde donde se perpetró el delito.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- D./Dña. [NOMBRE Y APELLIDOS], empleado/a de la empresa que recibió la llamada de la empresa informática [COMPLETAR] que detectó el acceso inconsentido.

- D./Dña. [NOMBRE Y APELLIDOS], titular de la empresa a la que le fueron ofrecidos los datos.

[OPCIONAL — incluir si procede]

.- Pericial del/de la autor/a del dictamen pericial informático que avala el acceso ilegal al sistema informático vulnerado.

- D./Dña. [NOMBRE Y APELLIDOS].

SÉPTIMO.- Como medidas cautelares se solicitan las siguientes:

[OPCIONAL — incluir si procede]

1.- Sobre la situación personal del/de la querellado/a, que se proceda a su detención y prisión provisional, o se le exija fianza por la libertad en la cantidad de [IMPORTE] euros y que se una e incorpore en la tramitación de las presentes diligencias.

[OPCIONAL — incluir si procede]

.- Para garantizar las responsabilidades civiles derivadas del delito, solicitamos se requiera al/a la querellado/a para que constituya fianza por importe de [IMPORTE]. euros y, en su defecto, se proceda al embargo de sus bienes en cantidad suficiente para atender a dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

[OPCIONAL — incluir si procede]

.- Se interesa la orden de entrada por orden judicial en la nave [COMPLETAR] sita en [LOCALIDAD] para la oportuna incautación de los datos obtenidos, a fin de comprobar dónde se hayan servido u ofrecido los mismos, previo control de los libros comerciales de clientes.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Es un delito de consumación anticipada. Basta la acción de apoderamientodirigida a alcanzar ese descubrimiento. Conseguir el conocimiento del secreto pertenece a la fase posterior de agotamiento de la infracción. La estructura del tipo es la propia de los delitos mutilados de dos actos: una vez constatada la intención antijurídica de descubrir el secreto, el tipo se consuma con la conducta de apoderamiento, interceptación o utilización de artificios técnicos, sin necesidad de que concurra un efectivo descubrimiento. Su difusión, revelación o cesión a terceros constituye la figura agravada del art. 278.2 CP.

================================================================================
