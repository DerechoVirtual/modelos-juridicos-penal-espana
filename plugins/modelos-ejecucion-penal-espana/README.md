# Después de la condena: suspensión, refundición y prescripción · España

> Plugin de Claude Code `modelos-ejecucion-penal-espana` · **16 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la fase posterior a la condena: liquidación de condena, suspensión de la pena, prescripción, refundición, revisión por una ley penal más favorable, libertad vigilada, impago de la multa y decomiso.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 16 está al final):

- **Recursos e impugnaciones** (8). Por ejemplo: Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ; Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025); Refundición de condenas: interponer recurso de casación.
- **Escritos de defensa** (1). Por ejemplo: Ejecutoria penal: alegaciones de la defensa del condenado.
- **Solicitudes y escritos de trámite** (6). Por ejemplo: Pedir la revisión de la condena por retroactividad de la norma penal más favorable; Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025); Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025).
- **Otros** (1). Por ejemplo: Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Impugnar la liquidación de condena»
   - «Pedir la revisión de la condena por una ley penal más favorable»
   - «Pedir la modificación de la libertad vigilada»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-ejecucion-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-ejecucion-penal-espana:ejecutoria-penal-impugnar-liquidacion-condena-hecha-laj-51`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 1.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-ejecucion-penal-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-ejecucion-penal-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-ejecucion-penal-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-ejecucion-penal-espana:<skill>`.

### Recursos e impugnaciones (8)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 51 | Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ | 2025 | `ejecutoria-penal-impugnar-liquidacion-condena-hecha-laj-51` |
| 55 | Ejecutoria penal: súplica contra el auto que resuelve alegaciones | 2025 | `ejecutoria-penal-suplica-contra-auto-resuelve-55` |
| 56 | Ejecutoria penal: reforma y subsidiario de apelación contra el auto que resuelve alegaciones | 2025 | `ejecutoria-penal-reforma-subsidiario-apelacion-contra-56` |
| 100 | Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025) | 2023 | `suspension-pena-denegada-apelacion-pidiendo-excepcional-100` |
| 557 | Refundición de condenas: interponer recurso de casación | 2018 | `refundicion-condenas-interponer-recurso-casacion-557` |
| 561 | Refundición de condenas: preparar la casación por infracción de ley | 2018 | `refundicion-condenas-preparar-casacion-infraccion-ley-561` |
| 755 | Decomiso autónomo: apelación del tercero contra la sentencia condenatoria | 2016 | `decomiso-autonomo-apelacion-tercero-contra-sentencia-755` |
| 760 | Decomiso en el proceso penal: apelación del tercero afectado contra la condena | 2016 | `decomiso-proceso-penal-apelacion-tercero-afectado-contra-760` |

### Escritos de defensa (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 58 | Ejecutoria penal: alegaciones de la defensa del condenado | 2025 | `ejecutoria-penal-alegaciones-defensa-condenado-58` |

### Solicitudes y escritos de trámite (6)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 142 | Pedir la revisión de la condena por retroactividad de la norma penal más favorable | 2023 | `pedir-revision-condena-retroactividad-norma-penal-mas-142` |
| 168 | Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025) | 2022 | `impago-multa-suspender-responsabilidad-personal-168` |
| 384 | Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025) | 2021 | `prescripcion-pena-peticion-penado-hasta-2-abril-2025-384` |
| 756 | Decomiso autónomo: designar bienes para decomisar | 2016 | `decomiso-autonomo-designar-bienes-decomisar-756` |
| 759 | Pedir la modificación de la libertad vigilada | 2016 | `pedir-modificacion-libertad-vigilada-759` |
| 761 | Decomiso de bienes: pedir que se llame al proceso penal al tercero afectado | 2016 | `decomiso-bienes-pedir-llame-proceso-penal-tercero-761` |

### Otros (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 762 | Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse | 2016 | `decomiso-contestacion-demanda-tercero-rebelde-no-pudo-762` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

