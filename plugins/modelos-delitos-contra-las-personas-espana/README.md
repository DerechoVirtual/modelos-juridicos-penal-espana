# Lesiones, amenazas, coacciones y homicidio · España

> Plugin de Claude Code `modelos-delitos-contra-las-personas-espana` · **63 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para acusar o defender en delitos contra la vida, la integridad y la libertad: homicidio, lesiones, omisión del deber de socorro, amenazas, coacciones, acoso (stalking), trata de seres humanos y delitos contra menores cometidos por internet.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 63 está al final):

- **Conformidad** (8). Por ejemplo: Ocultación del paradero de un cadáver: conformidad de la defensa; Promover por internet la autolesión de menores o discapacitados: conformidad de la defensa; Promover por internet trastornos alimenticios en menores o discapacitados: conformidad de la defensa.
- **Recursos e impugnaciones** (11). Por ejemplo: Omisión del deber de socorro: apelación contra la condena; Promover por internet el suicidio de menores o discapacitados: apelación contra la condena; Lesiones por esterilización de discapacitada: apelación contra la condena.
- **Querellas y denuncias** (12). Por ejemplo: Omisión de socorro por no prestar asistencia sanitaria: querella; Amenazas informáticas: querella; Acoso en una comunidad de propietarios (blocking): querella.
- **Escritos de acusación** (17). Por ejemplo: Lesiones dolosas o imprudentes: acusación con conclusiones alternativas; Trata de seres humanos: calificación provisional de la acusación; Lesiones con agravante de aporofobia o exclusión social: escrito de acusación.
- **Escritos de defensa** (13). Por ejemplo: Lesiones: escrito de defensa; Amenazas en redes sociales: calificación provisional de la defensa; Coacciones por mensajes de WhatsApp: defensa.
- **Medidas cautelares y protección** (1). Por ejemplo: Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Trata en tránsito: auto de inhibición a favor del Tribunal Central de Instancia.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Escrito de acusación por lesiones»
   - «Escrito de defensa en un delito de acoso (stalking)»
   - «Pedir una orden de alejamiento y prohibición de comunicación por acoso»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-delitos-contra-las-personas-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-delitos-contra-las-personas-espana:trata-transito-auto-inhibicion-favor-tribunal-central-35`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-contra-las-personas-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-delitos-contra-las-personas-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-delitos-contra-las-personas-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-delitos-contra-las-personas-espana:<skill>`.

### Conformidad (8)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 151 | Ocultación del paradero de un cadáver: conformidad de la defensa | 2023 | `ocultacion-paradero-cadaver-conformidad-defensa-151` |
| 303 | Promover por internet la autolesión de menores o discapacitados: conformidad de la defensa | 2021 | `promover-internet-autolesion-menores-discapacitados-303` |
| 309 | Promover por internet trastornos alimenticios en menores o discapacitados: conformidad de la defensa | 2021 | `promover-internet-trastornos-alimenticios-menores-309` |
| 315 | Promover por internet el suicidio de menores o discapacitados: conformidad de la defensa | 2021 | `promover-internet-suicidio-menores-discapacitados-315` |
| 436 | Lesiones: conformidad de la defensa | 2020 | `lesiones-conformidad-defensa-436` |
| 535 | Amenazas informáticas: defensa con conformidad | 2018 | `amenazas-informaticas-defensa-conformidad-535` |
| 636 | Acoso en una comunidad de propietarios (blocking): defensa con conformidad | 2018 | `acoso-comunidad-propietarios-blocking-defensa-636` |
| 684 | Amenazas en redes sociales: defensa con conformidad | 2017 | `amenazas-redes-sociales-defensa-conformidad-684` |

### Recursos e impugnaciones (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 148 | Ocultación del paradero de un cadáver: apelación contra la condena | 2023 | `ocultacion-paradero-cadaver-apelacion-contra-condena-148` |
| 265 | Omisión del deber de socorro: apelación contra la condena | 2022 | `omision-deber-socorro-apelacion-contra-condena-265` |
| 306 | Promover por internet la autolesión de menores o discapacitados: apelación contra la condena | 2021 | `promover-internet-autolesion-menores-discapacitados-306` |
| 311 | Promover por internet trastornos alimenticios en menores o discapacitados: apelación de la condena | 2021 | `promover-internet-trastornos-alimenticios-menores-311` |
| 313 | Promover por internet el suicidio de menores o discapacitados: apelación contra la condena | 2021 | `promover-internet-suicidio-menores-discapacitados-313` |
| 387 | Lesiones por esterilización de discapacitada: apelación contra la condena | 2020 | `lesiones-esterilizacion-discapacitada-apelacion-contra-387` |
| 435 | Lesiones: apelación contra la condena | 2020 | `lesiones-apelacion-contra-condena-435` |
| 533 | Apelación contra la condena por amenazas informáticas | 2018 | `apelacion-contra-condena-amenazas-informaticas-533` |
| 634 | Apelación contra la condena por acoso en una comunidad de propietarios (blocking) | 2018 | `apelacion-contra-condena-acoso-comunidad-propietarios-634` |
| 681 | Apelación contra la condena por amenazas en redes sociales | 2017 | `apelacion-contra-condena-amenazas-redes-sociales-681` |
| 700 | Apelación contra la condena por coacciones por mensajes de WhatsApp | 2017 | `apelacion-contra-condena-coacciones-mensajes-whatsapp-700` |

### Querellas y denuncias (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 150 | Ocultación del paradero de un cadáver: querella | 2023 | `ocultacion-paradero-cadaver-querella-150` |
| 266 | Omisión de socorro por no prestar asistencia sanitaria: querella | 2022 | `omision-socorro-no-prestar-asistencia-sanitaria-querella-266` |
| 302 | Promover por internet la autolesión de menores o discapacitados: denuncia | 2021 | `promover-internet-autolesion-menores-discapacitados-302` |
| 310 | Promover por internet trastornos alimenticios en menores o discapacitados: querella | 2021 | `promover-internet-trastornos-alimenticios-menores-310` |
| 316 | Promover por internet el suicidio de menores o discapacitados: denuncia | 2021 | `promover-internet-suicidio-menores-discapacitados-316` |
| 388 | Lesiones por esterilización de discapacitada: querella | 2020 | `lesiones-esterilizacion-discapacitada-querella-388` |
| 531 | Amenazas informáticas: querella | 2018 | `amenazas-informaticas-querella-531` |
| 638 | Acoso en una comunidad de propietarios (blocking): querella | 2018 | `acoso-comunidad-propietarios-blocking-querella-638` |
| 685 | Amenazas en redes sociales: querella | 2017 | `amenazas-redes-sociales-querella-685` |
| 710 | Homicidio o lesiones por imprudencia médica: querella | 2017 | `homicidio-lesiones-imprudencia-medica-querella-710` |
| 719 | Coacciones por mensajes de WhatsApp: querella | 2017 | `coacciones-mensajes-whatsapp-querella-719` |
| 817 | Amenazas: querella | 2016 | `amenazas-querella-817` |

### Escritos de acusación (17)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 104 | Lesiones dolosas o imprudentes: acusación con conclusiones alternativas | 2023 | `lesiones-dolosas-imprudentes-acusacion-conclusiones-104` |
| 149 | Ocultación del paradero de un cadáver: escrito de acusación | 2023 | `ocultacion-paradero-cadaver-escrito-acusacion-149` |
| 263 | Omisión del deber de socorro: calificación provisional de la acusación | 2022 | `omision-deber-socorro-calificacion-provisional-acusacion-263` |
| 272 | Trata de seres humanos: calificación provisional de la acusación | 2022 | `trata-seres-humanos-calificacion-provisional-acusacion-272` |
| 277 | Lesiones con agravante de aporofobia o exclusión social: escrito de acusación | 2022 | `lesiones-agravante-aporofobia-exclusion-social-escrito-277` |
| 297 | Lesiones a menor de edad: escrito de acusación | 2021 | `lesiones-menor-edad-escrito-acusacion-297` |
| 304 | Promover por internet la autolesión de menores o discapacitados: escrito de acusación | 2021 | `promover-internet-autolesion-menores-discapacitados-304` |
| 308 | Promover por internet trastornos alimenticios en menores o discapacitados: escrito de acusación | 2021 | `promover-internet-trastornos-alimenticios-menores-308` |
| 314 | Promover por internet el suicidio de menores o discapacitados: escrito de acusación | 2021 | `promover-internet-suicidio-menores-discapacitados-314` |
| 386 | Lesiones por esterilización de discapacitada: calificación provisional de la acusación particular | 2020 | `lesiones-esterilizacion-discapacitada-calificacion-386` |
| 437 | Lesiones: escrito de acusación | 2020 | `lesiones-escrito-acusacion-437` |
| 532 | Amenazas informáticas: calificación provisional de la acusación | 2018 | `amenazas-informaticas-calificacion-provisional-acusacion-532` |
| 637 | Acoso en una comunidad de propietarios (blocking): acusación | 2018 | `acoso-comunidad-propietarios-blocking-acusacion-637` |
| 682 | Amenazas en redes sociales: calificación provisional de la acusación | 2017 | `amenazas-redes-sociales-calificacion-provisional-682` |
| 698 | Coacciones por mensajes de WhatsApp: acusación | 2017 | `coacciones-mensajes-whatsapp-acusacion-698` |
| 814 | Amenazas: calificación provisional de la acusación | 2016 | `amenazas-calificacion-provisional-acusacion-814` |
| 816 | Acoso telefónico o stalking: acusación | 2016 | `acoso-telefonico-stalking-acusacion-816` |

### Escritos de defensa (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 152 | Ocultación del paradero de un cadáver: escrito de defensa | 2023 | `ocultacion-paradero-cadaver-escrito-defensa-152` |
| 264 | Omisión del deber de socorro: calificación provisional de la defensa | 2022 | `omision-deber-socorro-calificacion-provisional-defensa-264` |
| 307 | Promover por internet la autolesión de menores o discapacitados: escrito de defensa | 2021 | `promover-internet-autolesion-menores-discapacitados-307` |
| 312 | Promover por internet trastornos alimenticios en menores o discapacitados: escrito de defensa | 2021 | `promover-internet-trastornos-alimenticios-menores-312` |
| 317 | Promover por internet el suicidio de menores o discapacitados: escrito de defensa | 2021 | `promover-internet-suicidio-menores-discapacitados-317` |
| 385 | Lesiones por esterilización de discapacitada: calificación provisional de la defensa | 2020 | `lesiones-esterilizacion-discapacitada-calificacion-385` |
| 438 | Lesiones: escrito de defensa | 2020 | `lesiones-escrito-defensa-438` |
| 534 | Amenazas informáticas: calificación provisional de la defensa | 2018 | `amenazas-informaticas-calificacion-provisional-defensa-534` |
| 635 | Acoso en una comunidad de propietarios (blocking): defensa | 2018 | `acoso-comunidad-propietarios-blocking-defensa-635` |
| 683 | Amenazas en redes sociales: calificación provisional de la defensa | 2017 | `amenazas-redes-sociales-calificacion-provisional-defensa-683` |
| 699 | Coacciones por mensajes de WhatsApp: defensa | 2017 | `coacciones-mensajes-whatsapp-defensa-699` |
| 815 | Acoso o stalking: defensa | 2016 | `acoso-stalking-defensa-815` |
| 818 | Amenazas: calificación provisional de la defensa | 2016 | `amenazas-calificacion-provisional-defensa-818` |

### Medidas cautelares y protección (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 737 | Acoso o stalking: pedir medida cautelar de no aproximación y no comunicación | 2016 | `acoso-stalking-pedir-medida-cautelar-no-aproximacion-no-737` |

### Resoluciones, actas y documentos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 35 | Trata en tránsito: auto de inhibición a favor del Tribunal Central de Instancia | 2025 | `trata-transito-auto-inhibicion-favor-tribunal-central-35` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

