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

