# Acusación particular y derechos de la víctima · España

> Plugin de Claude Code `modelos-defensa-de-victimas-espana` · **54 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para representar a la víctima: derechos del Estatuto de la víctima, acusación particular, declaración telemática y protección frente a los medios, prueba preconstituida de menores, mediación penal y justicia restaurativa.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 54 está al final):

- **Conformidad** (3). Por ejemplo: Acuerdo de reparación: el investigado pide remitir la causa a enjuiciamiento para conformarse; Víctima que se opone a la posible conformidad del acusado; Acuerdo de reparación: conformidad del acusado ante el órgano de enjuiciamiento.
- **Recursos e impugnaciones** (4). Por ejemplo: Sobreseimiento libre: reforma y subsidiaria apelación de la víctima; Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima; Libertad condicional del penado: reforma y apelación de la víctima.
- **Escritos de acusación** (1). Por ejemplo: Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio.
- **Escritos de defensa** (1). Por ejemplo: Menor o discapacitado: la defensa propone que declare en el plenario.
- **Resoluciones, actas y documentos** (11). Por ejemplo: Mediación penal: traslado inicial del expediente a los letrados de las partes; Mediación penal: entrevista inicial informativa; Mediación penal: traslado del acuerdo a los letrados por el equipo de mediación.
- **Solicitudes y escritos de trámite** (33). Por ejemplo: Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa; Menor afectado por un proceso penal: su representante pide que sea oído; Persona mayor de edad afectada por un proceso penal: pedir ser oída.
- **Otros** (1). Por ejemplo: Víctima: oponerse a la clasificación en tercer grado del penado.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir que la declaración de un menor de 14 años sea prueba preconstituida»
   - «Acuerdo de mediación penal por impago de pensiones»
   - «Petición de la acusación particular para derivar la causa a justicia restaurativa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-defensa-de-victimas-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-defensa-de-victimas-espana:acuerdo-reparacion-investigado-pide-archivo-causa-penal-46`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-defensa-de-victimas-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-defensa-de-victimas-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

