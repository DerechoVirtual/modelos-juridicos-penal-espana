# Violencia de género, órdenes de protección e impago de pensiones · España

> Plugin de Claude Code `modelos-violencia-de-genero-espana` · **75 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la violencia de género y doméstica ante la Sección de Violencia sobre la Mujer: orden de protección, quebrantamiento, maltrato habitual, abandono de familia, impago de pensiones, sustracción de menores y cuestiones de competencia.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 75 está al final):

- **Conformidad** (5). Por ejemplo: Lesiones al animal de la pareja: conformidad de la defensa; Sustracción de menores: conformidad de la defensa; Inutilizar dispositivos electrónicos de control (violencia de género): defensa con conformidad.
- **Recursos e impugnaciones** (11). Por ejemplo: Orden de protección denegada: oposición a la apelación; Tentativa de asesinato con agravantes de parentesco y de género: apelación contra la condena; Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado.
- **Querellas y denuncias** (10). Por ejemplo: Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato; Quebrantamiento de condena (prohibición de comunicación online): querella; Matrimonio ilegal: querella.
- **Escritos de acusación** (11). Por ejemplo: Entrega de menor por precio para alterar la filiación: acusación; Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación; Abandono de familia: acusación.
- **Escritos de defensa** (11). Por ejemplo: Maltrato habitual (violencia de género): defensa; Quebrantamiento de medida cautelar de alejamiento: defensa; Lesiones al animal de la pareja: escrito de defensa.
- **Medidas cautelares y protección** (7). Por ejemplo: Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar; Violencia de género: la defensa se opone a suspender cautelarmente el régimen de visitas; Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad.
- **Resoluciones, actas y documentos** (7). Por ejemplo: Inhibición a otra Sección de Violencia sobre la Mujer por víctimas con distintos domicilios: auto; Delito sexual: auto de inhibición de Violencia sobre la Mujer a Violencia contra la Infancia; Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto.
- **Solicitudes y escritos de trámite** (13). Por ejemplo: Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor; Declinatoria a Violencia contra la Infancia por agresión sexual a hija menor y a su madre; Declinatoria a Violencia contra la Infancia por agresión sexual a menor por su pareja.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Escrito de acusación por impago de pensiones»
   - «Escrito de defensa por maltrato habitual»
   - «Denuncia por delito leve ante la Sección de Violencia sobre la Mujer con petición de juicio inmediato»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-violencia-de-genero-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-violencia-de-genero-espana:inhibicion-otra-seccion-violencia-sobre-mujer-victimas-31`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él.
   Todos los datos jurídicos del escrito (artículos vigentes, sentencias con su ECLI, convenios, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las correcciones y avisos de la revisión del 17-11-2026 (reformas legales, órganos, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el escrito; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te indica el plazo y ante quién se presenta, y te entrega el escrito en Word con un resumen de lo que queda pendiente.

El resultado es un borrador para que lo revise un profesional antes de presentarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-violencia-de-genero-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-violencia-de-genero-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-violencia-de-genero-espana:<skill>`). Son 75, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Conformidad (5)

- **Inutilizar dispositivos electrónicos de control (violencia de género): defensa con conformidad** (`inutilizar-dispositivos-electronicos-control-violencia-480`). Escrito de la defensa que acepta la acusación y la pena por inutilizar los dispositivos electrónicos de control en un caso de violencia de género, para obtener sentencia de conformidad.
- **Lesiones al animal de la pareja: conformidad de la defensa** (`lesiones-animal-pareja-conformidad-defensa-112`). Escrito de la defensa que muestra su conformidad con la acusación por lesiones al animal de la pareja y con la pena solicitada, para poner fin al procedimiento con una sentencia de conformidad.
- **Quebrantamiento de condena (prohibición de comunicación online): defensa con conformidad** (`quebrantamiento-condena-prohibicion-comunicacion-online-510`). Escrito de la defensa que muestra su conformidad con la acusación por quebrantamiento de condena al incumplir la prohibición de comunicación online, para que se dicte sentencia de conformidad.
- **Quebrantamiento de medida cautelar de alejamiento: defensa con conformidad** (`quebrantamiento-medida-cautelar-alejamiento-defensa-859`). Escrito de la defensa que muestra su conformidad con la acusación por quebrantar una medida cautelar de alejamiento y con la pena solicitada, para obtener sentencia de conformidad.
- **Sustracción de menores: conformidad de la defensa** (`sustraccion-menores-conformidad-defensa-287`). Escrito de la defensa que muestra su conformidad con la acusación por sustracción de menores y con la pena pedida, para que se dicte sentencia de conformidad.

### Recursos e impugnaciones (11)

- **Abandono de familia: apelación contra la absolución** (`abandono-familia-apelacion-contra-absolucion-416`). Recurso de apelación de la acusación contra una sentencia absolutoria por abandono de familia, para pedir al tribunal superior que revoque la absolución y condene al acusado.
- **Apelación contra la condena por quebrantamiento de condena (prohibición de comunicación online)** (`apelacion-contra-condena-quebrantamiento-condena-509`). Recurso de apelación del condenado por quebrantar una condena al incumplir la prohibición de comunicación online, para impugnar la sentencia y pedir la absolución o la rebaja de la pena.
- **Apelación contra la condena por quebrantamiento de medida cautelar de alejamiento** (`apelacion-contra-condena-quebrantamiento-medida-cautelar-853`). Recurso de apelación de la persona condenada contra la sentencia por quebrantamiento de condena (incumplimiento de una orden de alejamiento), fundado en errores en la valoración de la prueba, presentado ante la Sección de lo Penal del Tribunal de Instancia.
- **Impugnar la apelación contra la condena por quebrantamiento de medida cautelar de alejamiento** (`impugnar-apelacion-contra-condena-quebrantamiento-medida-451`). Escrito de la parte apelada que se opone al recurso contra su condena por quebrantar una medida cautelar de alejamiento, para que se confirme la sentencia de instancia.
- **Inutilizar dispositivos electrónicos de control (violencia de género): apelación contra la condena** (`inutilizar-dispositivos-electronicos-control-violencia-481`). Recurso de apelación del condenado por inutilizar los dispositivos electrónicos de control en violencia de género, contra la sentencia de instancia, pidiendo su absolución o una pena menor.
- **Lesiones al animal de la pareja: apelación contra la condena** (`lesiones-animal-pareja-apelacion-contra-condena-114`). Recurso de apelación del condenado por lesiones al animal de la pareja contra la sentencia de instancia, para pedir la revocación de la condena o la reducción de la pena.
- **Orden de protección denegada: oposición a la apelación** (`orden-proteccion-denegada-oposicion-apelacion-102`). Escrito de oposición, presentado por el investigado, a la apelación contra la denegación de una orden de protección, para que se confirme la decisión de no concederla.
- **Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado** (`orden-proteccion-violencia-genero-reforma-subsidiario-374`). Recurso de reforma y subsidiario de apelación del acusado contra la orden de protección por violencia de género; tenga en cuenta que la LO 1/2026 añadió la finalidad de evitar la reiteración delictiva.
- **Sustracción de menores: apelación contra la condena** (`sustraccion-menores-apelacion-contra-condena-289`). Recurso de apelación del condenado por sustracción de menores contra la sentencia de instancia, para solicitar la absolución o una pena menor ante el tribunal superior.
- **Tentativa de asesinato con agravantes de parentesco y de género: apelación contra la condena** (`tentativa-asesinato-agravantes-parentesco-genero-285`). Recurso de apelación del condenado por tentativa de asesinato con agravantes de parentesco y de género, que impugna la sentencia y pide su revocación o la reducción de la pena.
- **Violencia de género: apelación contra el sobreseimiento y archivo provisional** (`violencia-genero-apelacion-contra-sobreseimiento-archivo-389`). Recurso de apelación contra el sobreseimiento y archivo provisional de una causa de violencia de género, para pedir que se revoque y continúe la investigación.

### Querellas y denuncias (10)

- **Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato** (`delito-leve-ante-violencia-sobre-mujer-denuncia-peticion-383`). Denuncia de una víctima de violencia de género ante el juez por un delito leve de injurias o vejaciones, con petición de que se enjuicie de forma inmediata en la Sección de Violencia sobre la Mujer.
- **Entrega de menor por precio para alterar la filiación: querella** (`entrega-menor-precio-alterar-filiacion-querella-807`). Escrito por el que se ponen en conocimiento del juez hechos que pueden constituir un delito de entrega de un menor a cambio de precio para alterar su filiación, y se pide la apertura de la investigación contra el querellado.
- **Inutilizar dispositivos electrónicos de control (violencia de género): querella** (`inutilizar-dispositivos-electronicos-control-violencia-482`). Escrito que pone en conocimiento del juez de violencia sobre la mujer que el querellado no lleva dado de alta y en activo el dispositivo electrónico de control, hecho que puede ser delito de inutilización de dispositivos de control.
- **Lesiones al animal de la pareja: querella** (`lesiones-animal-pareja-querella-113`). Querella con la que el procurador, en nombre de la persona perjudicada, denuncia ante la Sección de Instrucción del Tribunal de Instancia las lesiones causadas al animal de la pareja y pide que se abra la investigación penal.
- **Maltrato habitual (violencia de género): querella** (`maltrato-habitual-violencia-genero-querella-835`). Querella de una mujer contra su pareja o ex pareja por malos tratos habituales, como delito de violencia de género, presentada ante la Sección de Violencia sobre la Mujer del Tribunal de Instancia.
- **Matrimonio ilegal: querella** (`matrimonio-ilegal-querella-806`). Querella del perjudicado contra quien ha contraído matrimonio sin estar legalmente divorciado, hecho que puede constituir un delito de matrimonio ilegal; se presenta ante el juez de instrucción para abrir la investigación.
- **Quebrantamiento de condena (prohibición de comunicación online): querella** (`quebrantamiento-condena-prohibicion-comunicacion-online-511`). Querella por quebrantamiento de condena contra quien, estando condenado a no comunicarse con la víctima, le escribió un mensaje en una red social; recuerda que la prohibición alcanza a cualquier medio tecnológico.
- **Quebrantamiento de medida cautelar de alejamiento: querella** (`quebrantamiento-medida-cautelar-alejamiento-querella-854`). Querella de la víctima contra su pareja por haber incumplido una orden de alejamiento, que puede constituir un delito de quebrantamiento de condena; se presenta ante la Sección de Violencia sobre la Mujer.
- **Sustracción de menores: querella** (`sustraccion-menores-querella-288`). Querella ante la Sección de Instrucción del Tribunal de Instancia por un delito de sustracción de menores, presentada por quien sufre el hecho para que se abra la instrucción contra el querellado.
- **Tentativa de asesinato con agravantes de parentesco y de género: querella** (`tentativa-asesinato-agravantes-parentesco-genero-286`). Querella ante la Sección de Instrucción del Tribunal de Instancia por tentativa de asesinato con las agravantes de parentesco y de género, para que se abra la investigación penal contra el querellado.

### Escritos de acusación (11)

- **Abandono de familia: acusación** (`abandono-familia-acusacion-813`). Escrito de la acusación particular en procedimiento abreviado que pide la apertura del juicio oral y califica provisionalmente los hechos como delito de abandono de familia.
- **Entrega de menor por precio para alterar la filiación: acusación** (`entrega-menor-precio-alterar-filiacion-acusacion-809`). Escrito de acusación en procedimiento abreviado que solicita la apertura del juicio oral y califica provisionalmente los hechos como entrega de un menor por precio para alterar su filiación.
- **Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación** (`impago-prestaciones-separacion-divorcio-nulidad-812`). Escrito de la acusación en procedimiento abreviado que pide la apertura del juicio oral y califica provisionalmente como delito de impago de prestaciones económicas debidas por separación, divorcio o nulidad.
- **Inutilizar dispositivos electrónicos de control (violencia de género): acusación** (`inutilizar-dispositivos-electronicos-control-violencia-484`). Escrito de la acusación con sus conclusiones provisionales por inutilización de dispositivos de control, cuando el acusado se quitó el dispositivo que debía llevar según la orden de protección dictada por agresión a su pareja.
- **Lesiones al animal de la pareja: escrito de acusación** (`lesiones-animal-pareja-escrito-acusacion-115`). Escrito de acusación de la acusación particular, una vez abierto el trámite del procedimiento abreviado, que pide la apertura del juicio oral y califica provisionalmente las lesiones causadas al animal de la pareja.
- **Maltrato habitual (violencia de género): acusación** (`maltrato-habitual-violencia-genero-acusacion-831`). Escrito de la acusación particular en procedimiento abreviado que pide la apertura del juicio oral y califica provisionalmente los hechos como maltrato habitual, ante la Sección de Violencia sobre la Mujer.
- **Matrimonio ilegal: acusación** (`matrimonio-ilegal-acusacion-804`). Escrito de acusación en procedimiento abreviado que solicita la apertura del juicio oral y califica provisionalmente como matrimonio ilegal el hecho de contraer matrimonio sin estar legalmente divorciado.
- **Quebrantamiento de condena (prohibición de comunicación online): acusación** (`quebrantamiento-condena-prohibicion-comunicacion-online-512`). Escrito de la acusación con sus conclusiones provisionales por quebrantamiento de condena, cuando el acusado escribió un mensaje en una red social pese a tener prohibida toda comunicación con la víctima.
- **Quebrantamiento de medida cautelar de alejamiento: acusación** (`quebrantamiento-medida-cautelar-alejamiento-acusacion-857`). Escrito de la acusación en procedimiento abreviado que pide la apertura del juicio oral y califica provisionalmente como quebrantamiento de condena el incumplimiento de una orden de alejamiento respecto de su pareja.
- **Sustracción de menores: escrito de acusación** (`sustraccion-menores-escrito-acusacion-290`). Escrito de acusación particular en procedimiento abreviado que pide la apertura del juicio oral y califica provisionalmente los hechos como sustracción de menores, ante la Sección de Instrucción del Tribunal de Instancia.
- **Tentativa de asesinato con agravantes de parentesco y de género: calificación de la acusación** (`tentativa-asesinato-agravantes-parentesco-genero-283`). Escrito de calificación de la acusación particular ante la Audiencia Provincial, en un sumario ordinario, que fija sus conclusiones provisionales por tentativa de asesinato con agravantes de parentesco y de género.

### Escritos de defensa (11)

- **Abandono de familia: defensa** (`abandono-familia-defensa-810`). Escrito de la defensa en procedimiento abreviado que presenta sus conclusiones provisionales frente a la acusación por abandono de familia, alegando que falta la voluntad de desatender las obligaciones.
- **Entrega de menor por precio para alterar la filiación: defensa** (`entrega-menor-precio-alterar-filiacion-defensa-808`). Escrito de la defensa en procedimiento abreviado que presenta sus conclusiones provisionales frente a la acusación por entrega de un menor por precio para alterar su filiación.
- **Impago de prestaciones por separación, divorcio o nulidad matrimonial: defensa** (`impago-prestaciones-separacion-divorcio-nulidad-811`). Escrito de la defensa en procedimiento abreviado que presenta sus conclusiones provisionales frente a la acusación por impago de prestaciones económicas, alegando falta de solvencia del acusado.
- **Inutilizar dispositivos electrónicos de control (violencia de género): defensa** (`inutilizar-dispositivos-electronicos-control-violencia-483`). Escrito de la defensa que presenta sus conclusiones provisionales en procedimiento abreviado por inutilización de dispositivos de control, alegando que los dispositivos electrónicos estaban estropeados.
- **Lesiones al animal de la pareja: escrito de defensa** (`lesiones-animal-pareja-escrito-defensa-111`). Escrito de defensa del acusado en diligencias previas por un delito de lesiones a un animal, presentado ante la Sección de Instrucción del Tribunal de Instancia al evacuar el traslado conferido.
- **Maltrato habitual (violencia de género): defensa** (`maltrato-habitual-violencia-genero-defensa-834`). Escrito de la defensa que presenta sus conclusiones provisionales en procedimiento abreviado por maltrato habitual, sosteniendo que los hechos no son constitutivos de delito.
- **Matrimonio ilegal: defensa** (`matrimonio-ilegal-defensa-805`). Escrito de la defensa en procedimiento abreviado que presenta sus conclusiones provisionales frente a la acusación por matrimonio ilegal, alegando falta de dolo porque el acusado creía estar ya divorciado.
- **Quebrantamiento de condena (prohibición de comunicación online): defensa** (`quebrantamiento-condena-prohibicion-comunicacion-online-508`). Escrito de la defensa que presenta sus conclusiones provisionales en procedimiento abreviado por quebrantamiento de condena mediante un mensaje en una red social, con aportación o impugnación de pericial informática.
- **Quebrantamiento de medida cautelar de alejamiento: defensa** (`quebrantamiento-medida-cautelar-alejamiento-defensa-856`). Escrito del acusado en procedimiento abreviado que presenta sus conclusiones provisionales frente a la acusación por quebrantar una orden de alejamiento, ante la Sección de Violencia sobre la Mujer.
- **Sustracción de menores: escrito de defensa** (`sustraccion-menores-escrito-defensa-291`). Escrito de defensa del acusado en las diligencias previas por sustracción de menores, presentado ante la Sección de Instrucción del Tribunal de Instancia al evacuar el traslado conferido.
- **Tentativa de asesinato con agravantes de parentesco y de género: calificación de la defensa** (`tentativa-asesinato-agravantes-parentesco-genero-284`). Escrito de calificación de la defensa del acusado ante la Audiencia Provincial, en un sumario ordinario por tentativa de asesinato con agravantes, en el que expone sus conclusiones provisionales frente a la acusación.

### Medidas cautelares y protección (7)

- **Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar** (`delito-contra-relaciones-familiares-acusacion-particular-273`). Escrito de la acusación particular ante la Sección de Violencia sobre la Mujer para que se acuerde cautelarmente el alejamiento del investigado en un procedimiento por un delito contra las relaciones familiares.
- **Menor víctima de violencia doméstica: pedir al juez penal suspender las visitas del progenitor** (`menor-victima-violencia-domestica-pedir-juez-penal-736`). Escrito de un menor víctima de violencia doméstica que pide al juez penal suspender el régimen de visitas de su progenitor como medida de protección dentro del proceso penal.
- **Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad** (`tentativa-homicidio-asesinato-acusacion-particular-pide-319`). Escrito de la acusación particular ante la Sección de Violencia sobre la Mujer que pide, como medida cautelar, suspender la patria potestad del investigado por tentativa de homicidio o asesinato.
- **Tentativa de homicidio o asesinato: la defensa se opone a suspender la patria potestad** (`tentativa-homicidio-asesinato-defensa-opone-suspender-320`). Escrito de la defensa ante la Sección de Violencia sobre la Mujer para oponerse a la suspensión cautelar de la patria potestad solicitada contra el investigado por tentativa de homicidio o asesinato.
- **Violencia de género con hijos menores: la víctima pide suspender el régimen de visitas** (`violencia-genero-hijos-menores-victima-pide-suspender-768`). Escrito de una víctima de violencia de género con hijos menores que pide al juez penal medidas civiles, entre ellas suspender el régimen de visitas, cuando no hay procedimiento civil abierto de separación o divorcio.
- **Violencia de género: la defensa se opone a suspender cautelarmente el régimen de visitas** (`violencia-genero-defensa-opone-suspender-cautelarmente-318`). Escrito de la defensa ante la Sección de Violencia sobre la Mujer para oponerse a que se suspenda cautelarmente el régimen de visitas del investigado con sus hijos menores en un caso de violencia de género.
- **Víctima con hijos mayores y menores: pedir medidas cautelares civiles en el proceso penal** (`victima-hijos-mayores-menores-pedir-medidas-cautelares-784`). Escrito de una víctima de violencia de género con hijos mayores y menores que pide al juez penal medidas cautelares de naturaleza civil cuando no hay un procedimiento civil abierto de separación o divorcio.

### Resoluciones, actas y documentos (7)

- **Delito sexual (procesos previos al 3/10/2025): Violencia sobre la Mujer rechaza la inhibición (auto)** (`delito-sexual-procesos-previos-3-10-2025-violencia-sobre-34`). Modelo de auto por el que la Sección de Violencia sobre la Mujer rechaza la inhibición de Instrucción en un delito sexual por tratarse de hechos anteriores a la entrada en vigor de la reforma de competencias de la LO 1/2025.
- **Delito sexual: auto de inhibición de Violencia sobre la Mujer a Violencia contra la Infancia** (`delito-sexual-auto-inhibicion-violencia-sobre-mujer-32`). Modelo de auto por el que la Sección de Violencia sobre la Mujer se inhibe a favor de la Sección de Violencia contra la Infancia y la Adolescencia en un delito contra la libertad sexual cuya víctima es una niña o adolescente.
- **Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto** (`falta-competencia-seccion-violencia-sobre-mujer-proceso-33`). Modelo de auto por el que una Sección de Violencia sobre la Mujer declara su falta de competencia objetiva para un proceso de familia al no existir procedimiento penal abierto entre las partes.
- **Impago de pensión alimenticia: Violencia sobre la Mujer rechaza la inhibición de Instrucción (auto)** (`impago-pension-alimenticia-violencia-sobre-mujer-rechaza-37`). Modelo de auto por el que una Sección de Violencia sobre la Mujer rechaza la inhibición de la Sección de Instrucción en un delito de impago de pensión alimenticia, al considerar que no es competente.
- **Inhibición a otra Sección de Violencia sobre la Mujer por víctimas con distintos domicilios: auto** (`inhibicion-otra-seccion-violencia-sobre-mujer-victimas-31`). Modelo de auto por el que una Sección de Violencia sobre la Mujer se inhibe a favor de otra en un delito de trata de seres humanos con numerosas víctimas que tienen distintos domicilios.
- **Inhibición a Violencia sobre la Mujer del domicilio de la víctima a fecha del hecho: auto** (`inhibicion-violencia-sobre-mujer-domicilio-victima-fecha-36`). Modelo de auto por el que una Sección de Violencia sobre la Mujer se inhibe a favor de la del lugar donde la víctima tenía su domicilio en la fecha de los hechos.
- **Inhibición de Instrucción a favor de Violencia sobre la Mujer del domicilio de la víctima: auto** (`inhibicion-instruccion-favor-violencia-sobre-mujer-39`). Modelo de auto por el que una Sección de Instrucción se inhibe a favor de la Sección de Violencia sobre la Mujer del domicilio de la víctima en un delito de trata de seres humanos.

### Solicitudes y escritos de trámite (13)

- **Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor** (`declinatoria-favor-seccion-violencia-sobre-mujer-40`). Escrito que pide a la Sección de Violencia sobre la Mujer, que tramita una agresión sexual a un menor, que se inhiba a favor de la Sección de Violencia contra la Infancia y la Adolescencia por ser la competente.
- **Declinatoria a favor de la Sección de Violencia sobre la Mujer por impago de alimentos a hijo menor** (`declinatoria-favor-seccion-violencia-sobre-mujer-impago-44`). Escrito que pide a la Sección de Violencia sobre la Mujer, que tramita un impago de pensión alimenticia a un hijo menor, que se inhiba a favor de la Sección de Violencia contra la Infancia y la Adolescencia.
- **Declinatoria a favor de la Sección de Violencia sobre la Mujer por trata de menores** (`declinatoria-favor-seccion-violencia-sobre-mujer-trata-43`). Escrito que pide a la Sección de Violencia sobre la Mujer, que tramita un delito de trata de seres humanos que afecta a un menor, que se inhiba a favor de la Sección de Violencia contra la Infancia y la Adolescencia.
- **Declinatoria a Violencia contra la Infancia por agresión sexual a hija menor y a su madre** (`declinatoria-violencia-contra-infancia-agresion-sexual-41`). Escrito dirigido a la Sección de Violencia contra la Infancia y la Adolescencia para que se inhiba a favor de la Sección de Violencia sobre la Mujer, que ya tramita la agresión sexual a la madre de la menor víctima.
- **Declinatoria a Violencia contra la Infancia por agresión sexual a menor por su pareja** (`declinatoria-violencia-contra-infancia-agresion-sexual-42`). Escrito dirigido a la Sección de Violencia contra la Infancia y la Adolescencia para que se inhiba a favor de la Sección de Violencia sobre la Mujer, al ser el agresor sexual de la menor su pareja.
- **Declinatoria a Violencia contra la Infancia por impago de pensión compensatoria y alimenticia** (`declinatoria-violencia-contra-infancia-impago-pension-45`). Escrito dirigido a la Sección de Violencia contra la Infancia y la Adolescencia para que se inhiba a favor de la Sección de Violencia sobre la Mujer en un delito de impago de pensión compensatoria y alimenticia.
- **Declinatoria por conexidad a favor de la Sección de Violencia sobre la Mujer** (`declinatoria-conexidad-favor-seccion-violencia-sobre-373`). Declinatoria de la acusación particular ante una Sección de Violencia sobre la Mujer para que se inhiba a favor de otra que ya conoce de diligencias por hechos conexos, que deben enjuiciarse conjuntamente.
- **Inhibitoria ante el Juez de Violencia sobre la Mujer** (`inhibitoria-ante-juez-violencia-sobre-mujer-375`). Escrito que pide a la Sección de Violencia sobre la Mujer que requiera de inhibición a la Sección de Instrucción por un único suceso con amenazas y agresiones recíprocas entre una pareja, para tramitarlo de forma conjunta.
- **La defensa propone a la Fiscalía un programa de resolución de conflictos o parentalidad positiva** (`defensa-propone-fiscalia-programa-resolucion-conflictos-276`). Escrito de la defensa dirigido al Fiscal para proponer que el investigado participe en un programa de resolución de conflictos o de parentalidad positiva, como vía para alcanzar una conformidad.
- **Perdón del ofendido menor o discapacitado: pedir que no surta efecto (hasta el 2 de abril de 2025)** (`perdon-ofendido-menor-discapacitado-pedir-no-surta-275`). Escrito de la acusación particular para que no surta efecto el perdón del ofendido menor o con discapacidad, aplicable a procedimientos anteriores al 2 de abril de 2025; se dirige a la Sección de Instrucción del Tribunal de Instancia.
- **Violencia sobre la Mujer: personación de la víctima en diligencias previas** (`violencia-sobre-mujer-personacion-victima-diligencias-376`). Escrito por el que la víctima de un delito de violencia de género se persona en las diligencias previas ante la Sección de Violencia sobre la Mujer para ejercer la acusación particular.
- **Víctima de violencia de género: separación o divorcio ante la Sección de Violencia sobre la Mujer** (`victima-violencia-genero-separacion-divorcio-ante-785`). Demanda de una víctima de violencia de género con hijos menores que promueve la separación o el divorcio ante la Sección de Violencia sobre la Mujer, para modificar las medidas civiles de la orden de protección.
- **Víctima en el proceso penal: pedir modificar las medidas civiles del proceso de familia** (`victima-proceso-penal-pedir-modificar-medidas-civiles-769`). Escrito de una víctima de violencia de género con hijos menores que pide al juez penal modificar las medidas civiles que antes había acordado el juez de familia.
