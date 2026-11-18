# Prueba digital: intervenciones, volcados y nulidad · España

> Plugin de Claude Code `modelos-prueba-digital-penal-espana` · **28 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la prueba digital en el proceso penal: intervenciones telefónicas, volcado de dispositivos, prueba digital y pericial informática, comunicaciones entre abogados, y nulidad de la prueba obtenida ilícitamente.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 28 está al final):

- **Recursos e impugnaciones** (1). Por ejemplo: Apelación contra una condena basada en prueba ilícita.
- **Escritos de acusación** (1). Por ejemplo: Prueba digital y pericial informática: propuesta en el escrito de acusación.
- **Escritos de defensa** (3). Por ejemplo: Nulidad de las intervenciones telefónicas: defensa; Tráfico de drogas con intervenciones telefónicas nulas: defensa; Impugnar una prueba digital en el escrito de defensa.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Computación en la nube (cloud computing): contrato de acceso a datos por cuenta de terceros.
- **Solicitudes y escritos de trámite** (22). Por ejemplo: Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025); Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado; Excluir del proceso las comunicaciones entre abogados defensores aportadas sin autorización.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir la nulidad de las intervenciones telefónicas»
   - «Impugnar una prueba digital en el escrito de defensa»
   - «Aportar como prueba un acta notarial del contenido de una web»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-prueba-digital-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-prueba-digital-penal-espana:prueba-ilicita-acusado-pide-audiencia-preliminar-antes-60`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-prueba-digital-penal-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-prueba-digital-penal-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-prueba-digital-penal-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-prueba-digital-penal-espana:<skill>`.

### Recursos e impugnaciones (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 701 | Apelación contra una condena basada en prueba ilícita | 2017 | `apelacion-contra-condena-basada-prueba-ilicita-701` |

### Escritos de acusación (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 703 | Prueba digital y pericial informática: propuesta en el escrito de acusación | 2017 | `prueba-digital-pericial-informatica-propuesta-escrito-703` |

### Escritos de defensa (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 562 | Nulidad de las intervenciones telefónicas: defensa | 2018 | `nulidad-intervenciones-telefonicas-defensa-562` |
| 563 | Tráfico de drogas con intervenciones telefónicas nulas: defensa | 2018 | `trafico-drogas-intervenciones-telefonicas-nulas-defensa-563` |
| 704 | Impugnar una prueba digital en el escrito de defensa | 2017 | `impugnar-prueba-digital-escrito-defensa-704` |

### Resoluciones, actas y documentos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 735 | Computación en la nube (cloud computing): contrato de acceso a datos por cuenta de terceros | 2016 | `computacion-nube-cloud-computing-contrato-acceso-datos-735` |

### Solicitudes y escritos de trámite (22)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 60 | Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025) | 2025 | `prueba-ilicita-acusado-pide-audiencia-preliminar-antes-60` |
| 61 | Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado | 2024 | `intervenciones-telefonicas-negarse-dar-juez-patron-movil-61` |
| 65 | Excluir del proceso las comunicaciones entre abogados defensores aportadas sin autorización | 2024 | `excluir-proceso-comunicaciones-entre-abogados-defensores-65` |
| 68 | Aportar como prueba comunicaciones o documentos entre defensores con autorización | 2024 | `aportar-como-prueba-comunicaciones-documentos-entre-68` |
| 702 | Querellante: aportar acta notarial del contenido de una web como prueba preconstituida | 2017 | `querellante-aportar-acta-notarial-contenido-web-como-702` |
| 705 | Defensa: pedir la nulidad de la prueba digital aportada | 2017 | `defensa-pedir-nulidad-prueba-digital-aportada-705` |
| 706 | Querellante: pedir que se reproduzca una grabación y aportarla como prueba preconstituida | 2017 | `querellante-pedir-reproduzca-grabacion-aportarla-como-706` |
| 707 | Querellante: proponer o aportar pericial informática en instrucción ante prueba digital impugnada | 2017 | `querellante-proponer-aportar-pericial-informatica-707` |
| 708 | Querellante: aportar prueba digital en la instrucción | 2017 | `querellante-aportar-prueba-digital-instruccion-708` |
| 709 | Querellado: impugnar la prueba digital (WhatsApp u otros) aportada en la instrucción | 2017 | `querellado-impugnar-prueba-digital-whatsapp-u-otros-709` |
| 711 | Deducir testimonio por posible delito hallado en correspondencia o correo electrónico intervenidos | 2017 | `deducir-testimonio-posible-delito-hallado-711` |
| 712 | Pedir el registro remoto de equipos informáticos por delitos cometidos con ellos | 2017 | `pedir-registro-remoto-equipos-informaticos-delitos-712` |
| 713 | Pedir datos de comunicaciones electrónicas para averiguar un delito | 2017 | `pedir-datos-comunicaciones-electronicas-averiguar-delito-713` |
| 714 | Pedir la apertura de la correspondencia ya intervenida | 2017 | `pedir-apertura-correspondencia-ya-intervenida-714` |
| 715 | Pedir la instalación de dispositivos técnicos de localización y seguimiento | 2017 | `pedir-instalacion-dispositivos-tecnicos-localizacion-715` |
| 716 | Pedir la captación de imágenes del investigado o de su entorno en lugar público | 2017 | `pedir-captacion-imagenes-investigado-entorno-lugar-716` |
| 720 | Sexting: pedir el registro de equipos informáticos para determinar la autoría | 2017 | `sexting-pedir-registro-equipos-informaticos-determinar-720` |
| 763 | Pedir al fiscal que solicite al juez intervenir las comunicaciones | 2016 | `pedir-fiscal-solicite-juez-intervenir-comunicaciones-763` |
| 764 | Pedir al fiscal que solicite al juez intervenir la correspondencia del investigado | 2016 | `pedir-fiscal-solicite-juez-intervenir-correspondencia-764` |
| 765 | Grabaciones y transcripciones intervenidas: pedir que se incluya información | 2016 | `grabaciones-transcripciones-intervenidas-pedir-incluya-765` |
| 766 | Grabaciones y transcripciones intervenidas: retirar lo que afecte a la vida privada | 2016 | `grabaciones-transcripciones-intervenidas-retirar-lo-766` |
| 767 | Usar en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones | 2016 | `usar-otro-proceso-penal-lo-obtenido-intervenir-767` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

