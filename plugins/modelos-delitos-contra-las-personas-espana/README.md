# Lesiones, amenazas, coacciones y homicidio · España

> Plugin de Claude Code `modelos-delitos-contra-las-personas-espana` · **63 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para acusar o defender en delitos contra la vida, la integridad y la libertad: homicidio, lesiones, omisión del deber de socorro, amenazas, coacciones, acoso (stalking), trata de seres humanos y delitos contra menores cometidos por internet.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 63 está al final):

- **Conformidad** (8). Por ejemplo: Ocultación del paradero de un cadáver: conformidad de la defensa; Promover por internet la autolesión de menores o discapacitados: conformidad de la defensa; Promover por internet trastornos alimenticios en menores o discapacitados: conformidad de la defensa.
- **Recursos e impugnaciones** (11). Por ejemplo: Omisión del deber de socorro: apelación contra la condena; Promover por internet el suicidio de menores o discapacitados: apelación contra la condena; Lesiones por esterilización de discapacitada: apelación contra la condena.
- **Querellas y denuncias** (12). Por ejemplo: Omisión de socorro por no prestar asistencia sanitaria: querella; Amenazas informáticas: querella; Acoso en una comunidad de propietarios (blocking): querella.
- **Escritos de acusación** (17). Por ejemplo: Lesiones dolosas o imprudentes: acusación con conclusiones alternativas; Trata de seres humanos: calificación provisional de la acusación; Lesiones con agravante de aporofobia o exclusión social: escrito de acusación.
- **Escritos de defensa** (13). Por ejemplo: Lesiones: escrito de defensa; Amenazas en redes sociales: calificación provisional de la defensa; Coacciones por mensajes de WhatsApp: defensa.
- **Medidas cautelares y protección** (1). Por ejemplo: Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Trata en tránsito: auto de inhibición a favor del Tribunal Central de Instancia.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Escrito de acusación por lesiones»
   - «Escrito de defensa en un delito de acoso (stalking)»
   - «Pedir una orden de alejamiento y prohibición de comunicación por acoso»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-delitos-contra-las-personas-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-delitos-contra-las-personas-espana:trata-transito-auto-inhibicion-favor-tribunal-central-35`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-contra-las-personas-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-delitos-contra-las-personas-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

