---
name: pharming-estafa-informatica-phishing-defensa-scammer-667
description: "Redacta el escrito «Pharming y estafa informática (phishing): defensa del scammer o del mulero» (formulario 667 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pharming y estafa informática (phishing): defensa del scammer o del mulero

> Formulario 0667 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…uno en torno a la responsabilidad civil.»

## Elecciones que hay que hacer

- pharming y falsedad en documento mercantil (si se trata del scammer) / estafa informática (si se trata del mulero

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.2 CP
- art. 392 y 390 CP
- art. 249.1 a) CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 77 CP
- arts. 392 CP
- art. 390 CP
- arts. 249.1 a) y 250.6 CP
- artículo 249.1 a) CP
- artículo 249.1 a) del Código Penal
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

### Formulario 0667 · Pharming y estafa informática (phishing): defensa del scammer o del mulero

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 3 bloques de opciones sin texto dejados en blanco con sus rótulos; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales negando ser autor de los delitos de pharming del art. 197.2 CP y falsedad en documento mercantil del art. 392 y 390 CP (en el caso de la defensa del scammer) o del delito de estafa informática del art. 249.1 a) CP (en el caso de la defensa del mulero)

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el delito de [ELEGIR: pharming y falsedad en documento mercantil (si se trata del scammer) / estafa informática (si se trata del mulero]) (1) comparezco ante este órgano judicial (2) y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (3) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original]

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original]

TERCERA.- Niego las correlativas. Mi representado/a no es autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el autor/la autora.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

[COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (4)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de la defensa del mulero / Si se trata de la defensa del scammer — el texto de cada opción no venía en el formulario original]

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Pharming es la explotación de una vulnerabilidad en el software de los servidores DNS (Domain Name System) o en el de los equipos de los propios usuarios, que permite a un atacante redirigir un nombre de dominio (domain name) a otra máquina distinta. De esta forma, un usuario que introduzca un determinado nombre de dominio que haya sido redirigido, accederá en su explorador de internet a la página web que el atacante haya especificado para ese nombre de dominio, que según Rey Huidobro se trataría de la web delincuente donde, confiado, el usuario realiza sus movimientos con total tranquilidad en la errónea esperanza de estar en la página original y donde deja al descubierto claves y datos personales (principalmente bancarios o financieros), que luego usa el delincuente para estafarle.

Según este autor la técnica pharming se utiliza normalmente para realizar ataques phishing, redirigiendo el nombre de dominio de una entidad de confianza a una página web, en apariencia idéntica, pero que en realidad ha sido creada por el atacante para obtener los datos privados del usuario, generalmente (y es lo que nos interesa) datos bancarios.

La palabra pharming deriva del término farm (granja en inglés) y está relacionada con el término phishing, utilizado para nombrar la técnica de ingeniería social que, mediante suplantación de correos electrónicos o páginas web, intenta obtener información confidencial de los usuarios, desde números de tarjetas de crédito hasta contraseñas.

El origen de la palabra se halla en que una vez que el atacante ha conseguido acceso a un servidor DNS o varios servidores (granja de servidores o DNS), se dice que ha hecho un pharming.

¿Dónde se ingresa el dinero del estafado?

Según Rey Huidobro (artículo «La estafa informática: relevancia penal del phising y el pharming», 2012) las cuentas beneficiarias de las transferencias pueden ser: cuentas nacionales abiertas con identidad falsa (generalmente se utilizan pasaportes extranjeros falsificados), cuentas en el extranjero, casos estos que resultan de muy difícil persecución y finalmente, lo que suele ser más común, cuentas de muleros, que reciben este apodo heredado de los «muleros» del narcotráfico. Son personas a las que han ofrecido un empleo que consiste en intermediar en cobros y pagos entre empresas, con frecuencia internacionalmente. Es requisito imprescindible para el postulante ser titular de una cuenta bancaria y tener disponibilidad para acudir inmediatamente a su oficina bancaria en cuanto sea requerido para ello. El trabajo consiste en recibir transferencias en su cuenta, y siguiendo instrucciones telefónicas o por correo electrónico hacerlas efectivas en su oficina bancaria y reenviarlas al destinatario que en cada momento se le señale mediante una remesadora (Wester Union o Money Gramm, principalmente) que también se le indica.

Las webs que ofertan este tipo de empleos suelen estar bien construidas y, para que el engaño sea creíble, el demandante pasa un riguroso proceso de selección (que siempre supera) y recibe por email una copia de su contrato de trabajo perfectamente cumplimentada y firmada teniendo todo el proceso una apariencia formal de legalidad.

¿Quién es el mulero?

Los muleros forman parte del final de la cadena de producción de las estafas en internet. Son los encargados de materializar buena parte de este tipo de engaños, siempre y cuando el sistema finalice con la emisión de una transferencia. Mientras que el verdadero promotor de este tipo de estafas permanece en el anonimato, el mulero hace de cabeza visible en el fraude, ya que no oculta su identidad

Sería una especie de testaferro, al modo de los administradores de hecho en los delitos societarios, aunque corren el riesgo de ser descubiertos y puestos a disposición judicial ante la investigación llevada a cabo por la Brigada de delitos tecnológicos.

En estos casos puede haber dos autores: el Scammer que permite estafar a la víctima y que entre en una web pensando que es aquella donde quería acceder y opera con sus claves y el mulero o persona a donde se envía el dinero.

Eloy Velasco entiende que la actuación de los scammer, previa a la realización de la transferencia inconsentida, supone, además, un concurso de delitos del art. 77 CP con el de falsedad en documento mercantil de los arts. 392 CP y art. 390 CP—por la Web falsificada — y con un delito de descubrimiento de secretos, del art. 197.2 CP—por la captación inconsentida y artificiosa del password y la contraseña—.

El mulero comete un delito de estafa de los arts. 249.1 a) y 250.6 CP, considerando que intervienen como cooperadores necesarios, pues su actuación contribuye necesariamente a la producción del resultado y es una auténtica «conditio sine qua non para que la estafa llegue a consumarse, y por hacerlo de común acuerdo con el autor material de la misma». (STS 51/2020, de 17 de febrero, Rec. 3945/2019, SAP 16.ª Madrid de 71/2006 de 6 Jul. 2006, Rec. 2/2006)

Si lo defraudado excede de más de 50.000 euros se aplicará la pena del art. 250.1.5º CP. Y la pena iría de 1 a 6 años de prisión y multa de seis a doce meses.

Respecto de la conducta del scammer y como apunta Luis Fernando Rey Huidobro (artículo «La estafa informática: relevancia penal del phising y el pharming», 2012) la manipulación informática o el artificio semejante integradora de la estafa no se dará en la primera fase de obtención ilícita de las claves de acceso a la cuenta bancaria, con la falsificación de páginas electrónicas (y posible modificación de direcciones DNS o los archivos «hots» que contienen las direcciones IP´s), ya que dicha conducta no ocasiona directamente ningún traspaso patrimonial ilícito, sino que es una manipulación realizada para obtener subrepticiamente las claves de acceso a las cuentas bancarias. Dichas manipulaciones quedarían fuera del concepto del artículo 249.1 a) CP, aunque podrían dar lugar a otras responsabilidades penales como, por ejemplo, por delito de falsedad documental o por descubrimiento y revelación de secretos. No ocurre lo mismo en la segunda fase, de utilización no consentida de las claves de acceso a la cuenta bancaria y firma electrónica para realizar la transferencia no autorizada. Aquí sí se da una manipulación informática que ocasiona directamente el traspaso patrimonial no consentido, plenamente insertable en el tenor literal del artículo 249.1 a). Esta versión está justificada tanto desde la interpretación objetiva como teleológica del mencionado precepto, teniendo en cuenta además el concepto de manipulación informática acogido en los tratados internacionales. En consecuencia, podemos decir que estas formas de criminalidad patrimonial (phising, pharming), consistentes en la realización de transferencias bancarias en perjuicio de terceros, mediante la utilización no consentida de datos personales de acceso y firma electrónica, son perfectamente insertables en el tipo del artículo 249.1 a) del Código Penal, que sanciona la estafa informática. Ahora bien, claramente respecto del mulero, pero el scammer cometería falsedad y descubrimiento y revelación de secretos.

(2) ¿Dónde se entiende cometido el delito de pharming?

Es aplicable aquí el Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005, que acoge el principio de ubicuidad, de tal modo que el delito se comete en todas las jurisdicciones en las que se haya realizado algún elemento del tipo, en consecuencia, el Juez de cualquiera de ellas que primero haya iniciado las actuaciones procesales será, en principio, competente para la instrucción de la causa (en este sentido Autos de la Sala Segunda del TS de 4-11-2005, 11-1-2008 y 6-4-2011, este último en un supuesto de phishing, donde las IP de los correos electrónicos remitidos se localizan en Turquía).

(3) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 Lecrim por el letrado de la administración de Justicia.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr)

================================================================================
