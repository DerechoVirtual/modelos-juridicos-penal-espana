---
name: pharming-estafa-informatica-phishing-acusacion-664
description: "Redacta el escrito «Pharming y estafa informática (phishing): acusación» (formulario 664 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pharming y estafa informática (phishing): acusación

> Formulario 0664 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (14 veces)
- [ ] LOCALIDAD
- [ ] IMPORTE (2 veces)
- [ ] PENA (2 veces)
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…: CONCLUSIONES PRIMERA.- El/la acusado/a»; «…nombre de dominio de la entidad bancaria»; «…e y sus datos bancarios. El/la acusado/a»; «… cuenta corriente en la entidad bancaria»; «…l dinero que detraía el primer acusado/a»; «…ccedía correspondiendo al/a la acusado/a»; «…es hechos son constitutivos por parte de»; «…la contraseña (pharming)— y por parte de»; «…y al/a la acusado/a»

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de los acusados.…
- .- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:…
- .- Pericial informática con dictamen del perito informático que llevó a cabo esta pericial específica del exam…
- .- Documental, teniendo por reproducido extracto de la cuenta de la suma apropiada y datos de la cuenta corrie…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 392 y 390 CP
- art. 197.2 CP
- art. 249.1 a) CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- arts. 392 CP
- art. 390 CP
- art. 48.3 CP
- art. 48.2 CP
- art. 48.1 y 57 CP
- art. 120.3 CP
- art. 77 CP
- arts. 249.1 y 250.6 CP
- artículo 249.1 a) CP
- artículo 249.1 a) del Código Penal
- art. 48 CP
- art. 57 CP
- art. 120.4 CP
- art. 777.2 LECrim

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

### Formulario 0664 · Pharming y estafa informática (phishing): acusación

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (6); 4 párrafos opcionales señalados; 29 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular presenta sus conclusiones provisionales calificando los hechos por parte del scammer de falsedad en documento mercantil de los arts. 392 y 390 CP, por web falsificada, y un delito de descubrimiento de secretos, del art. 197.2 CP por la captación inconsentida y artificiosa del password y la contraseña (pharming) y por parte del mulero de un delito de estafa del art. 249.1 a) CP.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial (1) y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo (2) solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/la acusado/a [COMPLETAR] creó un dominio falso aunque con apariencia de real, por el cual perpetró la acción de redirigir al perjudicado D./Dña. [NOMBRE Y APELLIDOS] al nombre de dominio de la entidad bancaria [COMPLETAR], en apariencia idéntica a la que había intentado acceder, pero que en realidad había sido creada para obtener los datos privados del querellante y sus datos bancarios.

El/la acusado/a [COMPLETAR], en colaboración con el primero antes citado, abrió una cuenta corriente en la entidad bancaria [COMPLETAR] en la que recibió el dinero que detraía el primer acusado/a [COMPLETAR] de las cuentas on-line del perjudicado con la conciencia y voluntad de abrir esa cuenta para que la operación que realizó el perjudicado de acceder a esa cuenta permitiera al primero obtener los datos bancarios y llevar a cabo la transferencia a la cuenta de

El Grupo de la Brigada de delitos tecnológicos localizó la IP del ordenador desde donde se produjo la creación del dominio donde se redirigían los accesos a la entidad bancaria donde pensó el perjudicado que accedía correspondiendo al/a la acusado/a [COMPLETAR] y, además, tras la investigación llevada a cabo, se localizó el dato de quién era el titular de la cuenta a donde se hizo la transferencia que correspondía a

La cantidad desviada fue la de [IMPORTE] euros.

SEGUNDA.- Tales hechos son constitutivos por parte de [COMPLETAR] del delito de concurso medial de falsedad en documento mercantil de los arts. 392 CP y art. 390 CP—por la Web falsificada — y un delito de descubrimiento de secretos, del art. 197.2 CP—por la captación inconsentida y artificiosa del password y la contraseña (pharming)— y por parte de [COMPLETAR] de un delito de estafa del art. 249.1 a) CP. (3)

TERCERA.- Son responsables de los delitos en concepto de autores los acusados.

CUARTA.- No concurren circunstancias agravantes.

QUINTA.- Procede imponer al/ a la acusado/a la pena de [PENA] y al/a la acusado/a [COMPLETAR] la pena de [PENA].

Además, procede imponer la pena de prohibición de comunicación con la víctima, o con aquellos de sus familiares u otras personas que determine el juez prevista en el art. 48.3 CP, la pena de prohibición de aproximarse a la víctima o familiares u otras personas que determine el juez prevista en el art. 48.2 CP y la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades. (4)

SEXTA.- En concepto de responsabilidad civil ambos acusados indemnizarán solidariamente a D./Dña. [NOMBRE Y APELLIDOS] con el importe de [IMPORTE] euros correspondiente a la cantidad sustraída.

Existe responsabilidad civil subsidiaria de la entidad bancaria por la vía del art. 120.3 CP al haberse omitido las normas de policía o reglamentarias de la entidad bancaria que han facilitado o impedido el acceso a la cuenta corriente del querellante. (5)

Las costas deberán ser satisfechas por los acusados.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes (6):

[OPCIONAL — incluir si procede]

1.- Interrogatorio de los acusados.

[OPCIONAL — incluir si procede]

.- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:

D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] agentes de la Brigada tecnológica que llevaron a cabo las diligencias de identificación del autor del delito.

D./Dña. [NOMBRE Y APELLIDOS] agente que llevó a cabo las diligencias de investigación para detectar el IP del ordenador desde el que se llevó a cabo la suplantación de identidad.

D./Dña. [NOMBRE Y APELLIDOS] agente que redactó el oficio policial para interesar la entrada y registro para la intervención del ordenador.

D./Dña. [NOMBRE Y APELLIDOS] agente que intervino en la diligencia de entrada y registro.

D./Dña. [NOMBRE Y APELLIDOS] director del banco de la entidad bancaria.

[OPCIONAL — incluir si procede]

.- Pericial informática con dictamen del perito informático que llevó a cabo esta pericial específica del examen del ordenador desde el que se realizó la operación, debiendo ser citado a través de la oficina judicial el siguiente perito:

D./Dña. [NOMBRE Y APELLIDOS]

Pericial caligráfica del acusado, respecto a la apertura de la cuenta corriente, debiendo ser citado a través de la oficina judicial el siguiente perito:

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducido extracto de la cuenta de la suma apropiada y datos de la cuenta corriente de.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) ¿Dónde se entiende cometido el delito de pharming?

Es aplicable aquí el Acuerdo del Pleno no jurisdiccional de la Sala Segunda del Tribunal Supremo de 3 de febrero de 2005, que acoge el principio de ubicuidad, de tal modo que el delito se comete en todas las jurisdicciones en las que se haya realizado algún elemento del tipo, en consecuencia, el Juez de cualquiera de ellas que primero haya iniciado las actuaciones procesales será, en principio, competente para la instrucción de la causa (en este sentido Autos de la Sala Segunda del TS de 4-11-2005, 11-1-2008 y 6-4-2011, este último en un supuesto de phishing, donde las IP de los correos electrónicos remitidos se localizan en Turquía).

(3) Pharming es la explotación de una vulnerabilidad en el software de los servidores DNS (Domain Name System) o en el de los equipos de los propios usuarios, que permite a un atacante redirigir un nombre de dominio (domain name) a otra máquina distinta. De esta forma, un usuario que introduzca un determinado nombre de dominio que haya sido redirigido, accederá en su explorador de internet a la página web que el atacante haya especificado para ese nombre de dominio, que según Rey Huidobro se trataría de la web delincuente donde, confiado, el usuario realiza sus movimientos con total tranquilidad en la errónea esperanza de estar en la página original y donde deja al descubierto claves y datos personales (principalmente bancarios o financieros), que luego usa el delincuente para estafarle.

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

El mulero comete un delito de estafa de los arts. 249.1 y 250.6 CP, considerando que intervienen como cooperadores necesarios, pues su actuación contribuye necesariamente a la producción del resultado y es una auténtica «conditio sine qua non para que la estafa llegue a consumarse, y por hacerlo de común acuerdo con el autor material de la misma». (STS 51/2020, de 17 de febrero, Rec. 3945/2019, SAP 16.ª Madrid de 71/2006 de 6 Jul. 2006, Rec. 2/2006)

Si lo defraudado excede de más de 50.000 euros se aplicará la pena del art. 250.1.5º CP. Y la pena iría de 1 a 6 años de prisión y multa de seis a doce meses.

Respecto de la conducta del scammer y como apunta Luis Fernando Rey Huidobro (artículo «La estafa informática: relevancia penal del phising y el pharming», 2012) la manipulación informática o el artificio semejante integradora de la estafa no se dará en la primera fase de obtención ilícita de las claves de acceso a la cuenta bancaria, con la falsificación de páginas electrónicas (y posible modificación de direcciones DNS o los archivos «hots» que contienen las direcciones IP´s), ya que dicha conducta no ocasiona directamente ningún traspaso patrimonial ilícito, sino que es una manipulación realizada para obtener subrepticiamente las claves de acceso a las cuentas bancarias. Dichas manipulaciones quedarían fuera del concepto del artículo 249.1 a) CP, aunque podrían dar lugar a otras responsabilidades penales como, por ejemplo, por delito de falsedad documental o por descubrimiento y revelación de secretos. No ocurre lo mismo en la segunda fase, de utilización no consentida de las claves de acceso a la cuenta bancaria y firma electrónica para realizar la transferencia no autorizada. Aquí sí se da una manipulación informática que ocasiona directamente el traspaso patrimonial no consentido, plenamente insertable en el tenor literal del artículo 249.1 a) CP. Esta versión está justificada tanto desde la interpretación objetiva como teleológica del mencionado precepto, teniendo en cuenta además el concepto de manipulación informática acogido en los tratados internacionales. En consecuencia, podemos decir que estas formas de criminalidad patrimonial (phising, pharming), consistentes en la realización de transferencias bancarias en perjuicio de terceros, mediante la utilización no consentida de datos personales de acceso y firma electrónica, son perfectamente insertables en el tipo del artículo 249.1 a) del Código Penal, que sanciona la estafa informática. Ahora bien, claramente respecto del mulero, pero el scammer cometería falsedad y descubrimiento y revelación de secretos.

(4) En este caso, ante la inexistencia de una previsión de esta pena se ha optado por acudir al mecanismo de la "prohibición de acudir al lugar del delito" que se configura en este caso por medio de identificar el "lugar" con "internet", en cuyo caso se acuerda esta pena por la vía del art. 48 CP, en relación con el art. 57 CP. (SJP Barcelona 243/2019, de 29 de mayo, Proc. 7/2018)

(5) Véase STS 108/2019 de 5 de marzo, Rec. 10024/2018

STS 53/2020 de 17 Feb. 2020, Rec. 10301/2019: se desarrolla el criterio del Tribunal Supremo con relación al ámbito de las responsabilidades del art. 120.3 CP que se extendería a las entidades bancarias en el caso de sustracción de fondos a un cliente por incumplimiento de las normas reglamentarias de protección del cliente ante estafas informáticas, lo que se indica de referencia jurisprudencial de cara al juicio oral.

STS 530/2019 de 31 de octubre, Rec. 1945/2018: responsabilidad ex delicto subsidiaria de la entidad bancaria por apropiación indebida de fondos en una cuenta por colaboración de un administrador solidario y empleado del banco. A diferencia del caso anterior, el delito se comete por un empleado del banco y en este caso opera la del art. 120.4 CP.

(6) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

================================================================================
