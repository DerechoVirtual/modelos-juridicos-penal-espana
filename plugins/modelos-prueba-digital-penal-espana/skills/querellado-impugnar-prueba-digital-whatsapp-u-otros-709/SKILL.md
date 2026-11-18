---
name: querellado-impugnar-prueba-digital-whatsapp-u-otros-709
description: "Redacta el escrito «Querellado: impugnar la prueba digital (WhatsApp u otros) aportada en la instrucción» (formulario 709 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Querellado: impugnar la prueba digital (WhatsApp u otros) aportada en la instrucción

> Formulario 0709 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] DESCRIBIR (2 veces)
- [ ] FECHA (2 veces)
- [ ] MENSAJE DE WHATSAPP
- [ ] LUGAR

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 384 LEC
- artículo 384.1 LEC
- artículo 299.2 LEC
- arts. 383 a 384 LEC
- Ley 6/2020

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

### Formulario 0709 · Querellado: impugnar la prueba digital (WhatsApp u otros) aportada en la instrucción

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); 10 llamadas a nota sin texto retiradas; 8 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que, en fase de instrucción, se impugna una prueba digital aportada (conversación de WhatsApp, Tuenti, Twitter, Skype, etc.) por considerarla no auténtica e inveraz, en base al artículo 384 LEC, aplicable supletoriamente al proceso penal.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia. A la Sección de Instrucción del Tribunal de Instancia deplaza nºD./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en las diligencias previas [Nº DE PROCEDIMIENTO] por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:Que por medio del presente escrito formulo expresa impugnación de la prueba digital consistente en [DESCRIBIR], en base a las siguientes

ALEGACIONES

Primera.- Con fecha [FECHA] se ha aportado por la parte querellante una prueba digital consistente en [DESCRIBIR] que esta parte impugna en base al artículo 384.1 LEC, habida cuenta que no se reconoce la validez ni veracidad del contenido de la misma e interesando que en su momento procesal oportuno no se le conceda valoración alguna, al haber sido expresamente impugnada por esta representación durante la fase de instrucción, y ello para su eficacia en la fase del plenario, con independencia de su expresa impugnación al formular el escrito de defensa, a fin de no causar indefensión a la parte y que pueda postular los medios que estime oportunos. Segunda.- Se impugna por esta parte porque en modo alguno envió el contenido del mensaje que se cita en la prueba digital aportada, habiéndose suplantado la identidad de mi representado/a en esta aportación, no siendo veraz el contenido de la citada prueba aportada. Se cita a estos efectos la Sentencia del Tribunal Supremo, Sala Segunda, de lo Penal, 300/2015 de 19 May. 2015, Rec. 2387/2014 cuando afirma que «la prueba de una comunicación bidireccional mediante cualquiera de los múltiples sistemas de mensajería instantánea debe ser abordada con todas las cautelas. La posibilidad de una manipulación de los archivos digitales mediante los que se materializa ese intercambio de ideas, forma parte de la realidad de las cosas. El anonimato que autorizan tales sistemas y la libre creación de cuentas con una identidad fingida, hacen perfectamente posible aparentar una comunicación en la que un único usuario se relaciona consigo mismo».

Por lo expuesto,

SUPLICO A LA SECCIÓNQue tenga por presentado este escrito, lo admita y se tenga por impugnada la prueba digital aportada por el/la querellante consistente en [MENSAJE DE WHATSAPP], correo electrónico, SMS, tuit, etc...Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] D./Dña. [NOMBRE Y APELLIDOS] Son tres las fases de la prueba digital (Joaquín DELGADO MARTÍN):1. Obtención de la prueba: se refiere al acceso a las fuentes de la prueba electrónica, es decir, a la obtención de la información o datos por las partes (o por la autoridad pública en el proceso penal) antes de su aportación al proceso. Se trata de acceder a la información o datos producidos o almacenados en un dispositivo electrónico, o bien transmitidos en forma electrónica a través de redes de comunicación abiertas o restringidas como Internet, telefonía fija, móvil u otras.2. Incorporación al proceso de la información o datos obtenidos que sean relevantes para la acreditación de hechos. Estos datos han de tener entrada en el proceso a través de un concreto medio probatorio admitido por el ordenamiento; y ha de ser respetado el procedimiento que, para el concreto medio de prueba, sea contemplado por la respectiva legislación procesal para ejercitar válidamente el derecho a la prueba.3. Valoración de la información o datos por el Juez o Tribunal de enjuiciamiento. Si se cumplen los requisitos de obtención e incorporación de la prueba electrónica al proceso, ésta puede desplegar eficacia probatoria siendo objeto de valoración por parte del Juez o Tribunal de conformidad con las reglas de la sana crítica (sistema de libre valoración de la prueba).
 La aportación al proceso de la prueba digital.

Los datos contenidos en un dispositivo electrónico han de ser aportados al proceso en un soporte determinado, lo que determinará el medio de prueba utilizado. En principio, todos los medios probatorios previstos por la Ley son aptos para incorporar al proceso los datos electrónicos.

En primer lugar, su contenido puede ser impreso en formato papel y presentado al proceso como un documento en soporte papel, resultando de aplicación el régimen jurídico de la prueba documental.

En segundo término, pueden ser incorporados al proceso mediante la aportación del propio documento electrónico, es decir, a través de la incorporación de los datos contenidos en soporte electrónico; resultando de aplicación el régimen jurídico de la prueba de instrumentos electrónicos del artículo 299.2 LEC que se contiene en los arts. 383 a 384 LEC y en la Ley 6/2020, de 11 de noviembre, reguladora de determinados aspectos de los servicios electrónicos de confianza.
 Se aplica como supletoria la LEC. Y en este caso el artículo 384.1 LEC en cuanto a la validez de la prueba si no hay impugnación de la parte a quien perjudique.
 Se incluye esta mención habida cuenta que el Tribunal Supremo (STS 300/2015, de 19 de mayo) tiene declarado con respecto a la aportación de un mensaje enviado a través de un sistema de mensajería instantánea (Tuenti, WhatsApp, Skype, Messenger, etc.) que de impugnarse esta prueba digital es preciso proponer y aportar prueba pericial que acredite ese contenido. Si es posible debe pedirse el peritaje de ambos terminales (emisor y receptor del mensaje) para detectar más fácilmente su veracidad.

En caso de impugnarse la veracidad de un correo electrónico, puede solicitarse al juez que inste al proveedor de servicios correspondiente que entregue las copias de sus servidores.
 Es preciso citar la existencia de razones en las que se fundamente la concreta impugnación, porque en la práctica hay ocasiones en que concurre una mera manifestación impugnatoria sin respaldo alegatorio; así como el propio contenido de las mencionadas razones.

================================================================================
