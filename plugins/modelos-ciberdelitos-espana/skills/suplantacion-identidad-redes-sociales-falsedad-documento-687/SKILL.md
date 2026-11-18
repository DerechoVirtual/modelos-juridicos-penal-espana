---
name: suplantacion-identidad-redes-sociales-falsedad-documento-687
description: "Redacta el escrito «Suplantación de identidad en redes sociales (falsedad en documento privado): defensa» (formulario 687 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplantación de identidad en redes sociales (falsedad en documento privado): defensa

> Formulario 0687 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… 461/2017, de 25 de mayo, Rec. 706/2017.»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental: contrato de arrendamiento del inmueble donde se llevó a cabo la diligencia de entrada y registr…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 395 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 401 CP
- art. 26 CP

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

### Formulario 0687 · Suplantación de identidad en redes sociales (falsedad en documento privado): defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado/a en un procedimiento abreviado presenta sus conclusiones frente a la acusación de falsedad en documento privado del art. 395 CP por suplantación de identidad en una red social, basándose en que no se ha podido demostrar que él haya sido quien ha usado el ordenador del que proviene la IP desde donde se cometieron los hechos.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de falsedad en documento privado por usurpación de identidad en redes sociales, (1) comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (2) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo lo que se le imputa ya que en el inmueble donde habita el ordenador atribuido al acusado, y desde donde presuntamente se ha podido cometer el delito de suplantación de identidad, es utilizado por varias personas, conviviendo en el momento de los hechos hasta cinco personas que solo han sido traídas al proceso penal como testigos, limitándose a negar la autoría, al igual que lo hace el acusado, pero, sin embargo, atribuyéndose la autoría a este sin más pruebas que el origen de un ordenador que es utilizado por muchas personas, incluso por amigos y conocidos de los que habitan en el inmueble, al ser el único ordenador existente. Además, el inmueble no está alquilado por el acusado, sino por dos personas que firmaron el contrato de arrendamiento. (1)

SEGUNDA.- Los hechos no son constitutivos de un delito de falsedad en documento privado.

TERCERA.- Niego las correlativas. Mi representado no es el autor del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado con todos los pronunciamientos favorables, por no ser el autor.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical: interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto] (todos los que residen en el inmueble y personas que en algún momento han podido utilizar el ordenador):

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental: contrato de arrendamiento del inmueble donde se llevó a cabo la diligencia de entrada y registro policial (4) en el que no consta la identidad del acusado.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Se ha intentado ubicar la persecución de este tipo de hechos en el delito del art. 401 CP, que sanciona al que usurpare el estado civil de otro será castigado con la pena de prisión de seis meses a tres años. No obstante, la doctrina y la jurisprudencia han puesto de manifiesto las serias dificultades para perseguir estos hechos antes expuestos por este tipo penal. Y ello porque, aunque aparentemente se trataría de una usurpación de la identidad de otra persona para crear ese perfil de otro, la jurisprudencia lo relaciona con la usurpación del "estado civil", que no se produce en estos supuestos. Nótese que si se tratara de un perfil falso de alguien que no existe no habría problema, porque el autor está creando un perfil falso de una identidad supuesta para enmascararse en esa identidad para que no se conozca su autoría.

En estos casos podría acudirse a la vía de considerar los supuestos de suplantación de identidad como un delito de falsificación de documento del art. 395 CP. Y ello porque los servicios prestados por Internet suelen estar soportados por un contrato mercantil, y la página web no deja de ser un documento, aunque sea electrónico, por lo que el falseamiento de los datos implica que se ha falsificado un documento mercantil. Además, el art. 26 CP considera documento todo soporte material que exprese o incorpore datos, hechos o narraciones con eficacia probatoria o cualquier otro tipo de relevancia jurídica, y, por lo tanto, no solo el documento papel, sino también los archivos electrónicos, han de ser considerados documentos, al contener información con aquellas características.

Se configura la creación de un perfil de una red social como un "archivo electrónico", y, por consecuencia, como un documento, de tal manera que si creamos ese perfil a nombre de otra persona se estará actuando de forma falsaria y faltando a la verdad en la identidad de la persona que ha abierto ese perfil, y se hace pasar por ella, por lo que no tendrá cabida en el art. 401 CP por no suplantarse "el estado civil", pero sí que se estará cometiendo una falsedad en "archivo electrónico". Así lo ha entendido la Audiencia Provincial de Madrid en su Auto AP Madrid 461/2017, de 25 de mayo, Rec. 706/2017.

[COMPLETAR]

Para averiguar la autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia. Pornografía infantil, estafas y fraudes por Internet, fraudes en el uso de las comunicaciones, ataques cibernéticos, piratería...

La Brigada de Investigación Tecnológica está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF) que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

(2) Este escrito debe presentarse en el plazo de 10 días desde que se recibe el escrito de acusación.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

(4) Podría ocurrir que a la hora de acceder a determinados datos para conocer la autoría la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a LECRIM y ss, introducido por la LO 13/2015, para poder conseguir pruebas en casos de delitos cometidos por medio de la informática.

================================================================================
