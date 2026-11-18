# Euroorden y cooperación penal en la UE · España

> Plugin de Claude Code `modelos-euroorden-y-cooperacion-penal-espana` · **33 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para causas con elemento europeo: reconocimiento mutuo de resoluciones penales (Ley 23/2014), su transmisión a otro Estado y los recursos contra ellas, euroorden, orden europea de investigación, justicia gratuita transfronteriza e indemnizaciones a víctimas en casos transfronterizos.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 33 está al final):

- **Recursos e impugnaciones** (15). Por ejemplo: Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de Instrucción); Denegar la ejecución de una resolución UE: reforma (Sección de Instrucción); Euroorden de entrega al Estado requirente: apelación.
- **Resoluciones, actas y documentos** (7). Por ejemplo: Indemnización en casos transfronterizos: impreso para transmitir la solicitud; Formulario para saber qué Estado miembro tiene antecedentes penales de un nacional de tercer país; Transacción judicial en regímenes económicos matrimoniales: certificación.
- **Solicitudes y escritos de trámite** (11). Por ejemplo: Justicia gratuita en otro Estado miembro de la UE: solicitud; Justicia gratuita transfronteriza: formulario para transmitir la solicitud; Ejecución en la UE de una resolución de la Sección de Instrucción: pedir su transmisión.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir que una resolución se ejecute en otro Estado de la UE»
   - «Personación para el reconocimiento de una resolución penal de otro Estado de la UE»
   - «Recurso de apelación contra la entrega en una euroorden»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-euroorden-y-cooperacion-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-euroorden-y-cooperacion-penal-espana:indemnizacion-casos-transfronterizos-impreso-transmitir-395`. Los nombres están en la lista de formularios de abajo.

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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-euroorden-y-cooperacion-penal-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-euroorden-y-cooperacion-penal-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-euroorden-y-cooperacion-penal-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-euroorden-y-cooperacion-penal-espana:<skill>`.

### Recursos e impugnaciones (15)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 575 | Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de Instrucción) | 2018 | `transmision-reconocimiento-mutuo-ue-reforma-subsidiaria-575` |
| 577 | Denegar la ejecución de una resolución UE: reforma (Sección de Instrucción) | 2018 | `denegar-ejecucion-resolucion-ue-reforma-seccion-577` |
| 578 | Transmisión por reconocimiento mutuo UE: súplica (Audiencia Provincial) | 2018 | `transmision-reconocimiento-mutuo-ue-suplica-audiencia-578` |
| 579 | Denegar la ejecución de una resolución UE: apelación (Sección de lo Penal) | 2018 | `denegar-ejecucion-resolucion-ue-apelacion-seccion-lo-579` |
| 580 | Denegar la ejecución de una resolución UE: apelación (Sección de Instrucción) | 2018 | `denegar-ejecucion-resolucion-ue-apelacion-seccion-580` |
| 581 | Denegar la ejecución de una resolución UE: súplica (Audiencia Provincial) | 2018 | `denegar-ejecucion-resolucion-ue-suplica-audiencia-581` |
| 582 | Denegar la ejecución de una resolución UE: reforma (Sección de lo Penal) | 2018 | `denegar-ejecucion-resolucion-ue-reforma-seccion-lo-penal-582` |
| 583 | Denegar la ejecución de una resolución UE: reforma y subsidiaria apelación (Sección de lo Penal) | 2018 | `denegar-ejecucion-resolucion-ue-reforma-subsidiaria-583` |
| 584 | Transmisión por reconocimiento mutuo UE: reforma (Sección de lo Penal) | 2018 | `transmision-reconocimiento-mutuo-ue-reforma-seccion-lo-584` |
| 586 | Transmisión por reconocimiento mutuo UE: apelación (Sección de Instrucción) | 2018 | `transmision-reconocimiento-mutuo-ue-apelacion-seccion-586` |
| 587 | Transmisión por reconocimiento mutuo UE: reforma (juez de instrucción) | 2018 | `transmision-reconocimiento-mutuo-ue-reforma-juez-587` |
| 589 | Transmisión por reconocimiento mutuo UE: reforma y subsidiaria apelación (Sección de lo Penal) | 2018 | `transmision-reconocimiento-mutuo-ue-reforma-subsidiaria-589` |
| 590 | Denegar la ejecución de una resolución UE: reforma y subsidiaria apelación (Sección de Instrucción) | 2018 | `denegar-ejecucion-resolucion-ue-reforma-subsidiaria-590` |
| 595 | Transmisión por reconocimiento mutuo UE: apelación (Sección de lo Penal) | 2018 | `transmision-reconocimiento-mutuo-ue-apelacion-seccion-lo-595` |
| 602 | Euroorden de entrega al Estado requirente: apelación | 2018 | `euroorden-entrega-estado-requirente-apelacion-602` |

### Resoluciones, actas y documentos (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 395 | Indemnización en casos transfronterizos: impreso para transmitir la solicitud | 2020 | `indemnizacion-casos-transfronterizos-impreso-transmitir-395` |
| 396 | Indemnización en casos transfronterizos: impreso para transmitir la decisión sobre la solicitud | 2020 | `indemnizacion-casos-transfronterizos-impreso-transmitir-396` |
| 488 | Formulario para saber qué Estado miembro tiene antecedentes penales de un nacional de tercer país | 2019 | `formulario-saber-estado-miembro-tiene-antecedentes-488` |
| 519 | Transacción judicial en regímenes económicos matrimoniales: certificación | 2019 | `transaccion-judicial-regimenes-economicos-matrimoniales-519` |
| 558 | Formulario de orden europea de investigación (OEI) | 2018 | `formulario-orden-europea-investigacion-oei-558` |
| 559 | Notificar a otro Estado de la UE las intervenciones de telecomunicaciones en su territorio | 2018 | `notificar-otro-estado-ue-intervenciones-559` |
| 560 | Acuse de recibo de una orden europea de investigación | 2018 | `acuse-recibo-orden-europea-investigacion-560` |

### Solicitudes y escritos de trámite (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 397 | Justicia gratuita en otro Estado miembro de la UE: solicitud | 2020 | `justicia-gratuita-otro-estado-miembro-ue-solicitud-397` |
| 398 | Justicia gratuita transfronteriza: formulario para transmitir la solicitud | 2020 | `justicia-gratuita-transfronteriza-formulario-transmitir-398` |
| 574 | Ejecución en la UE de una resolución de la Sección de Instrucción: pedir su transmisión | 2018 | `ejecucion-ue-resolucion-seccion-instruccion-pedir-574` |
| 576 | Reconocimiento de resolución penal UE: personación con Abogado ante la Sección de Instrucción | 2018 | `reconocimiento-resolucion-penal-ue-personacion-abogado-576` |
| 585 | Ejecución en la UE de una resolución de la Audiencia Provincial: pedir su transmisión | 2018 | `ejecucion-ue-resolucion-audiencia-provincial-pedir-585` |
| 588 | Ejecución en la UE de una resolución de la Sección de lo Penal: pedir su transmisión | 2018 | `ejecucion-ue-resolucion-seccion-lo-penal-pedir-588` |
| 591 | Reconocimiento de resolución penal UE: personación con Abogado ante la Audiencia Provincial | 2018 | `reconocimiento-resolucion-penal-ue-personacion-abogado-591` |
| 592 | Reconocimiento de resolución penal UE: personación con Procurador ante la Audiencia Provincial | 2018 | `reconocimiento-resolucion-penal-ue-personacion-592` |
| 593 | Reconocimiento de resolución penal UE: personación con Procurador ante la Sección de lo Penal | 2018 | `reconocimiento-resolucion-penal-ue-personacion-593` |
| 594 | Reconocimiento de resolución penal UE: personación con Abogado ante la Sección de lo Penal | 2018 | `reconocimiento-resolucion-penal-ue-personacion-abogado-594` |
| 596 | Reconocimiento de resolución penal UE: personación con Procurador ante la Sección de Instrucción | 2018 | `reconocimiento-resolucion-penal-ue-personacion-596` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

