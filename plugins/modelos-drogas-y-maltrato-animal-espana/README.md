# Tráfico de drogas, petaqueo y maltrato animal · España

> Plugin de Claude Code `modelos-drogas-y-maltrato-animal-espana` · **21 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para delitos contra la salud pública y maltrato animal: tráfico de drogas, petaqueo (LO 1/2026), adulteración de alimentos y maltrato de animales.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 21 está al final):

- **Conformidad** (6). Por ejemplo: Defraudación de fluido eléctrico en concurso real con tráfico de drogas: conformidad de la defensa; Petaqueo (combustible líquido a narcolancha): conformidad de la defensa; Lesiones a animales difundidas en redes sociales: conformidad de la defensa.
- **Recursos e impugnaciones** (5). Por ejemplo: Apelación contra la condena por adulteración de alimentos o bebidas (salud pública); Apelación contra la condena por narcotráfico (salud pública); Defraudación de fluido eléctrico en concurso real con tráfico de drogas: apelación contra la condena.
- **Querellas y denuncias** (3). Por ejemplo: Defraudación de fluido eléctrico para cultivo de drogas: querella; Adulteración de alimentos o bebidas (salud pública): querella; Lesiones a animales difundidas en redes sociales: querella.
- **Escritos de acusación** (3). Por ejemplo: Defraudación de fluido eléctrico en concurso con tráfico de drogas: escrito de acusación; Lesiones a animales difundidas en redes sociales: escrito de acusación; Adulteración de alimentos o bebidas (salud pública): acusación.
- **Escritos de defensa** (4). Por ejemplo: Defraudación de fluido eléctrico en concurso real con tráfico de drogas: escrito de defensa; Petaqueo (combustible líquido a narcolancha): escrito de defensa; Lesiones a animales difundidas en redes sociales: escrito de defensa.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Conformidad de la defensa por narcotráfico en un juicio rápido»
   - «Conformidad de la defensa por petaqueo»
   - «Apelación contra una condena por maltrato animal»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-drogas-y-maltrato-animal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-drogas-y-maltrato-animal-espana:defraudacion-fluido-electrico-cultivo-drogas-querella-6`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-drogas-y-maltrato-animal-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-drogas-y-maltrato-animal-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-drogas-y-maltrato-animal-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-drogas-y-maltrato-animal-espana:<skill>`.

### Conformidad (6)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 7 | Defraudación de fluido eléctrico en concurso real con tráfico de drogas: conformidad de la defensa | 2026 | `defraudacion-fluido-electrico-concurso-real-trafico-7` |
| 13 | Petaqueo (combustible líquido a narcolancha): conformidad de la defensa | 2026 | `petaqueo-combustible-liquido-narcolancha-conformidad-13` |
| 109 | Lesiones a animales difundidas en redes sociales: conformidad de la defensa | 2023 | `lesiones-animales-difundidas-redes-sociales-conformidad-109` |
| 788 | Adulteración de alimentos o bebidas (salud pública): defensa con conformidad en el abreviado | 2016 | `adulteracion-alimentos-bebidas-salud-publica-defensa-788` |
| 791 | Narcotráfico (salud pública): defensa con conformidad en el abreviado | 2016 | `narcotrafico-salud-publica-defensa-conformidad-abreviado-791` |
| 792 | Narcotráfico: defensa con conformidad en juicio rápido | 2016 | `narcotrafico-defensa-conformidad-juicio-rapido-792` |

### Recursos e impugnaciones (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 8 | Defraudación de fluido eléctrico en concurso real con tráfico de drogas: apelación contra la condena | 2026 | `defraudacion-fluido-electrico-concurso-real-trafico-8` |
| 12 | Petaqueo (combustible líquido a narcolancha): apelación contra la condena | 2026 | `petaqueo-combustible-liquido-narcolancha-apelacion-12` |
| 110 | Lesiones a animales difundidas en redes sociales: apelación contra la condena | 2023 | `lesiones-animales-difundidas-redes-sociales-apelacion-110` |
| 790 | Apelación contra la condena por adulteración de alimentos o bebidas (salud pública) | 2016 | `apelacion-contra-condena-adulteracion-alimentos-bebidas-790` |
| 793 | Apelación contra la condena por narcotráfico (salud pública) | 2016 | `apelacion-contra-condena-narcotrafico-salud-publica-793` |

### Querellas y denuncias (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 6 | Defraudación de fluido eléctrico para cultivo de drogas: querella | 2026 | `defraudacion-fluido-electrico-cultivo-drogas-querella-6` |
| 106 | Lesiones a animales difundidas en redes sociales: querella | 2023 | `lesiones-animales-difundidas-redes-sociales-querella-106` |
| 789 | Adulteración de alimentos o bebidas (salud pública): querella | 2016 | `adulteracion-alimentos-bebidas-salud-publica-querella-789` |

### Escritos de acusación (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 10 | Defraudación de fluido eléctrico en concurso con tráfico de drogas: escrito de acusación | 2026 | `defraudacion-fluido-electrico-concurso-trafico-drogas-10` |
| 108 | Lesiones a animales difundidas en redes sociales: escrito de acusación | 2023 | `lesiones-animales-difundidas-redes-sociales-escrito-108` |
| 786 | Adulteración de alimentos o bebidas (salud pública): acusación | 2016 | `adulteracion-alimentos-bebidas-salud-publica-acusacion-786` |

### Escritos de defensa (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 9 | Defraudación de fluido eléctrico en concurso real con tráfico de drogas: escrito de defensa | 2026 | `defraudacion-fluido-electrico-concurso-real-trafico-9` |
| 11 | Petaqueo (combustible líquido a narcolancha): escrito de defensa | 2026 | `petaqueo-combustible-liquido-narcolancha-escrito-defensa-11` |
| 107 | Lesiones a animales difundidas en redes sociales: escrito de defensa | 2023 | `lesiones-animales-difundidas-redes-sociales-escrito-107` |
| 787 | Adulteración de alimentos o bebidas (salud pública): defensa | 2016 | `adulteracion-alimentos-bebidas-salud-publica-defensa-787` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

