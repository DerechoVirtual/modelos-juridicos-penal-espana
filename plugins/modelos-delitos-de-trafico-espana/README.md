# Alcoholemia, conducción sin carné y juicio rápido · España

> Plugin de Claude Code `modelos-delitos-de-trafico-espana` · **39 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos de tráfico: conducción con alcohol o drogas, negativa a las pruebas, conducción sin permiso, temeraria o a velocidad excesiva, abandono del lugar del accidente, lesiones por imprudencia y juicio rápido.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 39 está al final):

- **Conformidad** (10). Por ejemplo: Grave riesgo vial por colocar obstáculos en la vía: conformidad de la defensa; Conducción sin permiso y bajo los efectos de drogas o alcohol: conformidad de la defensa; Conducción a velocidad excesiva: conformidad de la defensa.
- **Recursos e impugnaciones** (9). Por ejemplo: Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento; Conducción temeraria con manifiesto desprecio por la vida ajena: apelación contra la condena; Conducción temeraria: apelación contra la condena.
- **Querellas y denuncias** (5). Por ejemplo: Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia; Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella; Conducción bajo la influencia del alcohol y lesiones: querella.
- **Escritos de acusación** (7). Por ejemplo: Accidente con vehículo a motor: acusación del actor civil en el abreviado; Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de acusación; Conducción a velocidad excesiva: escrito de acusación.
- **Escritos de defensa** (6). Por ejemplo: Grave riesgo vial por colocar obstáculos en la vía: escrito de defensa; Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de defensa; Conducción a velocidad excesiva: escrito de defensa.
- **Solicitudes y escritos de trámite** (2). Por ejemplo: Allegado del perjudicado: reclamación a la aseguradora; Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Conformidad en un juicio rápido por conducir bajo los efectos del alcohol»
   - «Querella por abandono del lugar del accidente y lesiones»
   - «Denuncia por lesiones por imprudencia con un vehículo a motor»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-delitos-de-trafico-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-delitos-de-trafico-espana:accidente-vehiculo-motor-acusacion-actor-civil-abreviado-105`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-de-trafico-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-delitos-de-trafico-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-delitos-de-trafico-espana:<skill>`). Son 39, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Conformidad (10)

- **Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa con conformidad** (`abandono-lugar-accidente-lesiones-imprudentes-trafico-505`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por abandono del lugar del accidente y lesiones imprudentes de tráfico, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción a velocidad excesiva: conformidad de la defensa** (`conduccion-velocidad-excesiva-conformidad-defensa-359`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción a velocidad excesiva, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción bajo la influencia del alcohol y lesiones: defensa con conformidad en el abreviado** (`conduccion-bajo-influencia-alcohol-lesiones-defensa-798`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción bajo la influencia del alcohol con lesiones, en el procedimiento abreviado, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción bajo la influencia del alcohol: defensa con conformidad en juicio rápido** (`conduccion-bajo-influencia-alcohol-defensa-conformidad-796`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción bajo la influencia del alcohol, en el juicio rápido, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción sin permiso y bajo los efectos de drogas o alcohol: conformidad de la defensa** (`conduccion-sin-permiso-bajo-efectos-drogas-alcohol-247`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción sin permiso y bajo los efectos de drogas o alcohol, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción temeraria con manifiesto desprecio por la vida ajena: conformidad de la defensa** (`conduccion-temeraria-manifiesto-desprecio-vida-ajena-366`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción temeraria con manifiesto desprecio por la vida ajena, poniendo fin al procedimiento con sentencia de conformidad.
- **Conducción temeraria: conformidad de la defensa** (`conduccion-temeraria-conformidad-defensa-371`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por conducción temeraria, poniendo fin al procedimiento con sentencia de conformidad.
- **Grave riesgo vial por colocar obstáculos en la vía: conformidad de la defensa** (`grave-riesgo-vial-colocar-obstaculos-via-conformidad-240`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por grave riesgo vial por colocar obstáculos en la vía, poniendo fin al procedimiento con sentencia de conformidad.
- **Negativa a las pruebas de alcoholemia: defensa con conformidad en el abreviado** (`negativa-pruebas-alcoholemia-defensa-conformidad-801`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por negativa a las pruebas de alcoholemia, en el procedimiento abreviado, poniendo fin al procedimiento con sentencia de conformidad.
- **Negativa a las pruebas de alcoholemia: defensa con conformidad en juicio rápido** (`negativa-pruebas-alcoholemia-defensa-conformidad-juicio-802`). Escrito de la defensa para mostrar su conformidad con la acusación y la pena pedida en el proceso por negativa a las pruebas de alcoholemia, en el juicio rápido, poniendo fin al procedimiento con sentencia de conformidad.

### Recursos e impugnaciones (9)

- **Apelación contra la condena por abandono del lugar del accidente y lesiones imprudentes de tráfico** (`apelacion-contra-condena-abandono-lugar-accidente-504`). Recurso de apelación del condenado contra la sentencia que le impone una condena por abandono del lugar del accidente y lesiones imprudentes de tráfico, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por conducir bajo la influencia del alcohol** (`apelacion-contra-condena-conducir-bajo-influencia-797`). Recurso de apelación del condenado contra la sentencia que le impone una condena por conducción bajo la influencia del alcohol, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Apelación contra la condena por negarse a las pruebas de alcoholemia** (`apelacion-contra-condena-negarse-pruebas-alcoholemia-800`). Recurso de apelación del condenado contra la sentencia que le impone una condena por negativa a las pruebas de alcoholemia, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Conducción a velocidad excesiva: apelación contra la condena** (`conduccion-velocidad-excesiva-apelacion-contra-condena-360`). Recurso de apelación del condenado contra la sentencia que le impone una condena por conducción a velocidad excesiva, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Conducción sin permiso y bajo los efectos de drogas o alcohol: apelación contra la condena** (`conduccion-sin-permiso-bajo-efectos-drogas-alcohol-248`). Recurso de apelación del condenado contra la sentencia que le impone una condena por conducción sin permiso y bajo los efectos de drogas o alcohol, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Conducción temeraria con manifiesto desprecio por la vida ajena: apelación contra la condena** (`conduccion-temeraria-manifiesto-desprecio-vida-ajena-363`). Recurso de apelación del condenado contra la sentencia que le impone una condena por conducción temeraria con manifiesto desprecio por la vida ajena, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Conducción temeraria: apelación contra la condena** (`conduccion-temeraria-apelacion-contra-condena-368`). Recurso de apelación del condenado contra la sentencia que le impone una condena por conducción temeraria, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Grave riesgo vial por colocar obstáculos en la vía: apelación contra la condena** (`grave-riesgo-vial-colocar-obstaculos-via-apelacion-238`). Recurso de apelación del condenado contra la sentencia que le impone una condena por grave riesgo vial por colocar obstáculos en la vía, ante la Sección de la Audiencia Provincial, para pedir su revocación o una reducción de la pena.
- **Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento** (`lesiones-accidente-trafico-oposicion-reforma-contra-118`). Escrito de oposición al recurso de reforma interpuesto contra el auto de sobreseimiento en un proceso por lesiones en accidente de tráfico, para que se mantenga el archivo de la causa, negando la infracción grave determinante.

### Querellas y denuncias (5)

- **Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella** (`abandono-lugar-accidente-lesiones-imprudentes-trafico-506`). Querella de la acusación particular por abandono del lugar del accidente y lesiones imprudentes de tráfico, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Conducción bajo la influencia del alcohol y lesiones: querella** (`conduccion-bajo-influencia-alcohol-lesiones-querella-794`). Querella de la acusación particular por conducción bajo la influencia del alcohol y lesiones, calificando estas como imprudentes, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Conducción sin permiso y bajo los efectos de drogas o alcohol: querella** (`conduccion-sin-permiso-bajo-efectos-drogas-alcohol-250`). Querella de la acusación particular por conducción sin permiso y bajo los efectos de drogas o alcohol, con los hechos, su calificación jurídica y las diligencias que se piden al tribunal de instrucción para abrir el proceso penal.
- **Conducción temeraria: denuncia** (`conduccion-temeraria-denuncia-370`). Denuncia por un delito de conducción temeraria que se presenta ante el órgano de instrucción para poner los hechos en su conocimiento, identificar al conductor y pedir que se practiquen las diligencias de investigación.
- **Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia** (`delito-leve-lesiones-imprudencia-menos-grave-vehiculo-372`). Denuncia por un delito leve de lesiones causadas por imprudencia menos grave con un vehículo a motor, presentada por el perjudicado para que se investigue el hecho y se le reconozca como parte.

### Escritos de acusación (7)

- **Abandono del lugar del accidente y lesiones imprudentes de tráfico: acusación** (`abandono-lugar-accidente-lesiones-imprudentes-trafico-507`). Escrito de acusación en el procedimiento abreviado por abandono del lugar del accidente y lesiones imprudentes de tráfico, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Accidente con vehículo a motor: acusación del actor civil en el abreviado** (`accidente-vehiculo-motor-acusacion-actor-civil-abreviado-105`). Escrito de acusación del actor civil en el procedimiento abreviado por un accidente con vehículo a motor, en el que reclama la responsabilidad civil por los daños y lesiones y propone la prueba correspondiente.
- **Conducción a velocidad excesiva: escrito de acusación** (`conduccion-velocidad-excesiva-escrito-acusacion-361`). Escrito de acusación en el procedimiento abreviado por conducción a velocidad excesiva, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Conducción bajo la influencia del alcohol y lesiones: acusación** (`conduccion-bajo-influencia-alcohol-lesiones-acusacion-795`). Escrito de acusación en el procedimiento abreviado por conducción bajo la influencia del alcohol y lesiones, con calificación imprudente de las lesiones, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de acusación** (`conduccion-sin-permiso-bajo-efectos-drogas-alcohol-249`). Escrito de acusación en el procedimiento abreviado por conducción sin permiso y bajo los efectos de drogas o alcohol, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de acusación** (`conduccion-temeraria-manifiesto-desprecio-vida-ajena-365`). Escrito de acusación en el procedimiento abreviado por conducción temeraria con manifiesto desprecio por la vida ajena, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.
- **Conducción temeraria: escrito de acusación** (`conduccion-temeraria-escrito-acusacion-369`). Escrito de acusación en el procedimiento abreviado por conducción temeraria, con los hechos, su calificación, la pena y la responsabilidad civil que se piden y las pruebas propuestas.

### Escritos de defensa (6)

- **Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa** (`abandono-lugar-accidente-lesiones-imprudentes-trafico-503`). Escrito de defensa del acusado en el procedimiento abreviado por abandono del lugar del accidente y lesiones imprudentes de tráfico, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Conducción a velocidad excesiva: escrito de defensa** (`conduccion-velocidad-excesiva-escrito-defensa-358`). Escrito de defensa del acusado en el procedimiento abreviado por conducción a velocidad excesiva, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de defensa** (`conduccion-sin-permiso-bajo-efectos-drogas-alcohol-246`). Escrito de defensa del acusado en el procedimiento abreviado por conducción sin permiso y bajo los efectos de drogas o alcohol, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de defensa** (`conduccion-temeraria-manifiesto-desprecio-vida-ajena-364`). Escrito de defensa del acusado en el procedimiento abreviado por conducción temeraria con manifiesto desprecio por la vida ajena, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Conducción temeraria: escrito de defensa** (`conduccion-temeraria-escrito-defensa-367`). Escrito de defensa del acusado en el procedimiento abreviado por conducción temeraria, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.
- **Grave riesgo vial por colocar obstáculos en la vía: escrito de defensa** (`grave-riesgo-vial-colocar-obstaculos-via-escrito-defensa-239`). Escrito de defensa del acusado en el procedimiento abreviado por grave riesgo vial por colocar obstáculos en la vía, que niega o matiza los hechos y su calificación, plantea una alternativa y propone prueba de descargo.

### Solicitudes y escritos de trámite (2)

- **Allegado del perjudicado: reclamación a la aseguradora** (`allegado-perjudicado-reclamacion-aseguradora-362`). Carta de un allegado del perjudicado a la compañía aseguradora para reclamar la indemnización que le corresponde por el accidente, identificando la póliza, el vehículo y el tomador y fijando el importe pedido.
- **Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto** (`negativa-pruebas-alcoholemia-defensa-pide-proceso-799`). Escrito de la defensa en un proceso por negativa a las pruebas de alcoholemia para solicitar que se tramite por el proceso por aceptación de decreto, evitando el juicio si el acusado acepta la propuesta.
