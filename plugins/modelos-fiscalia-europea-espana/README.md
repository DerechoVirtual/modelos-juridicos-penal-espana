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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-fiscalia-europea-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-fiscalia-europea-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-fiscalia-europea-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-fiscalia-europea-espana:<skill>`.

### Conformidad (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 336 | Fiscalía Europea: el investigado pide declarar para reconocer los hechos y conformarse | 2021 | `fiscalia-europea-investigado-pide-declarar-reconocer-336` |

### Recursos e impugnaciones (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 337 | Fiscalía Europea: apelación contra resoluciones del Juez de Garantías | 2021 | `fiscalia-europea-apelacion-contra-resoluciones-juez-337` |
| 339 | Fiscalía Europea: impugnar decretos del Fiscal Europeo Delegado | 2021 | `fiscalia-europea-impugnar-decretos-fiscal-europeo-339` |
| 341 | Fiscalía Europea: oposición al recurso de apelación | 2021 | `fiscalia-europea-oposicion-recurso-apelacion-341` |

### Querellas y denuncias (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 321 | Fiscalía Europea: denuncia de un particular | 2021 | `fiscalia-europea-denuncia-particular-321` |
| 326 | Fiscalía Europea: querella de la acusación particular | 2021 | `fiscalia-europea-querella-acusacion-particular-326` |
| 328 | Fiscalía Europea: denuncia a través de abogado o procurador | 2021 | `fiscalia-europea-denuncia-traves-abogado-procurador-328` |

### Escritos de acusación (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 335 | Fiscalía Europea: escrito de acusación de la acusación particular | 2021 | `fiscalia-europea-escrito-acusacion-acusacion-particular-335` |

### Escritos de defensa (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 333 | Fiscalía Europea: escrito de defensa del responsable civil | 2021 | `fiscalia-europea-escrito-defensa-responsable-civil-333` |
| 334 | Fiscalía Europea: escrito de defensa de la persona acusada | 2021 | `fiscalia-europea-escrito-defensa-persona-acusada-334` |

### Medidas cautelares y protección (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 322 | Fiscalía Europea: pedir caución sustitutoria | 2021 | `fiscalia-europea-pedir-caucion-sustitutoria-322` |
| 323 | Fiscalía Europea: pedir que se amplíen las medidas cautelares reales | 2021 | `fiscalia-europea-pedir-amplien-medidas-cautelares-reales-323` |
| 349 | Fiscalía Europea: pedir medidas cautelares personales | 2021 | `fiscalia-europea-pedir-medidas-cautelares-personales-349` |
| 350 | Fiscalía Europea: pedir que se reduzcan las medidas cautelares reales | 2021 | `fiscalia-europea-pedir-reduzcan-medidas-cautelares-350` |
| 351 | Fiscalía Europea: pedir medidas cautelares reales | 2021 | `fiscalia-europea-pedir-medidas-cautelares-reales-351` |

### Solicitudes y escritos de trámite (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 324 | Fiscalía Europea: reclamación civil del actor civil | 2021 | `fiscalia-europea-reclamacion-civil-actor-civil-324` |
| 325 | Fiscalía Europea: pedir que se alce el secreto | 2021 | `fiscalia-europea-pedir-alce-secreto-325` |
| 327 | Fiscalía Europea: personación del actor civil | 2021 | `fiscalia-europea-personacion-actor-civil-327` |
| 329 | Fiscalía Europea: el investigado aporta elementos de descargo | 2021 | `fiscalia-europea-investigado-aporta-elementos-descargo-329` |
| 330 | Fiscalía Europea: la defensa pide asegurar fuentes de prueba | 2021 | `fiscalia-europea-defensa-pide-asegurar-fuentes-prueba-330` |
| 331 | Fiscalía Europea: la acusación particular pide asegurar con urgencia fuentes de prueba | 2021 | `fiscalia-europea-acusacion-particular-pide-asegurar-331` |
| 332 | Fiscalía Europea: la acusación particular pide asegurar fuentes de prueba | 2021 | `fiscalia-europea-acusacion-particular-pide-asegurar-332` |
| 338 | Fiscalía Europea: la acusación particular participa en los actos de investigación | 2021 | `fiscalia-europea-acusacion-particular-participa-actos-338` |
| 340 | Fiscalía Europea: el investigado participa en los actos de investigación | 2021 | `fiscalia-europea-investigado-participa-actos-340` |
| 342 | Fiscalía Europea: el investigado designa abogado | 2021 | `fiscalia-europea-investigado-designa-abogado-342` |
| 343 | Fiscalía Europea: el investigado designa procurador | 2021 | `fiscalia-europea-investigado-designa-procurador-343` |
| 344 | Fiscalía Europea: testimonios para la acusación particular o el actor civil en el juicio oral | 2021 | `fiscalia-europea-testimonios-acusacion-particular-actor-344` |
| 345 | Fiscalía Europea: testimonios para la defensa en el juicio oral | 2021 | `fiscalia-europea-testimonios-defensa-juicio-oral-345` |
| 346 | Fiscalía Europea: pedir diligencias de investigación que necesitan autorización judicial | 2021 | `fiscalia-europea-pedir-diligencias-investigacion-346` |
| 347 | Fiscalía Europea: el investigado pide diligencias de investigación | 2021 | `fiscalia-europea-investigado-pide-diligencias-347` |
| 348 | Fiscalía Europea: la acusación particular pide diligencias de investigación | 2021 | `fiscalia-europea-acusacion-particular-pide-diligencias-348` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

