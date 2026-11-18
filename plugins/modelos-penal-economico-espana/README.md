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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-penal-economico-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-penal-economico-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-penal-economico-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-penal-economico-espana:<skill>`.

### Conformidad (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 269 | Difusión, revelación o cesión de secretos de empresa: conformidad de la defensa | 2022 | `difusion-revelacion-cesion-secretos-empresa-conformidad-269` |
| 413 | Imposición de acuerdo societario abusivo: conformidad de la defensa | 2020 | `imposicion-acuerdo-societario-abusivo-conformidad-413` |
| 429 | Delito contable tributario para aplazar renta del local (COVID-19): conformidad (hasta el 2/4/2025) | 2020 | `delito-contable-tributario-aplazar-renta-local-covid-19-429` |
| 471 | Falseamiento de cuentas o documentos sociales (delito societario): defensa con conformidad | 2019 | `falseamiento-cuentas-documentos-sociales-delito-471` |
| 495 | Blanqueo de capitales imprudente y estafa: conformidad del abogado acusado | 2019 | `blanqueo-capitales-imprudente-estafa-conformidad-abogado-495` |
| 525 | Blanqueo de capitales tecnológico y estafa informática: defensa con conformidad | 2018 | `blanqueo-capitales-tecnologico-estafa-informatica-525` |
| 537 | Publicidad engañosa por internet: defensa con conformidad | 2018 | `publicidad-enganosa-internet-defensa-conformidad-537` |
| 543 | Falseamiento de información financiera: defensa con conformidad | 2018 | `falseamiento-informacion-financiera-defensa-conformidad-543` |
| 549 | Alteración de precios en el mercado: defensa con conformidad | 2018 | `alteracion-precios-mercado-defensa-conformidad-549` |
| 613 | Espionaje informático para descubrir secretos de empresa: defensa con conformidad | 2018 | `espionaje-informatico-descubrir-secretos-empresa-defensa-613` |

### Recursos e impugnaciones (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 268 | Difusión, revelación o cesión de secretos de empresa: apelación contra la condena | 2022 | `difusion-revelacion-cesion-secretos-empresa-apelacion-268` |
| 411 | Imposición de acuerdo societario abusivo: apelación contra la condena | 2020 | `imposicion-acuerdo-societario-abusivo-apelacion-contra-411` |
| 432 | Delito contable tributario para aplazar renta del local (COVID-19): apelación contra la condena | 2020 | `delito-contable-tributario-aplazar-renta-local-covid-19-432` |
| 469 | Apelación contra la condena por falseamiento de cuentas o documentos sociales (delito societario) | 2019 | `apelacion-contra-condena-falseamiento-cuentas-documentos-469` |
| 498 | Apelación contra la condena de un abogado por blanqueo imprudente y estafa | 2019 | `apelacion-contra-condena-abogado-blanqueo-imprudente-498` |
| 522 | Apelación contra la condena por blanqueo de capitales tecnológico y estafa informática | 2018 | `apelacion-contra-condena-blanqueo-capitales-tecnologico-522` |
| 536 | Apelación contra la condena por publicidad engañosa por internet | 2018 | `apelacion-contra-condena-publicidad-enganosa-internet-536` |
| 545 | Apelación contra la condena por falseamiento de información financiera por internet | 2018 | `apelacion-contra-condena-falseamiento-informacion-545` |
| 546 | Apelación contra la condena por alteración de precios en el mercado | 2018 | `apelacion-contra-condena-alteracion-precios-mercado-546` |
| 615 | Apelación contra la condena por espionaje informático para descubrir secretos de empresa | 2018 | `apelacion-contra-condena-espionaje-informatico-descubrir-615` |

### Querellas y denuncias (9)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 271 | Difusión, revelación o cesión de secretos de empresa: querella | 2022 | `difusion-revelacion-cesion-secretos-empresa-querella-271` |
| 415 | Imposición de acuerdo societario abusivo: querella | 2020 | `imposicion-acuerdo-societario-abusivo-querella-415` |
| 430 | Delito contable tributario para aplazar renta del local (COVID-19): querella | 2020 | `delito-contable-tributario-aplazar-renta-local-covid-19-430` |
| 497 | Blanqueo de capitales imprudente y estafa: querella contra el abogado y su cliente | 2019 | `blanqueo-capitales-imprudente-estafa-querella-contra-497` |
| 521 | Blanqueo de capitales tecnológico y estafa informática: querella | 2018 | `blanqueo-capitales-tecnologico-estafa-informatica-521` |
| 539 | Publicidad engañosa por internet: querella | 2018 | `publicidad-enganosa-internet-querella-539` |
| 542 | Falseamiento de información financiera por internet: querella | 2018 | `falseamiento-informacion-financiera-internet-querella-542` |
| 547 | Alteración de precios en el mercado: querella | 2018 | `alteracion-precios-mercado-querella-547` |
| 612 | Espionaje informático para descubrir secretos de empresa: querella | 2018 | `espionaje-informatico-descubrir-secretos-empresa-612` |

### Escritos de acusación (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 270 | Difusión, revelación o cesión de secretos de empresa: escrito de acusación | 2022 | `difusion-revelacion-cesion-secretos-empresa-escrito-270` |
| 414 | Imposición de acuerdo societario abusivo: escrito de acusación | 2020 | `imposicion-acuerdo-societario-abusivo-escrito-acusacion-414` |
| 428 | Delito contable tributario para aplazar renta del local (COVID-19): escrito de acusación | 2020 | `delito-contable-tributario-aplazar-renta-local-covid-19-428` |
| 468 | Falseamiento de cuentas o documentos sociales (delito societario): acusación | 2019 | `falseamiento-cuentas-documentos-sociales-delito-468` |
| 496 | Blanqueo de capitales imprudente y estafa: acusación contra el abogado y su cliente | 2019 | `blanqueo-capitales-imprudente-estafa-acusacion-contra-496` |
| 523 | Blanqueo de capitales tecnológico y estafa informática: acusación | 2018 | `blanqueo-capitales-tecnologico-estafa-informatica-523` |
| 538 | Publicidad engañosa por internet: acusación | 2018 | `publicidad-enganosa-internet-acusacion-538` |
| 541 | Falseamiento de información financiera: acusación | 2018 | `falseamiento-informacion-financiera-acusacion-541` |
| 550 | Alteración de precios en el mercado: acusación | 2018 | `alteracion-precios-mercado-acusacion-550` |
| 614 | Espionaje informático para descubrir secretos de empresa: acusación | 2018 | `espionaje-informatico-descubrir-secretos-empresa-614` |

### Escritos de defensa (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 155 | Detracción de materias primas o productos de primera necesidad: defensa alegando exención | 2023 | `detraccion-materias-primas-productos-primera-necesidad-155` |
| 156 | Alteración de precios en el mercado: defensa alegando exención | 2023 | `alteracion-precios-mercado-defensa-alegando-exencion-156` |
| 157 | Alteración de precios en concursos y subastas públicas: defensa alegando exención | 2023 | `alteracion-precios-concursos-subastas-publicas-defensa-157` |
| 267 | Difusión, revelación o cesión de secretos de empresa: escrito de defensa | 2022 | `difusion-revelacion-cesion-secretos-empresa-escrito-267` |
| 412 | Imposición de acuerdo societario abusivo: escrito de defensa | 2020 | `imposicion-acuerdo-societario-abusivo-escrito-defensa-412` |
| 431 | Delito contable tributario para aplazar renta del local (COVID-19): escrito de defensa | 2020 | `delito-contable-tributario-aplazar-renta-local-covid-19-431` |
| 470 | Falseamiento de cuentas o documentos sociales (delito societario): defensa | 2019 | `falseamiento-cuentas-documentos-sociales-delito-470` |
| 494 | Blanqueo de capitales imprudente y estafa: defensa del abogado acusado | 2019 | `blanqueo-capitales-imprudente-estafa-defensa-abogado-494` |
| 524 | Blanqueo de capitales tecnológico y estafa informática: defensa | 2018 | `blanqueo-capitales-tecnologico-estafa-informatica-524` |
| 540 | Publicidad engañosa por internet: defensa | 2018 | `publicidad-enganosa-internet-defensa-540` |
| 544 | Falseamiento de información financiera por internet: defensa | 2018 | `falseamiento-informacion-financiera-internet-defensa-544` |
| 548 | Alteración de precios en el mercado: defensa | 2018 | `alteracion-precios-mercado-defensa-548` |
| 616 | Espionaje informático para descubrir secretos de empresa: defensa | 2018 | `espionaje-informatico-descubrir-secretos-empresa-defensa-616` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

