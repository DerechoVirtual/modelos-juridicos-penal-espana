# Reforma, apelación y casación penal · España

> Plugin de Claude Code `modelos-recursos-penales-espana` · **24 formularios** · área: Penal (incluye 2 formularios de Procesal, marcados «(Procesal)») · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para recurrir en el proceso penal: reforma, apelación, queja y casación, oposición a los recursos de las otras partes, demanda de amparo y revisión de una condena firme tras una sentencia del Tribunal Europeo de Derechos Humanos.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 24 está al final):

- **Conformidad** (1). Por ejemplo: Procedimiento común: apelación de la defensa contra la sentencia de conformidad.
- **Recursos e impugnaciones** (21). Por ejemplo: Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado; Revisión penal tras una sentencia del TEDH: interposición del recurso; Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Casación desierta: decreto del Letrado de la Administración de Justicia.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Recurso de reforma y subsidiario de apelación contra el auto de prisión provisional»
   - «Recurso contra el sobreseimiento provisional de las diligencias previas»
   - «Apelación de la defensa contra una sentencia de conformidad»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-recursos-penales-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-recursos-penales-espana:oponerse-recurso-reforma-subsidiario-apelacion-contra-24`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-recursos-penales-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-recursos-penales-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-recursos-penales-espana:<skill>`). Son 24, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Conformidad (1)

- **Procedimiento común: apelación de la defensa contra la sentencia de conformidad** (`procedimiento-comun-apelacion-defensa-contra-sentencia-54`). Recurso de apelación de la defensa contra una sentencia dictada por conformidad en el procedimiento común, para impugnar la validez de la conformidad prestada o la sentencia que la recoge.

### Recursos e impugnaciones (21)

- **Abreviado: apelación contra el auto que deniega la apertura del juicio oral** (`abreviado-apelacion-contra-auto-deniega-apertura-juicio-103`). Recurso de apelación de la acusación contra el auto que, en el procedimiento abreviado, deniega la apertura del juicio oral y sobresee la causa, para que el tribunal superior ordene abrir el juicio.
- **Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar** (`abreviado-apelacion-contra-auto-le-pone-fin-tras-53`). Recurso de apelación de la acusación particular contra el auto que pone fin al procedimiento abreviado tras la audiencia preliminar, ante la Sección de lo Penal del Tribunal de Instancia o la Audiencia Provincial.
- **Abreviado: oposición a la adhesión a la apelación contra la sentencia** (`abreviado-oposicion-adhesion-apelacion-contra-sentencia-154`). Escrito de oposición, en el procedimiento abreviado, a la adhesión a la apelación formulada por la parte apelada contra la sentencia, presentado ante el tribunal de instancia para su remisión a la Audiencia Provincial.
- **Abreviado: oposición a la apelación contra la denegación de apertura del juicio oral** (`abreviado-oposicion-apelacion-contra-denegacion-apertura-101`). Escrito de la defensa del acusado en el procedimiento abreviado que se opone a la apelación de la acusación particular contra el auto que deniega la apertura del juicio oral y decreta el sobreseimiento.
- **Auto de la Audiencia Provincial: apelación penal** (`auto-audiencia-provincial-apelacion-penal-770`). Recurso de apelación ante la Sala de lo Civil y Penal del Tribunal Superior de Justicia contra un auto de sobreseimiento de la Audiencia Provincial, cuando se denegaron diligencias de prueba solicitadas en instancia.
- **Auto de libertad provisional del investigado o encausado: apelación** (`auto-libertad-provisional-investigado-encausado-618`). Recurso de apelación contra el auto que acuerda la libertad provisional del investigado o encausado, presentado ante el tribunal superior para que lo revoque o modifique las condiciones impuestas.
- **Auto de libertad provisional del investigado o encausado: reforma y subsidiaria apelación** (`auto-libertad-provisional-investigado-encausado-reforma-617`). Recurso de reforma y subsidiario de apelación contra el auto que acuerda la libertad provisional del investigado o encausado, para pedir que se revoque o se imponga una medida más severa.
- **Denegación de traductor o intérprete: reforma de la defensa del investigado** (`denegacion-traductor-interprete-reforma-defensa-742`). Recurso de reforma de la defensa del investigado contra la denegación de traductor o intérprete, para pedir que se le asista en su idioma y se garantice su derecho de defensa.
- **Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado** (`oponerse-recurso-reforma-subsidiario-apelacion-contra-24`). Escrito de la parte no recurrente que se opone al recurso de reforma y subsidiario de apelación interpuesto contra un auto del procedimiento abreviado, incluido el auto de transformación en abreviado.
- **Paso del abreviado a jurado denegado tácitamente: queja de la acusación particular** (`paso-abreviado-jurado-denegado-tacitamente-queja-159`). Escrito de queja de la acusación particular contra la denegación tácita del paso del procedimiento abreviado al del tribunal del jurado, para que el tribunal superior revise esa decisión.
- **Paso del ordinario al abreviado denegado: queja del investigado** (`paso-ordinario-abreviado-denegado-queja-investigado-160`). Escrito de queja del investigado contra la denegación del paso del procedimiento ordinario al abreviado, para que el tribunal superior revise esa decisión.
- **Prisión provisional en el abreviado: reforma y subsidiario de apelación** (`prision-provisional-abreviado-reforma-subsidiario-167`). Recurso de reforma y subsidiario de apelación contra el auto de prisión provisional dictado en el procedimiento abreviado, para pedir la libertad o una medida menos gravosa para el investigado.
- **Prueba de la defensa denegada en el procedimiento abreviado: queja (hasta el 2 de abril de 2025)** (`prueba-defensa-denegada-procedimiento-abreviado-queja-556`). Escrito de queja de la defensa por la denegación de prueba en el procedimiento abreviado, aplicable hasta el 2 de abril de 2025; desde entonces la prueba denegada se reproduce en la audiencia preliminar.
- **Prórroga de la instrucción: reforma y subsidiaria apelación** (`prorroga-instruccion-reforma-subsidiaria-apelacion-486`). Recurso de reforma y subsidiario de apelación contra el auto que prorroga la instrucción, para pedir que se deje sin efecto la prórroga o se revise su duración y justificación.
- **Querella inadmitida: reforma y subsidiario de apelación** (`querella-inadmitida-reforma-subsidiario-apelacion-121`). Recurso de reforma y subsidiario de apelación de quien presentó una querella inadmitida, para que el juez reconsidere la decisión o, en su defecto, el tribunal superior la revoque y admita a trámite la querella.
- **Recurso de amparo (Acuerdo TC de 15 de marzo de 2023, válido hasta el 14 de septiembre de 2026)** (`recurso-amparo-acuerdo-tc-15-marzo-2023-valido-hasta-14-70`). Demanda de recurso de amparo ante el Tribunal Constitucional por vulneración de derechos fundamentales en un proceso penal, con la medida cautelar de suspensión; revise la vigencia del Acuerdo del TC citado en el título.
- **Recurso de anulación: impugnación de la parte acusadora** (`recurso-anulacion-impugnacion-parte-acusadora-153`). Escrito de la parte acusadora que se opone al recurso de anulación interpuesto por el condenado contra la sentencia, pidiendo que se desestime y se mantenga la resolución recurrida.
- **Revisión penal tras una sentencia del TEDH: interposición del recurso** (`revision-penal-tras-sentencia-tedh-interposicion-recurso-p18`). Escrito de interposición del recurso de revisión penal tras una sentencia del TEDH, una vez autorizado; revise los requisitos de legitimación, el plazo de quince días y la persistencia de los efectos de la violación.
- **Sobreseimiento libre de la AP o la AN: recurso de casación** (`sobreseimiento-libre-ap-an-recurso-casacion-251`). Recurso de casación de la acusación particular contra el auto de sobreseimiento libre dictado por una Audiencia Provincial o por la Audiencia Nacional, presentado ante el mismo órgano para su remisión al Tribunal Supremo.
- **Sobreseimiento provisional tras las diligencias previas: reforma y subsidiaria apelación** (`sobreseimiento-provisional-tras-diligencias-previas-479`). Recurso de reforma y subsidiario de apelación contra el auto de sobreseimiento provisional dictado tras las diligencias previas, para que se reabra la investigación o se revoque el archivo.
- **Sobreseimiento provisional: oposición a la apelación** (`sobreseimiento-provisional-oposicion-apelacion-169`). Escrito de oposición a la apelación interpuesta contra un auto de sobreseimiento provisional, para pedir que el tribunal superior confirme el archivo provisional de la causa.

### Resoluciones, actas y documentos (1)

- **Casación desierta: decreto del Letrado de la Administración de Justicia** (`casacion-desierta-decreto-letrado-administracion-158`). Decreto del Letrado de la Administración de Justicia que declara desierto el recurso de casación por no haberse interpuesto en plazo, con indicación del recurso de revisión que cabe ante el Tribunal Supremo.

### Solicitudes y escritos de trámite (1)

- **Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir** (`revision-penal-tras-sentencia-tedh-pedir-autorizacion-p19`). Solicitud de autorización para interponer el recurso de revisión penal tras una sentencia del TEDH, que debe formularse dentro del año desde su firmeza y justificar que persisten los efectos de la violación.
