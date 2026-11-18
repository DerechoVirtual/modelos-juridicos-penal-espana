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

