# Prevaricación, malversación y denuncia falsa · España

> Plugin de Claude Code `modelos-prevaricacion-y-malversacion-espana` · **58 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos de cargos públicos y contra la Administración de Justicia: malversación, prevaricación (también urbanística y judicial), fraude, enriquecimiento ilícito, falso testimonio, denuncia falsa y querellas contra diputados y senadores.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 58 está al final):

- **Conformidad** (6). Por ejemplo: Enriquecimiento ilícito: conformidad de la defensa; Intrusismo profesional: conformidad de la defensa; Funcionario que deniega una prestación por discriminación: conformidad de la defensa.
- **Recursos e impugnaciones** (9). Por ejemplo: Falso testimonio: apelación contra la condena; Infidelidad en la custodia de documentos: apelación contra la condena; Prevaricación urbanística: apelación de la autoridad o funcionario condenado (todas las CCAA).
- **Querellas y denuncias** (16). Por ejemplo: Diputado o senador: querella ante el juez de instrucción; Prevaricación urbanística de autoridad o funcionario: querella (todas las CCAA); Delito urbanístico: querella contra el constructor (todas las CCAA).
- **Escritos de acusación** (13). Por ejemplo: Fraude a la Administración: calificación provisional de la acusación; Malversación: calificación provisional de la acusación; Prevaricación judicial: acusación.
- **Escritos de defensa** (13). Por ejemplo: Omisión del deber de impedir delitos: defensa; Denuncia falsa: defensa; Encubrimiento: defensa.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por prevaricación urbanística»
   - «Querella por falso testimonio»
   - «Querella por denuncia falsa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-prevaricacion-y-malversacion-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-prevaricacion-y-malversacion-espana:diputado-senador-querella-ante-juez-instruccion-96`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-prevaricacion-y-malversacion-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-prevaricacion-y-malversacion-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-prevaricacion-y-malversacion-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-prevaricacion-y-malversacion-espana:<skill>`.

### Conformidad (6)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 124 | Enriquecimiento ilícito: conformidad de la defensa | 2023 | `enriquecimiento-ilicito-conformidad-defensa-124` |
| 243 | Intrusismo profesional: conformidad de la defensa | 2022 | `intrusismo-profesional-conformidad-defensa-243` |
| 281 | Funcionario que deniega una prestación por discriminación: conformidad de la defensa | 2021 | `funcionario-deniega-prestacion-discriminacion-281` |
| 382 | Falso testimonio: conformidad de la defensa | 2021 | `falso-testimonio-conformidad-defensa-382` |
| 443 | Infidelidad en la custodia de documentos: defensa con conformidad | 2020 | `infidelidad-custodia-documentos-defensa-conformidad-443` |
| 472 | Fraude a la Administración: defensa con conformidad | 2019 | `fraude-administracion-defensa-conformidad-472` |

### Recursos e impugnaciones (9)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 126 | Enriquecimiento ilícito: apelación contra la condena | 2023 | `enriquecimiento-ilicito-apelacion-contra-condena-126` |
| 242 | Intrusismo profesional: apelación contra la condena | 2022 | `intrusismo-profesional-apelacion-contra-condena-242` |
| 278 | Funcionario que deniega una prestación por discriminación: apelación contra la condena | 2021 | `funcionario-deniega-prestacion-discriminacion-apelacion-278` |
| 380 | Falso testimonio: apelación contra la condena | 2021 | `falso-testimonio-apelacion-contra-condena-380` |
| 439 | Infidelidad en la custodia de documentos: apelación contra la condena | 2020 | `infidelidad-custodia-documentos-apelacion-contra-condena-439` |
| 453 | Prevaricación urbanística: apelación de la autoridad o funcionario condenado (todas las CCAA) | 2020 | `prevaricacion-urbanistica-apelacion-autoridad-453` |
| 456 | Delito urbanístico: apelación del constructor condenado (todas las CCAA) | 2020 | `delito-urbanistico-apelacion-constructor-condenado-todas-456` |
| 475 | Apelación contra la condena por fraude a la Administración | 2019 | `apelacion-contra-condena-fraude-administracion-475` |
| 501 | Apelación contra la condena por malversación | 2019 | `apelacion-contra-condena-malversacion-501` |

### Querellas y denuncias (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 96 | Diputado o senador: querella ante el juez de instrucción | 2023 | `diputado-senador-querella-ante-juez-instruccion-96` |
| 97 | Diputado o senador: querella ante el Tribunal Supremo | 2023 | `diputado-senador-querella-ante-tribunal-supremo-97` |
| 125 | Enriquecimiento ilícito: querella | 2023 | `enriquecimiento-ilicito-querella-125` |
| 245 | Intrusismo profesional: denuncia | 2022 | `intrusismo-profesional-denuncia-245` |
| 280 | Funcionario que deniega una prestación por discriminación: querella | 2021 | `funcionario-deniega-prestacion-discriminacion-querella-280` |
| 403 | Falso testimonio: querella | 2020 | `falso-testimonio-querella-403` |
| 442 | Infidelidad en la custodia de documentos: querella | 2020 | `infidelidad-custodia-documentos-querella-442` |
| 455 | Prevaricación urbanística de autoridad o funcionario: querella (todas las CCAA) | 2020 | `prevaricacion-urbanistica-autoridad-funcionario-querella-455` |
| 463 | Delito urbanístico: querella contra el constructor (todas las CCAA) | 2020 | `delito-urbanistico-querella-contra-constructor-todas-463` |
| 473 | Fraude a la Administración Pública: querella | 2019 | `fraude-administracion-publica-querella-473` |
| 502 | Malversación: querella | 2019 | `malversacion-querella-502` |
| 838 | Prevaricación judicial: querella | 2016 | `prevaricacion-judicial-querella-838` |
| 840 | Omisión del deber de impedir delitos: querella | 2016 | `omision-deber-impedir-delitos-querella-840` |
| 842 | Encubrimiento: querella | 2016 | `encubrimiento-querella-842` |
| 845 | Denuncia falsa: querella | 2016 | `denuncia-falsa-querella-845` |
| 878 | Desobediencia a la autoridad: querella | 2016 | `desobediencia-autoridad-querella-878` |

### Escritos de acusación (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 127 | Enriquecimiento ilícito: escrito de acusación | 2023 | `enriquecimiento-ilicito-escrito-acusacion-127` |
| 244 | Intrusismo profesional: escrito de acusación | 2022 | `intrusismo-profesional-escrito-acusacion-244` |
| 279 | Funcionario que deniega una prestación por discriminación: escrito de acusación | 2021 | `funcionario-deniega-prestacion-discriminacion-escrito-279` |
| 379 | Falso testimonio: escrito de acusación | 2021 | `falso-testimonio-escrito-acusacion-379` |
| 440 | Infidelidad en la custodia de documentos: calificación provisional de la acusación | 2020 | `infidelidad-custodia-documentos-calificacion-provisional-440` |
| 454 | Prevaricación urbanística de autoridad o funcionario: acusación (todas las CCAA) | 2020 | `prevaricacion-urbanistica-autoridad-funcionario-454` |
| 458 | Delito urbanístico: acusación contra el constructor (todas las CCAA) | 2020 | `delito-urbanistico-acusacion-contra-constructor-todas-458` |
| 474 | Fraude a la Administración: calificación provisional de la acusación | 2019 | `fraude-administracion-calificacion-provisional-acusacion-474` |
| 500 | Malversación: calificación provisional de la acusación | 2019 | `malversacion-calificacion-provisional-acusacion-500` |
| 839 | Prevaricación judicial: acusación | 2016 | `prevaricacion-judicial-acusacion-839` |
| 841 | Omisión del deber de impedir delitos: acusación | 2016 | `omision-deber-impedir-delitos-acusacion-841` |
| 843 | Denuncia falsa: acusación | 2016 | `denuncia-falsa-acusacion-843` |
| 844 | Encubrimiento: acusación | 2016 | `encubrimiento-acusacion-844` |

### Escritos de defensa (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 123 | Enriquecimiento ilícito: escrito de defensa | 2023 | `enriquecimiento-ilicito-escrito-defensa-123` |
| 241 | Intrusismo profesional: escrito de defensa | 2022 | `intrusismo-profesional-escrito-defensa-241` |
| 282 | Funcionario que deniega una prestación por discriminación: escrito de defensa | 2021 | `funcionario-deniega-prestacion-discriminacion-escrito-282` |
| 381 | Falso testimonio: escrito de defensa | 2021 | `falso-testimonio-escrito-defensa-381` |
| 441 | Infidelidad en la custodia de documentos: calificación provisional de la defensa | 2020 | `infidelidad-custodia-documentos-calificacion-provisional-441` |
| 452 | Prevaricación urbanística: defensa de la autoridad o funcionario (todas las CCAA) | 2020 | `prevaricacion-urbanistica-defensa-autoridad-funcionario-452` |
| 457 | Delito urbanístico: defensa del constructor (todas las CCAA) | 2020 | `delito-urbanistico-defensa-constructor-todas-ccaa-457` |
| 476 | Fraude a la Administración: calificación provisional de la defensa | 2019 | `fraude-administracion-calificacion-provisional-defensa-476` |
| 499 | Malversación: calificación provisional de la defensa | 2019 | `malversacion-calificacion-provisional-defensa-499` |
| 836 | Omisión del deber de impedir delitos: defensa | 2016 | `omision-deber-impedir-delitos-defensa-836` |
| 837 | Prevaricación judicial: defensa | 2016 | `prevaricacion-judicial-defensa-837` |
| 846 | Denuncia falsa: defensa | 2016 | `denuncia-falsa-defensa-846` |
| 847 | Encubrimiento: defensa | 2016 | `encubrimiento-defensa-847` |

### Solicitudes y escritos de trámite (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 99 | Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo | 2023 | `diputado-senador-acusacion-pide-remitir-causa-tribunal-99` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
