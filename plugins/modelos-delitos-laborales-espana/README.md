# Delitos contra los trabajadores y riesgos laborales · España

> Plugin de Claude Code `modelos-delitos-laborales-espana` · **22 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos en el ámbito laboral: imposición de condiciones ilegales, discriminación grave en el empleo, infracción de las normas de prevención de riesgos laborales y acoso laboral.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 22 está al final):

- **Conformidad** (4). Por ejemplo: Condiciones laborales ilegales (contratación irregular o pese a sanción): conformidad de la defensa; Discriminación grave en el empleo: conformidad de la defensa; Infracción de normas de riesgos laborales por imprudencia grave: defensa con conformidad.
- **Recursos e impugnaciones** (4). Por ejemplo: Apelación contra la condena por infracción de normas de riesgos laborales por imprudencia grave; Apelación contra la condena por infracción de normas de riesgos laborales; Condiciones laborales ilegales (contratación irregular o pese a sanción): apelación de la condena.
- **Querellas y denuncias** (5). Por ejemplo: Infracción de normas de riesgos laborales: querella; Acoso laboral: querella; Condiciones laborales ilegales (contratación irregular o pese a sanción): querella.
- **Escritos de acusación** (4). Por ejemplo: Condiciones laborales ilegales (contratación irregular o pese a sanción): escrito de acusación; Discriminación grave en el empleo: escrito de acusación; Infracción de normas de riesgos laborales por imprudencia grave: acusación.
- **Escritos de defensa** (5). Por ejemplo: Condiciones laborales ilegales (contratación irregular o pese a sanción): escrito de defensa; Discriminación grave en el empleo: escrito de defensa; Infracción de normas de riesgos laborales: defensa.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por infracción de las normas de prevención de riesgos laborales»
   - «Querella por discriminación grave en el empleo»
   - «Querella por acoso laboral»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-delitos-laborales-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-delitos-laborales-espana:condiciones-laborales-ilegales-contratacion-irregular-161`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-laborales-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-delitos-laborales-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-delitos-laborales-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-delitos-laborales-espana:<skill>`.

### Conformidad (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 165 | Condiciones laborales ilegales (contratación irregular o pese a sanción): conformidad de la defensa | 2023 | `condiciones-laborales-ilegales-contratacion-irregular-165` |
| 296 | Discriminación grave en el empleo: conformidad de la defensa | 2021 | `discriminacion-grave-empleo-conformidad-defensa-296` |
| 459 | Infracción de normas de riesgos laborales por imprudencia grave: defensa con conformidad | 2020 | `infraccion-normas-riesgos-laborales-imprudencia-grave-459` |
| 464 | Infracción de normas de riesgos laborales: defensa con conformidad | 2019 | `infraccion-normas-riesgos-laborales-defensa-conformidad-464` |

### Recursos e impugnaciones (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 163 | Condiciones laborales ilegales (contratación irregular o pese a sanción): apelación de la condena | 2023 | `condiciones-laborales-ilegales-contratacion-irregular-163` |
| 294 | Discriminación grave en el empleo: apelación contra la condena | 2021 | `discriminacion-grave-empleo-apelacion-contra-condena-294` |
| 462 | Apelación contra la condena por infracción de normas de riesgos laborales por imprudencia grave | 2020 | `apelacion-contra-condena-infraccion-normas-riesgos-462` |
| 465 | Apelación contra la condena por infracción de normas de riesgos laborales | 2019 | `apelacion-contra-condena-infraccion-normas-riesgos-465` |

### Querellas y denuncias (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 161 | Condiciones laborales ilegales (contratación irregular o pese a sanción): querella | 2023 | `condiciones-laborales-ilegales-contratacion-irregular-161` |
| 292 | Discriminación grave en el empleo: querella | 2021 | `discriminacion-grave-empleo-querella-292` |
| 460 | Infracción de normas de riesgos laborales por imprudencia grave: querella | 2020 | `infraccion-normas-riesgos-laborales-imprudencia-grave-460` |
| 467 | Infracción de normas de riesgos laborales: querella | 2019 | `infraccion-normas-riesgos-laborales-querella-467` |
| 830 | Acoso laboral: querella | 2016 | `acoso-laboral-querella-830` |

### Escritos de acusación (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 162 | Condiciones laborales ilegales (contratación irregular o pese a sanción): escrito de acusación | 2023 | `condiciones-laborales-ilegales-contratacion-irregular-162` |
| 293 | Discriminación grave en el empleo: escrito de acusación | 2021 | `discriminacion-grave-empleo-escrito-acusacion-293` |
| 461 | Infracción de normas de riesgos laborales por imprudencia grave: acusación | 2020 | `infraccion-normas-riesgos-laborales-imprudencia-grave-461` |
| 832 | Acoso laboral: acusación | 2016 | `acoso-laboral-acusacion-832` |

### Escritos de defensa (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 164 | Condiciones laborales ilegales (contratación irregular o pese a sanción): escrito de defensa | 2023 | `condiciones-laborales-ilegales-contratacion-irregular-164` |
| 295 | Discriminación grave en el empleo: escrito de defensa | 2021 | `discriminacion-grave-empleo-escrito-defensa-295` |
| 466 | Infracción de normas de riesgos laborales: defensa | 2019 | `infraccion-normas-riesgos-laborales-defensa-466` |
| 686 | Infracción de normas de riesgos laborales por imprudencia grave: defensa | 2017 | `infraccion-normas-riesgos-laborales-imprudencia-grave-686` |
| 833 | Acoso laboral: defensa | 2016 | `acoso-laboral-defensa-833` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
