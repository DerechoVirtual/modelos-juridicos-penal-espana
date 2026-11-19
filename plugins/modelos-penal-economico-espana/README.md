# Blanqueo, delitos societarios y penal económico · España

> Plugin de Claude Code `modelos-penal-economico-espana` · **52 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para el derecho penal económico: blanqueo de capitales, delitos societarios, secretos de empresa, alteración de precios en el mercado y delito contable tributario.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 52 está al final):

- **Conformidad** (10). Por ejemplo: Difusión, revelación o cesión de secretos de empresa: conformidad de la defensa; Imposición de acuerdo societario abusivo: conformidad de la defensa; Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025).
- **Recursos e impugnaciones** (10). Por ejemplo: Apelación contra la condena por falseamiento de cuentas o documentos sociales (delito societario); Apelación contra la condena de un abogado por blanqueo imprudente y estafa; Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática.
- **Querellas y denuncias** (9). Por ejemplo: Blanqueo de capitales imprudente y estafa: querella contra el abogado y su cliente; Blanqueo de capitales tecnológico y estafa informática: querella; Publicidad engañosa por internet: querella.
- **Escritos de acusación** (10). Por ejemplo: Falseamiento de cuentas o documentos sociales (delito societario): acusación; Falseamiento de información financiera: acusación; Alteración de precios en el mercado: acusación.
- **Escritos de defensa** (13). Por ejemplo: Detracción de materias primas o productos de primera necesidad: defensa alegando exención; Alteración de precios en concursos y subastas públicas: defensa alegando exención; Falseamiento de información financiera por internet: defensa.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por imposición de un acuerdo societario abusivo»
   - «Querella por blanqueo de capitales y estafa informática»
   - «Conformidad de la defensa por revelación de secretos de empresa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-penal-economico-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-penal-economico-espana:detraccion-materias-primas-productos-primera-necesidad-155`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-penal-economico-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-penal-economico-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-penal-economico-espana:<skill>`). Son 52, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Conformidad (10)

- **Alteración de precios en el mercado: defensa con conformidad** (`alteracion-precios-mercado-defensa-conformidad-549`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por alteración de precios en el mercado, poniendo fin al procedimiento con sentencia de conformidad.
- **Blanqueo de capitales imprudente y estafa: conformidad del abogado acusado** (`blanqueo-capitales-imprudente-estafa-conformidad-abogado-495`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por blanqueo de capitales imprudente y estafa, cuando el acusado es abogado, poniendo fin al procedimiento con sentencia de conformidad.
- **Blanqueo de capitales tecnológico y estafa informática: defensa con conformidad** (`blanqueo-capitales-tecnologico-estafa-informatica-525`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por blanqueo de capitales tecnológico y estafa informática, poniendo fin al procedimiento con sentencia de conformidad.
- **Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025)** (`delito-contable-tributario-aplazar-renta-local-covid-19-429`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por un delito contable tributario (aplazar la renta del local, COVID-19), poniendo fin al procedimiento con sentencia de conformidad.
- **Difusión, revelación o cesión de secretos de empresa: conformidad de la defensa** (`difusion-revelacion-cesion-secretos-empresa-conformidad-269`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por difusión, revelación o cesión de secretos de empresa, poniendo fin al procedimiento con sentencia de conformidad.
- **Espionaje informático para descubrir secretos de empresa: defensa con conformidad** (`espionaje-informatico-descubrir-secretos-empresa-defensa-613`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por espionaje informático para descubrir secretos de empresa, poniendo fin al procedimiento con sentencia de conformidad.
- **Falseamiento de cuentas o documentos sociales (delito societario): defensa con conformidad** (`falseamiento-cuentas-documentos-sociales-delito-471`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por falseamiento de cuentas o documentos sociales (delito societario), poniendo fin al procedimiento con sentencia de conformidad.
- **Falseamiento de información financiera: defensa con conformidad** (`falseamiento-informacion-financiera-defensa-conformidad-543`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por falseamiento de información financiera, poniendo fin al procedimiento con sentencia de conformidad.
- **Imposición de acuerdo societario abusivo: conformidad de la defensa** (`imposicion-acuerdo-societario-abusivo-conformidad-413`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por imposición de un acuerdo societario abusivo, poniendo fin al procedimiento con sentencia de conformidad.
- **Publicidad engañosa por internet: defensa con conformidad** (`publicidad-enganosa-internet-defensa-conformidad-537`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por publicidad engañosa por internet, poniendo fin al procedimiento con sentencia de conformidad.

### Recursos e impugnaciones (10)

- **Apelación contra la condena de un abogado por blanqueo imprudente y estafa** (`apelacion-contra-condena-abogado-blanqueo-imprudente-498`). Recurso de apelación del condenado contra la sentencia que le impone una condena por blanqueo de capitales imprudente y estafa, siendo el condenado abogado, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por alteración de precios en el mercado** (`apelacion-contra-condena-alteracion-precios-mercado-546`). Recurso de apelación del condenado contra la sentencia que le impone una condena por alteración de precios en el mercado, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática** (`apelacion-contra-condena-blanqueo-capitales-tecnologico-522`). Recurso de apelación del condenado contra la sentencia que le impone una condena por blanqueo de capitales tecnológico y estafa informática, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por espionaje informático para descubrir secretos de empresa** (`apelacion-contra-condena-espionaje-informatico-descubrir-615`). Recurso de apelación del condenado contra la sentencia que le impone una condena por espionaje informático para descubrir secretos de empresa, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por falseamiento de cuentas o documentos sociales (delito societario)** (`apelacion-contra-condena-falseamiento-cuentas-documentos-469`). Recurso de apelación del condenado contra la sentencia que le impone una condena por falseamiento de cuentas o documentos sociales (delito societario), ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por falseamiento de información financiera por internet** (`apelacion-contra-condena-falseamiento-informacion-545`). Recurso de apelación del condenado contra la sentencia que le impone una condena por falseamiento de información financiera por internet, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por publicidad engañosa por internet** (`apelacion-contra-condena-publicidad-enganosa-internet-536`). Recurso de apelación del condenado contra la sentencia que le impone una condena por publicidad engañosa por internet, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Delito contable tributario para aplazar renta del local (COVID-19): apelación contra la condena** (`delito-contable-tributario-aplazar-renta-local-covid-19-432`). Recurso de apelación del condenado contra la sentencia que le impone una condena por un delito contable tributario (aplazar la renta del local, COVID-19), ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Difusión, revelación o cesión de secretos de empresa: apelación contra la condena** (`difusion-revelacion-cesion-secretos-empresa-apelacion-268`). Recurso de apelación del condenado contra la sentencia que le impone una condena por difusión, revelación o cesión de secretos de empresa, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Imposición de acuerdo societario abusivo: apelación contra la condena** (`imposicion-acuerdo-societario-abusivo-apelacion-contra-411`). Recurso de apelación del condenado contra la sentencia que le impone una condena por imposición de un acuerdo societario abusivo, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.

### Querellas y denuncias (9)

- **Alteración de precios en el mercado: querella** (`alteracion-precios-mercado-querella-547`). Querella de la acusación particular por alteración de precios en el mercado, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Blanqueo de capitales imprudente y estafa: querella contra el abogado y su cliente** (`blanqueo-capitales-imprudente-estafa-querella-contra-497`). Querella de la acusación particular por blanqueo de capitales imprudente y estafa, dirigida contra un abogado y su cliente, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Blanqueo de capitales tecnológico y estafa informática: querella** (`blanqueo-capitales-tecnologico-estafa-informatica-521`). Querella de la acusación particular por blanqueo de capitales tecnológico y estafa informática, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Delito contable tributario para aplazar renta del local (COVID-19): querella** (`delito-contable-tributario-aplazar-renta-local-covid-19-430`). Querella de la acusación particular por un delito contable tributario (aplazar la renta del local, COVID-19), con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Difusión, revelación o cesión de secretos de empresa: querella** (`difusion-revelacion-cesion-secretos-empresa-querella-271`). Querella de la acusación particular por difusión, revelación o cesión de secretos de empresa, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Espionaje informático para descubrir secretos de empresa: querella** (`espionaje-informatico-descubrir-secretos-empresa-612`). Querella de la acusación particular por espionaje informático para descubrir secretos de empresa, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Falseamiento de información financiera por internet: querella** (`falseamiento-informacion-financiera-internet-querella-542`). Querella de la acusación particular por falseamiento de información financiera por internet, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Imposición de acuerdo societario abusivo: querella** (`imposicion-acuerdo-societario-abusivo-querella-415`). Querella de la acusación particular por imposición de un acuerdo societario abusivo, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Publicidad engañosa por internet: querella** (`publicidad-enganosa-internet-querella-539`). Querella de la acusación particular por publicidad engañosa por internet, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.

### Escritos de acusación (10)

- **Alteración de precios en el mercado: acusación** (`alteracion-precios-mercado-acusacion-550`). Escrito de acusación en el procedimiento abreviado por alteración de precios en el mercado, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Blanqueo de capitales imprudente y estafa: acusación contra el abogado y su cliente** (`blanqueo-capitales-imprudente-estafa-acusacion-contra-496`). Escrito de acusación en el procedimiento abreviado por blanqueo de capitales imprudente y estafa, contra el abogado y su cliente, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Blanqueo de capitales tecnológico y estafa informática: acusación** (`blanqueo-capitales-tecnologico-estafa-informatica-523`). Escrito de acusación en el procedimiento abreviado por blanqueo de capitales tecnológico y estafa informática, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Delito contable tributario para aplazar renta del local (COVID-19): escrito de acusación** (`delito-contable-tributario-aplazar-renta-local-covid-19-428`). Escrito de acusación en el procedimiento abreviado por un delito contable tributario (aplazar la renta del local, COVID-19), con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Difusión, revelación o cesión de secretos de empresa: escrito de acusación** (`difusion-revelacion-cesion-secretos-empresa-escrito-270`). Escrito de acusación en el procedimiento abreviado por difusión, revelación o cesión de secretos de empresa, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Espionaje informático para descubrir secretos de empresa: acusación** (`espionaje-informatico-descubrir-secretos-empresa-614`). Escrito de acusación en el procedimiento abreviado por espionaje informático para descubrir secretos de empresa, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Falseamiento de cuentas o documentos sociales (delito societario): acusación** (`falseamiento-cuentas-documentos-sociales-delito-468`). Escrito de acusación en el procedimiento abreviado por falseamiento de cuentas o documentos sociales (delito societario), con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Falseamiento de información financiera: acusación** (`falseamiento-informacion-financiera-acusacion-541`). Escrito de acusación en el procedimiento abreviado por falseamiento de información financiera, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Imposición de acuerdo societario abusivo: escrito de acusación** (`imposicion-acuerdo-societario-abusivo-escrito-acusacion-414`). Escrito de acusación en el procedimiento abreviado por imposición de un acuerdo societario abusivo, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Publicidad engañosa por internet: acusación** (`publicidad-enganosa-internet-acusacion-538`). Escrito de acusación en el procedimiento abreviado por publicidad engañosa por internet, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.

### Escritos de defensa (13)

- **Alteración de precios en concursos y subastas públicas: defensa alegando exención** (`alteracion-precios-concursos-subastas-publicas-defensa-157`). Escrito de defensa del acusado por alteración de precios en concursos y subastas públicas que alega la exención de responsabilidad, rebate la calificación de la acusación y propone prueba de descargo.
- **Alteración de precios en el mercado: defensa** (`alteracion-precios-mercado-defensa-548`). Escrito de defensa del acusado en el procedimiento abreviado por alteración de precios en el mercado, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Alteración de precios en el mercado: defensa alegando exención** (`alteracion-precios-mercado-defensa-alegando-exencion-156`). Escrito de defensa del acusado por alteración de precios en el mercado que alega la exención de responsabilidad, negando la calificación de la acusación y proponiendo las pruebas de descargo.
- **Blanqueo de capitales imprudente y estafa: defensa del abogado acusado** (`blanqueo-capitales-imprudente-estafa-defensa-abogado-494`). Escrito de defensa del acusado en el procedimiento abreviado por blanqueo de capitales imprudente y estafa, siendo acusado un abogado, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Blanqueo de capitales tecnológico y estafa informática: defensa** (`blanqueo-capitales-tecnologico-estafa-informatica-524`). Escrito de defensa del acusado en el procedimiento abreviado por blanqueo de capitales tecnológico y estafa informática, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Delito contable tributario para aplazar renta del local (COVID-19): escrito de defensa** (`delito-contable-tributario-aplazar-renta-local-covid-19-431`). Escrito de defensa del acusado en el procedimiento abreviado por un delito contable tributario (aplazar la renta del local, COVID-19), que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Detracción de materias primas o productos de primera necesidad: defensa alegando exención** (`detraccion-materias-primas-productos-primera-necesidad-155`). Escrito de defensa del acusado por detracción de materias primas o productos de primera necesidad, que alega la exención de responsabilidad y propone la prueba que la sustenta ante el órgano enjuiciador.
- **Difusión, revelación o cesión de secretos de empresa: escrito de defensa** (`difusion-revelacion-cesion-secretos-empresa-escrito-267`). Escrito de defensa del acusado en el procedimiento abreviado por difusión, revelación o cesión de secretos de empresa, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Espionaje informático para descubrir secretos de empresa: defensa** (`espionaje-informatico-descubrir-secretos-empresa-defensa-616`). Escrito de defensa del acusado en el procedimiento abreviado por espionaje informático para descubrir secretos de empresa, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Falseamiento de cuentas o documentos sociales (delito societario): defensa** (`falseamiento-cuentas-documentos-sociales-delito-470`). Escrito de defensa del acusado en el procedimiento abreviado por falseamiento de cuentas o documentos sociales (delito societario), que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Falseamiento de información financiera por internet: defensa** (`falseamiento-informacion-financiera-internet-defensa-544`). Escrito de defensa del acusado en el procedimiento abreviado por falseamiento de información financiera por internet, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Imposición de acuerdo societario abusivo: escrito de defensa** (`imposicion-acuerdo-societario-abusivo-escrito-defensa-412`). Escrito de defensa del acusado en el procedimiento abreviado por imposición de un acuerdo societario abusivo, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Publicidad engañosa por internet: defensa** (`publicidad-enganosa-internet-defensa-540`). Escrito de defensa del acusado en el procedimiento abreviado por publicidad engañosa por internet, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
