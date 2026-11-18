# Hurtos, robos, estafas y ocupación (LO 1/2026) · España

> Plugin de Claude Code `modelos-estafas-robos-y-hurtos-espana` · **83 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos patrimoniales, con la reforma de la LO 1/2026: hurto (también multirreincidente, de móviles y de productos agrarios), robo, estafa, apropiación indebida, administración desleal, usurpación y ocupación, insolvencias punibles y falsedades.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 83 está al final):

- **Conformidad** (14). Por ejemplo: Hurto de productos agrarios o ganaderos: defensa con conformidad; Estafa multirreincidente o leve agravada: conformidad de la defensa; Hurto de móvil: defensa con conformidad.
- **Recursos e impugnaciones** (19). Por ejemplo: Delito continuado: apelación contra la condena pidiendo la unidad natural de acción; Estafa del inquilino que no paga el alquiler (inquiokupación): apelación contra la condena; Hurto multirreincidente: apelación contra la condena.
- **Querellas y denuncias** (16). Por ejemplo: Daños: denuncia escrita ante la policía; Alteración de lindes: denuncia; Insolvencia punible: querella.
- **Escritos de acusación** (16). Por ejemplo: Defraudación de fluido eléctrico: escrito de acusación; Allanamiento de morada por ocupación de inmueble: calificación provisional de la acusación; Administración desleal: escrito de acusación.
- **Escritos de defensa** (17). Por ejemplo: Alzamiento de bienes (frustración de la ejecución): defensa; Apropiación indebida: defensa; Falsedad en documento público: defensa.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Usurpación de inmueble: pedir que se suspenda el desahucio.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Conformidad de la defensa en un hurto multirreincidente»
   - «Querella por estafa»
   - «Denuncia por la ocupación de un inmueble que no es morada»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-estafas-robos-y-hurtos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-estafas-robos-y-hurtos-espana:hurto-productos-agrarios-ganaderos-defensa-conformidad-1`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-estafas-robos-y-hurtos-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-estafas-robos-y-hurtos-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

