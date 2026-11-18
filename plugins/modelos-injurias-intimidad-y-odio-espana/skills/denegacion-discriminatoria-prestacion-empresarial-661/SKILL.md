---
name: denegacion-discriminatoria-prestacion-empresarial-661
description: "Redacta el escrito «Denegación discriminatoria de una prestación empresarial o profesional: querella» (formulario 661 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Denegación discriminatoria de una prestación empresarial o profesional: querella

> Formulario 0661 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] ESTADO CIVIL
- [ ] CALLE
- [ ] FECHA (3 veces)
- [ ] HORA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…del/de la menor de edad»; «…dentro de este partido, concretamente en»; «…, de profesión [PROFESIÓN], vecinos de»; «…, ambos como padres del/de la menor»; «…pietario/a del establecimiento comercial»; «…el/la hijo/a de los querellantes»; «… que les ayudan en el centro asistencial»; «…Derecho penal de un Estado democrático-"»

## Elecciones que hay que hacer

- padre / madre
- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la querellado/a sobre los hechos de la querella.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Documental: interesando se requiera al local para que aporte las cintas de grabación del establecimiento qu…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 512 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- art. 512 CP
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC

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

### Formulario 0661 · Denegación discriminatoria de una prestación empresarial o profesional: querella

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 29 campos de relleno marcados en blanco; 4 huecos del original que se habían perdido sin marca, marcados (FECHA, HORA, NOMBRE Y APELLIDOS, Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento del juez unos hechos que presentan los caracteres del delito de denegación discriminatoria de una prestación del artículo 512 CP, al haber impedido a una persona el acceso a un establecimiento comercial por razón de su discapacidad

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], como [ELEGIR: padre / madre] del/de la menor de edad [COMPLETAR], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 y siguientes de la Ley de Enjuiciamiento Criminal contra D./Dña. [NOMBRE Y APELLIDOS], por el delito del art. 512 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en [COMPLETAR].

SEGUNDO.- Los querellantes son D. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, y Dña. [NOMBRE Y APELLIDOS], de profesión [PROFESIÓN], vecinos de [COMPLETAR], con domicilio en [LOCALIDAD], ambos como padres del/de la menor [COMPLETAR].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], con domicilio en [LOCALIDAD]. (2)

CUARTO.- Los hechos que motivan la querella y que presentan caracteres delictivos son los siguientes: El/La querellado/a D./Dña. [NOMBRE Y APELLIDOS] es el/la propietario/a del establecimiento comercial [COMPLETAR] sito en la calle [CALLE] dedicado a negocio de hostelería. El día [FECHA] el/la hijo/a de los querellantes [COMPLETAR], que padece la enfermedad de síndrome de Down, accedió al local que no tenía prohibido acceso a menores, con otros/as amigos/as pertenecientes a un centro de ayuda a esta enfermedad, a fin de celebrar el cumpleaños de uno/a de ellos/as y lo hacían acompañados/as de dos trabajadores/as sociales que les ayudan en el centro asistencial [COMPLETAR]. Cuando el/la encargado/a del establecimiento se les acercó invitándoles a que se marcharan del local, les señaló que a esa hora entraban muchos clientes y necesitaban espacio, comunicándole el/la trabajador/a social D./Dña. [NOMBRE Y APELLIDOS] que ellos iban a consumir igual que cualquier otro cliente y que no se iban a marchar, momento en el que se acercaron dos personas más y les conminaron a abandonar el local porque el dueño del establecimiento así lo había ordenado, pese a la advertencia de que les iban a denunciar.

QUINTO.- Los hechos expuestos revisten los caracteres de un delito del art. 512 CP del que presuntamente es culpable el/la querellado/a titular del local (3).

SEXTO.- Como diligencias a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la querellado/a sobre los hechos de la querella.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

Declaración del/de la querellante.

- Que se reciba declaración a los/as encargados/as del local que se encontraban trabajando ese día.

- D./Dña [NOMBRE Y APELLIDOS], trabajador/a social presente en el lugar de los hechos y su compañero/a D./Dña. [NOMBRE Y APELLIDOS].

- Exploración de los/as menores que acudieron al local el día de los hechos:

[OPCIONAL — incluir si procede]

.- Documental: interesando se requiera al local para que aporte las cintas de grabación del establecimiento que grabaron la secuencia ocurrida el día [FECHA] a las [HORA] horas.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se exija fianza en la cantidad de [IMPORTE] euros para hacer frente a las responsabilidades civiles que se deriven y que se una e incorpore en la tramitación de las presentes diligencias.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Se interesa como medida urgente que se suspenda cautelarmente de sus funciones al/a la querellado/a para evitar que vuelva a cometer el delito, dado que, además, la pena que lleva aparejada es la de inhabilitación especial para para el ejercicio de profesión, oficio, industria o comercio e inhabilitación especial para profesión u oficio educativos, en el ámbito docente, deportivo y de tiempo libre.

SUPLICO A LA SECCIÓN:: Que acuerde la medida cautelar solicitada.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN:: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia.

Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) Se castiga en el art. 512 CP las conductas ejercidas por personas con establecimiento abierto al público que no dejasen acceder a los mismos a personas por razón de su ideología, religión o creencias, su situación familiar, pertenencia a una etnia, raza o nación, su origen nacional, su sexo, edad, orientación o identidad sexual o de género, razones de género, de aporofobia o de exclusión social, la enfermedad que padezca o su discapacidad. Es decir, por razones que atentan contra los derechos fundamentales de las personas. La LO 8/2021, de 4 de junio, ha añadido las relativas a su origen nacional, la edad, orientación o identidad sexual o de género, de aporofobia o de exclusión social como factores que son determinantes de la conducta discriminatoria.

No se admite en estos casos como defensa o excusa para impedir el acceso a estos establecimientos la mención de la "reserva del derecho de admisión", ya que este lo es para cuando una persona se comporta en un establecimiento comercial de forma indebida de tal manera que sea preciso obligarle a abandonar el establecimiento comercial.

Ello comporta un hecho delictivo ante una práctica que se extiende por algunas personas impidiendo el acceso a sus establecimientos a otras por razón de su discapacidad, religión, raza, creencias, sexo, etc.

Referencias jurisprudenciales en supuestos del art. 512 CP:

SAP Albacete 186/2017, de 27 de Abril, Rec. 1092/2016. "Denegación de entrada en local de ocio a clientes negros. No se justifica la conducta por el ejercicio del derecho de admisión."

SAP Barcelona de 8 de Julio de 2014, Rec. 75/2014 "Es evidente que se les denegó la entrada al local, discriminadamente por razón de orden sexual y ello comporta el tipo penal del articulo 512 por el que ha resultado condenado el acusado. Finalmente solo cabe añadir que el dato de que el acusado tenga una hija transexual, no excluye los hechos delictivos, pues lo cierto es que denegó la entrada por dicha condición a las perjudicadas."

SAP Valencia 119/2010, de 23 de Febrero, Rec. 16/2010 "Se condena por haber denegado, en una ocasión, una determinada prestación o servicio a unas personas que tenía derecho y habérselo denegado, en concreto, a causa de su discapacidad psíquica, y ello es así, porque, como afirma el Tribunal Supremo "el art. 512 CP no describe un tipo de autor - inadmisible en el Derecho penal de un Estado democrático-" [COMPLETAR], describiéndose en el mismo una determinada conducta punible, sea el que fuera quien la lleve a cabo, que encaja con la enjuiciada en autos (STS 1089/1998, de 29 de Septiembre, Rec. 3352/1997).

================================================================================
