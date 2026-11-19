# Prevaricación, malversación y denuncia falsa · España

> Plugin de Claude Code `modelos-prevaricacion-y-malversacion-espana` · **58 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos de cargos públicos y contra la Administración de Justicia: malversación, prevaricación (también urbanística y judicial), fraude, enriquecimiento ilícito, falso testimonio, denuncia falsa y querellas contra diputados y senadores.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 58 está al final):

- **Conformidad** (6). Por ejemplo: Enriquecimiento ilícito: conformidad de la defensa; Intrusismo profesional: conformidad de la defensa; Funcionario que deniega una prestación por discriminación: conformidad de la defensa.
- **Recursos e impugnaciones** (9). Por ejemplo: Falso testimonio: apelación contra la condena; Infidelidad en la custodia de documentos: apelación contra la condena; Prevaricación urbanística: apelación de la autoridad o funcionario condenado (todas las CCAA).
- **Querellas y denuncias** (16). Por ejemplo: Diputado o senador: querella ante el juez de instrucción; Prevaricación urbanística de autoridad o funcionario: querella (todas las CCAA); Delito urbanístico: querella contra el constructor (todas las CCAA).
- **Escritos de acusación** (13). Por ejemplo: Fraude a la Administración: calificación provisional de la acusación; Malversación: calificación provisional de la acusación; Prevaricación judicial: acusación.
- **Escritos de defensa** (13). Por ejemplo: Omisión del deber de impedir delitos: defensa; Denuncia falsa: defensa; Encubrimiento: defensa.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por prevaricación urbanística»
   - «Querella por falso testimonio»
   - «Querella por denuncia falsa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-prevaricacion-y-malversacion-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-prevaricacion-y-malversacion-espana:diputado-senador-querella-ante-juez-instruccion-96`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-prevaricacion-y-malversacion-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-prevaricacion-y-malversacion-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-prevaricacion-y-malversacion-espana:<skill>`). Son 58, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Conformidad (6)

- **Enriquecimiento ilícito: conformidad de la defensa** (`enriquecimiento-ilicito-conformidad-defensa-124`). Escrito de la defensa para mostrar conformidad con la acusación y la pena pedida en el proceso por enriquecimiento ilícito, poniendo fin al procedimiento con sentencia de conformidad.
- **Falso testimonio: conformidad de la defensa** (`falso-testimonio-conformidad-defensa-382`). Escrito de la defensa para mostrar conformidad con la acusación y la pena pedida en el proceso por falso testimonio, poniendo fin al procedimiento con sentencia de conformidad.
- **Fraude a la Administración: defensa con conformidad** (`fraude-administracion-defensa-conformidad-472`). Escrito de la defensa para mostrar conformidad con la acusación y la pena pedida en el proceso por fraude a la Administración, poniendo fin al procedimiento con sentencia de conformidad.
- **Funcionario que deniega una prestación por discriminación: conformidad de la defensa** (`funcionario-deniega-prestacion-discriminacion-281`). Escrito de la defensa para mostrar conformidad con la acusación contra el funcionario que denegó una prestación por motivos discriminatorios; hay que revisar las penas accesorias de inhabilitación aplicables.
- **Infidelidad en la custodia de documentos: defensa con conformidad** (`infidelidad-custodia-documentos-defensa-conformidad-443`). Escrito de la defensa para mostrar conformidad con la acusación y la pena pedida en el proceso por infidelidad en la custodia de documentos, poniendo fin al procedimiento con sentencia de conformidad.
- **Intrusismo profesional: conformidad de la defensa** (`intrusismo-profesional-conformidad-defensa-243`). Escrito de la defensa para mostrar conformidad con la acusación y la pena pedida en el proceso por intrusismo profesional, poniendo fin al procedimiento con sentencia de conformidad.

### Recursos e impugnaciones (9)

- **Apelación contra la condena por fraude a la Administración** (`apelacion-contra-condena-fraude-administracion-475`). Recurso de apelación del acusado condenado por fraude a la Administración contra la sentencia de instancia, solicitando ante el tribunal superior la revocación de la condena o la rebaja de la pena.
- **Apelación contra la condena por malversación** (`apelacion-contra-condena-malversacion-501`). Recurso de apelación del acusado condenado por malversación contra la sentencia de primera instancia, para pedir la absolución o una pena menor; conviene revisar el tipo atenuado y la reparación que tras la LO 14/2022 rebaja la pena.
- **Delito urbanístico: apelación del constructor condenado (todas las CCAA)** (`delito-urbanistico-apelacion-constructor-condenado-todas-456`). Recurso de apelación del constructor condenado por delito urbanístico contra la sentencia de primera instancia, para pedir la absolución o la reducción de la pena; revise la normativa urbanística autonómica citada.
- **Enriquecimiento ilícito: apelación contra la condena** (`enriquecimiento-ilicito-apelacion-contra-condena-126`). Recurso de apelación del acusado condenado por enriquecimiento ilícito contra la sentencia de primera instancia, para pedir su revocación y la absolución o, en su caso, la rebaja de la pena ante la Audiencia Provincial.
- **Falso testimonio: apelación contra la condena** (`falso-testimonio-apelacion-contra-condena-380`). Recurso de apelación de la defensa del condenado por falso testimonio contra la sentencia dictada en primera instancia, solicitando ante la Audiencia Provincial la revocación de la condena o su atenuación.
- **Funcionario que deniega una prestación por discriminación: apelación contra la condena** (`funcionario-deniega-prestacion-discriminacion-apelacion-278`). Recurso de apelación del funcionario condenado por denegar una prestación por motivos discriminatorios; impugna la sentencia y pide que la Audiencia Provincial lo absuelva o rebaje la condena.
- **Infidelidad en la custodia de documentos: apelación contra la condena** (`infidelidad-custodia-documentos-apelacion-contra-condena-439`). Recurso de apelación del condenado por infidelidad en la custodia de documentos contra la sentencia de instancia, para que el tribunal superior revoque la condena o reduzca la pena impuesta.
- **Intrusismo profesional: apelación contra la condena** (`intrusismo-profesional-apelacion-contra-condena-242`). Recurso de apelación de la defensa del condenado por intrusismo profesional, que impugna la sentencia de instancia y pide su revocación, la absolución o una pena menor ante la Audiencia Provincial.
- **Prevaricación urbanística: apelación de la autoridad o funcionario condenado (todas las CCAA)** (`prevaricacion-urbanistica-apelacion-autoridad-453`). Recurso de apelación de la autoridad o funcionario condenado por prevaricación urbanística que impugna la sentencia de instancia y pide su absolución o una condena menor; sirve para cualquier comunidad autónoma.

### Querellas y denuncias (16)

- **Delito urbanístico: querella contra el constructor (todas las CCAA)** (`delito-urbanistico-querella-contra-constructor-todas-463`). Querella contra el constructor, promotor o técnico por un delito urbanístico, presentada ante el juzgado de instrucción para iniciar la investigación; válida para todas las comunidades autónomas.
- **Denuncia falsa: querella** (`denuncia-falsa-querella-845`). Querella de quien ha sido denunciado falsamente contra el autor de la denuncia, presentada ante el juez de instrucción para que se investigue el delito de denuncia falsa.
- **Desobediencia a la autoridad: querella** (`desobediencia-autoridad-querella-878`). Querella de la acusación contra quien se niega abiertamente a cumplir las órdenes legítimas de la autoridad, presentada ante el juez de instrucción para investigar el delito de desobediencia.
- **Diputado o senador: querella ante el juez de instrucción** (`diputado-senador-querella-ante-juez-instruccion-96`). Querella de la acusación contra un diputado o senador, presentada ante el juez de instrucción cuando la persona querellada es aforada, para que se abra la investigación penal por los hechos que se describen.
- **Diputado o senador: querella ante el Tribunal Supremo** (`diputado-senador-querella-ante-tribunal-supremo-97`). Querella dirigida directamente a la Sala competente del Tribunal Supremo contra un diputado o senador aforado, para que se admita a trámite y se investiguen los hechos delictivos que se le atribuyen.
- **Encubrimiento: querella** (`encubrimiento-querella-842`). Querella de la acusación contra quien ayuda a los responsables de un delito a eludir la acción de la justicia o aprovecharse de sus efectos; se presenta ante el juez de instrucción para abrir la causa por encubrimiento.
- **Enriquecimiento ilícito: querella** (`enriquecimiento-ilicito-querella-125`). Querella de la acusación particular por un delito de enriquecimiento ilícito de un cargo o funcionario público, presentada ante el juzgado para solicitar la apertura de la instrucción y las diligencias de investigación.
- **Falso testimonio: querella** (`falso-testimonio-querella-403`). Querella de la acusación contra quien ha faltado a la verdad como testigo, perito o intérprete en un proceso, presentada ante el juzgado de instrucción para que investigue el falso testimonio.
- **Fraude a la Administración Pública: querella** (`fraude-administracion-publica-querella-473`). Querella de la acusación por fraude a la Administración Pública, presentada ante el juez de instrucción para que investigue los hechos y se persiga penalmente a quien defraudó a la hacienda o a la entidad pública.
- **Funcionario que deniega una prestación por discriminación: querella** (`funcionario-deniega-prestacion-discriminacion-querella-280`). Querella contra el funcionario que deniega una prestación por motivos discriminatorios, para iniciar la instrucción penal; recoge la pena de inhabilitación añadida por la LO 8/2021 al art. 511.4 CP.
- **Infidelidad en la custodia de documentos: querella** (`infidelidad-custodia-documentos-querella-442`). Querella contra el funcionario que, teniendo a su cargo documentos, los sustrae, destruye u oculta, o permite que otro lo haga; se presenta ante el juez de instrucción para pedir que se abra la causa.
- **Intrusismo profesional: denuncia** (`intrusismo-profesional-denuncia-245`). Denuncia de quien tiene conocimiento de un caso de intrusismo profesional, para poner los hechos en conocimiento del juzgado o del Ministerio Fiscal y que se inicie la investigación penal.
- **Malversación: querella** (`malversacion-querella-502`). Querella de la acusación contra el funcionario que administra de forma desleal o se apropia del patrimonio público, para iniciar la instrucción por malversación; advierte de las reformas de la LO 14/2022.
- **Omisión del deber de impedir delitos: querella** (`omision-deber-impedir-delitos-querella-840`). Querella contra quien, pudiendo hacerlo, no impide un delito o no promueve su persecución, presentada ante el juez de instrucción para pedir la apertura de diligencias por omisión del deber de impedir delitos.
- **Prevaricación judicial: querella** (`prevaricacion-judicial-querella-838`). Querella de la acusación particular contra un juez o magistrado por prevaricación judicial, presentada ante el órgano competente para que se admita y se investigue el dictado de una resolución injusta.
- **Prevaricación urbanística de autoridad o funcionario: querella (todas las CCAA)** (`prevaricacion-urbanistica-autoridad-funcionario-querella-455`). Querella de la acusación contra la autoridad o funcionario que informa o resuelve a sabiendas de forma injusta en materia urbanística, para abrir la instrucción; válida para todas las comunidades autónomas.

### Escritos de acusación (13)

- **Delito urbanístico: acusación contra el constructor (todas las CCAA)** (`delito-urbanistico-acusacion-contra-constructor-todas-458`). Escrito de acusación contra el constructor por delito urbanístico, con los hechos, la calificación, la responsabilidad civil y las penas que se solicitan; válido para todas las comunidades autónomas.
- **Denuncia falsa: acusación** (`denuncia-falsa-acusacion-843`). Escrito de acusación por denuncia falsa, que expone los hechos, la calificación jurídica y las penas que la acusación pide contra quien imputó falsamente un delito a otra persona.
- **Encubrimiento: acusación** (`encubrimiento-acusacion-844`). Escrito de acusación por encubrimiento, con los hechos, la calificación jurídica y las penas que se piden contra quien ayudó a los autores de un delito a eludir la justicia o aprovecharse de sus efectos.
- **Enriquecimiento ilícito: escrito de acusación** (`enriquecimiento-ilicito-escrito-acusacion-127`). Escrito de acusación por enriquecimiento ilícito en el que la parte acusadora fija los hechos, la calificación jurídica, la responsabilidad penal y civil y las penas que pide para el acusado.
- **Falso testimonio: escrito de acusación** (`falso-testimonio-escrito-acusacion-379`). Escrito de acusación por falso testimonio, con los hechos, la calificación jurídica, la participación del acusado y las penas que la acusación solicita ante el órgano de enjuiciamiento.
- **Fraude a la Administración: calificación provisional de la acusación** (`fraude-administracion-calificacion-provisional-acusacion-474`). Calificación provisional de la acusación por fraude a la Administración, en la que se describen los hechos, se califican jurídicamente y se piden las penas y la responsabilidad civil del acusado.
- **Funcionario que deniega una prestación por discriminación: escrito de acusación** (`funcionario-deniega-prestacion-discriminacion-escrito-279`). Escrito de acusación contra el funcionario que niega una prestación por discriminación; recoge las penas del art. 511 CP y la inhabilitación añadida por la LO 8/2021, que conviene revisar antes de redactar.
- **Infidelidad en la custodia de documentos: calificación provisional de la acusación** (`infidelidad-custodia-documentos-calificacion-provisional-440`). Calificación provisional de la acusación por infidelidad en la custodia de documentos, donde se exponen los hechos, el delito, la autoría, las circunstancias y la pena que se pide al acusado.
- **Intrusismo profesional: escrito de acusación** (`intrusismo-profesional-escrito-acusacion-244`). Escrito de acusación por intrusismo profesional, en el que la acusación expone los hechos, su calificación jurídica y la pena que solicita contra quien ejerció sin título o habilitación.
- **Malversación: calificación provisional de la acusación** (`malversacion-calificacion-provisional-acusacion-500`). Calificación provisional de la acusación por malversación, con hechos, tipo penal, autoría y penas solicitadas; revise el tipo atenuado del art. 432.3 CP y la rebaja por reparación del art. 434 tras la LO 14/2022.
- **Omisión del deber de impedir delitos: acusación** (`omision-deber-impedir-delitos-acusacion-841`). Escrito de acusación por omisión del deber de impedir delitos o de promover su persecución, con los hechos, la calificación jurídica y las penas que solicita la parte acusadora.
- **Prevaricación judicial: acusación** (`prevaricacion-judicial-acusacion-839`). Escrito de acusación por prevaricación judicial contra un juez o magistrado, con los hechos, su calificación como resolución injusta dictada a sabiendas y las penas que se solicitan.
- **Prevaricación urbanística de autoridad o funcionario: acusación (todas las CCAA)** (`prevaricacion-urbanistica-autoridad-funcionario-454`). Escrito de acusación contra la autoridad o funcionario por prevaricación urbanística, con hechos, calificación jurídica y penas solicitadas; sirve para cualquier comunidad autónoma.

### Escritos de defensa (13)

- **Delito urbanístico: defensa del constructor (todas las CCAA)** (`delito-urbanistico-defensa-constructor-todas-ccaa-457`). Escrito de defensa del constructor acusado de un delito urbanístico, que contesta a la acusación, propone prueba y pide la absolución o una calificación más favorable; sirve para cualquier comunidad autónoma.
- **Denuncia falsa: defensa** (`denuncia-falsa-defensa-846`). Escrito de defensa del acusado por denuncia falsa, que responde a la calificación de la acusación, propone prueba y pide la libre absolución o una pena menor.
- **Encubrimiento: defensa** (`encubrimiento-defensa-847`). Escrito de defensa del acusado por encubrimiento, para discrepar de la calificación de la acusación, proponer prueba y solicitar la absolución o, en su caso, una condena atenuada.
- **Enriquecimiento ilícito: escrito de defensa** (`enriquecimiento-ilicito-escrito-defensa-123`). Escrito de defensa del acusado por enriquecimiento ilícito, que contesta a la acusación, niega o matiza los hechos, propone prueba y pide la absolución o una calificación más favorable.
- **Falso testimonio: escrito de defensa** (`falso-testimonio-escrito-defensa-381`). Escrito de defensa del acusado por falso testimonio, que responde a la calificación de la acusación, propone prueba y solicita la absolución o, subsidiariamente, una condena menos grave.
- **Fraude a la Administración: calificación provisional de la defensa** (`fraude-administracion-calificacion-provisional-defensa-476`). Calificación provisional de la defensa en un proceso por fraude a la Administración, para oponerse a la acusación, proponer prueba y solicitar la absolución o una pena menor.
- **Funcionario que deniega una prestación por discriminación: escrito de defensa** (`funcionario-deniega-prestacion-discriminacion-escrito-282`). Escrito de defensa del funcionario acusado de denegar una prestación por discriminación, para contestar a la acusación, proponer prueba y pedir la absolución o una calificación más benigna.
- **Infidelidad en la custodia de documentos: calificación provisional de la defensa** (`infidelidad-custodia-documentos-calificacion-provisional-441`). Calificación provisional de la defensa en un proceso por infidelidad en la custodia de documentos, para discrepar de la acusación, proponer prueba y pedir la absolución o una pena atenuada.
- **Intrusismo profesional: escrito de defensa** (`intrusismo-profesional-escrito-defensa-241`). Escrito de defensa en un procedimiento por intrusismo profesional, para negar o matizar la calificación de la acusación, proponer prueba y solicitar la libre absolución o una pena menor.
- **Malversación: calificación provisional de la defensa** (`malversacion-calificacion-provisional-defensa-499`). Calificación provisional de la defensa en un proceso por malversación, para contestar a la acusación y pedir la absolución o la atenuación; tenga en cuenta el tipo atenuado y la reparación tras la LO 14/2022.
- **Omisión del deber de impedir delitos: defensa** (`omision-deber-impedir-delitos-defensa-836`). Escrito de defensa del acusado por omisión del deber de impedir delitos, que contesta a la acusación, propone prueba y solicita la absolución o una calificación más favorable.
- **Prevaricación judicial: defensa** (`prevaricacion-judicial-defensa-837`). Escrito de defensa del juez o magistrado acusado de prevaricación judicial, para oponerse a la calificación de la acusación, proponer prueba y pedir su absolución.
- **Prevaricación urbanística: defensa de la autoridad o funcionario (todas las CCAA)** (`prevaricacion-urbanistica-defensa-autoridad-funcionario-452`). Escrito de defensa de la autoridad o funcionario acusado de prevaricación urbanística, con su versión de los hechos, prueba propuesta y petición de absolución; válido para todas las comunidades autónomas.

### Solicitudes y escritos de trámite (1)

- **Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo** (`diputado-senador-acusacion-pide-remitir-causa-tribunal-99`). Escrito de la acusación al juez de instrucción para que remita la causa al Tribunal Supremo cuando aparecen indicios fundados contra una persona aforada, como una senadora o un diputado.
