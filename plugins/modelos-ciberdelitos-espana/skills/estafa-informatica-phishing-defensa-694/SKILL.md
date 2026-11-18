---
name: estafa-informatica-phishing-defensa-694
description: "Redacta el escrito «Estafa informática (phishing): defensa» (formulario 694 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (phishing): defensa

> Formulario 0694 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS] que reside en el inmueble y ha podido utilizar el ordenador.…
- .- Pericial caligráfica respecto de la firma del contrato de cuenta corriente para que comparezca al juicio el…
- .- Documental consistente en:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0694 · Estafa informática (phishing): defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 3 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa, en un procedimiento abreviado, presenta sus conclusiones ante acusación de delito de estafa informática (phising) del art. 249.1 a) CP, argumentando que él no es el autor, a pesar de que los hechos se cometieron desde un ordenador que se encontraba en su domicilio.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a, Procurador de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de estafa informática, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo lo que se le imputa (2), ya que en el inmueble donde habita, el ordenador atribuido al/a la acusado/a desde donde presuntamente se ha podido cometer el delito de estafa informática es utilizado por varias personas, conviviendo en el momento de los hechos hasta cinco personas que solo han sido traídas al proceso penal como testigos, limitándose a negar la autoría al igual que lo hace el acusado, pero, sin embargo, atribuyéndose la autoría a este sin más pruebas que el origen de un ordenador que es utilizado por muchas personas, incluso por amigos y conocidos de los que habitan en el inmueble, al ser el único ordenador existente en él. Además, el inmueble no está alquilado por el/la acusado/a, sino por dos personas que firmaron el contrato de arrendamiento.

Respecto a la identidad de la cuenta corriente se abrió por una persona a mi nombre, pero en la entidad bancaria nadie ha podido recordar si el/la acusado/a fue personalmente quien abrió la cuenta corriente. De suyo, el importe extraído permanece en la cuenta, que ha sido intervenida por orden judicial en la fase de instrucción, con lo que no hubo ni tan siquiera disposición de la suma extraída con la contraseña del perjudicado, no siendo responsabilidad del/de la acusado/a la autoría, porque se considera hasta perjudicado por haberse suplantado su personalidad al abrirse una cuenta a su nombre sobre la que se habrá utilizado su identidad. Con ello, al no conocer la existencia de esa cuenta, no se ha podido disponer de fondos, como se ha podido comprobar. (3)

SEGUNDA.- Los hechos no son constitutivos de un delito de estafa informática del art. 249.1 a) CP, ni de ningún otro.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede, ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el autor.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (4)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical: interrogatorio de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] que reside en el inmueble y ha podido utilizar el ordenador.

- D./Dña. [NOMBRE Y APELLIDOS] de la entidad bancaria donde se abrió la cuenta a la que se transfirió el importe defraudado.

[OPCIONAL — incluir si procede]

.- Pericial caligráfica respecto de la firma del contrato de cuenta corriente para que comparezca al juicio el perito D./Dña. [NOMBRE Y APELLIDOS] autor/a del dictamen pericial.

[OPCIONAL — incluir si procede]

.- Documental consistente en:

- Contrato de arrendamiento en el que no consta la identidad del/de la acusado/a.
- Contrato de apertura de cuenta corriente para que se coteje la firma del contrato con la del acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde que se recibe el escrito de acusación.

(2) La estafa informática regulada hasta el 11 de enero de 2023 en el art. 248.2 a y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP, consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son:

- La manipulación informática y artificio semejante,
- Transferencia patrimonial no consentida por el titular del mismo,
- ánimo de lucro, y
- perjuicio en tercero.

Modalidades típicas de estafas informáticas son el "phishing" y el "pharming" que son dos tipos de fraudes informáticos cuya finalidad común es la de apoderarse de información personal de un usuario de Internet, para acceder a sus cuentas de correo o de redes sociales y obtener adicionalmente datos de sus contactos virtuales, a fin de comerciarlos ilícitamente, o bien, conseguir claves en su banco (por medio de internet) para de este modo ingresar a las cuentas corrientes bancarias de los titulares y disponer de su dinero en las cuentas realizando una operación de transferencia de activos a un tercero que se denomina "mule".

Una vez detectada la IP la defensa podría apelar a la no acreditación de la autoría material al poder utilizarse este ordenador por distintas personas creando la "duda razonable" en el juez acerca de la realidad de la autoría del acusado.

(3) En estos casos de estafas informáticas los agentes de la policía judicial podrán haber detectado el número de la dirección IP del ordenador desde el que se ha cometido la estafa informática y tras ello, por la vía del art. 588 ter k LECRIM, se habrá interesado la orden judicial para la averiguación de la identidad del autor.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

================================================================================
