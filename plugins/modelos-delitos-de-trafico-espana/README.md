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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-de-trafico-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-delitos-de-trafico-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-delitos-de-trafico-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-delitos-de-trafico-espana:<skill>`.

### Conformidad (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 240 | Grave riesgo vial por colocar obstáculos en la vía: conformidad de la defensa | 2022 | `grave-riesgo-vial-colocar-obstaculos-via-conformidad-240` |
| 247 | Conducción sin permiso y bajo los efectos de drogas o alcohol: conformidad de la defensa | 2022 | `conduccion-sin-permiso-bajo-efectos-drogas-alcohol-247` |
| 359 | Conducción a velocidad excesiva: conformidad de la defensa | 2021 | `conduccion-velocidad-excesiva-conformidad-defensa-359` |
| 366 | Conducción temeraria con manifiesto desprecio por la vida ajena: conformidad de la defensa | 2021 | `conduccion-temeraria-manifiesto-desprecio-vida-ajena-366` |
| 371 | Conducción temeraria: conformidad de la defensa | 2021 | `conduccion-temeraria-conformidad-defensa-371` |
| 505 | Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa con conformidad | 2019 | `abandono-lugar-accidente-lesiones-imprudentes-trafico-505` |
| 796 | Conducción bajo la influencia del alcohol: defensa con conformidad en juicio rápido | 2016 | `conduccion-bajo-influencia-alcohol-defensa-conformidad-796` |
| 798 | Conducción bajo la influencia del alcohol y lesiones: defensa con conformidad en el abreviado | 2016 | `conduccion-bajo-influencia-alcohol-lesiones-defensa-798` |
| 801 | Negativa a las pruebas de alcoholemia: defensa con conformidad en el abreviado | 2016 | `negativa-pruebas-alcoholemia-defensa-conformidad-801` |
| 802 | Negativa a las pruebas de alcoholemia: defensa con conformidad en juicio rápido | 2016 | `negativa-pruebas-alcoholemia-defensa-conformidad-juicio-802` |

### Recursos e impugnaciones (9)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 118 | Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento | 2023 | `lesiones-accidente-trafico-oposicion-reforma-contra-118` |
| 238 | Grave riesgo vial por colocar obstáculos en la vía: apelación contra la condena | 2022 | `grave-riesgo-vial-colocar-obstaculos-via-apelacion-238` |
| 248 | Conducción sin permiso y bajo los efectos de drogas o alcohol: apelación contra la condena | 2022 | `conduccion-sin-permiso-bajo-efectos-drogas-alcohol-248` |
| 360 | Conducción a velocidad excesiva: apelación contra la condena | 2021 | `conduccion-velocidad-excesiva-apelacion-contra-condena-360` |
| 363 | Conducción temeraria con manifiesto desprecio por la vida ajena: apelación contra la condena | 2021 | `conduccion-temeraria-manifiesto-desprecio-vida-ajena-363` |
| 368 | Conducción temeraria: apelación contra la condena | 2021 | `conduccion-temeraria-apelacion-contra-condena-368` |
| 504 | Apelación contra la condena por abandono del lugar del accidente y lesiones imprudentes de tráfico | 2019 | `apelacion-contra-condena-abandono-lugar-accidente-504` |
| 797 | Apelación contra la condena por conducir bajo la influencia del alcohol | 2016 | `apelacion-contra-condena-conducir-bajo-influencia-797` |
| 800 | Apelación contra la condena por negarse a las pruebas de alcoholemia | 2016 | `apelacion-contra-condena-negarse-pruebas-alcoholemia-800` |

### Querellas y denuncias (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 250 | Conducción sin permiso y bajo los efectos de drogas o alcohol: querella | 2022 | `conduccion-sin-permiso-bajo-efectos-drogas-alcohol-250` |
| 370 | Conducción temeraria: denuncia | 2021 | `conduccion-temeraria-denuncia-370` |
| 372 | Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia | 2021 | `delito-leve-lesiones-imprudencia-menos-grave-vehiculo-372` |
| 506 | Abandono del lugar del accidente y lesiones imprudentes de tráfico: querella | 2019 | `abandono-lugar-accidente-lesiones-imprudentes-trafico-506` |
| 794 | Conducción bajo la influencia del alcohol y lesiones: querella | 2016 | `conduccion-bajo-influencia-alcohol-lesiones-querella-794` |

### Escritos de acusación (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 105 | Accidente con vehículo a motor: acusación del actor civil en el abreviado | 2023 | `accidente-vehiculo-motor-acusacion-actor-civil-abreviado-105` |
| 249 | Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de acusación | 2022 | `conduccion-sin-permiso-bajo-efectos-drogas-alcohol-249` |
| 361 | Conducción a velocidad excesiva: escrito de acusación | 2021 | `conduccion-velocidad-excesiva-escrito-acusacion-361` |
| 365 | Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de acusación | 2021 | `conduccion-temeraria-manifiesto-desprecio-vida-ajena-365` |
| 369 | Conducción temeraria: escrito de acusación | 2021 | `conduccion-temeraria-escrito-acusacion-369` |
| 507 | Abandono del lugar del accidente y lesiones imprudentes de tráfico: acusación | 2019 | `abandono-lugar-accidente-lesiones-imprudentes-trafico-507` |
| 795 | Conducción bajo la influencia del alcohol y lesiones: acusación | 2016 | `conduccion-bajo-influencia-alcohol-lesiones-acusacion-795` |

### Escritos de defensa (6)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 239 | Grave riesgo vial por colocar obstáculos en la vía: escrito de defensa | 2022 | `grave-riesgo-vial-colocar-obstaculos-via-escrito-defensa-239` |
| 246 | Conducción sin permiso y bajo los efectos de drogas o alcohol: escrito de defensa | 2022 | `conduccion-sin-permiso-bajo-efectos-drogas-alcohol-246` |
| 358 | Conducción a velocidad excesiva: escrito de defensa | 2021 | `conduccion-velocidad-excesiva-escrito-defensa-358` |
| 364 | Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de defensa | 2021 | `conduccion-temeraria-manifiesto-desprecio-vida-ajena-364` |
| 367 | Conducción temeraria: escrito de defensa | 2021 | `conduccion-temeraria-escrito-defensa-367` |
| 503 | Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa | 2019 | `abandono-lugar-accidente-lesiones-imprudentes-trafico-503` |

### Solicitudes y escritos de trámite (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 362 | Allegado del perjudicado: reclamación a la aseguradora | 2021 | `allegado-perjudicado-reclamacion-aseguradora-362` |
| 799 | Negativa a las pruebas de alcoholemia: la defensa pide el proceso por aceptación de decreto | 2016 | `negativa-pruebas-alcoholemia-defensa-pide-proceso-799` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

