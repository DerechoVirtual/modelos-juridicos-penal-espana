# Procedimientos ante la Fiscalía Europea · España

> Plugin de Claude Code `modelos-fiscalia-europea-espana` · **31 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los procedimientos de la Fiscalía Europea (LO 9/2021): escritos ante el Fiscal Europeo Delegado y el Juez de Garantías, personaciones, diligencias, medidas cautelares, escritos de defensa e impugnación de decretos.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 31 está al final):

- **Conformidad** (1). Por ejemplo: Fiscalía Europea: el investigado pide declarar para reconocer los hechos y conformarse.
- **Recursos e impugnaciones** (3). Por ejemplo: Fiscalía Europea: apelación contra resoluciones del Juez de Garantías; Fiscalía Europea: impugnar decretos del Fiscal Europeo Delegado; Fiscalía Europea: oposición al recurso de apelación.
- **Querellas y denuncias** (3). Por ejemplo: Fiscalía Europea: denuncia de un particular; Fiscalía Europea: querella de la acusación particular; Fiscalía Europea: denuncia a través de abogado o procurador.
- **Escritos de acusación** (1). Por ejemplo: Fiscalía Europea: escrito de acusación de la acusación particular.
- **Escritos de defensa** (2). Por ejemplo: Fiscalía Europea: escrito de defensa del responsable civil; Fiscalía Europea: escrito de defensa de la persona acusada.
- **Medidas cautelares y protección** (5). Por ejemplo: Fiscalía Europea: pedir caución sustitutoria; Fiscalía Europea: pedir que se amplíen las medidas cautelares reales; Fiscalía Europea: pedir medidas cautelares personales.
- **Solicitudes y escritos de trámite** (16). Por ejemplo: Fiscalía Europea: reclamación civil del actor civil; Fiscalía Europea: pedir que se alce el secreto; Fiscalía Europea: personación del actor civil.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Impugnar un decreto del Fiscal Europeo Delegado»
   - «Escrito de defensa de la persona acusada»
   - «Pedir diligencias de investigación que necesitan autorización judicial»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-fiscalia-europea-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-fiscalia-europea-espana:fiscalia-europea-denuncia-particular-321`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-fiscalia-europea-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-fiscalia-europea-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

