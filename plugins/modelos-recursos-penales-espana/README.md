# Reforma, apelación y casación penal · España

> Plugin de Claude Code `modelos-recursos-penales-espana` · **24 formularios** · área: Penal (incluye 2 formularios de Procesal, marcados «(Procesal)») · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para recurrir en el proceso penal: reforma, apelación, queja y casación, oposición a los recursos de las otras partes, demanda de amparo y revisión de una condena firme tras una sentencia del Tribunal Europeo de Derechos Humanos.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 24 está al final):

- **Conformidad** (1). Por ejemplo: Procedimiento común: apelación de la defensa contra la sentencia de conformidad.
- **Recursos e impugnaciones** (21). Por ejemplo: Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado; Revisión penal tras una sentencia del TEDH: interposición del recurso; Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Casación desierta: decreto del Letrado de la Administración de Justicia.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Recurso de reforma y subsidiario de apelación contra el auto de prisión provisional»
   - «Recurso contra el sobreseimiento provisional de las diligencias previas»
   - «Apelación de la defensa contra una sentencia de conformidad»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-recursos-penales-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-recursos-penales-espana:oponerse-recurso-reforma-subsidiario-apelacion-contra-24`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-recursos-penales-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-recursos-penales-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-recursos-penales-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-recursos-penales-espana:<skill>`.

### Conformidad (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 54 | Procedimiento común: apelación de la defensa contra la sentencia de conformidad | 2025 | `procedimiento-comun-apelacion-defensa-contra-sentencia-54` |

### Recursos e impugnaciones (21)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 24 | Oponerse al recurso de reforma y subsidiario de apelación contra un auto del abreviado | 2026 | `oponerse-recurso-reforma-subsidiario-apelacion-contra-24` |
| 53 | Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar | 2025 | `abreviado-apelacion-contra-auto-le-pone-fin-tras-53` |
| 70 | Recurso de amparo (Acuerdo TC de 15 de marzo de 2023, válido hasta el 14 de septiembre de 2026) | 2024 | `recurso-amparo-acuerdo-tc-15-marzo-2023-valido-hasta-14-70` |
| 101 | Abreviado: oposición a la apelación contra la denegación de apertura del juicio oral | 2023 | `abreviado-oposicion-apelacion-contra-denegacion-apertura-101` |
| 103 | Abreviado: apelación contra el auto que deniega la apertura del juicio oral | 2023 | `abreviado-apelacion-contra-auto-deniega-apertura-juicio-103` |
| 121 | Querella inadmitida: reforma y subsidiario de apelación | 2023 | `querella-inadmitida-reforma-subsidiario-apelacion-121` |
| 153 | Recurso de anulación: impugnación de la parte acusadora | 2023 | `recurso-anulacion-impugnacion-parte-acusadora-153` |
| 154 | Abreviado: oposición a la adhesión a la apelación contra la sentencia | 2023 | `abreviado-oposicion-adhesion-apelacion-contra-sentencia-154` |
| 159 | Paso del abreviado a jurado denegado tácitamente: queja de la acusación particular | 2023 | `paso-abreviado-jurado-denegado-tacitamente-queja-159` |
| 160 | Paso del ordinario al abreviado denegado: queja del investigado | 2023 | `paso-ordinario-abreviado-denegado-queja-investigado-160` |
| 167 | Prisión provisional en el abreviado: reforma y subsidiario de apelación | 2022 | `prision-provisional-abreviado-reforma-subsidiario-167` |
| 169 | Sobreseimiento provisional: oposición a la apelación | 2022 | `sobreseimiento-provisional-oposicion-apelacion-169` |
| 251 | Sobreseimiento libre de la AP o la AN: recurso de casación | 2022 | `sobreseimiento-libre-ap-an-recurso-casacion-251` |
| 479 | Sobreseimiento provisional tras las diligencias previas: reforma y subsidiaria apelación | 2019 | `sobreseimiento-provisional-tras-diligencias-previas-479` |
| 486 | Prórroga de la instrucción: reforma y subsidiaria apelación | 2019 | `prorroga-instruccion-reforma-subsidiaria-apelacion-486` |
| 556 | Prueba de la defensa denegada en el procedimiento abreviado: queja (hasta el 2 de abril de 2025) | 2018 | `prueba-defensa-denegada-procedimiento-abreviado-queja-556` |
| 617 | Auto de libertad provisional del investigado o encausado: reforma y subsidiaria apelación | 2018 | `auto-libertad-provisional-investigado-encausado-reforma-617` |
| 618 | Auto de libertad provisional del investigado o encausado: apelación | 2018 | `auto-libertad-provisional-investigado-encausado-618` |
| 742 | Denegación de traductor o intérprete: reforma de la defensa del investigado | 2016 | `denegacion-traductor-interprete-reforma-defensa-742` |
| 770 | Auto de la Audiencia Provincial: apelación penal | 2016 | `auto-audiencia-provincial-apelacion-penal-770` |
| 18 (Procesal) | Revisión penal tras una sentencia del TEDH: interposición del recurso | 2025 | `revision-penal-tras-sentencia-tedh-interposicion-recurso-p18` |

### Resoluciones, actas y documentos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 158 | Casación desierta: decreto del Letrado de la Administración de Justicia | 2023 | `casacion-desierta-decreto-letrado-administracion-158` |

### Solicitudes y escritos de trámite (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 19 (Procesal) | Revisión penal tras una sentencia del TEDH: pedir autorización para recurrir | 2025 | `revision-penal-tras-sentencia-tedh-pedir-autorizacion-p19` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

